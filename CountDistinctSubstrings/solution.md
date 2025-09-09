## CPP

### SOLUTION

    vector<int> countDistinctSubstrings(string s) {
        int n = s.size();
        unordered_set<string> substrings;
        for (int i = 0; i < n; i++) {
            string temp = "";
            for (int j = i; j < n; j++) {
                temp += s[j];
                substrings.insert(temp);
            }
        }
        vector<int> counts(n, 0);
        for (auto &sub : substrings) {
            counts[sub.size() - 1]++;
        }
        return counts;
    }

### METADATA

**TimeLimit**

2000

**MemoryLimit**

128

## JAVA

### SOLUTION

    static Set<String> distinctSubstrings(String s) {
        int n = s.length();
        Set<String> substrings = new HashSet<>();

        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j <= n; j++) {
                substrings.add(s.substring(i, j));
            }
        }
        return substrings;
    }

    static int[] countDistinctSubstrings(String s) {
        Set<String> substrings = distinctSubstrings(s);
        int[] counts = new int[s.length()];

        for (String substring : substrings) {
            counts[substring.length() - 1]++;
        }
        return counts;
    }


### METADATA

**TimeLimit**

2000

**MemoryLimit**

128

## C

### SOLUTION

    int* countDistinctSubstrings(char* s, int* returnSize) {
        int n = strlen(s);
        *returnSize = n;
        bool* seen = calloc(n * (n + 1) / 2, sizeof(bool)); // placeholder for uniqueness
        int* counts = calloc(n, sizeof(int));

        // naive substring comparison
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j <= n; j++) {
                // generate substring hash
                unsigned long hash = 0;
                for (int k = i; k < j; k++) {
                    hash = hash * 131 + s[k];
                }
                int idx = hash % (n * (n + 1) / 2);
                if (!seen[idx]) {
                    seen[idx] = true;
                    counts[j - i - 1]++;
                }
            }
        }
        free(seen);
        return counts;
    }


### METADATA

**TimeLimit**

2000

**MemoryLimit**

128

## JAVASCRIPT

### SOLUTION

    function countDistinctSubstrings(s) {
        let n = s.length;
        let substrings = new Set();

        for (let i = 0; i < n; i++) {
            let temp = "";
            for (let j = i; j < n; j++) {
                temp += s[j];
                substrings.add(temp);
            }
        }

        let counts = Array(n).fill(0);
        for (let sub of substrings) {
            counts[sub.length - 1]++;
        }
        return counts;
    }


### METADATA

**TimeLimit**

2000

**MemoryLimit**

128

## PYTHON

### SOLUTION

    def count_distinct_substrings(s: str) -> list[int]:
        n = len(s)
        substrings = set()

        for i in range(n):
            for j in range(i + 1, n + 1):
                substrings.add(s[i:j])

        counts = [0] * n
        for sub in substrings:
            counts[len(sub) - 1] += 1
        return counts



### METADATA

**TimeLimit**

2000

**MemoryLimit**

128