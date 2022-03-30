---
description: "给定一个数组 prices ，其中\_prices[i] 表示股票第 i 天的价格。  在每一天，你可能会决定购买和/或出售股票。你在任何时候\_最多\_只能持有 一股 股票。你也可以购买它，然后在 同一天 出售。 返回 你能获得的 最大 利润\_  来源：力扣（LeetCode） 链接：https://leetcode-cn.com/problems/best-time-to-buy-and-sell-"
---

# 买卖股票的最佳时机 II

```

// 只要今天比第二天低就可以买入， 提前知道可以暴富
func maxProfit(prices []int) int {
    if len(prices) == 1 {
        return 0 
    }
    sum := 0 
    for i:= 1 ; i < len(prices); i ++ {

        sub :=  prices[i] - prices[i -1 ]
        if sub > 0 {
            sum = sum + sub 
        }

    }
    return sum 
}
```
