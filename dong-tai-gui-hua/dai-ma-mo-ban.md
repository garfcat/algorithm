# 代码模版

```
// 递归代码模版
func recursion(level int, param int) {

    // 递归结束条件
    if level > MaxLevel {
        return
    }
    // 处理当前层的逻辑
    process(level, param)
    
    // 递归到下一层
    recursion(level+ 1, newParam)
    
    // 恢复当前层的状态
    
}


// 分治 是特殊的递归
func divideConquer(problem, param1, param2 ...) {

   // 递归终结条件
    if problem is Nil {
        // print result
        return
    }
    
    // 拆分问题为多个子问题
    data := prepare(problem)
    subproblems := splitProblem(problem, data)
    
    //调用递归函数即 下探到下一层
    subresult1 := divideConquer(subproblems[0], p1....)
    subresult2 := divideConquer(subproblems[1], p1....)
    subresult3 := divideConquer(subproblems[2], p1....)
    
    // 合并结果
    results := process_results(subresult1, subresult2, subresult3...)
    
}
```
