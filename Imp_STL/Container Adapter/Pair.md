### Pair

A `pair` is a simple container that holds two values of potentially different types. It is a part of the Standard Template Library (STL) and provides a way to combine two values into a single unit.

### Important Functions

-   **Initialization:**
```c++
    pair<int, string> p1;                // Default initialization (both values are uninitialized)
    pair<int, string> p2(1, "hello");    // Initializes a pair with values 1 and "hello"
    pair<int, string> p3 = make_pair(2, "world");  // Initializes a pair using make_pair
```
<br>

-   **Access:**
```c++
    int firstValue = p2.first;   // Accesses the first element (1 in this case)
    string secondValue = p2.second; // Accesses the second element ("hello" in this case)
```
<br>

-   **Comparison Operators:**
```c++
    bool isEqual = (p2 == p3);    // Checks if p2 is equal to p3
    bool isLess = (p2 < p3);      // Checks if p2 is less than p3 based on lexicographical order
    bool isNotEqual = (p2 != p3); // Checks if p2 is not equal to p3
    bool isGreater = (p2 > p3);   // Checks if p2 is greater than p3
    bool isGreaterOrEqual = (p2 >= p3); // Checks if p2 is greater than or equal to p3
    bool isLessOrEqual = (p2 <= p3);    // Checks if p2 is less than or equal to p3
```
<br>

-   **Swap:**
```c++
    p2.swap(p3);  // Swaps the values of p2 and p3
    // After swapping, p2 will be (2, "world") and p3 will be (1, "hello")
```
<br>

-   **Get Elements by Index:**
```c++
    int firstElement = get<0>(p2);    // Accesses the first element (1 in this case)
    string secondElement = get<1>(p2); // Accesses the second element ("hello" in this case)
```
<br>

-   **Tie:**
```c++
    int a;
    string b;
    tie(a, b) = p2;  // Unpacks p2 into variables a and b
    // After this, a will be 1 and b will be "hello"
```
<br>

### Properties

-   **Element Types:** Can store two values of any type, which can be the same or different.
-   **Lexicographical Comparison:** Pairs are compared lexicographically based on their first and second elements.
-   **Simple Structure:** Used for simple data grouping and is often employed in STL algorithms and containers for storing two related pieces of data together.
-   **Unpacking:** Can use `tie` to unpack a pair into separate variables.