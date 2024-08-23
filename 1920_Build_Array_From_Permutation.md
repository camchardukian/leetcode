**My solution**

/\*\*

- @param {number[]} nums
- @return {number[]}
  \*/
  var buildArray = function(nums) {
  const newNums = [];
  for (let i = 0; i < nums.length; i++) {
  newNums.push(nums[nums[i]]);
  }
  return newNums;
  };

**Reflection:**

I knew my solution was passable, but not ideal because I'm using extra space in memory by using a secondary array for storage.

Apparently, this isn't completely necessary. There's something called _modular arithmetic_ we could use to encode and decode multiple values in a single index.
