## Top 75 Leetcode problems

### 01. Two Sum:
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] res=new int[2];
        for(int i=0; i<nums.length; i++){
            for(int j=i+1; j<nums.length; j++){
                if(nums[i] + nums[j] == target){
                    res[0]=i;
                    res[1]=j;
                }
            }
        }
        return res;
    }
}
"""
Input: nums = [2,7,11,15], target = 9
Output: [0,1]

Input: nums = [3,2,4], target = 6
Output: [1,2]
"""
```

### 02. 121. Best Time to Buy and Sell Stock
```
class Solution {
    public int maxProfit(int[] prices) {
        int buy=prices[0];
        int pro=0;
        for(int i=1; i<prices.length; i++){
            if(prices[i] < buy){
                buy=prices[i];
            }
            else if(prices[i]-buy > pro){
                pro=prices[i]-buy;
            }
        }
        return pro;
    }
}
"""
Input: prices = [7,1,5,3,6,4]
Output: 5

Input: prices = [7,6,4,3,1]
Output: 0
"""
```

### 03. 238. Product of Array Except Self
```
class Solution {
    public int[] productExceptSelf(int[] nums) {
        int[] res=new int[nums.length];
        int l=0;
        for(int i=0; i<nums.length; i++){
            int pro=1;
            for(int j=0; j<nums.length; j++){
                if(i==j) continue;
                    pro*=nums[j];
            }
            res[l++]=pro;
        }
        return res;
    }
}
"""
Input: nums = [1,2,3,4]
Output: [24,12,8,6]

Input: nums = [-1,1,0,-3,3]
Output: [0,0,9,0,0]
"""
```

### 04. 217. Contains Duplicate
```
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Set<Integer> s=new HashSet<>();
        for(int i=0; i<nums.length; i++){
            if(s.contains(nums[i])){
                return true;
            }
            else{
                s.add(nums[i]);
            }
        }
       return false;
    }
}
"""
Input: nums = [1,2,3,1]
Output: true

Input: nums = [1,2,3,4]
Output: false
"""
```
