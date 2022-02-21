# 有效的括号

```
func isValid(s string) bool {
	if len(s)%2 == 1 {
		return false
	}
	pairs := map[rune]rune{
		')': '(',
		'}': '{',
		']': '[',
	}

	st := make([]rune, 0)
	for _, c := range s {
		if _, ok := pairs[c]; ok {
			if len(st) == 0 || st[len(st)-1] != pairs[c] {
				return false
			}
			st = st[:len(st)-1]
		} else {
			st = append(st, c)
		}
	}
	return len(st) == 0
}
```
