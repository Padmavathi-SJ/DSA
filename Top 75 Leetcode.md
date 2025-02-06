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
