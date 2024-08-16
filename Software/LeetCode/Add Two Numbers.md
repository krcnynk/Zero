1st
```c
class Solution {
 public:
  ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
    if (l1 == nullptr && l2 == nullptr) {
      return nullptr;
    }

    auto remainderCheck = [](ListNode* l1, ListNode* l2, int c) {
      return (l1->val + l2->val + c) % 10;
    };  // at most 8
    auto carryCheck = [](ListNode* l1, ListNode* l2, int c) {
      return (l1->val + l2->val + c) >= 10 ? 1 : 0;
    };  // at most 1
    int outgoingCarry = 0;
    int remain;
    ListNode zero = ListNode();
    ListNode* ll = nullptr;
    int count = -1;
    while (l1 != nullptr || l2 != nullptr || outgoingCarry == 1) {
      if (l1 == nullptr) l1 = &zero;
      if (l2 == nullptr) l2 = &zero;
      remain = remainderCheck(l1, l2, outgoingCarry);
      outgoingCarry = carryCheck(l1, l2, outgoingCarry);
      if (count < 0) {
        ll = new ListNode(remain);
        head = ll;
        count = 0;
      } else {
        ll->next = new ListNode(remain);
        ll = ll->next;
      }
      l1 = l1->next;
      l2 = l2->next;
    }

    return head;
  }

 private:
  ListNode* head;
};
```