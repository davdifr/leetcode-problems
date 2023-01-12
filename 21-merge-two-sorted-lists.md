## Merge Two Sorted Lists

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists in a one **sorted** list. The list should be made by splicing together the nodes of the first two lists.

Return *the head of the merged linked list*.

 

**Example 1:**

![img](https://assets.leetcode.com/uploads/2020/10/03/merge_ex1.jpg)



```
Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]
```

**Example 2:**

```
Input: list1 = [], list2 = []
Output: []
```

**Example 3:**

```
Input: list1 = [], list2 = [0]
Output: [0]
```

 

**Constraints:**

- The number of nodes in both lists is in the range `[0, 50]`.
- `-100 <= Node.val <= 100`
- Both `list1` and `list2` are sorted in **non-decreasing** order.



## Solution

```js
var mergeTwoLists = function(list1, list2) {
    if (!list1 && !list2) return null;

    if (!list1) return list2;
    if (!list2) return list1;

    let list3 = new ListNode(0);
    let l1 = list1, l2 = list2, l3 = list3;

    while (l1 && l2) {
        if (l1.val <= l2.val) {
            l3.next = new ListNode(l1.val);
            l1 = l1.next;
        } else {
            l3.next = new ListNode(l2.val);
            l2 = l2.next;
        }
        l3 = l3.next;
    }
    if(l1) l3.next = l1
    if(l2) l3.next = l2

    return list3.next;
};
```

## Score

![merge-two-sorted-lists](assets/merge-two-sorted-lists.png)
