---
cover: >-
  https://images.unsplash.com/photo-1552664730-d307ca884978?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=2970&q=80
coverY: 0
description: 题目介绍 leetcode 283
---

# 移动零

给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

示例:

输入: \[0,1,0,3,12] 输出: \[1,3,12,0,0] 说明:

必须在原数组上操作，不能拷贝额外的数组。 尽量减少操作次数。

来源：力扣（LeetCode） 链接：https://leetcode-cn.com/problems/move-zeroes 著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



```
func moveZeroes(nums []int) {
j := 0 // 表示下一个非0的元素
for i:=0 ;i < len(nums); i++ {
    if nums[i] != 0 {
        nums[j] = nums[i] // 将不等于0的数放到 j 的位置上
        if i != j { // 如果i 不等与 j ,则将i 位置数据设置为0
            nums[i] = 0 
        }
        j++
    } 

}
```
