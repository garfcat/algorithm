---
description: 两个链表是否相交，并求得相交的点
---

# 链表相交

1. 哈希方法
2. 等长

```
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func getIntersectionNode(headA, headB *ListNode) *ListNode {
    tmpA := headA
    tmpB := headB

    lenA := 0
    lenB := 0

    for tmpA != nil {
        tmpA = tmpA.Next
        lenA++
    }

    for tmpB != nil {
        tmpB = tmpB.Next
        lenB++
    }
    tmpA = headA
    tmpB = headB
    if lenA > lenB {
        for i := 0 ; i < lenA-lenB; i ++ {
            tmpA = tmpA.Next
        }
    } else if lenA < lenB {
         for i := 0 ; i < lenB-lenA; i ++ {
            tmpB = tmpB.Next
        } 
    }
    for tmpA != nil && tmpB != nil {
        if tmpA == tmpB {
            return tmpA
        }
        tmpA = tmpA.Next
        tmpB = tmpB.Next
    }
    return nil 
}
```
