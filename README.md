# Specification for Project 2 Python Module

## Overview

The second module introduces additional Python programming basics including loops and branching. 
The module provides practical project setup techniques and a series of reusable functions for
drafting project folders (e.g. folders for a range of years, or from a list of folder names).

## Deliverable Names

- GitHub Repository:  datafun-02-projsetup
- Documentation:      README.md
- Script:             yourname_projsetup.py

Create a new GitHub repository with a default README.md.
In your GitHub repository, create new file with the name listed above.
You are always welcome to use a pseudonym or brand name instead of your actual name.
It should be pretty unique and consistent across all projects.

## Module Specification

### Objective

Develop a Python module that demonstrates proficiency in loops, project folder creation using pathlib, and importing modules.
This module should include reusable functions for creating sets of project folders based on various criteria.

### Requirements

#### 1. Import Attributes from Module 1

Demonstrate the ability to fetch and import yourname_attr.py from Module 1 using curl at the command line. Add your prior code to this project by importing it after your other imports.

```python
import os
import pathlib
import time
import yourname_attr 
```

#### 2. Implement Functions for Folder Creation

1. Implement reusable functions to create a series of project folders.
1. Each function should have a clear purpose, input parameters, and return values if applicable.
1. Include a docstring for each function to describe its behavior.
1. Use for in range(), for in list, and while loops to demonstrate different looping techniques.
1. Use a list comprehension to demonstrate transforming a list into a new list.
1. Use conditional branching to demonstrate different folder creation options, such as including options to force lowercase or remove spaces.

Specific functions to implement and the technique to demonstrate.

Function 1. For item in Range: Create a function to generate folders for a given range (e.g., years).

```python
def create_folders_for_range(start, end):
```

Function 2. For Item in List: Develop a function to create folders from a list of names.

```python
def create_folders_from_list(folder_list):
```

Function 3. List Comprehension: Create a function to create prefixed folders by transforming a list of names and combining each with a prefix (e.g., "data-").

```python
def create_prefixed_folders(folder_list, prefix):
```

Function 4. While Loop: Write a function to create folders periodically (e.g., one folder every 5 seconds).

```python
def create_folders_periodically(duration):
```

#### 3. Join Paths with Pathlib

In your code, use pathlib to join paths and create folders.
Never use operating system-specific path symbols such as slashes, backslashes, or double back slashes.
For example:

```python
import pathlib

# Create a path object
project_path = pathlib.Path.cwd()

# Define the new sub folder path
data_path = project_path.joinpath('data')

# Create new if it doesn't exist, otherwise do nothing
data_path.mkdir(exist_ok=True)
```

#### 4. Main Function

Implement a `main()` function to test the folder creation functions and demonstrate the use of imported modules. For example:

```python
def main():
    ''' Main function to demonstrate module capabilities. '''

    # Demonstrating imported functionality from Module 1
    print("Imported attributes:")
    print(f"Name: {yourname_attr.my_name_string}")
    print(f"Course Count: {yourname_attr.course_count_string}")
    print(f"Experience Status: {yourname_attr.is_experienced_string}")
    print(f"Hours Invested: {yourname_attr.hours_invested_string}")

    # Call function 1 to create folders for a range (e.g. years)
    start_year = 2021
    end_year = 2023
    create_folders_for_range(start_year, end_year)

    # Call function 2 to create folders given a list
    folder_names = ['data-csv', 'data-excel', 'data-json']
    create_folders_from_list(folder_names)

    # Call function 3 to create folders using comprehension
    folder_names = ['csv', 'excel', 'json']
    prefix = 'data-'
    create_prefixed_folders(folder_names, prefix)

    # Call function 4 to create folders periodically using while
    duration_secs = 5  # duration in seconds
    create_folders_periodically(duration_secs)

    # Add options e.g., to force lowercase and remove spaces 
    # to one or more of your functions (e.g. function 2) 
    # Call your function and test these options
    regions = [
      "North America", 
      "South America", 
      "Europe", 
      "Asia", 
      "Africa", 
      "Oceania", 
      "Middle East"
    ]
    create_folders_from_list(regions, to_lowercase=True, remove_spaces=True)
```

### Conditional Script Execution

Ensure the main function only executes when the script is run directly,
not when imported as a module by using standard boilerplate code.

```python
if __name__ == '__main__':
    main()
```

### Module Design

- Include a docstring at the top of the file describing its purpose.
- The code should be clear, well-organized, and demonstrate good practices.
- Include comments and docstrings for clarity.

### Evaluation Criteria

- Functionality: The project should be functional and meet all requirements.
- Documentation: The project should be well-written and well-documented.
- Presentation: The project should be presented in a clear and organized manner.
- Professionalism: The project should be submitted on-time and reflect an original, creative effort.

See rubric for additional information.
