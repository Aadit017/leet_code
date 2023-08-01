# Search Insert Position
Easy
14.1K
614
Companies
Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with O(log n) runtime complexity.

```
class Solution {
    public int searchInsert(int[] nums, int target) {
        /*
        Not keeping any runtime complexity into consideration
        1. If the element is found
            - return the index pos

        2. if the element isnt found 
            - Array is alr sorted 
            - a. target<nums[0] , return 0
            - b. target>nums[size], return size+1
            - if the above fail 
                c. nums[i-1]<target && nums[i]>=target , return i
        */
        for(int i=0; i<nums.length ;i++){
            if(nums[i]==target){
                return i;
            }
        }

        // Case 2#
        if(target<nums[0]){
            return 0;
        }else if(target>nums[nums.length-1]){
            return nums.length;
        }else{
            for(int i=1;i<nums.length;i++){
                if(nums[i-1]<target){
                    if(nums[i]>=target){
                        return i;
                    }
                }
            }
        }
    return 0;
    }
}
```