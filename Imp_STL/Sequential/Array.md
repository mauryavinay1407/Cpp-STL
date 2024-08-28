Array
---

An `array` is a fixed-size container that encapsulates fixed size arrays. It is a wrapper around a built-in array that provides additional functionality and integrates with the STL.

### Important Functions

-   **Constructor:**
```c++
    std::array<int, 5> arr;  // Creates an array of size 5
```
-   **Element Access:**
```c++
    arr[0] = 10;      // Access element at index 0 (no bounds checking)
    int value = arr.at(1);  // Access element at index 1 with bounds checking
```
-   **Size:**
```c++
    size_t size = arr.size();  // Returns the number of elements in the array
```
-   **Front/Back:**
```c++
    int front = arr.front();  // Returns the first element
    int back = arr.back();    // Returns the last element
```
-   **Fill:**
```c++
    arr.fill(0);  // Fills the entire array with 0
```
-   **Swap:**
```c++
    std::array<int, 5> arr2;
    arr.swap(arr2);  // Swaps the contents of arr with arr2
```
-   **Iterators:**
```c++
    for (auto it = arr.begin(); it != arr.end(); ++it) {
        std::cout << *it << " ";
    }
```

### Properties

-   **Fixed Size:** The size is fixed at compile-time, making it a good choice for arrays with a known size that will not change.
-   **Performance:** Offers better performance for small, fixed-size arrays compared to dynamic arrays due to reduced overhead.
-   **Ease of Use:** Provides a more feature-rich alternative to raw arrays, integrating with STL algorithms and utilities.