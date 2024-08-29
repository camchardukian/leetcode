# Two Sum

[**Problem Link**](https://leetcode.com/problems/two-sum)

**Prompt:** Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

**Initial Thoughts:**

```

// The first and most basic way of solving this problem would be to loop through each index if said value plus any of the later values added up to be the target number. For example index 0 + index 1? no? index 0 + index 2? index 0+ index 3? index 1 + index 2? And so on until we tried all the possible combinations.

// A more efficient solution, however, would be to subtract nums[index] from target and see if the array includes said value and if so that the index isn’t the same as the current index. This should be more efficient than the brute force solution.
```

**My Solution:**

```
var twoSum = function (nums, target) {
  for (let i = 0; i < nums.length; i++) {
    const requiredNumIndex = nums.indexOf(target - nums[i]);
    if (requiredNumIndex > -1 && requiredNumIndex !== i) {
      return [i, requiredNumIndex];
    }
  }
};
```

**Reflection:** My solution was decent, but it could have been made more efficient by not having to use the `indexOf()` method inside of a loop. I could have instead used a hash map. This would have improved the time complexity at the cost of some space complexity.

After learning more about `Maps` in JavaScript, I challenged myself to complete this problem again with a more optimal solution.

```
var twoSum = function (nums, target) {
  const numMap = new Map();
  for (let i = 0; i < nums.length; i++) {
    const complement = target - nums[i];
    if (numMap.has(complement)) {
      return [numMap.get(complement), i];
    }
    numMap.set(nums[i], i);
  }
};
```
