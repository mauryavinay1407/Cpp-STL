C++ STL Containers
==================

A container is an object that stores a collection of objects of a specific type. For example, if we need to store a list of names, we can use a `vector`.

C++ STL provides different types of containers based on our requirements.

* * * * *

Types of STL Container in C++
-----------------------------

In C++, there are generally 3 kinds of STL containers:

-   Sequential Containers
-   Associative Containers
-   Unordered Associative Containers

* * * * *

1\. Sequential Containers in C++
--------------------------------

In C++, sequential containers allow us to store elements that can be accessed in sequential order.

Internally, sequential containers are implemented as arrays or linked lists data structures.

Types of Sequential Containers

-   *Array*
-   *Vector*
-   *Deque*
-   *List*
-   *Forward List*

2\. Associative Containers in C++
---------------------------------

In C++, associative containers allow us to store elements in sorted order. The order doesn't depend upon when the element is inserted.

Internally, they are implemented as binary tree data structures.

Types of Associative Containers

-   *Set*
-   *Map*
-   *Multiset*
-   *Multimap*

3\. Unordered Associative Containers in C++
-------------------------------------------

In C++, STL Unordered Associative Containers provide the unsorted versions of the associative container.

Internally, unordered associative containers are implemented as hash table data structures.

Types of Unordered Associative Containers

-   *Unordered Set*
-   *Unordered Map*
-   *Unordered Multiset*
-   *Unordered Multimap*

Container Adapters in C++
In C++, Container Adapters take an existing STL container and provide a restricted interface to make them behave differently. For example,

A stack is a container adapter that uses the sequential container deque and provides a restricted interface to support push() and pop() operations only.

Types of Container Adapters

Stack
Queue
Priority Queue