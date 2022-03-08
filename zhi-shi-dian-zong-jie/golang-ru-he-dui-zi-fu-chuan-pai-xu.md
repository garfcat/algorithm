# golang 如何对字符串排序

```
//    利用sort 函数 自定义比较函数 
func sort(str string) string {
        s := []byte(str)
        sort.Slice(s, func(i, j int) bool { return s[i] < s[j] })
        sortedStr := string(s)
        return sortedStr
}
```
