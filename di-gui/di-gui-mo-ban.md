# 递归模版

```
func recursion(level int, param int) {

    // 递归推出条件
    if level > MaxLevel {
        process_result()
        return
    }
    
    // 处理当前层的数据
    process_data(level, param)
    
    //进入下一层
    recursion(level+1, param)
    
    // 清理当前层的状态数据

}
```
