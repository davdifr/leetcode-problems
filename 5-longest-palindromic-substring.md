## Longest Palindromic Substring

Given a string `s`, return *the longest*  *palindromic* *substring* in `s`.

**Example 1:**

```
Input: s = "babad"
Output: "bab"
Explanation: "aba" is also a valid answer.
```

**Example 2:**

```
Input: s = "cbbd"
Output: "bb"
```

 

**Constraints:**

- `1 <= s.length <= 1000`
- `s` consist of only digits and English letters.



## Solution

```js
const isPalindrome = (s) => {
  const middle = Math.floor(s.length / 2);
  const last = s.length - 1;

  for (let i = 0; i < middle; i++) {
    if (s[i] !== s[last - i]) return false;
  }
  return s;
};

const longestPalindrome = (s) => {
  let length = s.length;
  let substring;

  const genSubstring = (start, end) => s.slice(start, end);

  for (let i = length; i >= 1; i--) {
    for (let j = 0; j <= length - i; j++) {
      substring = genSubstring(j, j + i);
      if (isPalindrome(substring)) return substring;
    }
  }
  return s[0] || "";
};
```

