# 不同路径2

```
func uniquePathsWithObstacles(obstacleGrid [][]int) int {
    m := len(obstacleGrid)
    n := len(obstacleGrid[0])
   dp := make([][]int , m)
    for i := 0; i < m ; i ++  {
        dp[i] = make([]int, n)
    }
    var recur func (x int , y int ) int
   recur = func (x int , y int ) int {
       // 结束条件
       if obstacleGrid[x][y] == 1 {
           return 0 
       }
        if x == 0 && y == 0 {
            return 1
        }

        // 缓存
        if dp[x][y] != 0 {
            return dp[x][y]
        }

        // 递推公式
        if x - 1 < 0  && y -1 >= 0 {
             dp[x][y] =  recur(x, y -1 )
        }
        if x - 1 >= 0 && y -1 < 0 {
              dp[x][y] =  recur(x - 1, y )
        }
        if x - 1 >= 0 && y - 1 >=0 {
              dp[x][y] = recur(x-1, y) + recur(x, y -1 )
        }
        return dp[x][y]
    }

    dp[m-1][n-1] = recur(m-1, n-1)

    return dp[m-1][n-1]
}

```
