---
description: 定 n 个非负整数，用来表示柱状图中各个柱子的高度。每个柱子彼此相邻，且宽度为 1 。  求在该柱状图中，能够勾勒出来的矩形的最大面积。
---

# 柱状图中最大的矩形

```
1. 暴力求解
// func largestRectangleArea(heights []int) int {
//     maxArea := 0 
//     for i := 0 ; i < len(heights) ; i ++ {
//         minHeight := heights[i]
//         for j := i ; j < len(heights); j ++ {
//             minHeight = min(minHeight, heights[j])
//             maxArea = max(maxArea, minHeight*(j-i+1))
//         }
//     }
//     return maxArea
// }



func max(a, b int) int {
	if a >= b {
		return a
	}
	return b
}

func min(a, b int) int {
	if a <= b {
		return a
	}
	return b
}

type Element struct {
	value int
	index int
}

type stackType struct {
	Array []Element
}

func (st *stackType) peek() Element {
	if len(st.Array) == 0 {
		return Element{}
	}
	return st.Array[len(st.Array)-1]
}
func (st *stackType) pop() {
	if len(st.Array) == 0 {
		return
	}
	st.Array = st.Array[:len(st.Array)-1]
}

func (st *stackType) push(ele Element) {
	st.Array = append(st.Array, ele)
}
func (st *stackType) size() int {
	return len(st.Array)
}

func newStack() *stackType {
	stack := &stackType{
		Array: make([]Element, 0),
	}
	initElement := Element{
		index: -1,
		value: -1,
	}
	stack.push(initElement)
	return stack
}
func largestRectangleArea(heights []int) int {
	stack := newStack()

	maxArea := 0
	for i := 0; i < len(heights)+1; i++ {
		for {
			top := stack.peek()
			if i < len(heights) && top.value <= heights[i] {
				newElement := Element{
					index: i,
					value: heights[i],
				}
				stack.push(newElement)
				break
			}
			if stack.size() == 1 {
				break
			}
			stack.pop()
			left := stack.peek()
			area := top.value * (i - left.index - 1) 
			maxArea = max(maxArea, area)
		}
	}

	return maxArea
}
```
