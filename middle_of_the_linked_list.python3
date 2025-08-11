# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        
        cnt = 0
        s = []
        current = head

        while current is not None:
            current = current.next
            cnt += 1
        
        mid = cnt//2

        while mid:
            head = head.next
            mid -= 1

        return head
        