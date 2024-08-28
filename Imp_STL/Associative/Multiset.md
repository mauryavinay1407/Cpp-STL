Multiset
--------

A `multiset` is similar to a `set`, but it allows duplicate elements.

### Important Functions

-   **Insertion:**
```c++
    multiset<int> ms;
    ms.insert(10);  // Inserts 10 into the multiset
```
-   **Erasure:**
```c++
    ms.erase(10);  // Removes all occurrences of 10 from the multiset
    ms.erase(ms.find(10));  // Removes only one occurrence of 10
```
-   **Count:**
```c++

    int count = ms.count(10);  // Returns the number of occurrences of 10
```
-   **Iteration:**
```c++
    for (auto it = ms.begin(); it != ms.end(); ++it) {
        cout << *it << " ";
    }
```
### Properties

-   **Ordered:** Elements are stored in ascending order.
-   **Duplicates Allowed:** Multiple occurrences of elements are allowed.