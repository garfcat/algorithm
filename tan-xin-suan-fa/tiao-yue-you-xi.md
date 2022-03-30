---
description: 给定一个非负整数数组 nums ，你最初位于数组的 第一个下标 。  数组中的每个元素代表你在该位置可以跳跃的最大长度。  判断你是否能够到达最后一个下标。
---

# 跳跃游戏

```
func canJump(nums []int) bool {
    if len(nums ) <= 1 {
        return true 
    }
    end := len(nums) - 1
    for i := len(nums) -1 ; i >=0 ; i -- {
      if   nums[i] + i  >= end {
          end = i 
      }
    }
    return end == 0 
}
```
