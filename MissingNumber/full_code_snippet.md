## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    ios::sync_with_stdio(false);
    cin.tie(NULL);

    int n;
    cin >> n;
    vector<int> nums(n - 1);
    for (int i = 0; i < n - 1; i++) {
        cin >> nums[i];
    }

    int result = findMissingNumber(n, nums);
    cout << result << "\n";

    return 0;
}


## JAVA

import java.util.*;

public class Main {

    // user code comes here

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int[] nums = new int[n - 1];
        for (int i = 0; i < n - 1; i++) {
            nums[i] = sc.nextInt();
        }

        int result = new Main().findMissingNumber(n, nums);
        System.out.println(result);
    }
}


## C

#include <stdio.h>

// user code comes here

int main() {
    int n;
    scanf("%d", &n);

    int nums[n - 1];
    for (int i = 0; i < n - 1; i++) {
        scanf("%d", &nums[i]);
    }

    int result = findMissingNumber(n, nums, n - 1);
    printf("%d\n", result);

    return 0;
}


## JAVASCRIPT

'use strict';

// user code comes here

const fs = require('fs');
const input = fs.readFileSync(0, 'utf-8').trim().split(/\s+/);

let n = parseInt(input[0]);
let nums = input.slice(1).map(Number);

let result = findMissingNumber(n, nums);
console.log(result);


## python

# user code comes here

import sys

data = sys.stdin.read().strip().split()
n = int(data[0])
nums = list(map(int, data[1:]))

result = findMissingNumber(n, nums)
print(result)