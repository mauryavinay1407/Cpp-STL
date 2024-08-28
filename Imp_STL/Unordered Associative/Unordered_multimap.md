Unordered Multimap
---

An `unordered_multimap` is an unordered collection of key-value pairs where multiple values can be associated with the same key. It uses a hash table for storing elements, providing average O(1) time complexity for insertions and lookups.

### Important Functions

-   **Initialization:**
```c++
    unordered_multimap<int, string> umm;           // Default initialization (empty unordered multimap)
    unordered_multimap<int, string> umm2 = {{1, "one"}, {2, "two"}, {2, "deux"}}; // Initializes an unordered multimap with key-value pairs
```
<br>

-   **Insertion:**
```c++
    umm.insert({1, "one"});        // Inserts a key-value pair (1, "one") into the unordered multimap
    umm.insert({2, "two"});        // Inserts a key-value pair (2, "two")
    umm.insert({2, "deux"});       // Inserts another key-value pair with key 2 (duplicates allowed)
```
<br>

-   **Erasure:**
```c++
   umm.erase(2);                  // Removes all key-value pairs with key 2 from the unordered multimap
    umm.erase(1);                  // Removes all key-value pairs with key 1
```
<br>

-   **Find:**
```c++
 auto range = umm.equal_range(2);  // Returns a pair of iterators to the range of elements with key 2
    for (auto it = range.first; it != range.second; ++it) {
        cout << it->second << " ";    // Prints all values associated with key 2
    }
```
<br>

-   **Count:**
```c++
   size_t count = umm.count(2);      // Returns the number of key-value pairs with key 2
    cout << "Number of pairs with key 2: " << count << endl;
```
<br>

-   **Iteration:**
```c++
 for (auto it = umm.begin(); it != umm.end(); ++it) {
        cout << it->first << ": " << it->second << endl;  // Prints all key-value pairs
    }
```
<br>

-   **Size:**
```c++
 size_t size = umm.size();         // Returns the number of key-value pairs in the unordered multimap
```
<br>

-   **Clear:**
```c++
 umm.clear();                      // Removes all key-value pairs from the unordered multimap
```
<br>

### Properties

-   **Unordered:** Key-value pairs are not stored in any particular order.
-   **Allow Duplicates:** Multiple values can be associated with the same key.
-   **Hash Table:** Implemented using a hash table, providing average O(1) time complexity for insertions, deletions, and lookups.
-   **Efficient Lookup:** Provides efficient average-case performance for search operations.