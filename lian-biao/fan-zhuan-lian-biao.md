---
description: 给你单链表的头节点 head ，请你反转链表，并返回反转后的链表。
---

# 反转链表

```
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func reverseList(head *ListNode) *ListNode {
   var newHead *ListNode
    for head != nil {
        tmp := head.Next
        head.Next = newHead
        newHead = head
        head = tmp
    }
    return newHead
}
```
