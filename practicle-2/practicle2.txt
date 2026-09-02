n = int(input("Enter number of items: "))

weights = list(map(int, input("Enter weights: ").split()))
values = list(map(int, input("Enter values: ").split()))

W = int(input("Enter capacity: "))

dp = [0] * (W + 1)

for i in range(n):
    for w in range(W, weights[i] - 1, -1):
        dp[w] = max(dp[w], values[i] + dp[w - weights[i]])

print("Maximum value =", dp[W])