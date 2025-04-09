# Two Sum

## Problem Description

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

## Approach

Use a hash map to store the complement of each number and its index.

## Solution

```python
def two_sum(nums, target):
    # Create a hash map to store numbers and their indices
    num_map = {}
    
    # Iterate through the array
    for i, num in enumerate(nums):
        # Calculate the complement
        complement = target - num
        
        # Check if the complement exists in the map
        if complement in num_map:
            # Return the indices of the two numbers
            return [num_map[complement], i]
        
        # Add the current number and its index to the map
        num_map[num] = i
    
    # No solution found
    return None

# Test cases
print(two_sum([2, 7, 11, 15], 9))  # Expected: [0, 1]
print(two_sum([3, 2, 4], 6))       # Expected: [1, 2]
print(two_sum([3, 3], 6))          # Expected: [0, 1]
```

## Time and Space Complexity

- Time Complexity: O(n)
- Space Complexity: O(n)

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
