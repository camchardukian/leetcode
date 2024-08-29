# Contains Duplicate

[**Problem Link**](https://leetcode.com/problems/contains-duplicate)

**Prompt:** Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

**Initial Thoughts:**

```
// It seems like we could solve this problem just by creating a Set from nums and returning Set.size() !== nums.length.
```

**My Solution:**

```
var containsDuplicate = function (nums) {
  return new Set(nums).size !== nums.length;
};
```

**Reflection:** While my solution was solid, another interesting solution would have been to sort the array, and then loop through checking whether any adjacent values were the same.

This would be more efficient than looping through an unsorted array because with an unsorted array we'd have to loop through all of the values to perform each comparison rather than only having to compare adjacent values.
