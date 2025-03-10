"# Learning-Python" 
Below is the combined, well‐formatted markdown file that includes all topics and examples from both files. Feel free to extend or modify any examples as needed!

---

# Python Learning Notes (From Basics to Advanced)

This document covers Python from the basics to advanced topics, complete with one‐liner definitions, detailed examples, and best practices.

---

# 1. Python Basics

### 1.1 Printing & Memory Check
- **Definition:** Print statements display output and the built-in `id()` returns the memory address of an object.
- **Example:**
  ```python
  name = "taha"
  print(id(name))  # Output: Memory address of the variable 'name'
  ```

### 1.2 Comments
- **Single-line comment:**  
  ```python
  # This is a single-line comment
  ```
- **Multi-line comment:**  
  ```python
  """
  This is a multi-line comment.
  It can span multiple lines.
  """
  ```

### 1.3 Data Types & Variables
- **Definition:** Variables store data values; Python supports several built-in types.
- **Common Types:** `int`, `float`, `str`, `bool`, `list`, `tuple`, `set`, `dict`
- **Type Hints & Naming Conventions (PEP-8, snake_case):**
  ```python
  name: str = "Taha"
  age: int = 28
  height: float = 5.9
  is_student: bool = True
  ```
  
### 1.4 Operators
- **Arithmetic:** `+`, `-`, `*`, `/`, `**` (exponent), `//` (floor division), `%` (modulus)
- **Comparison:** `==`, `!=`, `>`, `<`, `>=`, `<=`
- **Logical:** `and`, `or`, `not`
- **Membership:** `in`, `not in`
- **Identity:** `is`, `is not`
- **Example:**
  ```python
  a, b = 5, 10
  print(a ** 2)        # Output: 25 (Exponentiation)
  print(b // a)        # Output: 2  (Floor division)
  print(a < b and a != b)  # Output: True
  ```

### 1.5 Input from User
- **Example:**
  ```python
  name = input("Enter your name: ")
  print(f"Hello, {name}")
  ```

---

# 2. Strings & String Methods

- **Definition:** A string is a sequence of characters enclosed in quotes.
- **Common Methods:**  
  `.lower()`, `.upper()`, `.capitalize()`, `.title()`, `.strip()`, `.index()`, `.count()`, `.replace()`, `.split()`, `.join()`, `.isalnum()`
- **Examples:**
  ```python
  text = "Hello World"
  print(text.upper())                    # Output: HELLO WORLD
  print(text.replace("World", "Python")) # Output: Hello Python
  
  # Using f-strings and checking length
  name = "taha"
  print(f"Hello, {name}")  # Output: Hello, taha
  print(len(name))         # Output: 4
  
  # Rounding a float
  value = 10.5678
  print(round(value, 2))   # Output: 10.57
  ```

---

# 3. Lists (Dynamic Arrays)

- **Definition:** A list is an ordered, mutable collection of items.
- **Common Operations & Methods:**
  - **Creation & Access:**
    ```python
    my_list = [1, 2, 3]
    print(my_list[0])  # Output: 1
    ```
  - **Modifying Lists:**
    ```python
    fruits = ["apple", "banana", "cherry"]
    fruits.append("orange")   # Add element at the end
    fruits.insert(1, "mango") # Insert at a specific index
    fruits.extend(["kiwi", "grape"])  # Merge lists
    fruits.pop()              # Remove last element
    fruits.pop(1)             # Remove element at index 1
    fruits.remove("apple")    # Remove by value
    fruits.sort()             # Sort list
    fruits.reverse()          # Reverse list
    print(fruits)
    ```
  - **Other Methods:** `.count(value)`, `.clear()`, `.copy()`, slicing (`list[start:end]`), and repeating elements (`[value] * number`)

---

# 4. Loops

### 4.1 For Loop
- **Definition:** Iterates over items of a sequence.
- **Example:**
  ```python
  my_list = [1, 2, 3, 4, 5]
  for item in my_list:
      print(item)
  
  # Using enumerate to get index and value
  for index, value in enumerate(my_list):
      print(f"Index {index}: {value}")
  ```

### 4.2 While Loop
- **Definition:** Repeats as long as a condition is true.
- **Example:**
  ```python
  count = 1
  while count <= 5:
      print(count)
      count += 1
  ```

### 4.3 Else with Loops
- **Definition:** The `else` block executes if the loop completes normally (without a `break`).
- **Example:**
  ```python
  for i in range(3):
      print(i)
  else:
      print("Loop completed")
  ```

---

# 5. Tuple (Immutable List)

- **Definition:** A tuple is an ordered, immutable sequence of values.
- **Example:**
  ```python
  names: tuple[str, str, str] = ("Taha", "Ahmed", "Alex")
  print(names[0])  # Output: Taha
  # Tuples support slicing like lists.
  print(names[0:2]) # Output: ("Taha", "Ahmed")
  ```


A tuple is an **immutable** sequence, meaning you cannot change its content after creation. Because of its immutability, tuples have only a couple of built-in methods:

- **`index(value)`**  
  Returns the first index of the specified value.
- **`count(value)`**  
  Returns the number of times a specified value appears in the tuple.

### Accessing Tuple Values

Since tuples are ordered, you can access values using **indexing** or **slicing**:

```python
# Creating a tuple
my_tuple = (10, 20, 30, 40, 30)

# Accessing values using indexing
print(my_tuple[2])  # Output: 30

# Using the index() method to find the first occurrence of a value
first_index = my_tuple.index(30)
print(first_index)  # Output: 2

# Counting the occurrence of a value
count_30 = my_tuple.count(30)
print(count_30)  # Output: 2

# Slicing a tuple
print(my_tuple[1:4])  # Output: (20, 30, 40)
```

---

# 6. Set (Unique Unordered Collection)

- **Definition:** A set is an unordered collection of unique items.
- **Example:**
  ```python
  my_set: set[str] = {"a", "b", "c", "a"}
  print(my_set)  # Output: {'a', 'b', 'c'} (duplicates removed)
  
  # Common methods:
  my_set.add("d")
  my_set.remove("b")
  print(my_set)
  ```

A set is an **unordered** collection of unique elements. Because it is unordered, you **cannot access elements via indexing**. Instead, you iterate over the set or use membership tests.

### Common Set Methods

- **`add(element)`**  
  Adds an element to the set.
- **`remove(element)`**  
  Removes the specified element. Raises a `KeyError` if the element is not present.
- **`discard(element)`**  
  Removes the specified element if it exists. Unlike `remove()`, it does not raise an error if the element is missing.
- **`pop()`**  
  Removes and returns an arbitrary element from the set.
- **`clear()`**  
  Removes all elements from the set.
- **`update(other_set)`**  
  Adds elements from another set (or any iterable) to the set.
- **`union(other_set)`**, **`intersection(other_set)`**, **`difference(other_set)`**, and **`symmetric_difference(other_set)`**  
  Return new sets based on set operations.

### Accessing Set Values

Since sets do not support indexing, you typically iterate over them:

```python
# Creating a set
my_set = {1, 2, 3, 4, 5}

# Iterating over a set to access its values
for value in my_set:
    print(value)

# Adding an element
my_set.add(6)
print(my_set)  # Output will include 6 (order is not guaranteed)

# Removing an element using remove() and discard()
my_set.remove(2)  # Raises KeyError if 2 is not present
my_set.discard(3) # Does nothing if 3 is not present

# Popping an element (removes and returns an arbitrary element)
popped_value = my_set.pop()
print(f"Popped: {popped_value}")
print(my_set)
```

Yes, because sets are **unordered collections**, they don’t support direct indexing like lists. However, sets have **specific use cases** where they are extremely useful:

---

#### ✅ **Why Use Sets in Python?**
1. **Uniqueness Guarantee (No Duplicates)**
   - If you need to store unique values and automatically remove duplicates, sets are perfect.
   ```python
   my_set = {1, 2, 3, 3, 4}
   print(my_set)  # Output: {1, 2, 3, 4} (Duplicates are removed)
   ```

2. **Fast Membership Checking (`O(1)` Complexity)**
   - Checking if an element exists in a set is much **faster than lists** because sets use **hashing**.
   ```python
   my_set = {"apple", "banana", "cherry"}
   print("banana" in my_set)  # Output: True (Fast lookup)
   ```
## **Why Do Lists and Sets Have Different Searching Times?**
The key reason lists and sets have different searching times is their underlying data structures.

## **1. Lists (`list`)**  
- Lists are implemented as **dynamic arrays**.
- Searching for an element requires checking each item one by one (**linear search**), making the time complexity **O(n)** in the worst case.

## **2. Sets (`set`)**  
- Sets use a **hash table** (unordered collection).
- When searching for an element, Python computes its **hash value** and looks it up in constant time, making the average time complexity **O(1)**.
- However, in the worst case (when many elements collide in the same hash bucket), lookup time can degrade to **O(n)**.

---

## **What is Hashing?**
Hashing is a technique used to map data (like strings or numbers) to a fixed-size value called a **hash code** or **hash value** using a **hash function**.

## **Understanding Hashing with an Example**
Imagine you are storing names in a dictionary. Instead of searching through the entire list, a **hash function** converts each name into a unique index:

| Name       | Hash Value (Index) |
|------------|------------------|
| "Alice"    | 102              |
| "Bob"      | 215              |
| "Charlie"  | 178              |

When searching for "Charlie," instead of checking each name one by one, the system directly jumps to index **178**, making it much faster.

---

## **What is Non-Hashing?**
Non-hashing refers to data structures that do not use hash functions for lookup, such as:
- **Lists (`list`)** → Use linear search (**O(n)**)

---

## **Key Takeaways**
- **Hashing is fast** but requires extra memory.
- **Lists (non-hashing) are slower** but maintain order.
- If you need **fast lookups**, use a **set** or **dictionary (`dict`)**.
- If **order matters**, use a **list** or **tree-based structures**.

---

## **What is a Bucket?**
A **bucket** is a storage location inside a **hash table** where multiple values can be stored if they share the same **hash code**.

- When inserting a value in a set or dictionary, Python computes a **hash value** using the built-in `hash()` function.
- This **hash value** determines which **bucket** the value will go into.
- Because hash values are mapped to a **limited number of buckets**, multiple values may end up in the same bucket, causing a **hash collision**.

---

## **How Do Multiple Values Share the Same Hash Code?**
Since the number of possible hash values is large but not infinite, and the number of buckets is fixed, **different values can sometimes get the same hash value modulo the number of buckets**.

## **Example of Hash Collisions**
Let's say our hash function maps values to only **5 buckets**:

| Value    | Hash Code | Bucket (Hash Code % 5) |
|----------|----------|----------------------|
| "Alice"  | 102      | 102 % 5 = **2** |
| "Charlie"| 178      | 178 % 5 = **3** |
| "Eve"    | 157      | 157 % 5 = **2** |
| "Tom"    | 45       | 45 % 5 = **0** |

- Here, **"Alice"** and **"Eve"** both go into **bucket 2**, creating a **hash collision**.

---

## **How Does Python Handle Hash Collisions?**
Python resolves hash collisions using **chaining** (linked lists inside buckets):

1. Each bucket starts as **empty**.
2. When inserting an item:
   - If the bucket is empty, the item is placed directly.
   - If the bucket is already occupied (**collision**), Python stores the new value in a **linked list** at that bucket.
3. When searching for an item:
   - Python computes the **hash value** and finds the correct bucket.
   - If multiple values are in the same bucket, it **checks each one sequentially** inside the bucket.

---

## **Example of Hash Table with Buckets**
Imagine we have **3 buckets**, and we insert three names:

| Name     | Hash Code | Bucket (Hash Code % 3) |
|----------|----------|----------------------|
| "Alice"  | 102      | 102 % 3 = **0** |
| "Bob"    | 205      | 205 % 3 = **2** |
| "Charlie"| 306      | 306 % 3 = **0** |

Now, **bucket 0** contains both "Alice" and "Charlie":

```plaintext
Bucket 0 → ["Alice", "Charlie"]
Bucket 1 → []
Bucket 2 → ["Bob"]
```

If we search for "Charlie":
1. Compute the hash (`306`).
2. Find bucket `0`.
3. Check each item in the bucket to find "Charlie".

---

## **Why Don't We Always Get Collisions?**
Python's hash table is **optimized**:
- It dynamically **resizes** when too many elements are added.
- It increases the number of **buckets**, reducing collisions.
- It uses a **prime number of buckets** for better distribution.

---

## **Key Takeaways**
✔ **Buckets** store values based on their hash codes.  
✔ **Hash collisions** happen when multiple values share the same bucket.  
✔ Python resolves collisions using **chaining** (linked lists inside buckets).  
✔ The more buckets available, the fewer collisions occur.  

Would you like me to show a Python example of how a simple hash table with buckets works?




3. **Set Operations (Union, Intersection, Difference)**
   - Sets allow powerful mathematical operations:
   ```python
   set1 = {1, 2, 3}
   set2 = {3, 4, 5}
   print(set1 | set2)  # Union → {1, 2, 3, 4, 5}
   print(set1 & set2)  # Intersection → {3}
   print(set1 - set2)  # Difference → {1, 2}
   ```

4. **Eliminating Duplicates from a List**
   - If you have a list with duplicates, you can convert it into a set to remove them:
   ```python
   my_list = [1, 2, 2, 3, 4, 4, 5]
   unique_values = set(my_list)
   print(unique_values)  # Output: {1, 2, 3, 4, 5}
   ```

5. **Efficient Data Storage When Order Doesn’t Matter**
   - If you don’t need ordering but require **fast lookups and uniqueness**, sets are ideal.

---

### ❌ **When NOT to Use Sets**
- **If you need to keep elements in order**, use a `list`.
- **If you need indexed access**, use a `list` or `tuple`.

---

### 🔥 **Key Takeaway**
Use a `set` when:
- You need **unique values**.
- You want **fast lookups**.
- You need **set operations** (union, intersection, difference).

---

# 7. Dictionary (Key-Value Pairs)

- **Definition:** A dictionary stores data in key-value pairs.
- **Examples:**
  ```python
  # Creation and basic operations
  my_dict: dict[str, any] = {"name": "Taha", "age": 28}
  print(my_dict["name"])  # Access: Output -> Taha
  
  my_dict["name"] = "Ahmed"  # Modify
  my_dict["city"] = "Cairo"  # Add new key-value pair
  
  # Deletion
  del my_dict["age"]
  # or using pop:
  my_dict.pop("city", None)
  
  # Safe access using get()
  print(my_dict.get("name", "Default Name"))
  
  # Iterating over keys, values, and items
  for key, value in my_dict.items():
      print(f"{key}: {value}")
  ```

  ### 1. **Iterating Over Keys (Default Behavior)**
  ```python
  my_dict = {"name": "Taha", "age": 22, "city": "Lahore"}
  
  for key in my_dict:  # Default: Iterates over keys
      print(key)
  ```
  **Output:**
  ```
  name
  age
  city
  ```
  By default, iterating over a dictionary only gives the **keys**.
  
  ---
  
  ### 2. **Iterating Over Values**
  ```python
  for value in my_dict.values():
      print(value)
  ```
  **Output:**
  ```
  Taha
  22
  Lahore
  ```
  Here, `.values()` returns the dictionary's values.
  
  ---
  
  ### 3. **Iterating Over Key-Value Pairs (Using `.items()`)**
  ```python
  for key, value in my_dict.items():
      print(f"{key}: {value}")
  ```
  **Output:**
  ```
  name: Taha
  age: 22
  city: Lahore
  ```
  `.items()` is necessary when you want **both the keys and values** in one iteration.
  
  ---
  
  ### **Conclusion**
  - You **can** iterate over a dictionary without `.items()`, but you'll only get the **keys**.
  - If you need both the **keys and values**, you **must** use `.items()`.

The line:

```python
print(my_dict.get("name", "Default Name"))
```

is using the **`.get()` method** of a dictionary to **safely retrieve** the value of the `"name"` key.

---

#### ✅ **Why Use `.get()` Instead of `my_dict["name"]`?**
If the key **exists**, `.get()` returns its value:
```python
my_dict = {"name": "Taha", "age": 28}
print(my_dict.get("name", "Default Name"))  # Output: Taha
```

If the key **does not exist**, `.get()` **does not raise an error** (unlike `my_dict["key"]`); instead, it returns the **default value**:
```python
my_dict = {"age": 28}
print(my_dict.get("name", "Default Name"))  # Output: Default Name
```

---

### ❌ **If You Use `my_dict["name"]` Without `.get()`**
If the key **does not exist**, Python will throw a `KeyError`:
```python
my_dict = {"age": 28}
print(my_dict["name"])  # ❌ KeyError: 'name'
```

---

### 🔥 **Key Takeaway**
Use `.get(key, default_value)` when:
- You want to avoid **errors** if the key is missing.
- You need a **default fallback value** when the key is not found.

---

# 8. Comprehensions

- **Definition:** A concise way to create lists, sets, or dictionaries.
  
### 8.1 List Comprehension
- **Example:**
  ```python
  squared = [x**2 for x in range(10)]
  print(squared)
  ```
  

### **Example Use Cases:**
#### ✅ Common Use Case 1: Squaring Numbers
```python
squared = [x**2 for x in range(10)]
```

#### ✅ Common Use Case 2: Filtering Even Numbers
```python
even_numbers = [x for x in range(20) if x % 2 == 0]
```
**Output:** `[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]`

#### ✅ Common Use Case 3: Converting Strings to Uppercase
```python
words = ["hello", "world", "python"]
uppercase_words = [word.upper() for word in words]
```
**Output:** `['HELLO', 'WORLD', 'PYTHON']`

---

### **Conclusion**
🔹 **Yes**, list comprehensions are frequently used in Python because they are fast, concise, and readable.  
🔹 However, avoid using them when the logic is too complex, as it can reduce readability. 
  

### 8.2 Set & Dictionary Comprehension
- **Examples:**
  ```python
  unique_nums = {x for x in range(10)}
  print(unique_nums)
  
  squared_dict = {x: x**2 for x in range(5)}
  print(squared_dict)
  ```
### **Example Use Cases:**

#### **1️⃣ Set Comprehension Example: Unique Values**
A **set comprehension** is useful when you need a **collection of unique values**.

```python
unique_nums = {x for x in range(10)}
print(unique_nums)
```
🔹 **Use Case:** Removing duplicates from a list.

```python
numbers = [1, 2, 3, 4, 5, 5, 6, 6, 7]
unique_numbers = {x for x in numbers}  
print(unique_numbers)  
```
**Output:** `{1, 2, 3, 4, 5, 6, 7}`  

✅ **Why use set comprehension?**  
- Removes duplicate values automatically.  
- Faster than converting a list to a set manually.

---

#### **2️⃣ Dictionary Comprehension Example: Mapping Values**
A **dictionary comprehension** is useful when you need to create a key-value mapping.

```python
squared_dict = {x: x**2 for x in range(5)}
print(squared_dict)
```
**Output:** `{0: 0, 1: 1, 2: 4, 3: 9, 4: 16}`

🔹 **Use Case:** Counting word frequency in a sentence.

```python
sentence = "hello world hello python"
word_count = {word: sentence.split().count(word) for word in sentence.split()}
print(word_count)
```
**Output:** `{'hello': 2, 'world': 1, 'python': 1}`

✅ **Why use dictionary comprehension?**  
- Makes key-value pairs efficiently.  
- Useful for transforming or filtering data.

---

### **When to Use These?**
✔ **Set Comprehension:** When you need unique values.  
✔ **Dictionary Comprehension:** When you need to create mappings efficiently.  

---

# 9. Lambda, Map, Filter, Reduce

### 9.1 Lambda (Anonymous Function)
- **Definition:** A small anonymous function defined with the `lambda` keyword.
- **Example:**
  ```python
  add = lambda a, b: a + b
  print(add(2, 3))  # Output: 5
  ```

### 9.2 Map (Apply Function to Iterable)
- **Example:**
  ```python
  numbers = [1, 2, 3, 4]
  squared = list(map(lambda x: x ** 2, numbers))
  print(squared)  # Output: [1, 4, 9, 16]
  ```

### 9.3 Filter (Filter Values)
- **Example:**
  ```python
  even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
  print(even_numbers)  # Output: [2, 4]
  ```

### 9.4 Reduce (Reduce Iterable to Single Value)
- **Example:**
  ```python
  from functools import reduce
  result = reduce(lambda x, y: x + y, numbers)
  print(result)  # Output: 10
  ```

---

# 10. Functions

- **Definition:** A block of reusable code that performs a specific task.
- **Example:**
  ```python
  def greet(name: str) -> str:
      return f"Hello, {name}"
  
  # Calling the function
  print(greet("Taha"))  # Output: Hello, Taha
  
  # Different types of arguments:
  def func(pos1, pos2, *args, **kwargs):
      print(pos1, pos2)
      print(args)
      print(kwargs)
  
  func("first", "second", "extra1", "extra2", key1="value1", key2="value2")
  ```

  Here's a concise example demonstrating all parameter types:

  ```python
  def demo(a, b, *args, greeting="Hello", **kwargs):
      print("Positional:", a, b)         # Required positional arguments
      print("Extra positional:", args)   # Arbitrary positional parameter (*args)
      print("Greeting:", greeting)       # Keyword argument with a default value
      print("Extra keyword:", kwargs)    # Arbitrary keyword parameter (**kwargs)
  
  # Use case: mixing different argument types
  demo(10, 20, 30, 40, greeting="Hi", extra="value")
  ```
  
  **Output:**
  ```
  Positional: 10 20
  Extra positional: (30, 40)
  Greeting: Hi
  Extra keyword: {'extra': 'value'}
  ```
  
  - **`a, b`**: Required positional arguments.
  - **`*args`**: Captures extra positional arguments.
  - **`greeting`**: A keyword parameter with a default value.
  - **`**kwargs`**: Captures extra keyword arguments.
  
  This pattern is useful when you need flexibility in the number and type of arguments your function accepts.

---

  # 11. Modules & Imports
  
  - **Definition:** Modules allow you to organize and reuse code across multiple files.
  - **Examples:**
    ```python
    # Importing a module
    import math
    print(math.sqrt(25))  # Output: 5.0
    
    # Importing specific functions or using aliases
    from math import pow
    print(pow(2, 3))  # Output: 8
    
    import datetime as dt
    print(dt.datetime.now())
    ```
  
  - **Example of a Python script:**
    ```python
    def main():
        print("Hello from project-01!")
  
    if __name__ == "__main__":
        main()
    ```
  
    **Explanation:**
    - `def main():`: Defines a function named `main` that prints a message.
    - `if __name__ == "__main__":`: This ensures the `main` function only runs when the script is executed directly, not when imported as a module.
    - **Why use this?** It makes your script more modular, allowing you to reuse functions in other scripts without automatically running the code.
  
    **Example of importing and using the script:**
    ```python
    import project_01
    # Nothing prints, but you can call project_01.main()
    project_01.main()  # Output: Hello from project-01!
    ```



---
'''
# 12. Error/Exception Handling

- **Definition:** Handling errors gracefully using try-except blocks.
- **Examples:**

### **1. Handling ZeroDivisionError:**
```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Caught ZeroDivisionError: Cannot divide by zero.")
```

### **2. Handling IndexError:**
```python
try:
    lst = [1, 2, 3]
    result = lst[5]
except IndexError:
    print("Caught IndexError: List index is out of range.")
```

### **3. Handling KeyError:**
```python
try:
    dct = {"a": 1, "b": 2}
    result = dct["c"]
except KeyError:
    print("Caught KeyError: The key does not exist in the dictionary.")
```

### **4. Handling ValueError:**
```python
try:
    result = int("not a number")
except ValueError:
    print("Caught ValueError: Invalid value for conversion.")
```

### **5. Handling FileNotFoundError:**
```python
try:
    with open("non_existent_file.txt", "r") as file:
        result = file.read()
except FileNotFoundError:
    print("Caught FileNotFoundError: File not found.")
```

### **6. Raising a Custom Error:**
```python
class CustomError(Exception):
    pass

try:
    raise CustomError("This is a custom error message.")
except CustomError as e:
    print(f"Caught CustomError: {e}")
```

Each example is simplified to focus on a single error type, making it easier to understand and experiment with individually. Let me know if you’d like me to add more examples or explanations! 🚀
'''


# 13. Object-Oriented Programming (OOP)


## Comprehensive Guide to Object-Oriented Programming (OOP) in Python

Object-Oriented Programming (OOP) is a programming paradigm that organizes code into “objects” and “classes,” making it easier to manage and scale complex programs. This guide is designed for beginners and intermediate learners, offering clear explanations, real-world examples, and best practices.

---

### 1. Introduction to OOP

### What is OOP?
- **Definition:** OOP is a programming style that uses objects to represent data and methods to manipulate that data.
- **Importance:** It helps in structuring code, promotes reusability, and makes it easier to maintain and extend applications.

### Real-World Analogy
- **Analogy:** Think of a class as a blueprint for a house. The blueprint defines the structure, while each house built from that blueprint (object) can have unique characteristics like color or furniture.
- **Objects & Classes:** Just as houses built from the same blueprint share features but can differ in details, objects are instances of classes that share attributes and methods but can hold individual data.

---

### 2. Classes and Objects

### Creating a Class and an Object
A class is a template, and an object is an instance of that class.

#### Example: Person Class

```python
class Person:
    def __init__(self, name: str, age: int):
        self.name = name  # Instance attribute for name
        self.age = age    # Instance attribute for age

    def greet(self):
        # Instance method that returns a greeting message
        return f"Hello, my name is {self.name} and I am {self.age} years old."

# Creating an object of Person
person1 = Person("Alice", 30)
print(person1.greet())  # Output: Hello, my name is Alice and I am 30 years old.
```

---

### 3. Inheritance

Inheritance allows a class to inherit attributes and methods from another class.

### Single Inheritance Example
#### Example: Student Class Inheriting from Person
```python
class Student(Person):
    def __init__(self, name: str, age: int, student_id: int):
        # Call the parent class's __init__ method using super()
        super().__init__(name, age)
        self.student_id = student_id  # Additional attribute for Student

    # Overriding the greet method from Person
    def greet(self):
        return f"Hello, I am {self.name}, {self.age} years old, and my student ID is {self.student_id}."

student1 = Student("Bob", 20, 12345)
print(student1.greet())  # Output: Hello, I am Bob, 20 years old, and my student ID is 12345.
```

### Multiple Inheritance
Python supports multiple inheritance, where a class can inherit from more than one parent class. Use this feature cautiously to avoid complexity.

### Multiple Inheritance Example: Father, Mother, and Child

Multiple inheritance allows a class to inherit attributes and methods from more than one parent class. This can be useful to combine features from multiple classes.

```python
class Father:
    def __init__(self, father_name: str):
        self.father_name = father_name

    def show_father_name(self):
        return f"Father's Name: {self.father_name}"


class Mother:
    def __init__(self, mother_name: str):
        self.mother_name = mother_name

    def show_mother_name(self):
        return f"Mother's Name: {self.mother_name}"


class Child(Father, Mother):
    def __init__(self, father_name: str, mother_name: str, child_name: str):
        # Initialize both parent classes
        Father.__init__(self, father_name)
        Mother.__init__(self, mother_name)
        self.child_name = child_name

    def show_child_name(self):
        return f"Child's Name: {self.child_name}"


# Creating an instance of Child
child = Child("John", "Emma", "Liam")

# Accessing methods from both parents and the child class
print(child.show_father_name())  # Output: Father's Name: John
print(child.show_mother_name())  # Output: Mother's Name: Emma
print(child.show_child_name())   # Output: Child's Name: Liam
```

### Key Points
- **Method Resolution Order (MRO):** Python follows a specific order to resolve methods when using multiple inheritance. You can check it with `Child.__mro__`.
- **Initialization:** Be sure to call the `__init__` method of each parent class explicitly to initialize their attributes.

---

### 4. Special (Magic) Methods

Magic methods (also known as dunder methods) start and end with double underscores. They allow custom behavior for built-in operations.

#### Example: Vector Class with Special Methods
```python
class Vector:
    def __init__(self, x: float, y: float):
        self.x = x  # x-coordinate
        self.y = y  # y-coordinate

    def __str__(self):
        # Defines how the object is printed
        return f"Vector({self.x}, {self.y})"

    def __add__(self, other):
        # Allows the use of the + operator with Vector objects
        if isinstance(other, Vector):
            return Vector(self.x + other.x, self.y + other.y)
        return NotImplemented

    def __call__(self):
        # Allows the object to be called as a function
        return (self.x, self.y)

v1 = Vector(2, 3)
v2 = Vector(4, 1)
v3 = v1 + v2
print(str(v3))   # Output: Vector(6, 4)
print(v1())      # Output: (2, 3)
```

---

### 5. The Four Pillars of OOP

### Encapsulation Example: Public, Protected, and Private Attributes

Encapsulation involves bundling data and methods within a class and restricting direct access to some attributes.

```python
class Person:
    def __init__(self, name: str, age: int):
        self.name = name              # Public attribute
        self._age = age              # Protected attribute (conventionally private)
        self.__ssn = "123-45-6789"   # Private attribute

    def get_ssn(self):
        # Public method to access the private attribute
        return self.__ssn

    def set_age(self, age: int):
        # Public method to modify protected attribute
        if age > 0:
            self._age = age

    def get_age(self):
        # Public method to access protected attribute
        return self._age


person = Person("Alice", 30)

# Accessing public attribute
print(person.name)            # Output: Alice

# Accessing protected attribute (possible but not recommended directly)
print(person._age)            # Output: 30

# Accessing private attribute (through a getter method)
print(person.get_ssn())       # Output: 123-45-6789

# Modifying protected attribute using a public method
person.set_age(35)
print(person.get_age())       # Output: 35
```

### Key Points
- **Public Attributes:** Accessible from anywhere (e.g., `name`).
- **Protected Attributes:** Conventionally private, indicated by a single underscore (e.g., `_age`). Accessible but discouraged outside the class.
- **Private Attributes:** Hidden from outside access, indicated by double underscores (e.g., `__ssn`). Access through public methods like getters and setters.


### 5.1 Encapsulation
Encapsulation involves bundling data (attributes) and methods that work on the data within one unit, e.g., a class. It also restricts direct access to some of the object's components.

#### Example: Private Attributes with Getters and Setters
```python
class BankAccount:
    def __init__(self, balance: float):
        self.__balance = balance  # Private attribute using double underscore

    def deposit(self, amount: float):
        if amount > 0:
            self.__balance += amount

    def withdraw(self, amount: float):
        if 0 < amount <= self.__balance:
            self.__balance -= amount

    def get_balance(self):
        # Getter method to access the private attribute
        return self.__balance

account = BankAccount(1000)
account.deposit(500)
account.withdraw(200)
print(account.get_balance())  # Output: 1300
```

### 5.2 Polymorphism
Polymorphism allows methods to do different things based on the object calling them. This can be achieved through method overriding and dynamic behavior (duck typing).

#### Example: Animal Classes with Method Overriding
```python
class Animal:
    def speak(self):
        # Base method meant to be overridden
        pass

class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"

def animal_sound(animal: Animal):
    # Polymorphic function that works with any Animal subclass
    print(animal.speak())

dog = Dog()
cat = Cat()
animal_sound(dog)  # Output: Woof!
animal_sound(cat)  # Output: Meow!
```

### 5.3 Abstraction
Abstraction hides complex implementation details and exposes only the necessary parts. Python’s `abc` module facilitates this with abstract base classes.

#### Example: Vehicle Abstract Base Class
```python
from abc import ABC, abstractmethod

class Vehicle(ABC):
    @abstractmethod
    def start(self):
        # Abstract method that must be implemented by subclasses
        pass

class Car(Vehicle):
    def start(self):
        return "Car engine started!"

# Uncommenting the following line would raise an error because Vehicle is abstract
# vehicle = Vehicle()

car = Car()
print(car.start())  # Output: Car engine started!
```

---

### 6. Class Variables and Methods

### Class Variables
Class variables are shared by all instances of a class.

### Static Methods
Static methods do not operate on an instance but are related to the class.

#### Example: MathOperations Class
```python
class MathOperations:
    pi = 3.14159  # Class variable

    @staticmethod
    def add(a: float, b: float) -> float:
        # Static method for adding two numbers
        return a + b

print(MathOperations.pi)           # Output: 3.14159
print(MathOperations.add(10, 20))  # Output: 30
```

---

### 7. Additional Concepts

### Callable Objects with `__call__`
You can make an object behave like a function by defining the `__call__` method.

#### Example: Counter Class
```python
class Counter:
    def __init__(self):
        self.count = 0

    def __call__(self):
        # Increment the counter each time the object is called
        self.count += 1
        return self.count

counter = Counter()
print(counter())  # Output: 1
print(counter())  # Output: 2
```

### Inspecting Methods with `dir()`
The built-in `dir()` function lists the attributes and methods of an object.
```python
print(dir(Counter))  # Lists all methods and attributes of the Counter class
```

### Importing and Using Classes Across Files
Organize your code by separating classes into different files.

#### Example:
- **File: `person.py`**
  ```python
  class Person:
      def __init__(self, name: str):
          self.name = name

      def greet(self):
          return f"Hello, {self.name}!"
  ```
- **File: `main.py`**
  ```python
  from person import Person  # Import the Person class from person.py

  person = Person("Alice")
  print(person.greet())  # Output: Hello, Alice!
  ```

---

### 8. Best Practices

- **Naming Conventions:**  
  - Use **PascalCase** for class names (e.g., `Person`, `BankAccount`).
  - Use **snake_case** for methods and variable names (e.g., `greet`, `get_balance`).

- **Encapsulation:**  
  - Keep attributes private (using `__attribute`) if they should not be accessed directly.
  - Provide getters and setters to control access when needed.

- **Documentation:**  
  - Use docstrings to document classes and methods for clarity.
  - Inline comments help explain code snippets, especially for beginners.

- **Code Organization:**  
  - Separate classes into different modules (files) to enhance code readability and reusability.
  - Follow the Single Responsibility Principle: each class should have a single purpose.

---

### 9. Conclusion

### Summary of Key Points
- **OOP Basics:** Understand classes and objects as the fundamental building blocks.
- **Inheritance & Polymorphism:** Learn how to extend functionality and override methods.
- **Encapsulation & Abstraction:** Keep data safe and simplify complex systems.
- **Best Practices:** Use proper naming, document your code, and organize your project for maintainability.

### When to Use OOP
OOP is particularly beneficial in large-scale projects where modularity, reusability, and maintainability are crucial. It also helps in modeling real-world entities and their interactions.

This guide provides a solid foundation for beginners, while the advanced topics and best practices will aid intermediate learners in mastering OOP in Python. Happy coding!

---

# 14. File Handling

- **Definition:** Reading from and writing to files.
- **Examples:**
  ```python
  # Reading from a file
  with open("file.txt", "r") as f:
      content = f.read()
      print(content)
  
  # Writing to a file (this will overwrite if the file exists)
  with open("file.txt", "w") as file:
      file.write("Hello, Python!")
  ```

---

# 15. Advanced Topics

### 15.1 Decorators
- **Definition:** A decorator is a function that wraps another function to extend its behavior.
- **Example:**
  ```python
  def decorator(func):
      def wrapper(*args, **kwargs):
          print("Before function execution")
          result = func(*args, **kwargs)
          print("After function execution")
          return result
      return wrapper
  
  @decorator
  def my_function():
      print("Inside function")
  
  my_function()
  # Output:
  # Before function execution
  # Inside function
  # After function execution
  ```

### 15.2 Generators
- **Definition:** A generator is a function that yields a sequence of values using the `yield` keyword.
- **Example:**
  ```python
  def my_gen():
      for i in range(3):
          yield i
  
  gen = my_gen()
  print(next(gen))  # Output: 0
  print(next(gen))  # Output: 1
  print(next(gen))  # Output: 2
  ```

---

Happy coding!
