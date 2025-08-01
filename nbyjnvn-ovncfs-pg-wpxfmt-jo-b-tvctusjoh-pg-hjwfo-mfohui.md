```ts
function maxVowels(s: string, k: number): number {
    let count = 0
    let maxCount = 0
    const vowels = ["a", "e", "i", "o", "u"]

    for (let i = 0; i < s.length; i++) {
        if (i < k) {
            if (vowels.includes(s[i])) {
                count += 1
                maxCount = count
            }
            continue
        }

        if (vowels.includes(s[i])) {
                count += 1
        }

        if (vowels.includes(s[i - k])) {
                count -= 1
        }

        if (count > maxCount) {
            maxCount = count
        }
    }

    return maxCount
};
```


1456. Maximum Number of Vowels in a Substring of Given Length

Given a string s and an integer k, return the maximum number of vowel letters in any substring of s with length k.

Vowel letters in English are 'a', 'e', 'i', 'o', and 'u'.

 

Example 1:

Input: s = "abciiidef", k = 3
Output: 3
Explanation: The substring "iii" contains 3 vowel letters.
Example 2:

Input: s = "aeiou", k = 2
Output: 2
Explanation: Any substring of length 2 contains 2 vowels.
Example 3:

Input: s = "leetcode", k = 3
Output: 2
Explanation: "lee", "eet" and "ode" contain 2 vowels.
 

Constraints:

1 <= s.length <= 105
s consists of lowercase English letters.
1 <= k <= s.length
