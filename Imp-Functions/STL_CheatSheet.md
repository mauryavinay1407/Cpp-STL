C++ STL Functions Cheat Sheet
=============================

This guide covers important functions provided by the C++ Standard Template Library (STL), including utility functions for algorithms, numeric operations, and more.

1\. `accumulate`
----------------

The `accumulate` function calculates the sum of a range of elements.

### Syntax
```c++
T accumulate(InputIterator first, InputIterator last, T init);
```

-   `first`, `last`: The range of elements.
-   `init`: Initial value of the sum.

### Example
```c++
vector<int> nums = {1, 2, 3, 4, 5};
int sum = std::accumulate(nums.begin(), nums.end(), 0);

cout << "Sum: " << sum << std::endl;  // Output: Sum: 15
```

### Overflow Consideration

When working with large ranges or values, using `std::accumulate` with an `int` as the initial value can lead to overflow. This is because the sum is calculated using the type of the initial value.

```c++
long long sum = std::accumulate(nums.begin(), nums.end(), 0LL);
```

2\. `max` and `min`
-------------------

These functions return the maximum and minimum of two or more elements.

### Syntax
```c++
T max(const T& a, const T& b);
T min(const T& a, const T& b);

T max(initializer_list<T> il);
T min(initializer_list<T> il);
```
### Example
```c++
int a = 10, b = 20;
int maximum = std::max(a, b);
int minimum = std::min(a, b);

std::cout << "Max: " << maximum << std::endl;  // Output: Max: 20
std::cout << "Min: " << minimum << std::endl;  // Output: Min: 10`
```
### Using with Containers
```c++
std::vector<int> nums = {1, 2, 3, 4, 5};
int maxNum = *std::max_element(nums.begin(), nums.end());
int minNum = *std::min_element(nums.begin(), nums.end());
```
3\. `sort`
----------

The `sort` function sorts elements in a range.

### Syntax
```c++
void sort(RandomIt first, RandomIt last);`
```
### Example
```c++
vector<int> nums = {5, 3, 4, 1, 2};
sort(nums.begin(), nums.end());

for (int n : nums) {
    std::cout << n << " ";  // Output: 1 2 3 4 5
}
```
### Custom Comparator
```c++
sort(nums.begin(), nums.end(), std::greater<int>());
```
4\. `find`
----------

The `find` function searches for a value in a range.

### Syntax
```c++
InputIterator find(InputIterator first, InputIterator last, const T& value);
```
### Example
```c++
vector<int> nums = {1, 2, 3, 4, 5};
auto it = std::find(nums.begin(), nums.end(), 3);

if (it != nums.end()) {
    std::cout << "Found: " << *it << std::endl;  // Output: Found: 3
}
```
5\. `count`
-----------

The `count` function counts the occurrences of a value in a range.

### Syntax
```c++
typename iterator_traits<InputIterator>::difference_type
count(InputIterator first, InputIterator last, const T& value);
```
### Example
```
vector<int> nums = {1, 2, 3, 1, 2, 1};
int count = std::count(nums.begin(), nums.end(), 1);

std::cout << "Count of 1: " << count << std::endl;  // Output: Count of 1: 3
```
6\. `unique`
------------

The `unique` function removes consecutive duplicates from a range.

### Syntax
```c++
ForwardIterator unique(ForwardIterator first, ForwardIterator last);
```
### Example
```c++
vector<int> nums = {1, 1, 2, 3, 3, 4, 4, 5};
auto it = std::unique(nums.begin(), nums.end());
nums.erase(it, nums.end());

for (int n : nums) {
    std::cout << n << " ";  // Output: 1 2 3 4 5
}
```
7\. `reverse`
-------------

The `reverse` function reverses the order of elements in a range.

### Syntax
```c++
void reverse(BidirectionalIterator first, BidirectionalIterator last);
```
### Example
```c++
vector<int> nums = {1, 2, 3, 4, 5};
reverse(nums.begin(), nums.end());

for (int n : nums) {
    std::cout << n << " ";  // Output: 5 4 3 2 1
}
```
8\. `binary_search`
-------------------

The `binary_search` function checks if a value exists in a sorted range.

### Syntax
```c++
bool binary_search(ForwardIterator first, ForwardIterator last, const T& value);
```
### Example
```c++
std::vector<int> nums = {1, 2, 3, 4, 5};
bool found = std::binary_search(nums.begin(), nums.end(), 3);

std::cout << "Found 3: " << found << std::endl;  // Output: Found 3: 1 (true)
```
9\. `next_permutation` and `prev_permutation`
---------------------------------------------

These functions generate the next or previous lexicographical permutation of a range.

### Syntax

```c++
bool next_permutation(BidirectionalIterator first, BidirectionalIterator last);
bool prev_permutation(BidirectionalIterator first, BidirectionalIterator last);
```
### Example
```c++
vector<int> nums = {1, 2, 3};
next_permutation(nums.begin(), nums.end());

for (int n : nums) {
    std::cout << n << " ";  // Output: 1 3 2
}
```
10\. `lower_bound` and `upper_bound`
------------------------------------

These functions return iterators to the first element not less than (`lower_bound`) or greater than (`upper_bound`) a given value in a sorted range.

### Syntax
```c++
ForwardIterator lower_bound(ForwardIterator first, ForwardIterator last, const T& value);
ForwardIterator upper_bound(ForwardIterator first, ForwardIterator last, const T& value);
```
### Example
```c++
vector<int> nums = {1, 2, 2, 3, 4, 5};
auto lb = std::lower_bound(nums.begin(), nums.end(), 2);
auto ub = std::upper_bound(nums.begin(), nums.end(), 2);

std::cout << "Lower bound of 2: " << (lb - nums.begin()) << std::endl;  // Output: 1
std::cout << "Upper bound of 2: " << (ub - nums.begin()) << std::endl;  // Output: 3
```

11\. `move`
-----------

```c++
/*
    To efficiently transfer the resources from source to target.
    By efficient, I mean no usage of extra space and time for creating copy.
*/
Examples :
    string source = "TIM";
    string target = "";
    target = std::move(source);
    cout << " source = " << source << endl;
    cout << "target = "  << target << endl;
    /*
        output :
        source = 
        target = "TIM"
    */
    
    vector<string> v;
    string str = "example";
    v.push_back(std::move(str));
    /*
    After this, str becomes empty i.e. ""
    And while moving str inside v, no extra copy of str was done implicitly.
    */

    vector<int> temp{1, 2, 3};
    vector<vector<int>> result;
    result.push_back(std::move(temp));
    /*
    This allows no copy of "temp" being created.
    It ensures that the contents of "temp"
    will be moved into the "result".  This is less
    expensive, also means temp will now be empty.
    */
```

12\. `std::distance`

---------------------------------------------

These functions help find the iterator to the maximum or minimum element in a container. You can then use `std::distance` to calculate the index of these elements.

#### Syntax

```c++
ForwardIterator std::max_element(ForwardIterator first, ForwardIterator last);
ForwardIterator std::min_element(ForwardIterator first, ForwardIterator last);
template <class InputIterator>
typename iterator_traits<InputIterator>::difference_type std::distance(InputIterator first, InputIterator last);`
```
#### Example

```c++
int main() {
    std::vector<int> nums = {3, 2, 1, 6, 0, 5};

    // Find index of the maximum element
    auto maxIt = std::max_element(nums.begin(), nums.end());
    int maxIndex = std::distance(nums.begin(), maxIt);

    // Find index of the minimum element
    auto minIt = std::min_element(nums.begin(), nums.end());
    int minIndex = std::distance(nums.begin(), minIt);

    std::cout << "Max element index: " << maxIndex << "\n";  // Output: 3
    std::cout << "Min element index: " << minIndex << "\n";  // Output: 4
}
```
