

This script demonstrates various list manipulation techniques in Python.

Key Features:
- List creation
- Appending elements
- Inserting elements
- Extending lists
- Removing elements
- Sorting lists
- Finding element indices

Usage:
python list_manipulation.py

Author: [Brandistone Mabeya]
Date: [12/12/2024]
Version: 1.0
"""

def list_manipulation_demo():
    """
    Demonstrates comprehensive list manipulation techniques.
    
    Steps:
    1. Create an empty list
    2. Append elements
    3. Insert element at specific position
    4. Extend list
    5. Remove last element
    6. Sort list
    7. Find element index
    """
    # Create an empty list
    my_list = []
    print("Initial empty list:", my_list)

    # Append elements 10, 20, 30, 40
    my_list.append(10)
    my_list.append(20)
    my_list.append(30)
    my_list.append(40)
    print("After appending: ", my_list)

    # Insert 15 at the second position (index 1)
    my_list.insert(1, 15)
    print("After inserting 15: ", my_list)

    # Extend my_list with [50, 60, 70]
    my_list.extend([50, 60, 70])
    print("After extending: ", my_list)

    # Remove the last element
    my_list.pop()
    print("After removing last element: ", my_list)

    # Sort the list in ascending order
    my_list.sort()
    print("After sorting: ", my_list)

    # Find and print the index of 30
    index_of_30 = my_list.index(30)
    print("Index of 30: ", index_of_30)

    # Additional list operations demonstration
    additional_list_operations(my_list)

def additional_list_operations(base_list):
    """
    Demonstrates additional list manipulation techniques.
    
    Args:
        base_list (list): The list to perform operations on
    """
    print("\n--- Additional List Operations ---")
    
    # List comprehension
    squared_list = [x**2 for x in base_list]
    print("Squared list:", squared_list)
    
    # Filtering even numbers
    even_numbers = [num for num in base_list if num % 2 == 0]
    print("Even numbers:", even_numbers)
    
    # List slicing
    print("First three elements:", base_list[:3])
    print("Last three elements:", base_list[-3:])
    
    # Reversing the list
    reversed_list = base_list[::-1]
    print("Reversed list:", reversed_list)

def error_handling_demo():
    """
    Demonstrates error handling with list operations.
    """
    print("\n--- Error Handling Demonstration ---")
    
    try:
        # Intentional error - accessing non-existent index
        test_list = [1, 2, 3]
        print(test_list[10])
    except IndexError as e:
        print("Caught IndexError:", e)
    
    try:
        # Intentional error - removing from empty list
        empty_list = []
        empty_list.pop()
    except IndexError as e:
        print("Caught IndexError when popping from empty list:", e)

def main():
    """
    Main function to run all list manipulation demonstrations.
    """
    print("Python List Manipulation Tutorial")
    print("=" * 40)
    
    # Run primary list manipulation demo
    list_manipulation_demo()
    
    # Run additional demonstrations
    additional_list_operations([10, 20, 30, 40, 50])
    
    # Demonstrate error handling
    error_handling_demo()

# Performance and advanced features
def performance_comparison():
    """
    Demonstrates performance of different list operations.
    """
    import timeit
    
    # Append vs Extend
    append_time = timeit.timeit('my_list = []; [my_list.append(i) for i in range(1000)]', number=1000)
    extend_time = timeit.timeit('my_list = []; my_list.extend(range(1000))', number=1000)
    
    print("\n--- Performance Comparison ---")
    print(f"Append method time: {append_time:.5f} seconds")
    print(f"Extend method time: {extend_time:.5f} seconds")

# Run the script
if __name__ == "__main__":
    main()
    performance_comparison()

"""
Learning Resources:
- Python Official Documentation
- Real Python Tutorials
- GeeksforGeeks Python Lists

Recommended Exercises:
1. Modify the script to handle different input types
2. Implement custom list sorting
3. Create a list manipulation utility function

Error Handling Tips:
- Always use try-except for robust code
- Validate list operations before performing them
- Check list length and indices

Best Practices:
- Use meaningful variable names
- Comment complex list operations
- Understand time complexity of list methods
"""
