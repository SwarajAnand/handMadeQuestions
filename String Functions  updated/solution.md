## CPP

### SOLUTION

vector<int> z_function(const string &s) {
    int n = s.size();
    vector<int> z(n);
    int l = 0, r = 0;
    for (int i = 1; i < n; i++) {
        if (i <= r) z[i] = min(r - i + 1, z[i - l]);
        while (i + z[i] < n && s[z[i]] == s[i + z[i]]) z[i]++;
        if (i + z[i] - 1 > r) l = i, r = i + z[i] - 1;
    }
    z[0] = 0;
    return z;
}

vector<int> prefix_function(const string &s) {
    int n = s.size();
    vector<int> pi(n);
    for (int i = 1; i < n; i++) {
        int j = pi[i - 1];
        while (j > 0 && s[i] != s[j]) j = pi[j - 1];
        if (s[i] == s[j]) j++;
        pi[i] = j;
    }
    return pi;
}
### METADATA
**TimeLimit**
1000

**MemoryLimit**
524288


## JAVA

### SOLUTION

static int[] zFunction(String s) {
    int n = s.length();
    int[] z = new int[n];
    int l = 0, r = 0;
    for (int i = 1; i < n; i++) {
        if (i <= r) z[i] = Math.min(r - i + 1, z[i - l]);
        while (i + z[i] < n && s.charAt(z[i]) == s.charAt(i + z[i])) z[i]++;
        if (i + z[i] - 1 > r) { l = i; r = i + z[i] - 1; }
    }
    z[0] = 0;
    return z;
}

static int[] prefixFunction(String s) {
    int n = s.length();
    int[] pi = new int[n];
    for (int i = 1; i < n; i++) {
        int j = pi[i - 1];
        while (j > 0 && s.charAt(i) != s.charAt(j)) j = pi[j - 1];
        if (s.charAt(i) == s.charAt(j)) j++;
        pi[i] = j;
    }
    return pi;
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
524288

## C

### SOLUTION

int* z_function(const char *s, int n) {
    int* z = (int*)malloc(n * sizeof(int));
    int l = 0, r = 0;
    z[0] = 0;
    for (int i = 1; i < n; i++) {
        if (i <= r) 
            z[i] = (r - i + 1 < z[i - l]) ? (r - i + 1) : z[i - l];
        else 
            z[i] = 0;
        while (i + z[i] < n && s[z[i]] == s[i + z[i]]) 
            z[i]++;
        if (i + z[i] - 1 > r) { 
            l = i; 
            r = i + z[i] - 1; 
        }
    }
    return z;
}

int* prefix_function(const char *s, int n) {
    int* pi = (int*)malloc(n * sizeof(int));
    pi[0] = 0;
    for (int i = 1; i < n; i++) {
        int j = pi[i - 1];
        while (j > 0 && s[i] != s[j]) 
            j = pi[j - 1];
        if (s[i] == s[j]) 
            j++;
        pi[i] = j;
    }
    return pi;
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
524288

## JAVASCRIPT

### SOLUTION
function zFunction(s) {
    const n = s.length;
    const z = new Array(n).fill(0);
    let l = 0, r = 0;
    for (let i = 1; i < n; i++) {
        if (i <= r) z[i] = Math.min(r - i + 1, z[i - l]);
        while (i + z[i] < n && s[z[i]] === s[i + z[i]]) z[i]++;
        if (i + z[i] - 1 > r) { l = i; r = i + z[i] - 1; }
    }
    z[0] = 0;
    return z;
}

function prefixFunction(s) {
    const n = s.length;
    const pi = new Array(n).fill(0);
    for (let i = 1; i < n; i++) {
        let j = pi[i - 1];
        while (j > 0 && s[i] !== s[j]) j = pi[j - 1];
        if (s[i] === s[j]) j++;
        pi[i] = j;
    }
    return pi;
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
524288

## python

### SOLUTION

def z_function(s):
    n = len(s)
    z = [0] * n
    l, r = 0, 0
    for i in range(1, n):
        if i <= r:
            z[i] = min(r - i + 1, z[i - l])
        while i + z[i] < n and s[z[i]] == s[i + z[i]]:
            z[i] += 1
        if i + z[i] - 1 > r:
            l, r = i, i + z[i] - 1
    z[0] = 0
    return z

def prefix_function(s):
    n = len(s)
    pi = [0] * n
    for i in range(1, n):
        j = pi[i - 1]
        while j > 0 and s[i] != s[j]:
            j = pi[j - 1]
        if s[i] == s[j]:
            j += 1
        pi[i] = j
    return pi

### METADATA
**TimeLimit**
1000

**MemoryLimit**
524288

---