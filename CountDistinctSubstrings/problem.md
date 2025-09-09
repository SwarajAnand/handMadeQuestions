## Title
**Substring Distribution**

## Slug
substring-distribution

## Difficulty
Hard

## Description
You are given a string of length `n`. For every integer `1 … n`, you need to determine the number of **distinct substrings** of that exact length.  

Efficient suffix-based techniques such as **suffix automaton** or **suffix array with LCP (Longest Common Prefix)** are typically required to solve this problem within the given constraints.

## Examples

### 1
#### Input
abab

#### Output
2 2 2 1


#### Explanation
The distinct substrings are:  
- Length 1 → `a, b` → 2  
- Length 2 → `ab, ba` → 2  
- Length 3 → `aba, bab` → 2  
- Length 4 → `abab` → 1  

So the output is `2 2 2 1`.

## Input Format
- The only input line contains a string `s` of length `n` consisting of lowercase letters `a–z`.

## Output Format
- Print `n` integers, where the `i`-th integer is the number of distinct substrings of length `i`.

## Constraints
- `1 ≤ n ≤ 10^5`

## Time Limit
1 second  

## Memory Limit
512 MB  

## Tags *(Internal Use Only)*
strings, suffix-array, suffix-automaton, distinct-substrings