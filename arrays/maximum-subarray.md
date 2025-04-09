# Maximum Subarray

## Problem Description

Find the contiguous subarray which has the largest sum.

## Approach

Use Kadane's algorithm to keep track of the current sum and maximum sum.

## Solution

```python
def max_subarray(nums):
    # Initialize variables
    current_sum = max_sum = nums[0]
    
    # Traverse the array
    for num in nums[1:]:
        # Calculate the current sum
        # Either take the current number or add it to the previous sum
        current_sum = max(num, current_sum + num)
        
        # Update the maximum sum if necessary
        max_sum = max(max_sum, current_sum)
    
    return max_sum

# Test cases
print(max_subarray([-2, 1, -3, 4, -1, 2, 1, -5, 4]))  # Expected: 6
print(max_subarray([1]))                              # Expected: 1
print(max_subarray([5, 4, -1, 7, 8]))                 # Expected: 23
```

## Time and Space Complexity

- Time Complexity: O(n)
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
