# Memoization Demo: Optimizing Recursive Algorithms in Python

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Topic](https://img.shields.io/badge/Topic-Memoization-orange)
![Algorithm](https://img.shields.io/badge/Algorithm-Fibonacci-green)
![Environment](https://img.shields.io/badge/Environment-Jupyter%20Notebook-orange)

## Overview

This repository demonstrates **Memoization**, a programming optimization technique that improves the performance of recursive algorithms by storing previously calculated results and reusing them when needed.

Using the Fibonacci sequence as an example, this project compares two approaches:

- **Normal Recursion:** Calculates Fibonacci numbers by repeatedly calling the same function, resulting in many repeated computations.
- **Memoization:** Stores previously calculated values in a dictionary and retrieves them whenever the same subproblem occurs again.

The main objective is to understand how caching intermediate results can reduce computational work and improve algorithm efficiency.

## Project Objectives

- Understand how recursive algorithms work.
- Identify repeated computations in recursive solutions.
- Learn how memoization eliminates redundant calculations.
- Compare execution time between normal recursion and memoized recursion.
- Understand the relationship between memoization and dynamic programming.

## Understanding Memoization

Memoization is a **Top-Down Dynamic Programming** technique in which the result of a function call is stored for future use.

Instead of solving the same subproblem repeatedly, the program checks whether its result is already available.

### 1. Normal Recursion

The standard recursive Fibonacci implementation follows this recurrence:

\[
F(n)=F(n-1)+F(n-2)
\]

Each function call generates additional recursive calls until the base condition is reached.

For example, calculating `fib(5)` involves repeatedly calculating smaller Fibonacci values. Many of these calculations are duplicated.

**Time Complexity:** Approximately \(O(2^n)\) as a commonly used upper-bound description.

**Space Complexity:** \(O(n)\) auxiliary recursion-stack space.

### 2. Memoization Approach

Memoization solves the repeated-computation problem by maintaining a dictionary that stores calculated Fibonacci values.

The process is:

1. Check whether the required value already exists in the dictionary.
2. If available, return the stored result.
3. Otherwise, calculate the value recursively.
4. Store the result in the dictionary.
5. Return the calculated value.

This ensures that each required Fibonacci value is calculated only once.

**Time Complexity:** \(O(n)\)

**Space Complexity:** \(O(n)\), including the dictionary and recursion stack.

## Project Implementation

The Jupyter Notebook contains the following implementation steps:

### Step 1: Import the Required Library

The Python `time` module is used to measure execution time.

### Step 2: Implement Normal Recursion

A recursive Fibonacci function calculates values without storing previous results.

### Step 3: Measure Execution Time

The `time.time()` function is used to record the time taken by the recursive implementation.

### Step 4: Implement Memoization

A second Fibonacci function uses a dictionary as a cache to store previously calculated values.

### Step 5: Compare Performance

The execution times of both implementations can be compared to understand the performance improvement achieved through memoization.

## Complexity Comparison

| Parameter | Normal Recursion | Memoization |
|---|---|---|
| Approach | Repeated recursion | Top-Down Dynamic Programming |
| Caching | No | Yes, using a dictionary |
| Repeated calculations | Many | Avoided for cached inputs |
| Time complexity | Exponential upper bound | \(O(n)\) |
| Auxiliary space | \(O(n)\) | \(O(n)\) |
| Performance | Slower for larger inputs | More efficient for larger inputs |

*Complexity refers to the standard Fibonacci implementations shown in this notebook. Exact execution time depends on the input and computing environment.*

## Tech Stack

- **Programming Language:** Python
- **Core Concepts:** Recursion, Memoization, Dynamic Programming
- **Data Structure:** Python Dictionary
- **Performance Measurement:** Python `time` module
- **Development Environment:** Jupyter Notebook

## Repository Structure

```text
memoization-demo/
│
├── memoization-demo.ipynb
└── README.md
```

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/mani787060/memoization-demo.git
```

### 2. Navigate to the Project Directory

```bash
cd memoization-demo
```

### 3. Install Jupyter Notebook

```bash
pip install notebook
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `memoization-demo.ipynb` and execute the cells in order.

No additional Python packages are required because the implementation uses Python's built-in `time` module and dictionary data structure.

## Important Execution Note

The normal recursive Fibonacci implementation becomes extremely slow as the input increases because it repeatedly calculates the same values.

For a practical comparison, use a smaller input such as `30` or `35` for normal recursion.

Memoization can handle much larger inputs efficiently. However, the current notebook's recursive memoized implementation still depends on Python's recursion limit.

Also, the notebook uses `1` as the return value for both `n=0` and `n=1`. This is a shifted Fibonacci convention. For the standard Fibonacci sequence, the base cases should instead return `0` and `1`, respectively.

## Practical Applications

Memoization is useful when a function repeatedly solves the same subproblems and produces consistent results for the same inputs.

Some related applications and concepts include:

- **Dynamic Programming:** Reusing solutions to overlapping subproblems.
- **AI and Machine Learning:** Caching repeated computations where inputs and outputs can be safely reused.
- **Natural Language Processing:** Transformer models use Key-Value (KV) caching to avoid recomputing previous attention keys and values during autoregressive generation. This is a related caching technique, although it is not identical to ordinary function memoization.
- **Optimization Problems:** Improving recursive solutions that contain overlapping subproblems.

## Key Learnings

Through this project, I explored:

- How recursive function calls work.
- Why repeated calculations can make recursive algorithms inefficient.
- How dictionaries can be used to store intermediate results.
- How memoization improves computational efficiency.
- How execution-time measurements can help compare different implementations.
- How memoization connects to the broader concept of dynamic programming.

## Future Improvements

Possible extensions to this project include:

- Implementing Fibonacci using bottom-up tabulation.
- Comparing recursion, memoization, and tabulation.
- Using Python's built-in `functools.lru_cache`.
- Adding function-call counters to measure redundant computations.
- Visualizing execution-time differences for different input sizes.
- Creating a more structured benchmark with repeated runs.

---

If you find this repository useful for learning recursion and dynamic programming, feel free to explore the notebook and share your feedback.
