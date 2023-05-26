# Automation
Automation in Python involves using the Python programming language to automate repetitive tasks and streamline processes. It can be applied to areas such as file and data processing, web scraping, task scheduling, system administration, testing, network automation, GUI automation, and deployment/DevOps. Python's wide range of libraries and tools make it easy to implement automation and improve efficiency.

### How can you use regular expressions in Python to search for specific patterns in a string, and what is the primary library to work with them?
A RegEx, or Regular Expression, are a sequence of characters used to check whether a pattern exists in a given text (string) or not. If you've ever used search engines, search and replace tools of word processors and text editors - you've already seen regular expressions in use. They are used at the server side to validate the format of email addresses or passwords during registration, used for parsing text data files to find, replace, or delete certain string, etc. They help in manipulating textual data, which is often a prerequisite for data science projects involving text mining.

Python has a built-in package called re, which can be used to work with Regular Expressions.

```python
import re

#Check if the string starts with "The" and ends with "Spain":

txt = "The rain in Spain"
x = re.search("^The.*Spain$", txt)

if x:
  print("YES! We have a match!")
else:
  print("No match")
# output: YES! We have a match!
```
#### RegEx Functions

Function        | Description
----------------|-------------------------------------------
findall         | Returns a list containing all matches
search          | Returns a Match object if there is a match anywhere in the string
split           | Returns a list where the string has been split at each match
sub             | Replaces one or many matches with a string

### What is the purpose of the shutil library in Python, and provide an example of a common use case for file or directory management with this library?
The shutil library in Python provides a high-level interface for file and directory operations. It offers convenient functions for copying, moving, renaming, and deleting files and directories. The primary purpose of the shutil library is to simplify common file and directory management tasks and provide cross-platform compatibility.

A common use case for the shutil library is to copy or move files and directories. Here's an example:

#### Example 1:
```python
# Python program to explain shutil.copy() method

# importing shutil module
import shutil

source = "path/main.py"
destination ="path/main2.py"

# Copy the content of
# source to destination
dest = shutil.copy(source, destination)

# Print path of newly
# created file
print("Destination path:", dest) # Output: Destination path: path/main2.py
```
### Explain one automation idea from the assigned material and describe how it can be implemented using Python’s regular expressions and shutil libraries.
One automation idea from the assigned material is `moving folders` using Python's regular expressions and `shutil` library.

Let's say you have a directory that contains multiple subfolders, and you want to move specific folders that match a certain pattern to a different location. For example, let's assume you have a directory called "Source" with subfolders that have names starting with "Project_" followed by a number (e.g., "Project_001", "Project_002", etc.). You want to move all these project folders to a different directory called "Destination".

```python
import re
import shutil
import os

source_dir = 'path/to/Source'  # Specify the source directory containing the folders
destination_dir = 'path/to/Destination'  # Specify the destination directory to move the folders

pattern = r'^Project_\d+'  # Regular expression pattern to match the folder names

for folder_name in os.listdir(source_dir):  # Iterate over the items in the source directory
    if re.match(pattern, folder_name):  # Check if the folder name matches the pattern
        source_path = os.path.join(source_dir, folder_name)  # Construct the source path
        destination_path = os.path.join(destination_dir, folder_name)  # Construct the destination path
        shutil.move(source_path, destination_path)  # Move the folder from source to destination
```
By combining Python's regular expressions and shutil library, you can automate the process of moving folders that match a specific pattern from one directory to another. This provides a flexible and efficient way to manage and organize your files based on specific criteria.

### *Resources:*
[Python Regular Expressions Tutorial](https://www.datacamp.com/tutorial/python-regular-expression-tutorial)
[shutil](https://pymotw.com/3/shutil/)
[Automation Ideas](https://www.youtube.com/watch?v=qbW6FRbaSl0&t=69s)
[Automating Your Browser and Desktop Apps](https://www.youtube.com/watch?v=dZLyfbSQPXI)
[Watchdog](https://pythonhosted.org/watchdog/)
## Things I want to know more about