# Valid Anagram

[**Challenge Link**](https://leetcode.com/problems/valid-anagram)

**Prompt:** Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Initial Thoughts:**

```
// I'm pretty sure if I convert s and t into arrays, sort them, join them and then they equal each other then they must be anagrams.
```

**My Solution:**

```
var isAnagram = function (s, t) {
  return s.split("").sort().join("") === t.split("").sort().join("");
};
```

**Reflection:** My solution was ok from a time complexity standpoint, but probably not as ideal from a space complexity standpoint. An alternative solution that may have been a bit more efficient would have been to create a `Map` add key value pairs to it, and then add and remove the occurrence frequency of the various letters to/from the Map as we iterate through the two strings.
