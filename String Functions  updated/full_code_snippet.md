## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    ios::sync_with_stdio(false);
    cin.tie(NULL);

    string s;
    cin >> s;

    vector<int> z = z_function(s);
    vector<int> pi = prefix_function(s);

    for (int i = 0; i < (int)z.size(); i++) {
        cout << z[i] << (i + 1 == (int)z.size() ? '\n' : ' ');
    }
    for (int i = 0; i < (int)pi.size(); i++) {
        cout << pi[i] << (i + 1 == (int)pi.size() ? '\n' : ' ');
    }

    return 0;
}

## JAVA

import java.util.*;

public class Main {

    // user code comes here

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.next();
        sc.close();

        int[] z = zFunction(s);
        int[] pi = prefixFunction(s);

        for (int i = 0; i < z.length; i++) {
            System.out.print(z[i]);
            if (i < z.length - 1) System.out.print(" ");
        }
        System.out.println();

        for (int i = 0; i < pi.length; i++) {
            System.out.print(pi[i]);
            if (i < pi.length - 1) System.out.print(" ");
        }
        System.out.println();
    }
}

## C

#include <stdio.h>
#include <string.h>
#include <stdlib.h>

// user code comes here
int main() {
    char s[1000005];
    scanf("%s", s);
    int n = strlen(s);

    int* z = z_function(s, n);
    int* pi = prefix_function(s, n);

    for (int i = 0; i < n; i++) {
        printf("%d", z[i]);
        if (i < n - 1) printf(" ");
    }
    printf("\n");

    for (int i = 0; i < n; i++) {
        printf("%d", pi[i]);
        if (i < n - 1) printf(" ");
    }
    printf("\n");

    free(z);
    free(pi);
    return 0;
}

## JAVASCRIPT

'use strict';

// user code comes here

const fs = require('fs');

function main() {
    const input = fs.readFileSync(0, 'utf-8').trim().split(/\s+/);
    const s = input[0];

    const z = zFunction(s);
    const pi = prefixFunction(s);

    console.log(z.join(" "));
    console.log(pi.join(" "));
}

main();

## python

import sys

# user code comes here

if __name__ == "__main__":
    s = sys.stdin.readline().strip()

    z = z_function(s)
    pi = prefix_function(s)

    print(" ".join(map(str, z)))
    print(" ".join(map(str, pi)))