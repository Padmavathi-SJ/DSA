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

### 05. 53. Maximum Subarray
```
class Solution {
    public int maxSubArray(int[] nums) {
        int maxSum=nums[0];
        int currSum=nums[0];
        for(int i=1; i<nums.length; i++){
            currSum=Math.max(nums[i], currSum+nums[i]);
            maxSum=Math.max(currSum, maxSum);
        }
        return maxSum;
    }
}
"""
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6

Input: nums = [5,4,-1,7,8]
Output: 23
"""
```

### 06. 287. Find the Duplicate Number
```
class Solution {
    public int findDuplicate(int[] nums) {
        int res=0;
        for(int i=0; i<nums.length; i++){
            for(int j=i+1; j<nums.length; j++){
                if(nums[i] == nums[j]){
                    res=nums[i];
                    break;
                }
            }
        }
        return res;
    }
}
"""
Input: nums = [1,3,4,2,2]
Output: 2

Input: nums = [3,1,3,4,2]
Output: 3
"""
```

### 07. 152. Maximum Product Subarray
```
class Solution {
    public int findPro(int[] nums, int s, int e){
        int pro=1;
        for(int i=s; i<=e; i++){
            pro*=nums[i];
        }
        return pro;
    }
    public int maxProduct(int[] nums) {
        if(nums.length==1) return nums[0];
        int maxPro=0;
        for(int i=0; i<nums.length; i++){
           for(int j=i; j<nums.length; j++){
            int currPro=findPro(nums, i, j);
            maxPro=Math.max(currPro, maxPro);
           }
        }
        return maxPro;
    }
}
"""
Input: nums = [2,3,-2,4]
Output: 6


Input: nums = [-2,0,-1]
Output: 0
"""
```

### 08. 153. Find Minimum in Rotated Sorted Array
```
class Solution {
    public int findMin(int[] nums) {
        int min=nums[0];
        for(int i=1; i<nums.length; i++){
            min=Math.min(min, nums[i]);
        }
        return min;
    }
}
"""
Input: nums = [3,4,5,1,2]
Output: 1


Input: nums = [4,5,6,7,0,1,2]
Output: 0
"""
```
```
class Solution {
    public int findMin(int[] nums) {
        List<Integer> l=new ArrayList<>();
        for(int i=0; i<nums.length; i++){
            l.add(nums[i]);
        }
        return Collections.min(l);
    }
}
```

### 09. 33. Search in Rotated Sorted Array
```
class Solution {
    public int search(int[] nums, int target) {
        List<Integer> l=new ArrayList<>();
        for(int i=0; i<nums.length; i++){
            l.add(nums[i]);
        }
        if(l.contains(target)){
            return l.indexOf(target);
        }
        else{
            return -1;
        }
    }
}
"""
Input: nums = [4,5,6,7,0,1,2], target = 0
Output: 4

Input: nums = [4,5,6,7,0,1,2], target = 3
Output: -1
"""
```

## Linked List
### 206. Reverse Linked List
```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode prev=null;
        ListNode current=head;
        ListNode next;
        while(current!=null){
            next=current.next;
            current.next=prev;
            prev=current;
            current=next;
        }
        return prev;
    }
}
"""
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]
"""
```

### 141. Linked List Cycle
```
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    public boolean hasCycle(ListNode head) {
       ListNode slow=head;
       ListNode fast=head;
       while(fast!=null && fast.next!=null){
        slow=slow.next;
        fast=fast.next.next;
        if(slow==fast){
            return true;
        }
       }
       return false;
}

}
"""
Input: head = [3,2,0,-4], pos = 1
Output: true
Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).

Input: head = [1,2], pos = 0
Output: true
Explanation: There is a cycle in the linked list, where the tail connects to the 0th node.
"""
```

### 21. Merge Two Sorted Lists
```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        if(list1==null) return list2;
        if(list2==null) return list1;
        ListNode dummy=new ListNode(-1);
        ListNode temp=dummy;
        while(list1!=null && list2!=null){
            if(list1.val < list2.val){
                temp.next=list1;
                temp=list1;
                list1=list1.next;
            }
            else{
                temp.next=list2;
                temp=list2;
                list2=list2.next;
            }
        }
        if(list1!=null) temp.next=list1;
        if(list2!=null) temp.next=list2;
        return dummy.next;
    }
}
"""
Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]

Input: list1 = [], list2 = []
Output: []
"""
```
