# Binary Search

## Problem Description

Implement binary search to find a target value in a sorted array.

## Approach

Use two pointers (left, right) to narrow down the search space.

## Solution

```python
def binary_search(nums, target):
    # Initialize pointers
    left, right = 0, len(nums) - 1
    
    # Perform binary search
    while left <= right:
        # Calculate the middle index
        mid = left + (right - left) // 2
        
        # Check if the middle element is the target
        if nums[mid] == target:
            return mid
        
        # If the target is greater, ignore the left half
        elif nums[mid] < target:
            left = mid + 1
        
        # If the target is smaller, ignore the right half
        else:
            right = mid - 1
    
    # Target not found
    return -1

# Test cases
print(binary_search([-1, 0, 3, 5, 9, 12], 9))  # Expected: 4
print(binary_search([-1, 0, 3, 5, 9, 12], 2))  # Expected: -1
print(binary_search([5], 5))                   # Expected: 0
```

## Time and Space Complexity

- Time Complexity: O(log n)
- Space Complexity: O(1)

## Test Cases

```
# Test Case 1
Input: [1, 2, 3, 4]
Expected Output: [0, 3]

# Test Case 2
Input: [5, 6, 7, 8]
Expected Output: [1, 3]
```

## Notes

This solution demonstrates a clean and efficient approach to the problem.
