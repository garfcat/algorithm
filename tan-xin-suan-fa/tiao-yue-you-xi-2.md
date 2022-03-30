---
description: "给你一个非负整数数组\_nums ，你最初位于数组的第一个位置。  数组中的每个元素代表你在该位置可以跳跃的最大长度。  你的目标是使用最少的跳跃次数到达数组的最后一个位置。  假设你总是可以到达数组的最后一个位置。  来源：力扣（LeetCode） 链接：https://leetcode-cn.com/problems/jump-game-ii 著作权归领扣网络所有。商业转载请联系官方授权，非商业"
---

# 跳跃游戏2

```


// [3,2,1,0,4]
func jump(nums []int) int {
    if len(nums) <= 1 {
        return 0
    }

    end := len(nums) - 1
    pre := end
    cnt := 0
    for end != 0 {
        for i := end ; i >=0 ; i-- {
            if nums[i] + i >= end {
                pre = i 
                continue
            }
        }
        if end == pre {
            return 0 
        }
        end = pre 
        cnt ++
    }

  return cnt 
}
```
