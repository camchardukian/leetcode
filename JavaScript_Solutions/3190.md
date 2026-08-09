**Solution:**

```
/**
 * @param {number[]} nums
 * @return {number}
 */
var minimumOperations = function(nums) {
    let count = 0;
    function recurse(number) {
        if (number === 0 || number === 3 || number % 3 === 0) {
            return;
        }
        else if (number < 3) {
            count +=1;
            return;
        } else {
            recurse(number % 3);
        }
    }
    for (let i = 0; i < nums.length; i++) {
        recurse(nums[i])
    }
    return count;
};
```

**Reflection:** While my recursive solution worked, using recursion to solve this problem wasn't necessary. I could've used an iterative approach like this instead:

```
/**
 * @param {number[]} nums
 * @return {number}
 */
var minimumOperations = function(nums) {
    let count = 0;
    for (let i = 0; i < nums.length; i++) {
        if (nums[i] % 3) {
            count+=1;
        }
    }
    return count;
};
```
