# Problem
Convert roman numbers to integers.

If you're not aware how roman numbers work, read through the [LeetCode problem](https://leetcode.com/problems/roman-to-integer/description/).

# Rationale

We have two base cases: one where the number doesn't have any "direction inversions", like `LI = 51`, and the result is simply summing up the two characters. The second base case is having a direction inversion, like `IX = 9`. We can break down all characters in a roman number string into pairs and treat each pair like our base case.

We'll map roman characters to numbers and process the list character by character. If the next number is smaller or equal than the current one (fallling into the "LI" case), we can just sum and move to the next character. If it's not (falling in the "IX" case), we'll take the difference and sum that instead. Note we're picking the smaller or equal check instead of the smaler check so repeated characters, like "II", are correctly processed. Assuming cases like "IIX" won't happen is intuitive from the problem definition.

Since we can just loop through the string, runtime complexity should be `O(n)`. Extra space is `O(1)` as well.