## CPP

### SOLUTION

    string inverseSuffixArray(int n, vector<int>& suffixArray) {
        // convert to 0-based
        for (int i = 0; i < n; i++) sa[i]--;

        // compute rank array
        vector<int> rank(n);
        for (int i = 0; i < n; i++) {
            rank[sa[i]] = i;
        }

        string s(n, '?');
        char current = 'a';
        s[sa[0]] = current;

        for (int i = 1; i < n; i++) {
            int prev = sa[i - 1], cur = sa[i];

            // Compare suffixes at prev and cur
            if (prev + 1 < n && cur + 1 < n) {
                if (rank[prev + 1] > rank[cur + 1]) {
                    current++;
                    if (current > 'z') return "-1";
                }
            } else {
                // One suffix ends → must increase character
                current++;
                if (current > 'z') return "-1";
            }

            s[cur] = current;
        }

        return s;
    }

### METADATA

**TimeLimit**

2000

**MemoryLimit**

128


## JAVA

### SOLUTION

    String inverseSuffixArray(int n, int[] suffixArray) {
        // convert to 0-based
        for (int i = 0; i < n; i++) sa[i]--;

        // compute rank array
        int[] rank = new int[n];
        for (int i = 0; i < n; i++) {
            rank[sa[i]] = i;
        }

        char[] s = new char[n];
        char current = 'a';
        s[sa[0]] = current;

        for (int i = 1; i < n; i++) {
            int prev = sa[i - 1], cur = sa[i];

            // Compare suffixes at prev and cur
            if (prev + 1 < n && cur + 1 < n) {
                if (rank[prev + 1] > rank[cur + 1]) {
                    current++;
                    if (current > 'z') return "-1";
                }
            } else {
                // One suffix ends → must increase character
                current++;
                if (current > 'z') return "-1";
            }

            s[cur] = current;
        }

        return new String(s);
    }

### METADATA

**TimeLimit**

2000

**MemoryLimit**

128


## C

### SOLUTION

    char* inverseSuffixArray(int n, int* suffixArray) {
        // convert to 0-based
        for (int i = 0; i < n; i++) sa[i]--;

        // compute rank array
        int* rank = (int*)malloc(n * sizeof(int));
        for (int i = 0; i < n; i++) {
            rank[sa[i]] = i;
        }

        char* s = (char*)malloc((n + 1) * sizeof(char));
        char current = 'a';
        for (int i = 0; i < n; i++) s[i] = '?';
        s[n] = '\0';

        s[sa[0]] = current;

        for (int i = 1; i < n; i++) {
            int prev = sa[i - 1], cur = sa[i];

            // Compare suffixes at prev and cur
            if (prev + 1 < n && cur + 1 < n) {
                if (rank[prev + 1] > rank[cur + 1]) {
                    current++;
                    if (current > 'z') {
                        free(rank);
                        free(s);
                        return "-1";
                    }
                }
            } else {
                current++;
                if (current > 'z') {
                    free(rank);
                    free(s);
                    return "-1";
                }
            }

            s[cur] = current;
        }

        free(rank);
        return s;
    }

### METADATA

**TimeLimit**

2000

**MemoryLimit**

128


## PYTHON

### SOLUTION

    def inverse_suffix_array(n: int, suffixArray: list[int]) -> str:
        # convert to 0-based
        sa = [x - 1 for x in sa]

        # compute rank array
        rank = [0] * n
        for i in range(n):
            rank[sa[i]] = i

        s = ['?'] * n
        current = 'a'
        s[sa[0]] = current

        for i in range(1, n):
            prev, cur = sa[i - 1], sa[i]

            if prev + 1 < n and cur + 1 < n:
                if rank[prev + 1] > rank[cur + 1]:
                    current = chr(ord(current) + 1)
                    if current > 'z':
                        return "-1"
            else:
                current = chr(ord(current) + 1)
                if current > 'z':
                    return "-1"

            s[cur] = current

        return "".join(s)

### METADATA

**TimeLimit**

2000

**MemoryLimit**

128


## JAVASCRIPT

### SOLUTION

    function inverseSuffixArray(n, suffixArray) {
        // convert to 0-based
        for (let i = 0; i < n; i++) sa[i]--;

        // compute rank array
        let rank = new Array(n);
        for (let i = 0; i < n; i++) {
            rank[sa[i]] = i;
        }

        let s = new Array(n).fill('?');
        let current = 'a';
        s[sa[0]] = current;

        for (let i = 1; i < n; i++) {
            let prev = sa[i - 1], cur = sa[i];

            if (prev + 1 < n && cur + 1 < n) {
                if (rank[prev + 1] > rank[cur + 1]) {
                    current = String.fromCharCode(current.charCodeAt(0) + 1);
                    if (current > 'z') return "-1";
                }
            } else {
                current = String.fromCharCode(current.charCodeAt(0) + 1);
                if (current > 'z') return "-1";
            }

            s[cur] = current;
        }

        return s.join('');
    }

### METADATA

**TimeLimit**

2000

**MemoryLimit**

128
