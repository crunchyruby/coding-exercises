# Valid Parentheses

## Problem Description

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

## Approach

Use a stack to keep track of opening brackets and check if they match with closing brackets.

## Solution

```python
def is_valid(s):
    # Create a stack to keep track of opening brackets
    stack = []
    
    # Define a mapping of closing brackets to their opening counterparts
    bracket_map = {')': '(', '}': '{', ']': '['}
    
    # Iterate through each character in the string
    for char in s:
        # If the character is a closing bracket
        if char in bracket_map:
            # Pop the top element from the stack if it's not empty, otherwise use a dummy value
            top_element = stack.pop() if stack else '#'
            
            # Check if the popped element matches the corresponding opening bracket
            if bracket_map[char] != top_element:
                return False
        else:
            # If the character is an opening bracket, push it onto the stack
            stack.append(char)
    
    # If the stack is empty, all brackets were matched
    return len(stack) == 0

# Test cases
print(is_valid("()"))          # Expected: True
print(is_valid("()[]{}"))      # Expected: True
print(is_valid("(]"))          # Expected: False
print(is_valid("([)]"))        # Expected: False
print(is_valid("{[]}"))        # Expected: True
```

## Time and Space Complexity

- Time Complexity: O(n)
- Space Complexity: O(n)

## Test Cases

```
# Test Case 1
Input: "()[]{}"
Expected Output: True

# Test Case 2
Input: "([)]"
Expected Output: False
```

## Notes

This solution demonstrates a clean and efficient approach to the problem.
