Merge Sort in Python
Description

This program implements the Merge Sort algorithm in Python.

Merge Sort is a sorting algorithm that uses the Divide and Conquer technique. It divides the list into smaller parts, sorts them, and then merges them to produce a sorted list.

How the Program Works
The user enters a list of numbers.
The program divides the list into two parts.
Each part is divided again until each part contains one element.
The smaller lists are compared and merged in sorted order.
The sorted parts are combined to form the final sorted list.
The program displays the original and sorted lists.
Algorithm
Start.
Read the list of numbers from the user.
If the list contains one or zero elements, return the list.
Find the middle position of the list.
Divide the list into left and right parts.
Apply Merge Sort to both parts.
Compare elements from the left and right parts.
Add the smaller element to the result.
Add any remaining elements.
Return the sorted list.
Display the sorted list.
Stop.
Python Code
def merge_sort(a):
    if len(a) <= 1:
        return a

    mid = len(a) // 2

    left = merge_sort(a[:mid])
    right = merge_sort(a[mid:])

    result = []

    i = 0
    j = 0

    while i < len(left) and j < len(right):

        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    result.extend(left[i:])
    result.extend(right[j:])

    return result


a = list(map(int, input("Enter the list\n").split()))

print("Before:", a)

a = merge_sort(a)

print("After:", a)
Example Input
Enter the list
8 3 5 2 9 1
Example Output
Before: [8, 3, 5, 2, 9, 1]
After: [1, 2, 3, 5, 8, 9]
Time Complexity
Best Case: O(n log n)
Average Case: O(n log n)
Worst Case: O(n log n)
Space Complexity
O(n)
Key Concept

Merge Sort = Divide → Sort → Merge

Requirements
Python 3.x
No external libraries are required.
