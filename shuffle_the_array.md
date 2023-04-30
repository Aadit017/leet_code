# Given the array nums consisting of 2n elements in the form [x1,x2,...,xn,y1,y2,...,yn].

Return the array in the form [x1,y1,x2,y2,...,xn,yn].
Example 1:
Input: nums = [2,5,1,3,4,7], n = 3
Output: [2,3,5,4,1,7] 
Explanation: Since x1=2, x2=5, x3=1, y1=3, y2=4, y3=7 then the answer is [2,3,5,4,1,7].

```
class Solution {
    public int[] shuffle(int[] nums, int n) {
        List<Integer> list = new ArrayList<Integer>();
        int arr1[]=new int[n];
        int arr2[]=new int[n];
        for(int i=0;i<n;i++){
            arr1[i]=nums[i];
        }
        for(int i=n;i<n+n;i++){
            int l=i-n;
            arr2[l]=nums[i];
        }
        for(int i=0;i<n;i++){
            list.add(arr1[i]);
            list.add(arr2[i]);
        }
        int arr[]=new int[n+n];
        for(int i=0;i<list.size();i++){
            arr[i]=list.get(i);
        }
        return arr;
    }
}
```