# Concatenation of Array

[**Challenge Link**](https://leetcode.com/problems/concatenation-of-array/)

**Prompt:** Given an integer array nums of length n, you want to create an array ans of length 2n where ans[i] == nums[i] and ans[i + n] == nums[i] for 0 <= i < n (0-indexed).

Specifically, ans is the concatenation of two nums arrays.

Return the array ans.

**My Solution:**

```
/**
 * @param {number[]} nums
 * @return {number[]}
 */
var getConcatenation = function(nums) {
    return [...nums, ...nums]
};
```

**Reflection:** My solution seems good for most cases. I probably could have used a for loop to be more memory efficient for cases where there are literally millions of elements inside the array, but otherwise I like my solution better because it's clean and concise.
