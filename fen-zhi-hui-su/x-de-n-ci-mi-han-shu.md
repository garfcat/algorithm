---
description: 实现 pow(x, n) ，即计算 x 的 n 次幂函数（即，xn ）。
---

# x 的 n 次幂函数

这个题目要考虑 两个情况：

1. n 为负数： 提前处理，可以使得后面逻辑统一
2. n 为奇偶:  分情况处理

```
func myPow(x float64, n int) float64 {
    if n < 0 {
        x = 1/x
        n = -n
    }
    return fastPow(x, n) 
}

func fastPow(x float64, n int) float64 {
    if n ==0 {
        return 1.0
    }

    half := fastPow(x, n/2)
    if n % 2 == 1 {
        return half * half * x
    }

    return half * half
}
```
