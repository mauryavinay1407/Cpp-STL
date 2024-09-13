Sorting in C++: `std::sort` with Iterators
==========================================

C++ provides the `std::sort` function in the `<algorithm>` library, which is widely used for sorting containers. In this, we will focus on how to use `std::sort` with **iterators** and highlight two approaches:

1.  Using **member functions** `begin()` and `end()`.
2.  Using **global functions** `std::begin()` and `std::end()`.

### 1\. `sort(intervals.begin(), intervals.end())`

### Description:

-   This method directly calls the **member functions** `begin()` and `end()` from the container (such as `std::vector`, `std::list`, etc.).
-   It works **only with STL containers** that support `begin()` and `end()` member functions.

```cpp
     vector<int> intervals = {5, 2, 9, 1, 5, 6}; // Sort the intervals in ascending order using member functions begin() and end() 
     sort(intervals.begin(),intervals.end());
    // Display sorted intervals
    for (const auto& interval : intervals) {
        std::cout << "[" << interval[0] << ", " << interval[1] << "]\n";     // Output:  Sorted intervals: 1 2 5 5 6 9
    }
```
### When to Use:

-   Use `intervals.begin()` and `intervals.end()` when working with **STL containers** like `std::vector`, `std::list`, etc.
-   **Limitation**: This approach won't work with plain arrays or other data structures that do not have `begin()` and `end()` member functions.

* * * * *

### 2\. `sort(begin(intervals), end(intervals))`

### Description:

-   This method calls the **global functions** `std::begin()` and `std::end()`.
-   It is more **generic** and works with both **STL containers** and **raw arrays**.
-   This makes it more flexible and portable across different types of data structures.

```cpp
   std::vector<int> intervals = {3, 1, 4, 1, 5, 9}; 
    // Sort the intervals in ascending order using global functions begin() and end() 
   sort(begin(intervals), end(intervals));
    cout << "Sorted intervals: ";
   for (const auto& val : intervals){
   cout << val << " ";       // Output:  Sorted intervals: 1 1 3 4 5 9
    }
```
Example Usage with Array:

```cpp
int intervals[] = {10, 3, 5, 6, 2, 7}; 
// Sort the array in ascending order using global functions begin() and end() 
sort(begin(intervals), end(intervals));
 cout << "Sorted intervals: ";
 for (const auto& val : intervals) {
 cout << val << " ";   // Output : Sorted intervals: 2 3 5 6 7 10
```

Example Usage with vector<vector<int>>:
- It will sort the all index of vector on the basis of first element of sub vector:
---example:1
```cpp
vector<vector<int>> intervals = {{1, 3}, {2, 2}, {1, 2}, {2, 1}}; 
// Sort the intervals 
sort(begin(intervals), end(intervals));
cout << "Sorted intervals: \n"; 
for (const auto& interval : intervals) {
 std::cout << "[" << interval[0] << ", " << interval[1] << "] "; // Output: Sorted intervals: [1, 2] [1, 3] [2, 1] [2, 2]
```

---example:2

```cpp
    vector<vector<int>> intervals = {{2, 1, 4}, {9, 2, 4}, {5, 3, 7}};

    // Sort using global functions std::begin() and std::end()

   sort(begin(intervals), end(intervals));

    // Display sorted intervals

    for (const auto& interval : intervals) {
        cout << "[" << interval[0] << ", " << interval[1] << ", " << interval[2] << "] "; // Output: [2, 1, 4] [5, 3, 7] [9, 2, 4]
    }
```

Example using custom comparator:
```cpp
bool customComparator(const std::vector<int>& a, const std::vector<int>& b) {
 if (a[0] == b[0]) {
 return a[1] < b[1]; // Sort by second element if the first element is the same 
} 
return a[0] < b[0]; // Sort by first element 
} 
int main() { 
vector<vector<int>> intervals = {{1, 3}, {2, 2}, {1, 2}, {2, 1}}; 
// Sort the intervals using the custom comparator 
sort(intervals.begin(), intervals.end(), customComparator);
 cout << "Sorted intervals: \n";
 for (const auto& interval : intervals) {
cout << "[" << interval[0] << ", " << interval[1] << "] "; //Output:  [1, 2] [1, 3] [2, 1] [2, 2]
}
 return 0; 
}
```


### When to Use:

-   Use `std::begin()` and `std::end()` when working with either **STL containers** or **C-style arrays**.
-   This approach offers more **generality** and can be used in template functions or algorithms where the input type may vary between arrays and containers.
