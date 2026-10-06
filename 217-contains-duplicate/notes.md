# 217. Contains Duplicate (Easy)

**Problem:** Given an integer array `nums`, return `true` if any value appears at least twice, and `false` if every element is distinct.

| Input | Output |
|---|---|
| nums = [1,2,3,1] | true |
| nums = [1,2,3,4] | false |

**Approach:** HashSet remembers the numbers seen so far. For each number, check whether it is already in the set, then add it.

**Code explanation:**
- `set.contains(nums[i])` true means a duplicate, so return `true` immediately.
- Otherwise `set.add(nums[i])` records it.
- `return false` runs only if the loop finishes with no repeat.

**Complexity:** O(n) time, O(n) space (brute force: O(n^2) time)

**Key points:**
- HashSet (not HashMap) because only "seen or not" matters.
- Same Check-then-Store pattern as Two Sum.
- Set is the interface, HashSet is the class.