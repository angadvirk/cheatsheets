# Arrays
### **Intro to Arrays**
* A contiguous region of memory, that stores values.
* Values stored within can be indexed using integers.
* Array indices usually start from 0 (aka: zero-indexing).

### **Complexity Analysis**
* Accessing an element in an array with its index - **O(1)**
* Searching for an element in an array - **O(n)**
* Appending to / popping off an element from the end of an array - **O(1)**
* (Note: the above may take **O(n)** time if it is a dynamic array and the new element added results in array capacity being exceeded and thus a new array of double the old capacity is allocated and all the elements are copied over)
* Inserting / removing an element from the beginning or middle of an array - **O(n)**

### **Uses of Arrays**
- Good for uses where you expect there to be a lot of **random access**, since arrays can do that in constant time, given the index.
- Used to build more complex data structures like Hash Tables.
- Used by IO routines as buffers.
- Lookup tables and inverse lookup tables.
- Can be used to return multiple values from a function.
- Used in DP to cache answers to subproblems.
