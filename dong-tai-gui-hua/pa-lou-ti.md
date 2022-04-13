# 爬楼梯

```
// 递归+缓存
func climbStairs(n int) int {
    if n == 1 {
        return 1
    }
    if n == 2 {
        return 2 
    }
  dp := make([]int, n )
  var recursion func(i int) int
  recursion = func(i int) int {
      // 结束条件
      if i == 0 {
          return  1
      }
      if i == 1 {
        return 2 
     }
    // 缓存
    if dp[i] != 0 {
        return dp[i]
    }
    // 当前层
    dp[i] = recursion(i-1) + recursion(i-2)
    return dp[i]
  }
  recursion(n-1)
  return dp[n-1]
}


func climbStairs(n int) int {
    if n == 1 {
        return 1
    }
    if n == 2 {
        return 2 
    }
  dp := make([]int, n )
    dp[0] = 1
    dp[1] =2 
  for i := 2; i < n ; i ++ {
      dp[i] = dp[i-1] + dp[i-2]
  }
    return dp[n-1]
}
// 最简单的方式
func climbStairs(n int) int {
    if n == 1 {
        return 1
    }
    if n == 2 {
        return 2 
    }
    f1 := 1
    f2 := 2
    f3 := f1 + f2 
    for i := 3; i <= n ; i ++ {
        f3 = f1 + f2 
        f1, f2 = f2, f3 
    }

    return f3 
}







```
