Multimap
---

A `multimap` is an associative container that stores key-value pairs. Unlike a `map`, a `multimap` allows multiple values to be associated with a single key. The elements are stored in sorted order based on the key.

### Important Functions

-   **Insertion:**
```c++
   multimap<int, string> mm;
    mm.insert({1, "one"});       // Inserts a key-value pair (1, "one")
    mm.insert({1, "uno"});       // Inserts another key-value pair with the same key (1, "uno")
```
<br>

-   **Erasure:**
```c++
    mm.erase(1);                // Removes all key-value pairs with key 1
    mm.erase(mm.find(1));       // Removes a single key-value pair with key 1 (if there are multiple, only the first is removed)
```
<br>

-   **Find:**
```c++
   auto range = mm.equal_range(1);  // Returns a pair of iterators to the range of key-value pairs with key 1
    for (auto it = range.first; it != range.second; ++it) {
        cout << it->second << " ";  // Prints all values associated with key 1
    }
```
<br>

-   **Iteration:**
```c++
   for (const auto& kv : mm) {
        cout << kv.first << ": " << kv.second << endl;  // Prints all key-value pairs
    }
```
<br>

-   **Count:**
```c++
 size_t count = mm.count(1);  // Returns the number of key-value pairs with key 1`
```
<br>

-   **Find Specific Key:**
```c++
  auto it = mm.find(1);       // Finds an iterator to the first key-value pair with key 1
    if (it != mm.end()) {
        cout << it->second << endl;  // Prints the value associated with key 1
    }
```
<br>

### Properties

-   **Allow Duplicates:** Multiple values can be associated with a single key.
-   **Sorted by Key:** Elements are stored in ascending order based on the key.
-   **Associative:** Provides O(log n) time complexity for insertion, deletion, and search operations.