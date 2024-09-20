Given an array `nums` of size `n`, return _the majority element_.

The majority element is the element that appears more than `⌊n / 2⌋` times. You may assume that the majority element always exists in the array.

**Example 1:**
**Input:** nums = [3,2,3]
**Output:** 3

**Example 2:**
**Input:** nums = [2,2,1,1,1,2,2]
**Output:** 2

https://leetcode.com/problems/majority-element/description/?envType=study-plan-v2&envId=top-interview-150

### Solution:
Boyer-Moore Majority Voting Algorithm
https://www.geeksforgeeks.org/boyer-moore-majority-voting-algorithm/

```java
public static int majorityElement(int[] nums) {  
    int candidate = nums[0];  
    int count = 0;  
  
    for (int num : nums) {  
        if (count == 0) {  
            candidate = num;  
        }  
  
        count += (num == candidate ? 1 : -1);  
    }  
  
    return candidate;  
}
```