### Stack

A `stack` is a container that follows the Last In, First Out (LIFO) principle.

### Important Functions

-   **Push:**
```c++
    stack<int> stk;
    stk.push(10);  // Pushes 10 onto the stack
```
-   **Pop:**
```c++
    stk.pop();  // Removes the top element from the stack
```
-   **Top:**
```c++
    int top = stk.top();  // Returns the top element of the stack
```
-   **Size:**
```c++
    size_t size = stk.size();  // Returns the number of elements in the stack
```
### Properties

-   **LIFO:** Elements are accessed in reverse order of their insertion.
-   **Efficient:** Provides efficient O(1) push and pop operations.