# N叉树后序遍历

```
/**
 * Definition for a Node.
 * type Node struct {
 *     Val int
 *     Children []*Node
 * }
 */

func postorder(root *Node) []int {
    res := []int{}
    if root == nil {
        return res
    }
    for _,children := range root.Children {
        res = append(res, postorder(children)...)
    }
    res = append(res, root.Val)
    return res
}
```
