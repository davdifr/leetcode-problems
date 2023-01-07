## Longest Substring Without Repeating Characters

Given a string `s`, find the length of the **longest** **substring** without repeating characters.

**Example 1:**

```
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

**Example 2:**

```
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```

**Example 3:**

```
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
```

 

**Constraints:**

- `0 <= s.length <= 5 * 10^4`
- `s` consists of English letters, digits, symbols and spaces.



## Solution

```js
var lengthOfLongestSubstring = function(s) {
    let sub = [];
    let max = 0;
    for (let i = 0; i < s.length;) {
        if (!sub.includes(s[i]))
            sub.push(s[i++]);
        else {
            if (max < sub.length) max = sub.length;
            sub.shift();
        }
    }
    return Math.max(max, sub.length);
};
```

