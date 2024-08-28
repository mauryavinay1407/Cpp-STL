Set
---

A `set` is an ordered collection of unique elements. The elements in a `set` are automatically sorted in ascending order.

### Important Functions

-   **Insertion:**
```c++
    set<int> s;
    s.insert(10);  // Inserts 10 into the set
```
<br>

-   **Erasure:**
```c++
    s.erase(10);  // Removes 10 from the set
```
<br>

-   **Find:**
```c++    
    auto it = s.find(10);  // Returns an iterator to the element 10 if found
```
<br>

-   **Size:**
```c++
    size_t size = s.size();  // Returns the number of elements in the set
```
-   **Iteration:**
```c++
    for (auto it = s.begin(); it != s.end(); ++it) {
        cout << *it << " ";
    }
```
### Properties

-   **Ordered:** Elements are stored in ascending order.
-   **Unique:** No duplicate elements are allowed.
-   **Balanced BST:** Implemented using a self-balancing binary search tree (usually Red-Black Tree).