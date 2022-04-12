# 最长公共字符串

```
//递归
func longestCommonSubsequence(text1 string, text2 string) int {
    m := len(text1)+1
    n := len(text2)+1
    dp := make([][]int, m)
    for i := 0 ; i < m; i++ {
        dp[i] = make([]int, n)
    }

    var recursion func(x int , y int ) int 

    recursion = func(x int , y int ) int {
        // 结束条件
        if x == 0 || y == 0 {
            return 0 
        }
   
        // process data
        // 缓存处理
        if dp[x][y] != 0 {
            return dp[x][y]
        }
        // 逻辑处理
        if text1[x-1] == text2[y-1] {
            // drill down
            dp[x][y] = recursion(x-1, y -1 ) + 1
        } else {
             dp[x][y] = max(recursion(x-1, y  ), recursion(x, y -1 ))
        }
        return dp[x][y]
    }
     recursion(m-1, n -1)
     return dp[m-1][n-1]
}

func max(i ,j  int) int {
    if i <= j {
        return j
    }
    return i
}


// 非递归
func max(i ,j  int) int {
    if i <= j {
        return j
    }
    return i
}

// 类似于斐波那契数列 只不过这里是二维的
func longestCommonSubsequence(text1 string, text2 string) int {
   m := len(text1)+1
   n := len(text2)+1
    count := make([][]int,m)
    for i := 0; i < m ; i ++ {
        count[i] = make([]int, n)
    }
 
    for i := 1; i < m; i ++ {
        for j :=1;j < n; j ++ {
            if text1[i-1] == text2[j-1] {
                count[i][j] =  count[i-1][j-1]+1
            } else {
                count[i][j] = max(count[i-1][j],count[i][j-1])
            }
        }
    }
    return count[m-1][n-1]

}
```
