# Largest Number At Least Twice of Others

## Problem

You are give an integer array **nums** where the largest integer us **unique**
Determine whether the largest element in the array is **at least twice** as much as every other number in the array. If it is, return the _**index**_ of the largest element, or return **-1** otherwise.

Example 1:

Input: nums = [3, 6, 1, 0]

Output: 1

Explanation: 6 is the largest integer, and for every other number in the array x, 6 is more than twice as big as x. The index of value 6 is 1, so we return 1.

Example 2:

Input: nums = [1, 2, 3, 4]

Output: -1

Explanation: 4 isn't at least as big as twice the value of 3, so we return -1.

Constraints:

2 <= nums.length <= 50

0 <= nums[i] <= 100

The largest element in nums is unique.

## Solution
### Python3
_I'm just starting to learn to code, I hope if I understand, you will too !!! Have fun ^^_
```
class Solution:
    def dominantIndex(self, nums: List[int]) -> int:
        maxIndex = 0                                                            # Finding index of max of the array
        for i in range(0, len(nums)):
            if (nums[i] > nums[maxIndex]):
                maxIndex = i
        for i in range(0, len(nums)):
            if (maxIndex != i and nums[maxIndex] < (2 * nums[i])):              # Return -1 if the max element is not twice of the i-th element
                return -1
        return maxIndex
```

