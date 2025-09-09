## CPP

/*
Solution for CPP
*/
int findMissingNumber(int n, const vector<int>& nums) {
    long long expectedSum = 1LL * n * (n + 1) / 2;
    long long actualSum = 0;
    for (int x : nums) actualSum += x;
    return (int)(expectedSum - actualSum);
}


## JAVA

/*
Solution for JAVA
*/
public int findMissingNumber(int n, int[] nums) {
    long expectedSum = 1L * n * (n + 1) / 2;
    long actualSum = 0;
    for (int x : nums) {
        actualSum += x;
    }
    return (int)(expectedSum - actualSum);
}


## C

/*
Solution for C
*/
int findMissingNumber(int n, int nums[], int size) {
    long long expectedSum = 1LL * n * (n + 1) / 2;
    long long actualSum = 0;
    for (int i = 0; i < size; i++) {
        actualSum += nums[i];
    }
    return (int)(expectedSum - actualSum);
}


## JAVASCRIPT

/*
Solution for Javascript
*/
function findMissingNumber(n, nums) {
    let expectedSum = n * (n + 1) / 2;
    let actualSum = nums.reduce((a, b) => a + b, 0);
    return expectedSum - actualSum;
}


## python

"""
Solution for Python
"""
def findMissingNumber(n, nums):
    expected_sum = n * (n + 1) // 2
    actual_sum = sum(nums)
    return expected_sum - actual_sum