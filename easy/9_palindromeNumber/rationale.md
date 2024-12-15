# Problem
Given a number, check if it is a palindrome.

Examples: 121 is a palindrome, -121 is not (as the palindrome format becomes 121-).

LeetCode link: https://leetcode.com/problems/palindrome-number

# Intuition
## 1st idea - treating numbers as strings
Theoretically, we could just convert the numbers to strings and check, from 0 to i, if `str[i] = str[str.size - i - 1]` - this falls back to a standard palindrome string case. 

There certainly is a way to do this without converting ints to strings, not sure if it avoids the `O(n)` complexity though.

## 2nd idea - modulo equivalent
If you think of it, comparing the 1st and the last digit of a number is equivalent to testing if `n % 10^(i)` equals `n % 10^(digits - i)`, where `digits = 10 % i`.

Reversing the number is probably faster than testing these though, as we don't need to calculate `pow(10, x)` multiple times - then we can just compare the reversed number with the number itself.

Reversing a number is simply getting each of its digits, from right to left, and summing them into a result. You can get the last digit for a number `n` by taking it modulo 10 - `n % 10`.

The issue with this approach, in LeetCode, is I'm falling into some overflow issues when testing edge cases where the reversed number falls outside the integer range. Wondering how I could fix this?