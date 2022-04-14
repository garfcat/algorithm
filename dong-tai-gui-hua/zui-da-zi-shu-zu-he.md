# 最大子数组和

```
// 标准动态规划
func maxSubArray(nums []int) int {
    if len(nums) == 0 {
        return 0
    }
    dp := make([]int, len(nums))
    dp[0] = nums[0]
    maxSum := nums[0]
    for i:= 1 ; i < len(nums) ; i++ {
        dp[i] = max(nums[i] + dp[i-1], nums[i])
        maxSum = max(maxSum, dp[i])
    }

    return maxSum
}
func max(x ,y int) int {
    if x > y {
        return x
    }
    return y 
}


// 内存优化
func maxSubArray(nums []int) int {
    if len(nums) == 0 {
        return 0
    }

    maxSum := nums[0]
    sum := nums[0]
    for i:= 1 ; i < len(nums) ; i++ {
        sum = max(nums[i]+sum, nums[i])
        maxSum = max(maxSum, sum)
    }

    return maxSum
}
```
