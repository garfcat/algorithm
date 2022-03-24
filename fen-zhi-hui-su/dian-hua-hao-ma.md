# 电话号码

```

func letterCombinations(digits string) []string {
    if len(digits) == 0 { //处理边界
        return nil 
    }
    var res []string
    hash  :=  map[byte][]string{
    '2': []string{"a", "b", "c"},
    '3': []string{"d", "e", "f"},
    '4': []string{"g", "h", "i"},
    '5': []string{"j", "k", "l"},
    '6': []string{"m", "n", "o"},
    '7': []string{"p", "q", "r", "s"},
    '8': []string{"t", "u", "v"},
    '9': []string{"w", "x", "y", "z"},
  
}
    var df func (n int, digits string, r string)
    df = func (n int, digits string, r string)  {
        if n == len(digits) {
            res = append(res, r)
            return
        }
        str :=  hash[digits[n]]
        for _,v := range str {  
            // r+v 是包含了revert current status的动作
            df(n+1, digits, r+v)
        }
    }

    df(0, digits, "")

    return res
}



```
