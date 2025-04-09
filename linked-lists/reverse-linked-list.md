# Reverse Linked List

## Problem Description

Reverse a singly linked list.

## Approach

Use three pointers (prev, current, next) to reverse the links.

## Solution

```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def reverse_linked_list(head):
    # Initialize pointers
    prev = None
    current = head
    
    # Traverse the list
    while current:
        # Save the next node
        next_temp = current.next
        
        # Reverse the link
        current.next = prev
        
        # Move pointers one position ahead
        prev = current
        current = next_temp
    
    # Return the new head (which is the previous tail)
    return prev

# Helper function to create a linked list from a list of values
def create_linked_list(values):
    dummy = ListNode(0)
    current = dummy
    for val in values:
        current.next = ListNode(val)
        current = current.next
    return dummy.next

# Helper function to convert a linked list to a list for easy printing
def linked_list_to_list(head):
    result = []
    current = head
    while current:
        result.append(current.val)
        current = current.next
    return result

# Test cases
list1 = create_linked_list([1, 2, 3, 4, 5])
reversed_list1 = reverse_linked_list(list1)
print(linked_list_to_list(reversed_list1))  # Expected: [5, 4, 3, 2, 1]

list2 = create_linked_list([1, 2])
reversed_list2 = reverse_linked_list(list2)
print(linked_list_to_list(reversed_list2))  # Expected: [2, 1]
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
