# Problem
Given an array of strings, find the longest prefix found among them.

https://leetcode.com/problems/longest-common-prefix/

# Idea
## First idea that comes to mind - bruteforcing
First we find the smallest string in the array in `O(n)` time (n = array length, not string length). Let's call the smallest string length `s`.

We loop through the strings in the array in `i = [0, s]` and look to characters in the i-th position for `j = [0, n]`. If we don't find any deviant, we add the character in the i-th to the prefix. If we find a deviant, we return the prefix.

This can hit `O(n^2)` in the worst possible case, but I can't think of any better alternative - also, this probably hits `O(n log n)` consistently as it jumps out of the loop at every possible opportunity.