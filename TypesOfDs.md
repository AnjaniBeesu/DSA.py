# Data Structures

## Definition

A **Data Structure** is a way of **organizing, storing, and managing data** so that operations like **accessing, searching, inserting, deleting, and updating** can be performed efficiently.
# or
> "A data structure is a specialized way of organizing data in memory to optimize operations like access, insertion, deletion, searching, and traversal. Choosing the right data structure directly impacts an algorithm's time and space complexity."git push -u origin main

---

# Data Structures Flowchart

```
                           DATA STRUCTURES
                                  │
                 ┌────────────────┴────────────────┐
                 │                                 │
          Primitive DS                     Non-Primitive DS
                 │                                 │
      ┌──────────┼──────────┐            ┌─────────┴─────────┐
      │          │          │            │                   │
    Integer     Float      Char       Linear DS        Non-Linear DS
      │                       │            │                   │
    Boolean                  string , etc.   ┌─────┼─────┐        ┌────┴────┐
                                    │     │     │        │         │
                                  Array Linked  Stack   Tree     Graph
                                         List    Queue
```

---

# Types of Data Structures

## 1. Primitive Data Structures

These are the **basic built-in data types** provided by programming languages.

Examples:
- Integer
- Float
- Character
- Boolean

---

## 2. Non-Primitive Data Structures

These are built using primitive data types.

They are divided into:

### A. Linear Data Structures

Elements are stored **sequentially**.

Examples:
- Array
- Linked List
- Stack
- Queue

```
10 → 20 → 30 → 40
```

Characteristics:
- Sequential arrangement
- Easy traversal
- One predecessor and one successor (except first & last)

---

### B. Non-Linear Data Structures

Elements are **not stored sequentially**.

Examples:
- Tree
- Graph

Tree

```
      A
     / \
    B   C
   / \
  D   E
```

Graph

```
A ----- B
|       |
|       |
C ----- D
```

Characteristics:
- Hierarchical or network structure
- One node may connect to multiple nodes
- Better for representing relationships

---

# Classification Summary

| Primitive | Non-Primitive |
|------------|---------------|
| Built-in | User-defined |
| Stores single values | Stores collections of values |
| Examples: int, char, float | Arrays, Linked Lists, Stacks, Queues, Trees, Graphs |

---


