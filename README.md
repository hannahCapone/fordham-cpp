# Fordham C++ coursework

C++ projects from my computer science classes at Fordham University. Some files started from starter code written by professors and instructors, such as the `TestDriver` declarations marked "for autograding only".

## Data structures (`namespace ds`)

| Files | What it is |
| --- | --- |
| `IntArray.h/.cpp` | Fixed-length integer array with in-place reverse |
| `AList.h` | Array-based list that grows by a factor of 2 |
| `SortedAList.h` | Sorted array-based list (needs `SortedList.h`, which isn't in this repo) |
| `SLList.h` | Singly linked list |
| `VList.h` | List built on `std::vector` |
| `BSTMap.h`, `BSTPrinter.h` | Binary search tree map, plus a printer that draws the tree |
| `DiGraph.h`, `DiGraphAdjList.h/.cpp` | Directed graph ADT with an adjacency-list implementation and cycle detection (depth-first search) |

## Big-integer expression evaluator

`BigInt.h`, `Token.h`, `Tokenizer.h`, `Transformer.h/.cpp`, `ExprTreeNode.h`, `Evaluator.h/.cpp`

A small calculator for arbitrarily large integers with variables. The tokenizer splits input into numbers, variables and operators (`+`, `-`, `=`, `;`). The transformer converts infix to postfix using operator precedence. The evaluator builds an expression tree from the postfix tokens and evaluates it with `BigInt`, which stores digits in a `VList`.

## Bank accounts

`BankAccount.h`, `SavingAccount.h/.cpp`, `CheckingAccount.h/.cpp`, `atm2000.cpp`

Inheritance practice: savings and checking accounts derive from `BankAccount`, adding an interest rate and a per-check fee. `atm2000.cpp` is a console ATM that moves money between the two. `BankAccount.cpp` isn't in this repo, so this one doesn't link as is.

## Other programs

- `customer.cpp`: reads a customer list from a file, assigns account numbers, and overloads `<<` and `>>` for a `Customer` class.
- `FCFS.cpp`: CPU scheduling simulation, first come first served. Reads process names and run times, then reports average waiting time, turnaround time and throughput.
- `roundrobin.cpp`: round-robin scheduling simulation with a 3-second time slice, timed with `SIGALRM`.

## Building

The single-file programs compile on their own, for example:

```
g++ -std=c++17 FCFS.cpp -o fcfs
g++ -std=c++17 roundrobin.cpp -o roundrobin
```

The `ds` headers are libraries without a `main`. Their class test drivers aren't included.
