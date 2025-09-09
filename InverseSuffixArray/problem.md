## Title
**Inverse Suffix Array**

## Slug
inverse-suffix-array

## Difficulty
Medium

## Description
You are given the **suffix array** of a string, and your task is to reconstruct any valid string that corresponds to this suffix array.  

The suffix array of a string of length `n` is a permutation of numbers `1, 2, …, n` that represents the lexicographical order of the suffixes of the string.  

If multiple valid strings exist, you may output any of them.  
If no such string exists, output `-1`.

## Examples

### 1
#### Input

7

4 1 3 5 6 7 2

#### Output
aybabtu


#### Explanation
The suffixes of `"aybabtu"` in lexicographical order are:
- `abtu` (position 4)  
- `aybabtu` (position 1)  
- `babtu` (position 3)  
- `btu` (position 5)  
- `tu` (position 6)  
- `u` (position 7)  
- `ybabtu` (position 2)  

The given suffix array `[4, 1, 3, 5, 6, 7, 2]` matches this ordering.

## Input Format
- The first line contains an integer `n` — the length of the string.  
- The second line contains `n` integers — the suffix array of the string.

## Output Format
- Print any string of length `n` consisting of lowercase letters `a–z` that corresponds to the suffix array.  
- If no valid string exists, print `-1`.

## Constraints
- `1 ≤ n ≤ 10^5`

## Time Limit
1 second  

## Memory Limit
512 MB  

## Tags *(Internal Use Only)*
strings, suffix-array, inverse-problem, reconstruction