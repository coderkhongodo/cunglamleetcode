# TwoSum

## Problem Description

>Given an array of integers `nums` and an integer `target`, return **indices** of the two numbers such that they add up to `target`.
You may assume that each input would have **exactly one solution**, and you may not use the same element twice.
You can return the answer in **any order**.

### Example 1:
>Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
### Example 2:
>Input: nums = [3,2,4], target = 6
Output: [1,2]

## Step-by-step explanation:
> **Input and Output**:
    You have an array of integers `nums` and a target sum `target`.
   You need to return a pair of indices `[index1, index2]` such that `nums[index1] + nums[index2] = target`.

> **Using a Hash Map (unordered_map)**:
   The algorithm uses a hash map (in C++, it's called `unordered_map`) to store values from `nums` and their corresponding indices.
   The key in the map is a number from `nums`, and the value is the index of that number.

> **Iterating through the array**:
   The algorithm loops through the array `nums` using a `for` loop. The variable `i` represents the current index.

> **Checking for complement**:
   For each number `nums[i]`, the algorithm calculates a "complement" (`tmp`), which is `target - nums[i]`. This is the number that, when added to `nums[i]`, equals the target.
   It then checks if this complement is already in the hash map using `mp.count(tmp)`. If the complement exists, that means you've found two numbers that add up to the target.
   
> **Returning the solution**:
   If the complement is found in the map, the algorithm returns the indices of the complement (stored in the map) and the current index `i`.
   If no complement is found, the current number (`nums[i]`) and its index are added to the map so it can be used in future iterations.

> **Final output**:
  If the loop completes without finding a solution (which won't happen in valid inputs according to the problem constraints), it returns `[0, 0]` as a default.
## Solution

```C++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> mp;
        for(int i = 0; i < nums.size(); i++){
            int tmp = target - nums[i];
            if(mp.count(tmp)){
                return {mp[tmp], i};
            }
            mp[nums[i]] = i;
        }
        return {0, 0};
    }
}
```
## Nice to meet you😘
Contact: cunglamleetcode@gmail.com 
Tiktok: [here](https://www.tiktok.com/@cunglamleetcode)
