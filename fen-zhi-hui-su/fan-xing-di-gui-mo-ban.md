# 泛型递归模版

```
func recursion(level int, data int) {
    // 1. terminate
    if terminate is true {
        return
    }
    // 2. process current level
        process(level, data)
    // 3. drill into  next level
        recursion(level+1, data)
    // 4. reverse current level if needed

}
```
