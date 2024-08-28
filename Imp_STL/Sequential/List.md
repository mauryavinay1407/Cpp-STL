List
---

A `list` is a doubly linked list that allows fast insertion and deletion at any position.

### Important Functions

-   **Push Front/Back:**
```c++
    list<int> lst;
    lst.push_front(10);  // Adds 10 to the front of the list
    lst.push_back(20);   // Adds 20 to the back of the list
```
-   **Pop Front/Back:**
```c++
    lst.pop_front();  // Removes the first element from the list
    lst.pop_back();   // Removes the last element from the list
```
-   **Insert:**
```c++
    auto it = lst.begin();
    advance(it, 2);
    lst.insert(it, 15);  // Inserts 15 at the 3rd position in the list
```
-   **Erase:**
```c++
    lst.erase(it);  // Erases the element at the iterator position
```
-   **Size:**
```c++
    size_t size = lst.size();  // Returns the number of elements in the list
```
-   **Iteration:**
```c++
    for (auto it = lst.begin(); it != lst.end(); ++it) {
        cout << *it << " ";
    }
```

### Properties

-   **Doubly Linked:** Each element points to the next and previous elements, allowing bidirectional traversal.
-   **Efficient Insertions/Deletions:** Insertions and deletions are efficient compared to `vector` and `deque`.