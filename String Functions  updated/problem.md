## Title
Codebreaker's String Puzzle

## Slug
codebreakers-string-puzzle

## Difficulty
Medium

## Description
Deep within the archives of an ancient guild, you discover encrypted scrolls filled with mysterious strings. To unlock their secrets, you must analyze the structure of each string using two powerful functions:

- **Z-function (z(i))**: the maximum length of a substring starting at position i that also matches the prefix of the string. For consistency, z(1) = 0.
- **Prefix-function (π(i))**: the maximum length of a substring ending at position i that matches a prefix of the string, with length at most i - 1.

These functions are crucial in modern string algorithms like **Z-algorithm** and **Knuth–Morris–Pratt (KMP)**, used by codebreakers to find repeating patterns and unlock hidden meanings.

Your task is to compute both functions for the given string.

## Examples

### 1
#### Input
abaabca

#### Output
0 0 1 2 0 0 1
0 0 1 1 2 0 1

#### Explanation
*Z-function (z(i))*

*Rule: z(i) = length of longest substring starting at position i that also matches the prefix.*
*By definition, z(1) = 0.*
	*•	i = 1 → z(1) = 0 (always).*
	*•	i = 2 → substring "baabca" vs prefix "abaabca" → first chars don’t match → z(2) = 0.*
	*•	i = 3 → substring "aabca" vs prefix "abaabca" → match = "a" → length 1 → z(3) = 1.*
	*•	i = 4 → substring "abca" vs prefix "abaabca" → match = "ab" → length 2 → z(4) = 2.*
	*•	i = 5 → substring "bca" vs prefix "abaabca" → mismatch immediately → z(5) = 0.*
	*•	i = 6 → substring "ca" vs prefix "abaabca" → mismatch immediately → z(6) = 0.*
	*•	i = 7 → substring "a" vs prefix "abaabca" → match = "a" → length 1 → z(7) = 1.*
*so Z = 0 0 1 2 0 0 1*

⸻

*Prefix-function (π(i))*

*Rule: π(i) = length of the longest prefix which is also a suffix for substring s[1..i].*
	*•	i = 1 (“a”) → no proper prefix-suffix → π(1) = 0.*
	*•	i = 2 (“ab”) → no border → π(2) = 0.*
	*•	i = 3 (“aba”) → prefix "a" = suffix "a" → π(3) = 1.*
	*•	i = 4 (“abaa”) → prefix "a" = suffix "a" → π(4) = 1.*
	*•	i = 5 (“abaab”) → prefix "ab" = suffix "ab" → π(5) = 2.*
	*•	i = 6 (“abaabc”) → no prefix = suffix → π(6) = 0.*
	*•	i = 7 (“abaabca”) → prefix "a" = suffix "a" → π(7) = 1.*

*So: π = 0 0 1 1 2 0 1*

## Input Format
- A single line containing a string s of length n.
- Each character is a lowercase English letter (a–z).

## Output Format
- Print two lines:
  - First line → values of the **Z-function**.
  - Second line → values of the **Prefix-function**.
- Values should be space-separated.

## Constraints
- 1 ≤ n ≤ 10^6
- Characters of the string are in the range a–z.

## Time Limit
1 second

## Memory Limit
256 MB

## Tags
strings, z-algorithm, kmp