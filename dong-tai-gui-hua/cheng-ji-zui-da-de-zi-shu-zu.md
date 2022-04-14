# 乘积最大的子数组

```
func maxProduct(nums []int) int {
    if len(nums) == 0 {
        return 0
    }

    dpMax := make([]int, len(nums))
    dpMin := make([]int, len(nums))
    dpMax[0] = nums[0]
    dpMin[0] = nums[0]
    maxA := nums[0]
    for i := 1 ; i < len(nums); i++ {
        dpMax[i] = max(max(dpMax[i-1] * nums[i],dpMin[i-1] * nums[i]), nums[i])
        dpMin[i] = min(min(dpMax[i-1] * nums[i],dpMin[i-1] * nums[i]), nums[i])
        maxA = max(maxA, dpMax[i])
    }

    return maxA 
}



func max(x,y int ) int {
    if x > y {
        return x
    }
    return y 
}
func min(x,y int ) int {
    if x < y {
        return x
    }
    return y 
}
```
