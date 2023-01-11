## Valid Parentheses

Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
3. Every close bracket has a corresponding open bracket of the same type.

 

**Example 1:**

```
Input: s = "()"
Output: true
```

**Example 2:**

```
Input: s = "()[]{}"
Output: true
```

**Example 3:**

```
Input: s = "(]"
Output: false
```

 

**Constraints:**

- `1 <= s.length <= 10^4`
- `s` consists of parentheses only `'()[]{}'`.



## Solution

```js
var isValid = function(s) {
    if (s.length === 0 || s.length % 2 !== 0) return false;

    const par = {
        "(": 1,
        ")": -1,
        "[": 2,
        "]": -2,
        "{": 3,
        "}": -3
    };

    let stack = [0];
    let curr = 0;

    for (let i = 0; i < s.length; i++) {
        curr = par[s[i]];
        if (curr > 0) stack.push(curr);
        else if (curr + stack.at(-1) === 0) stack.pop();
        else return false 
    }
    
    return stack.length === 1;
};
```



## Score

![valid-parentheses](assets/valid-parentheses.png)