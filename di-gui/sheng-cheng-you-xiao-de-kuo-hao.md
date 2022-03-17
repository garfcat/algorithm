---
description: "数字 n\_代表生成括号的对数，请你设计一个函数，用于能够生成所有可能的并且 有效的 括号组合。  \_  示例 1：  输入：n = 3 输出：[\"((()))\",\"(()())\",\"(())()\",\"()(())\",\"()()()\"] 示例 2：  输入：n = 1 输出：[\"()\"]  来源：力扣（LeetCode） 链接：https://leetcode-cn.com/problems/gen"
---

# 生成有效的括号

```

/*
 左括号的个数最多为n 个

 右括号小于等于左括号的个数

*/
type Result struct {
    res []string 
}
func (r *Result)generateParenthesis(n int, left int, right int, res string)  {
    // 不符合规范的
    if left < right || left > n {
        return 
    }
    // 符合条件的结果
    if left == n && left == right {
        r.res = append(r.res, res)
        return 
    }

    // 处理当前层
    r.generateParenthesis(n, left+1, right, res+"(")
    r.generateParenthesis(n, left, right + 1, res+")")

}

func generateParenthesis(n int) []string {
    r := &Result{
        res : []string{},
    }
    r.generateParenthesis(n,0,0,"")
    return r.res
}
```
