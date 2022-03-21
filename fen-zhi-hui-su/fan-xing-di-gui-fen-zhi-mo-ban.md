# 泛型递归/分治模版

## &#x20;泛型递归

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

## 泛型分治

```
func divide_conquer(problem interface{}, data inferface{})  interface{} {

    res := make([]interface{}, 0 )
    
    //1. recursion is terminate
    if problem is nil {
        process_result()
        return 
    }
    //2. prepare data
    data := prepare(problem, data)
    problems := splitProblem(problem,data)
    
    // 3. conquer sub problems
    for k,v := range problems {
     res = append(res, divide_conquer(v, data))
    }

    // 4.process result
    result = process_result(res)
    return result
}
```
