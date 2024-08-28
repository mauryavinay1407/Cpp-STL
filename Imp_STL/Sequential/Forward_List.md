Forward List
---

A `forward_list` is a singly linked list provided by the Standard Template Library (STL). Unlike `list`, which is a doubly linked list, `forward_list` only supports forward traversal and does not support reverse traversal.

### Important Functions

-   **Initialization:**
```c++
    forward_list<int> fl;           // Default initialization (empty forward list)
    forward_list<int> fl2 = {1, 2, 3}; // Initializes a forward list with values 1, 2, 3
```
<br>

-   **Insertion at the Beginning:**
```c++
    fl.push_front(10);    // Inserts 10 at the beginning of the forward list
    fl.push_front(20);    // Inserts 20 at the beginning of the forward list
```
<br>

-   **Erasure:**
```c++
 fl.pop_front();       // Removes the first element from the forward list
```
<br>

-   **Find:**
```c++
    auto it = find(fl.begin(), fl.end(), 20);  // Finds an element with value 20
    if (it != fl.end()) {
        cout << "Found 20" << endl;
    }
```
<br>

-   **Iteration:**
```c++
  for (auto it = fl.begin(); it != fl.end(); ++it) {
        cout << *it << " ";  // Prints all elements in the forward list
    }
```
<br>

-   **Size:**
```c++
  size_t size = distance(fl.begin(), fl.end());  // Returns the number of elements in the forward list
```
<br>

-   **Clear:**
```c++
 fl.clear();    // Removes all elements from the forward list
```
<br>

### Properties

-   **Forward Traversal:** Supports only forward traversal of elements.
-   **Efficient Insertion/Deletion:** Efficient insertions and deletions at the beginning.
-   **Memory Overhead:** Uses less memory compared to `list` because it does not maintain a backward pointer.