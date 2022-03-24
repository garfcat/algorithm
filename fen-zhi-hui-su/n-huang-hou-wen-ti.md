# n 皇后问题

```

//leetcode submit region begin(Prohibit modification and deletion)
func solveNQueens(n int) [][]string {
	var res [][]string
	draws := make([][]string, n)
	for i := 0; i < n; i++ {
		draws[i] = make([]string, n)
		for j := 0; j < n; j++ {
			draws[i][j] = "."
		}
	}
	cols := make(map[int]bool)
	pie := make(map[int]bool)
	na := make(map[int]bool)
	var solve func(level int, row int)
	solve = func(row int, n int) {
		//fmt.Printf("%v\n", strings)
		// terminate
		if row >= n {
			ss := []string{}
			for i := 0; i < n; i++ {
				ss = append(ss, strings.Join(draws[i], ""))
			}
			res = append(res, ss)
			return
		}

		// process current level
		for col := 0; col < n; col++ {
			if cols[col] || pie[row+col] || na[row-col] {
				continue
			}
			cols[col] = true
			pie[row+col] = true
			na[row-col] = true
			draws[row][col] = "Q"
			solve(row+1, n)
			draws[row][col] = "."
			cols[col] = false
			pie[row+col] = false
			na[row-col] = false
		}
		// drill down
	}
	solve(0, n)
	return res
}
```
