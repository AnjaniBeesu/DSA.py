# Arrays

## Definition

An **array** is a linear data structure that stores multiple elements of the **same data type** in **contiguous (continuous) memory locations**. Each element is identified by an **index**, allowing fast access to any element.

Example:

```python
arr = [10, 20, 30, 40, 50]
```

| Index | 0 | 1 | 2 | 3 | 4 |
|-------:|:-:|:-:|:-:|:-:|:-:|
| Value  |10 |20 |30 |40 |50 |

---

# Characteristics

- Stores elements in contiguous memory.
- Elements are accessed using their index.
- Indexing starts from **0** in most programming languages.
- Stores elements of the same data type (conceptually; Python lists are dynamic and can hold mixed types).
- Supports random (direct) access.

---

# Advantages

- Fast access to elements using their index.
- Simple to implement and use.
- Efficient memory usage due to contiguous storage.
- Good cache performance because elements are stored next to each other.
- Suitable for implementing other data structures like stacks, queues, heaps, and hash tables.

---

# Disadvantages

- Fixed size in many programming languages.
- Insertion and deletion at arbitrary positions are expensive because elements must be shifted.
- Requires contiguous memory.
- Searching an unsorted array is slow.
- May waste memory if allocated size is larger than required.

---

# Common Operations and Time Complexity

| Operation | Time Complexity |
|-----------|-----------------|
| Access by Index | **O(1)** |
| Update Element | **O(1)** |
| Traverse | **O(n)** |
| Linear Search | **O(n)** |
| Binary Search (Sorted Array) | **O(log n)** |
| Insert at Beginning | **O(n)** |
| Insert at Middle | **O(n)** |
| Insert at End | **O(1)** (Average) |
| Delete from Beginning | **O(n)** |
| Delete from Middle | **O(n)** |
| Delete from End | **O(1)** |

---

# Basic Operations

## Access

```python
arr = [10, 20, 30]

print(arr[1])
```

Output:

```
20
```

Time Complexity: **O(1)**

---

## Traversal

```python
for num in arr:
    print(num)
```

Time Complexity: **O(n)**

---

## Insertion

At the end:

```python
arr.append(40)
```

Average Time Complexity: **O(1)**

At a specific position:

```python
arr.insert(1, 15)
```

Time Complexity: **O(n)**

---

## Deletion

Delete last element:

```python
arr.pop()
```

Time Complexity: **O(1)**

Delete by index:

```python
arr.pop(2)
```

Time Complexity: **O(n)**

---

## Searching

### Linear Search

```python
target = 30

for i in range(len(arr)):
    if arr[i] == target:
        print(i)
```

Time Complexity:

**O(n)**

---

### Binary Search

Works only on a **sorted array**.

Time Complexity:

**O(log n)**

---

# Real-World Applications

Arrays are used in many everyday applications, including:

- Student records
- Employee databases
- Product inventories
- Browser history
- Music playlists
- Image processing (pixels)
- Video frames
- Game boards
- Sensor data collection
- Weather and temperature records
- Financial and stock market data
- Machine learning datasets

---

# Real-World Examples

## Student Marks

```python
marks = [85, 90, 78, 88, 95]
```

Each index represents a student's marks.

---

## Monthly Sales

```python
sales = [1200, 1350, 980, 1500]
```

Each element stores sales for one month.

---

## Image Representation

An image is stored as a 2D array where each element represents a pixel value.

Example:

```
120 125 130
110 140 150
100 115 125
```

---

## Game Board

A Tic-Tac-Toe board can be represented as:

```python
board = [
    ["X", "O", "X"],
    ["O", "X", "O"],
    [" ", "X", " "]
]
```

---

# Applications in Data Structures

Arrays are used to implement:

- Stacks
- Queues
- Hash Tables
- Heaps
- Matrices
- Dynamic Arrays
- Graph adjacency matrices

---

# Common Array Patterns

- Traversal
- Two Pointers
- Sliding Window
- Prefix Sum
- Binary Search
- Frequency Counting
- Sorting
- Hashing with Arrays

# Common Array Patterns In Depth 

Array patterns are common problem-solving techniques used in coding interviews and competitive programming. Learning these patterns helps you recognize the best approach for solving a problem instead of trying random solutions.

---

## 1. Traversal

### Definition

Traversal means **visiting every element of an array exactly once** to perform some operation.

This is the most basic array pattern and is usually the first step in solving many array problems.

### Example

```python
arr = [10, 20, 30, 40]

for num in arr:
    print(num)
```

Output:

```
10
20
30
40
```

### Visualization

```
Index:  0   1   2   3
Array: [10][20][30][40]
         ↑
        Visit every element →
```

### Common Uses

- Finding the maximum or minimum element
- Calculating the sum or average
- Counting occurrences
- Printing elements
- Searching (Linear Search)

### Time Complexity

```
O(n)
```

because every element is visited once.

---

## 2. Two Pointers

### Definition

The Two Pointer technique uses **two indices (pointers)** that move through an array to solve problems efficiently.

Instead of using nested loops, two pointers reduce unnecessary comparisons.

The pointers may:

- Start from opposite ends
- Start from the same end
- Move at different speeds

### Example

Find two numbers whose sum is 9.

```python
arr = [1, 2, 3, 4, 5, 6]
target = 9
```

Start:

```
1  2  3  4  5  6
↑              ↑
L              R
```

Current Sum:

```
1 + 6 = 7
```

Too small.

Move Left pointer.

```
1  2  3  4  5  6
   ↑           ↑
   L           R
```

```
2 + 6 = 8
```

Still small.

Move Left.

```
1  2  3  4  5  6
      ↑        ↑
      L        R
```

```
3 + 6 = 9
```

Target found.

### Why use it?

Without Two Pointers:

```
Nested loops

O(n²)
```

With Two Pointers:

```
Single pass

O(n)
```

### Common Uses

- Pair Sum
- Removing duplicates
- Merging sorted arrays
- Reversing an array
- Container With Most Water

---

## 3. Sliding Window

### Definition

Sliding Window is used when we need to process **a continuous (contiguous) portion of an array**.

Instead of recalculating everything for every subarray, we move ("slide") a window across the array.

Think of placing a window over part of the array and sliding it one position at a time.

### Example

Find the maximum sum of any 3 consecutive elements.

```python
arr = [2, 1, 5, 1, 3, 2]
```

Window size = 3

First Window

```
[2 1 5] 1 3 2

Sum = 8
```

Slide one step

```
2 [1 5 1] 3 2

Sum = 7
```

Slide again

```
2 1 [5 1 3] 2

Sum = 9
```

Slide again

```
2 1 5 [1 3 2]

Sum = 6
```

Maximum Sum

```
9
```

### Why use it?

Without Sliding Window:

```
Calculate every subarray again

O(n × k)
```

With Sliding Window:

```
Reuse previous calculation

O(n)
```

### Common Uses

- Maximum subarray sum
- Longest substring
- Minimum window substring
- Fixed-size window problems
- Variable-size window problems

---

## 4. Prefix Sum

### Definition

Prefix Sum stores the **running sum** of an array.

Each position contains the sum of all previous elements including itself.

Instead of repeatedly adding numbers, we answer range-sum queries instantly.

### Example

```python
arr = [2, 4, 6, 8]
```

Prefix Sum

```
Index:   0   1   2   3
Array:   2   4   6   8
Prefix:  2   6  12  20
```

Explanation

```
2

2+4 = 6

2+4+6 = 12

2+4+6+8 = 20
```

Want the sum from index 1 to 3?

Instead of

```
4+6+8
```

Use

```
Prefix[3] - Prefix[0]

20 - 2 = 18
```

### Time Complexity

Building Prefix Sum

```
O(n)
```

Each range query

```
O(1)
```

### Common Uses

- Range Sum Queries
- Cumulative Frequency
- Subarray Sum problems

---

## 5. Binary Search

### Definition

Binary Search repeatedly divides a **sorted array** into halves until the target is found.

Instead of checking every element, it eliminates half of the remaining search space every step.

### Example

Find 14

```
2 4 6 8 10 12 14 16
```

Middle

```
8
```

Target is larger.

Discard left half.

Remaining

```
10 12 14 16
```

Middle

```
12
```

Still larger.

Remaining

```
14 16
```

Middle

```
14
```

Found.

### Why use it?

Linear Search

```
O(n)
```

Binary Search

```
O(log n)
```

### Requirement

The array **must be sorted**.

### Common Uses

- Searching
- Lower Bound
- Upper Bound
- Finding insertion position

---

## 6. Frequency Counting

### Definition

Frequency Counting keeps track of **how many times each element appears**.

Instead of repeatedly scanning the array, we store counts using a dictionary (hash map).

### Example

```python
arr = [1, 2, 2, 3, 1, 2]
```

Frequency Table

```
1 → 2

2 → 3

3 → 1
```

### Python Example

```python
frequency = {}

for num in arr:
    frequency[num] = frequency.get(num, 0) + 1
```

### Common Uses

- Counting duplicates
- Most frequent element
- Character counting
- Anagrams
- Mode of an array

### Time Complexity

```
O(n)
```

---

## 7. Sorting

### Definition

Sorting arranges elements in a specific order.

Usually:

- Ascending
- Descending

### Example

Before

```
5 1 4 2 3
```

After

```
1 2 3 4 5
```

Sorting often makes problems easier because ordered data reveals useful patterns.

### Common Algorithms

| Algorithm | Average Complexity |
|------------|-------------------|
| Merge Sort | O(n log n) |
| Heap Sort | O(n log n) |
| Quick Sort | O(n log n) |
| Bubble Sort | O(n²) |
| Selection Sort | O(n²) |
| Insertion Sort | O(n²) |

### Common Uses

- Binary Search
- Two Pointers
- Median problems
- Duplicate detection

---

## 8. Hashing with Arrays

### Definition

Hashing stores values so they can be accessed **almost instantly** using a key.

Instead of searching through an array every time, we directly check whether a value exists.

Python uses a **dictionary** (hash map) to implement hashing.

### Example

Without Hashing

```python
arr = [3, 8, 12, 15]

Search 12
```

Need to check:

```
3

8

12
```

Time Complexity

```
O(n)
```

With Hashing

```python
numbers = {
    3: True,
    8: True,
    12: True,
    15: True
}
```

Searching for 12

```
numbers[12]
```

Time Complexity

```
O(1)
```

### Common Uses

- Two Sum
- Contains Duplicate
- Frequency Counting
- Fast Lookup
- Removing duplicates

---

# Summary

| Pattern | Main Idea | Time Complexity |
|---------|-----------|-----------------|
| Traversal | Visit every element once | O(n) |
| Two Pointers | Two indices move through the array | O(n) |
| Sliding Window | Reuse calculations for contiguous subarrays | O(n) |
| Prefix Sum | Store cumulative sums | Build: O(n), Query: O(1) |
| Binary Search | Repeatedly divide a sorted array | O(log n) |
| Frequency Counting | Count occurrences using a hash map | O(n) |
| Sorting | Arrange elements in order | O(n log n) (average for efficient sorts) |
| Hashing | Fast lookup using keys | O(1) average |
---

# Popular LeetCode Problems

## Easy

| Problem | Concept |
|---------|---------|
| Two Sum | Hashing, Traversal |
| Remove Duplicates from Sorted Array | Two Pointers |
| Best Time to Buy and Sell Stock | Traversal |
| Contains Duplicate | Hashing |
| Maximum Subarray | Kadane's Algorithm |
| Merge Sorted Array | Two Pointers |
| Move Zeroes | Two Pointers |
| Plus One | Simulation |
| Missing Number | Math, XOR |
| Intersection of Two Arrays | Hashing |

---

## Medium

| Problem | Concept |
|---------|---------|
| Product of Array Except Self | Prefix Sum |
| 3Sum | Two Pointers |
| Container With Most Water | Two Pointers |
| Rotate Array | Array Manipulation |
| Spiral Matrix | Matrix Traversal |
| Set Matrix Zeroes | Matrix |
| Sort Colors | Dutch National Flag |
| Find First and Last Position | Binary Search |
| Search in Rotated Sorted Array | Binary Search |
| Next Permutation | Array Manipulation |

---

## Hard

| Problem | Concept |
|---------|---------|
| Trapping Rain Water | Two Pointers |
| First Missing Positive | Index Mapping |
| Median of Two Sorted Arrays | Binary Search |
| Sliding Window Maximum | Deque |
| Largest Rectangle in Histogram | Monotonic Stack |

---

# Summary

## Advantages

- Fast random access
- Cache-friendly
- Simple implementation
- Efficient traversal

## Disadvantages

- Fixed size 
- Expensive insertion and deletion
- Requires contiguous memory
- Linear search in unsorted arrays

---

# Complexity Summary

| Operation | Complexity |
|-----------|------------|
| Access | O(1) |
| Update | O(1) |
| Traverse | O(n) |
| Linear Search | O(n) |
| Binary Search | O(log n) |
| Insert (End) | O(1) Average |
| Insert (Beginning/Middle) | O(n) |
| Delete (End) | O(1) |
| Delete (Beginning/Middle) | O(n) |

---