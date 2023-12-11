# Group Anagrams

[**Problem Link**](https://leetcode.com/problems/group-anagrams)

**Prompt:** Given an array of strings strs, group the anagrams together. You can return the answer in any order.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Initial Thoughts:**

```
// We will output a 2d array in which each internal array is group of matching anagrams.

// To do this, we can sort each individual item in the array, and then sort the array itself. Then we create a currentItems array and start looping through the entire sortedArray.

// If the previous value is different to the current value, we'll push currentItems to our outputArray. If the previous value is the same as the current value, we'll push the current item to currentItems.

// After we finish looping through the sortedArray we can return the outputArray as our answer.

// This brute force solution seems pretty inefficient but once I finish implementing it I think I'll have a greater appreciation once I read about how to solve this problem in an optimal manner.

// Actually, this solution has the problem that the items in the outputArray would be sorted. I may just have to do nested loops instead… Could I use a hash map here and do something like this?

// Sorted item as the key of the hashmap (map), and an array with the actual item as the value. As we loop through the array, we can check if the hashmap has the sortedItem. If not, we add the sorted item as a key and non-sorted item as a value inside the hashmap. Otherwise, we take the key of this sorted item and concat the non-sorted item to the value array.
```

**My Solution:**

```
var groupAnagrams = function (strs, map = new Map()) {
  if (strs.length === 1) {
    return [[strs[0]]];
  }
  map.set(strs[0].split("").sort().join(""), [strs[0]]);
  for (let i = 1; i < strs.length; i++) {
    const sortedStr = strs[i].split("").sort().join("");
    if (!map.has(sortedStr)) {
      map.set(sortedStr, [strs[i]]);
      continue;
    }
    map.get(sortedStr).push(strs[i]);
  }
  return Array.from(map.values());
};
```

**Reflection:** My solution was pretty good. I'm proud of myself for being able to come up with a somewhat optimized solution all by myself. After solving the problem, however, I saw there was a solution that was similar to mine, but a bit more optimized.

Instead of using the `sortedStr` as our key, we would use an array of charCounts of all of the letters in a given string. This apparently would result in a more efficient time complexity of `O(N * K)` instead of the `O(N * (K * log(K)))` my solution had.
