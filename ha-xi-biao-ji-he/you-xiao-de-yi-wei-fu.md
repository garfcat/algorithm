---
description: "给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的字母异位词。  注意：若\_s 和 t\_中每个字符出现的次数都相同，则称\_s 和 t\_互为字母异位词。  \_  示例\_1:  输入: s = \"anagram\", t = \"nagaram\" 输出: true 示例 2:  输入: s = \"rat\", t = \"car\" 输出: false  来源：力扣（LeetCode） 链接："
---

# 有效的异位符

```
// 先排序，再比较
func isAnagram(s string, t string) bool {
    a := SortString(s)
    b := SortString(t)

    return a == b

}

 
func SortString(w string) string {
    s := strings.Split(w, "")
    sort.Strings(s)
    return strings.Join(s, "")
}

// 哈希 
// hash[v]-- 如果原来不存在 则 hash[v]-- 等效于 hash[v] = 0 - 1
func isAnagram(s string, t string) bool {
    if len(s) != len(t) {
        return false
    }
    hash := make(map[rune]int)
    for _,v :=range s {
        hash[v]++
    }
    for _,v := range t {
        hash[v]--
        if hash[v] < 0 {
            return false
        }
    }
    
    return true
}
```
