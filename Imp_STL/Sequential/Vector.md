Vector
---

A `vector` is a dynamic array that can grow or shrink in size.

### Important Functions

-   **Push Back:**
```c++
    vector<int> v;
    v.push_back(10);  // Adds 10 to the end of the vector
```
<br>

-   **Pop Back:**
```c++
    v.pop_back();  // Removes the last element from the vector
```
<br>

-   **Size:**
```c++
    size_t size = v.size();  // Returns the number of elements in the vector
```
<br>

-   **Access:**
```c++
    int value = v[0];  // Access the first element of the vector
```
-   **Iteration:**
```c++
    for (int i = 0; i < v.size(); ++i) {
        cout << v[i] << " ";
    }
```
<br>

### Properties

-   **Dynamic Size:** Can grow or shrink in size.
-   **Contiguous Memory:** Elements are stored in contiguous memory locations.