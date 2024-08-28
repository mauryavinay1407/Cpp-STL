Unordered Set
-------------

An `unordered_set` is an unordered collection of unique elements. The elements are not sorted.

### Important Functions

-   **Insertion:**
```c++
    unordered_set<int> us;
    us.insert(10);  // Inserts 10 into the unordered_set
```
-   **Erasure:**
```c++
    us.erase(10);  // Removes 10 from the unordered_set
```
-   **Find:**
```c++
    auto it = us.find(10);  // Returns an iterator to the element 10 if found
```
-   **Size:**
```c++
    size_t size = us.size();  // Returns the number of elements in the unordered_set
```
-   **Iteration:**
```c++
    for (auto it = us.begin(); it != us.end(); ++it) {
        cout << *it << " ";
    }
```
### Properties

-   **Unordered:** Elements are not stored in any particular order.
-   **Unique:** No duplicate elements are allowed.
-   **Hash Table:** Implemented using a hash table, providing average O(1) time complexity for operations.