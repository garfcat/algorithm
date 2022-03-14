# 递归模版

```
func recursion(level int, param1 interface, param2 interface, ...) {

    // 递归推出条件
    if level > MaxLevel {
        process_result()
        return
    }
    
    // 处理当前层的数据
    process_data(level, data...)
    
    //进入下一层
    recursion(level+1, param1, param2,...)
    
    // 清理当前层的状态数据

}
```
