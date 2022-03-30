# 分发饼干问题

```
// 双层循环 这个答案不是很好
func findContentChildren(g []int, s []int) int {
    sort.Ints(g)
    sort.Ints(s)

    cnt := 0 
    i := 0
    j := 0
    for i < len(g) && j < len(s) {
        if g[i] > s[j] {
            j ++
            continue
        }
        i ++ 
        j ++
        cnt ++


    }
    return cnt
}


// 一层循环
func findContentChildren(g []int, s []int) int {
    sort.Ints(g)
    sort.Ints(s)

    cnt := 0 
    i := 0
    j := 0
    for i < len(g) && j < len(s) {
        if g[i] > s[j] {
            j ++
            continue
        }
        i ++ 
        j ++
        cnt ++


    }
    return cnt

}
```
