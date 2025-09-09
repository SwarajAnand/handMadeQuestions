## CPP

    #include <bits/stdc++.h>
    using namespace std;

    // user code comes here

    int main() {
    string s;
    cin >> s;

    vector<int> counts = countDistinctSubstrings(s);
    for (int i = 0; i < counts.size(); i++) {
        if (i > 0) cout << " ";
        cout << counts[i];
    }
    return 0;
}

## JAVA

    import java.util.*;

    // user code comes here

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.next();   // read input string
        sc.close();

        int[] counts = countDistinctSubstrings(s);

        for (int i = 0; i < counts.length; i++) {
            if (i > 0) System.out.print(" ");
            System.out.print(counts[i]);
        }
    }


## C

    #include <stdio.h>
    #include <string.h>
    #include <stdlib.h>
    #include <stdbool.h>

    // user code comes here

    int main() {
        char s[100005];
        scanf("%s", s);

        int n;
        int* counts = countDistinctSubstrings(s, &n);

        for (int i = 0; i < n; i++) {
            if (i > 0) printf(" ");
            printf("%d", counts[i]);
        }
        free(counts);
        return 0;
    }

## PYTHON

    import sys

    // user code comes here

    if __name__ == "__main__":
        s = input().strip()
        counts = count_distinct_substrings(s)
        print(" ".join(map(str, counts)))


## JAVASCRIPT

    const fs = require("fs");
    const input = fs.readFileSync(0, "utf-8").trim(); 

    // user code comes here

    let counts = countDistinctSubstrings(input);
    console.log(counts.join(" "));