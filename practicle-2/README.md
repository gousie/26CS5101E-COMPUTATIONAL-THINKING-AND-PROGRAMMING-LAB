# 0/1 Knapsack using Dynamic Programming

## 📌 Description

This project implements the **0/1 Knapsack Problem** using **Dynamic Programming** in Python.

In the 0/1 Knapsack problem, each item can either be:

* **Selected (1)**
* **Not selected (0)**

The goal is to maximize the total value of selected items without exceeding the given knapsack capacity.

## 🧠 Algorithm

The program uses a **1-dimensional Dynamic Programming array**.

For every item, we check:

```text
Take the item
OR
Don't take the item
```

and select the option with the maximum value.

### Formula

```text
dp[w] = max(dp[w], value[i] + dp[w - weight[i]])
```

The DP array is traversed **backwards** so that each item is used only once.

## 💻 Program

```python
n = int(input("Enter number of items: "))

weights = list(map(int, input("Enter weights: ").split()))
values = list(map(int, input("Enter values: ").split()))

W = int(input("Enter capacity: "))

dp = [0] * (W + 1)

for i in range(n):
    for w in range(W, weights[i] - 1, -1):
        dp[w] = max(dp[w], values[i] + dp[w - weights[i]])

print("Maximum value =", dp[W])
```

## ▶️ Example

### Input

```text
Enter number of items: 4
Enter weights: 1 3 4 5
Enter values: 1 4 5 7
Enter capacity: 7
```

### Output

```text
Maximum value = 9
```

## 📊 Complexity Analysis

Let:

* `n` = number of items
* `W` = knapsack capacity

### Time Complexity

```text
O(n × W)
```

Each item is processed for every possible capacity.

### Space Complexity

```text
O(W)
```

Only a single DP array of size `W + 1` is used.

## ⭐ Features

* Uses Dynamic Programming
* Solves the 0/1 Knapsack problem
* Uses 1D DP for optimized memory usage
* Simple Python implementation
* Time complexity: **O(n × W)**
* Space complexity: **O(W)**

## 🛠️ Requirements

* Python 3.x

No external libraries are required.

## 📚 Concepts Used

* Dynamic Programming
* Arrays
* Optimization
* 0/1 Knapsack
* Time Complexity
* Space Complexity

