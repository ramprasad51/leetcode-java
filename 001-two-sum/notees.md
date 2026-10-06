# 1. Two Sum (Easy)

**Problem:** Given an integer array `nums` and an integer `target`, return the indices of the two numbers that add up to `target`. Exactly one solution exists, and the same element cannot be used twice.

| Input | Output |
|---|---|
| nums = [2,7,11,15], target = 9 | [0,1] |
| nums = [3,2,4], target = 6 | [1,2] |

**Approach:** HashMap with key = number, value = its index. For each `x`, compute `need = target - x`. If `need` is already in the map, return its stored index and the current index. Otherwise store `x` and its index.

**Code explanation:**
- `need = target - nums[i]` is the partner value.
- `containsKey(need)` is an average O(1) check.
- `put(nums[i], i)` runs after the check, so an element never pairs with itself.
- `return new int[]{}` is only there to satisfy the compiler.

**Complexity:** O(n) time, O(n) space (brute force: O(n^2) time, O(1) space)

**Mistake I made:** stored `need` in the map instead of `nums[i]`.

**Key idea:** Need, Check, Store