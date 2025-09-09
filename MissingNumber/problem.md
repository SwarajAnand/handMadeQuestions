## Title
The Lost Page in the Ancient Scroll  

## Slug
missing-number  

## Difficulty
Easy  

## Description
An ancient scroll contains `n` magical numbers inscribed in sequence, from `1` to `n`.  
However, during its long journey through kingdoms and battles, **one number vanished from the scroll**.  

Your task is to help the archivists recover the **missing number** by analyzing the remaining sequence of `n - 1` numbers.  

## Examples  

### 1  
#### Input  
5  
2 3 1 5  

#### Output  
4  

#### Explanation  
The numbers should be `1, 2, 3, 4, 5`.  
From the given input, `{2, 3, 1, 5}` are present, which means `4` is missing.  

### 2  
#### Input  
4  
2 1 4  

#### Output  
3  

#### Explanation  
The complete sequence is `1, 2, 3, 4`.  
Here we are missing the number `3`.  

## Input Format  
1. The first input line contains an integer `n` — the total count of numbers that should appear on the scroll.  
2. The second line contains `n - 1` integers, all distinct, each between `1` and `n`.  

## Output Format  
Print the missing number.  

## Constraints  
- `2 ≤ n ≤ 2 * 10^5`  

## Time Limit  
1 second  

## Memory Limit  
512 MB  

## Tags  
`math` `implementation` `prefix-sum`  