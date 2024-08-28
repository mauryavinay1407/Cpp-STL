Map
---

A `map` is an ordered collection of key-value pairs. The keys are unique and sorted in ascending order.

### Important Functions

-   **Insertion:**
```c++
    map<int, string> m;
    m[1] = "one";  // Inserts a key-value pair (1, "one")
```
-   **Erasure:**
```c++
    m.erase(1);  // Removes the key-value pair with key 1
```
-   **Find:**
```c++
    auto it = m.find(1);  // Returns an iterator to the key-value pair with key 1 if found
```
-   **Iteration:**
```c++
    for (auto it = m.begin(); it != m.end(); ++it) {
        cout << it->first << ": " << it->second << endl;
    }
```
### Properties

-   **Ordered:** Keys are stored in ascending order.
-   **Unique Keys:** No duplicate keys are allowed.
-   **Balanced BST:** Implemented using a self-balancing binary search tree (usually Red-Black Tree).