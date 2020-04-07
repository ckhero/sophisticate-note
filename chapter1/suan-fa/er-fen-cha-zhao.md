## 二分查找

> [https://leetcode-cn.com/problems/find-first-and-last-position-of-element-in-sorted-array/solution/er-fen-cha-zhao-suan-fa-xi-jie-xiang-jie-by-labula/](https://leetcode-cn.com/problems/find-first-and-last-position-of-element-in-sorted-array/solution/er-fen-cha-zhao-suan-fa-xi-jie-xiang-jie-by-labula/)

## 正常

> ```
> int binarySearch(int[] nums, int target) {
>     int left = 0; 
>     int right = nums.length - 1; // 注意
>
>     while(left <= right) {
>         int mid = left + (right - left) / 2;
>         if(nums[mid] == target)
>             return mid; 
>         else if (nums[mid] < target)
>             left = mid + 1; // 注意
>         else if (nums[mid] > target)
>             right = mid - 1; // 注意
>     }
>     return -1;
> }
> ```

## 左届

> ```
> int left_bound(int[] nums, int target) {
>     int left = 0, right = nums.length - 1;
>     // 搜索区间为 [left, right]
>     while (left <= right) {
>         int mid = left + (right - left) / 2;
>         if (nums[mid] < target) {
>             // 搜索区间变为 [mid+1, right]
>             left = mid + 1;
>         } else if (nums[mid] > target) {
>             // 搜索区间变为 [left, mid-1]
>             right = mid - 1;
>         } else if (nums[mid] == target) {
>             // 收缩右侧边界
>             right = mid - 1;
>         }
>     }
>     // 检查出界情况
>     if (left >= nums.length || nums[left] != target)
>         return -1;
>     return left;
> }
> ```

## 右届

> ```
> int right_bound(int[] nums, int target) {
>     if (nums.length == 0) return -1;
>     int left = 0, right = nums.length;
>     
>     while (left < right) {
>         int mid = (left + right) / 2;
>         if (nums[mid] == target) {
>             left = mid + 1; // 注意
>         } else if (nums[mid] < target) {
>             left = mid + 1;
>         } else if (nums[mid] > target) {
>             right = mid;
>         }
>     }
>     return left - 1; // 注意
> }
> ```





