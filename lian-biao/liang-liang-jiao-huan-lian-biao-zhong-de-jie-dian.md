# 两两交换链表中的节点

```
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */

func swapPairs(head *ListNode) *ListNode {
    if head == nil || head.Next == nil {
        return head
    }
    dummyHead := &ListNode{}
    dummyHead.Next = head
    curNode := dummyHead
    for curNode.Next != nil && curNode.Next.Next != nil  {
         f := curNode
         s := curNode.Next
         t := curNode.Next.Next


         f.Next = t
         s.Next = t.Next
         t.Next = s 

         curNode = curNode.Next.Next
    }
    return dummyHead.Next

}
```
