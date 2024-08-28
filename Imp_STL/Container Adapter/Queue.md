### Queue

A `queue` is a container that follows the First In, First Out (FIFO) principle. Elements are added at the back and removed from the front.

### Important Functions

-   **Push:**
```c++
    queue<int> q;
    q.push(10);  // Enqueues 10 into the queue
    q.push(20);  // Enqueues 20 into the queue
```
<br>

-   **Pop:**
```c++
    q.pop();  // Dequeues the front element from the queue (10 in this case)
    // After popping, 20 becomes the new front
```
<br>

-   **Front:**
```c++
  int front = q.front();  // Returns the front element of the queue (20 in this case after the pop)
```
<br>

-   **Back:**
```c++
 int back = q.back();  // Returns the back element of the queue (20 in this case, or the last element added)
```
<br>

-   **Size:**
```c++
 size_t size = q.size();  // Returns the number of elements in the queue
```
<br>

-   **Empty:**
```c++
 bool isEmpty = q.empty();  // Returns true if the queue is empty, false otherwise
```
<br>

### Properties

-   **FIFO:** Elements are accessed in the order they were inserted. The first element added is the first one to be removed.
-   **Efficient:** Provides efficient O(1) operations for both enqueue (`push`) and dequeue (`pop`).
-   **Underlying Container:** Typically implemented using a `deque` (double-ended queue) to support fast insertions and deletions from both ends.