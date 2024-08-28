Unordered Map
---

An `unordered_map` is an unordered collection of key-value pairs. The keys are unique and not sorted.

### Important Functions

-   **Insertion:**
```c++
    unordered_map<int, string> um;
    um[1] = "one";  // Inserts a key-value pair (1, "one")
```
-   **Erasure:**
```c++
 um.erase(1);  // Removes the key-value pair with key 1`
```
-   **Find:**
```c++
 auto it = um.find(1);  // Returns an iterator to the key-value pair with key 1 if found
    if (it != um.end()) {
        // Key found
    }
```
-   **Access:**
```c++
    string value = um[1];  // Accesses the value associated with key 1
    // If key 1 doesn't exist, it will be created with a default value
```
-   **Check Key Existence:**
```c++
 if (um.count(1) > 0) {
        // Key 1 exists
    }
```
-   **Size:**
```c++
 size_t size = um.size();  // Returns the number of key-value pairs in the unordered_map
```
-   **Iteration:**
```c++
   for (auto it = um.begin(); it != um.end(); ++it) {
        cout << it->first << ": " << it->second << endl;
    }
```
### Properties

-   **Unordered:** Keys are not stored in any particular order.
-   **Unique Keys:** No duplicate keys are allowed.
-   **Hash Table:** Implemented using a hash table, providing average O(1) time complexity for operations.