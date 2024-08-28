Deque
---

A `deque` (double-ended queue) is a dynamic array that allows fast insertion and deletion at both ends.

### Important Functions

-   **Push Front/Back:**
```c++
    deque<int> dq;
    dq.push_front(10);  // Adds 10 to the front of the deque
    dq.push_back(20);   // Adds 20 to the back of the deque
```
-   **Pop Front/Back:**
```c++
    dq.pop_front();  // Removes the first element from the deque
    dq.pop_back();   // Removes the last element from the deque
```
-   **Size:**
```c++
    size_t size = dq.size();  // Returns the number of elements in the deque
```
-   **Access:**
```c++
    int front = dq.front();  // Access the first element of the deque
    int back = dq.back();    // Access the last element of the deque
```
-   **Iteration:**
```c++
    for (auto it = dq.begin(); it != dq.end(); ++it) {
        cout << *it << " ";
    }
```
### Properties

-   **Double-ended:** Allows insertion and deletion from both ends.
-   **Dynamic Size:** Can grow or shrink in size.