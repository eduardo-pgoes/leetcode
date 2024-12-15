# The problem
Given a list `v` of integers, return the indices of the two numbers in the list whose sum hit a specific target (assuming they always exist).

LeetCode link: https://leetcode.com/problems/two-sum

# The ideas
## Low memory complecityy - Brute-forcing
`O(n^2)` runtime, just loop through 0 to j items for each `v[i]` and check if the sum `v[i] + v[j]` hits the target. `O(n)` memory complexity.

Improving runtime:

## Low runtime complexity - hashmap
Since we don't care about the order, we could:
- Add each number to a  `{ number: index }` map
- Check if, for `v[i]`, `target - v[i]` exists in the map - let's call that map entry `e`
  - If there is, return `[i, e[target - v[i]]]`