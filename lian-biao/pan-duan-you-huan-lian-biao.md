---
description: 给你一个链表的头节点 head ，判断链表中是否有环。
---

# 判断有环链表

解决方法:

1. 暴力循环&#x20;
2. 哈希
3. 快慢指针

```
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func hasCycle(head *ListNode) bool {
    fast := head 
    slow := head

    for  fast != nil && fast.Next != nil  {
     
        slow = slow.Next
        fast = fast.Next.Next
        if slow == fast {
            return true
        }
    }
    
    return false
}
```
