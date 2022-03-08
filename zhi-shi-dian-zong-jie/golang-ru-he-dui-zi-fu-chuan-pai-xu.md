# golang 如何对字符串排序

```
//    利用sort 函数 自定义比较函数 
func sort(str string) string {
    s := []byte(str)
    sort.Slice(s, func(i, j int) bool { return s[i] < s[j] })
    sortedStr := string(s)
    return sortedStr
}

// 将字符串切分成字符串组， 利用sort.Strings 进行排序 然后组装
func sort(str string) string {
    array := strings.split(str,"")
    sort.Strings(array)
    return strings.Join(array, "")
}

```
