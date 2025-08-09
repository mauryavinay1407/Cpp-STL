# C++ `find()` vs `rfind()` -- Complete Guide

## 1. Introduction

`find()` and `rfind()` are member functions of `std::string` used for searching substrings within a string.

- **`find()`** → Searches **forward** from the given index
- **`rfind()`** → Searches **backward** starting from the given index

---

## 2. Syntax

### `find()`

```cpp
size_t find(const string& str, size_t pos = 0) const;
```

- **`str`** → substring to find
- **`pos`** → starting position for **forward search** (default: 0)
- Returns → the index of **first occurrence** at or after `pos`, or `string::npos` if not found

### `rfind()`

```cpp
size_t rfind(const string& str, size_t pos = string::npos) const;
```

- **`str`** → substring to find
- **`pos`** → starting position for **backward search** (default: `string::npos`)  
  It starts from `pos` and moves backward
- Returns → the index of **last occurrence** before or at `pos`, or `string::npos` if not found

---

## 3. Basic Examples

### Example -- `find()`

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string text = "abc abc abc";
    cout << text.find("abc") << endl;        // 0  (first "abc")
    cout << text.find("abc", 1) << endl;     // 4  (skip first char, finds at index 4)
}
```

### Example -- `rfind()`

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string text = "abc abc abc";
    cout << text.rfind("abc") << endl;       // 8  (last "abc")
    cout << text.rfind("abc", 7) << endl;    // 4  (last before index 7)
}
```

---

## 4. Comparison Table

| Function | Direction | Second Parameter Meaning | Example Output |
|----------|-----------|-------------------------|----------------|
| `find` | Forward | Start searching from this index | `"abc abc".find("abc", 1)` → `4` |
| `rfind` | Backward | Start searching backward from this index | `"abc abc abc".rfind("abc", 7)` → `4` |

---

## 5. Edge Cases

### 5.1 Substring Not Found

```cpp
string s = "hello";
cout << s.find("world") << endl;   // string::npos
cout << s.rfind("world") << endl;  // string::npos
```

### 5.2 Empty Substring

```cpp
string s = "hello";
cout << s.find("") << endl;        // 0
cout << s.find("", 2) << endl;     // 2
cout << s.rfind("") << endl;       // 5 (end of string)
cout << s.rfind("", 2) << endl;    // 2
```

### 5.3 Searching Whole String

```cpp
string s = "abc";
cout << s.find("abc") << endl;     // 0
cout << s.rfind("abc") << endl;    // 0
```

---

## 6. `starts_with` Equivalent Using `find()` / `rfind()`

C++20 introduced `.starts_with()` but in older versions:

```cpp
string s = "abcdef";
string prefix = "abc";

bool startsWith = (s.find(prefix) == 0);        // Using find()
bool startsWith2 = (s.rfind(prefix, 0) == 0);   // Using rfind()
```

---

## 7. User-Defined Versions

### Forward Search (`find`)

```cpp
int myFind(const string& text, const string& pattern, int start = 0) {
    for (int i = start; i <= (int)text.size() - (int)pattern.size(); i++) {
        if (text.substr(i, pattern.size()) == pattern) return i;
    }
    return -1; // Not found
}
```

### Backward Search (`rfind`)

```cpp
int myRFind(const string& text, const string& pattern, int start) {
    if (start > (int)text.size() - 1) start = text.size() - 1;
    for (int i = start; i >= 0; i--) {
        if (text.substr(i, pattern.size()) == pattern) return i;
    }
    return -1; // Not found
}
```

---

## 8. Visual Examples

### `find("abc", 2)`

```
Index:  0   1   2   3   4   5   6   7   8   9   10
Text:  [a] [b] [c] [ ] [a] [b] [c] [ ] [a] [b] [c]
                ^
                Start search here → finds at index 4
```

### `rfind("abc", 7)`

```
Index:  0   1   2   3   4   5   6   7   8   9   10
Text:  [a] [b] [c] [ ] [a] [b] [c] [ ] [a] [b] [c]
                        ^
                        Start backward search → finds at index 4
```

---

## 9. Summary

- **`find()`** → Forward search from `pos`
- **`rfind()`** → Backward search from `pos`
- If `pos` is omitted, defaults are:
  - `find()` → starts from index 0
  - `rfind()` → starts from the end of the string
- Use `.find(x) == 0` or `.rfind(x, 0) == 0` to check **prefix match**

---

## Key Takeaways

1. Both functions return `string::npos` when the substring is not found
2. `find()` searches left-to-right, `rfind()` searches right-to-left
3. The position parameter has different default values for each function
4. Both are useful for different search scenarios depending on whether you need the first or last occurrence
