Priority Queue
-----

A `priority_queue` is a container adapter that provides a way to manage elements with priority. By default, it functions as a max-heap where the largest element is at the top. It can be customized to act as a min-heap or use different underlying containers.

### Key Functions

-   **Initialization:**
```c++
 
    // Max-Heap (default)
    priority_queue<int> maxHeap;

    // Min-Heap using a comparator
    priority_queue<int, std::vector<int>, std::greater<int>> minHeap;
```
-   **Push:**
```c++
    maxHeap.push(10);      // Inserts 10 into the max-heap
    minHeap.push(5);       // Inserts 5 into the min-heap
```
-   **Pop:**
```c++
    maxHeap.pop();         // Removes the top element (the largest) from the max-heap
    minHeap.pop();         // Removes the top element (the smallest) from the min-heap
```
-   **Top:**
```c++
    int maxTop = maxHeap.top();  // Accesses the top element (the largest) of the max-heap
    int minTop = minHeap.top();  // Accesses the top element (the smallest) of the min-heap
```
-   **Size:**
```c++
    size_t maxSize = maxHeap.size();  // Returns the number of elements in the max-heap
    size_t minSize = minHeap.size();  // Returns the number of elements in the min-heap
```
-   **Empty:**
```c++
    bool isMaxEmpty = maxHeap.empty();  // Checks if the max-heap is empty
    bool isMinEmpty = minHeap.empty();  // Checks if the min-heap is empty
```
### Custom Comparator

To use a custom comparator for ordering:
```c++
struct CustomComparator {
    bool operator()(const int& a, const int& b) const {
        return a > b;  // Custom comparator for a max-heap (default)
    }
};

std::priority_queue<int, std::vector<int>, CustomComparator> customHeap;
customHeap.push(3);
customHeap.push(1);
customHeap.push(2);
```

### Using Different Containers

You can use different underlying containers with `priority_queue`:

-   **Using `std::deque`:**
```c++
    priority_queue<int, std::deque<int>> dequeHeap;
    dequeHeap.push(20);
    dequeHeap.push(10);
```
-   **Using `std::vector` (default behavior):**
```c++
    priority_queue<int, std::vector<int>> vectorHeap;
    vectorHeap.push(50);
    vectorHeap.push(30);
```
### Properties

-   **Heap Structure:** By default, it is a max-heap, but it can be configured as a min-heap by specifying a comparator.
-   **Top Element:** Always provides access to the element with the highest (max-heap) or lowest (min-heap) priority.
-   **Efficient Operations:** Provides O(log n) complexity for insertions and removals, and O(1) complexity for accessing the top element.
-   **Custom Comparator:** Allows for custom sorting and ordering based on user-defined rules.