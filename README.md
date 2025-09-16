# Concurrent Data Structures in C++

This project implements and benchmarks **thread-safe concurrent data structures** in C++ using `std::shared_mutex` and `std::atomic`.  
It compares performance of **Stack**, **Linked List**, and **Binary Search Tree (BST)** under multi-threaded workloads.

---

## Features
- **Concurrent Stack** with lock-protected push/pop operations  
- **Concurrent Linked List** with read/write-dominated workloads  
- **Concurrent Binary Search Tree** with insert, search, and delete under concurrency  
- **Workload simulation**:  
  - *Read-dominated*: 90% reads, 5% writes, 5% deletes  
  - *Write-dominated*: 50% writes, 50% deletes  
- **Scalable benchmarking** across varying thread counts and keyspace sizes  
- Experimental results logged to `results.txt`

---

## Project Structure
```
├── stack.cpp                  # Concurrent stack implementation
├── linked_list.cpp            # Concurrent linked list implementation
├── binary_search_tree.cpp     # Concurrent BST implementation
├── results.txt                # Benchmark results (sample output)
└── README.md                  # Project documentation
```

---

## Build & Run
Compile each data structure separately:

```bash
# Stack
g++ -std=c++17 -pthread stack.cpp -o stack
./stack

# Linked List
g++ -std=c++17 -pthread linked_list.cpp -o linked_list
./linked_list

# Binary Search Tree
g++ -std=c++17 -pthread binary_search_tree.cpp -o bst
./bst
```

---

## Sample Results
Example snippet from `results.txt`:

```
Concurrent Linked List.
1  number of concurrent threads for 100000 operations took 716ms.
2  number of concurrent threads for 100000 operations took 378ms.
...

Concurrent Stack.
1  number of concurrent threads for 100000 operations took 540ms.
2  number of concurrent threads for 100000 operations took 283ms.
...
```

---

## Notes
- Requires **C++17 or later** (`std::shared_mutex`).  
- Results may vary based on CPU, OS scheduler, and thread count.  
- Best run on multi-core systems for realistic performance.  
