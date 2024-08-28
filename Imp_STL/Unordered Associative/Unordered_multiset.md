Unordered Multiset
---

An `unordered_multiset` is an unordered collection of elements where duplicates are allowed. The elements are not stored in any particular order, and it uses a hash table for storing elements, providing average O(1) time complexity for insertions and lookups.

### Important Functions

-   **Initialization:**
```c++
    unordered_multiset<int> ums;             // Default initialization (empty unordered multiset)
    unordered_multiset<int> ums2 = {1, 2, 2, 3}; // Initializes an unordered multiset with values 1, 2, 2, 3
```
<br>

-   **Insertion:**
```c++
    ums.insert(10);     // Inserts 10 into the unordered multiset
    ums.insert(20);     // Inserts 20 into the unordered multiset
    ums.insert(10);     // Inserts another 10 (duplicates allowed)
```
<br>

-   **Erasure:**
```c++
 ums.erase(10);      // Removes all occurrences of 10 from the unordered multiset
```
<br>

-   **Find:**
```c++
    auto it = ums.find(20);  // Returns an iterator to one of the elements with value 20 if found
    if (it != ums.end()) {
        cout << "Found 20" << endl;
    }
```
<br>

-   **Count:**
```c++
 size_t count = ums.count(2);  // Returns the number of occurrences of 2 in the unordered multiset
```
<br>

-   **Iteration:**
```c++
 for (auto it = ums.begin(); it != ums.end(); ++it) {
        cout << *it << " ";  // Prints all elements in the unordered multiset
    }
```
<br>

-   **Size:**
```c++
 size_t size = ums.size();  // Returns the number of elements in the unordered multiset
```
<br>

-   **Clear:**
```c++
 ums.clear();   // Removes all elements from the unordered multiset
```
<br>

### Properties

-   **Unordered:** Elements are not stored in any particular order.
-   **Allow Duplicates:** Multiple occurrences of the same element are allowed.
-   **Hash Table:** Implemented using a hash table, providing average O(1) time complexity for insertions, deletions, and lookups.
-   **Efficient Lookup:** Provides efficient average-case performance for search operations.