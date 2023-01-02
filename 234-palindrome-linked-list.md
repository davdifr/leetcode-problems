## Palindrome Linked List
Given the `head` of a singly linked list, return `true` *if it is a* *palindrome* *or* `false` *otherwise*.



 

**Example 1:**

![img](https://assets.leetcode.com/uploads/2021/03/03/pal1linked-list.jpg)

```
Input: head = [1,2,2,1]
Output: true
```

**Example 2:**

![img](https://assets.leetcode.com/uploads/2021/03/03/pal2linked-list.jpg)

```
Input: head = [1,2]
Output: false
```

 

**Constraints:**

- The number of nodes in the list is in the range `[1, 105]`.
- `0 <= Node.val <= 9`

 

**Follow up:** Could you do it in `O(n)` time and `O(1)` space?



## Solution

```js
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {boolean}
 */

 const isPalindrome = head => {
    let seq = '';
    while (head) {
        seq += head.val;
        head = head.next;
    }
    const middle = Math.floor(seq.length / 2);
    const l = seq.length - 1;

    for (let i = 0; i < middle; i++)
        if (seq[i] != seq[l - i])
            return false;
    return true;
};
```