---
description: "给你一个字符串数组，请你将 字母异位词 组合在一起。可以按任意顺序返回结果列表。  字母异位词 是由重新排列源单词的字母得到的一个新单词，所有源单词中的字母通常恰好只用一次。  \_  示例 1:  输入: strs = [\"eat\", \"tea\", \"tan\", \"ate\", \"nat\", \"bat\"] 输出: [[\"bat\"],[\"nat\",\"tan\"],[\"ate\",\"eat\",\"tea\"]]"
---

# 字母异位词分组

```

// 排序归类
func groupAnagrams(strs []string) [][]string {
    groupHash := make(map[string][]string)
    for _,str := range strs {
        key := sortStr(str)
        groupHash[key] = append(groupHash[key], str)
    }
    res := make([][]string, 0)
    for _,v := range groupHash {
        res = append(res, v)
    }
    return res 
}
func sortStr(str string) string {
    s := strings.Split(str, "")
    sort.Strings(s)
    return strings.Join(s, "")
}
```
