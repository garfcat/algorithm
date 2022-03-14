# 二叉树中序遍历

```
// Some code

func inorderTraversal(root *TreeNode) []int {

    res := []int{}
    if root == nil {
        return res
    }
    
    res = append(res, inorderTraversal(root.Left)...)
    res = append(res, root.Val)
    res = append(res, inorderTraversal(root.Right)...)
    return res
}
```
