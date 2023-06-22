# Hashtables

## What is a Hashtable?
In Python, a hash table is a built-in data structure known as a dictionary. A dictionary is an unordered collection of key-value pairs, where each key is unique and associated with a value. It is implemented internally using a hash table data structure.

A hash table, or dictionary, provides efficient lookup, insertion, and deletion of elements based on their keys. It achieves this efficiency by using a hash function to convert the key into a hash code, which is then used to calculate an index in an array-like structure called the hash table.

### Example:
```python
# Create a dictionary
person = {
    "name": "John Doe",
    "age": 30,
    "city": "New York"
}

# Access values using keys
print(person["name"])  # Output: John Doe
print(person["age"])   # Output: 30

# Modify values
person["age"] = 35
print(person["age"])   # Output: 35

# Add a new key-value pair
person["occupation"] = "Engineer"
print(person)          # Output: {'name': 'John Doe', 'age': 35, 'city': 'New York', 'occupation': 'Engineer'}

# Remove a key-value pair
del person["city"]
print(person)          # Output: {'name': 'John Doe', 'age': 35, 'occupation': 'Engineer'}
```
## What is a Hash function?
Python provides a built-in hash function called hash() that can be used in conjunction with a hash table, which is implemented using dictionaries.

The hash() function takes an object as input and returns a hash value, which is an integer representation of the object. This hash value can then be used as an index in the hash table to store and retrieve values associated with keys.

### Example:
```python
hash_table = {}

key1 = "apple"
value1 = 10

# Calculate the hash value for the key using the hash() function
hash_key1 = hash(key1)

# Store the value in the hash table using the hash value as the key
hash_table[hash_key1] = value1

# Retrieve the value from the hash table using the key
retrieved_value = hash_table[hash_key1]
print(retrieved_value)  # Output: 10
```

In this example, the hash() function is used to calculate the hash value for the key "apple", and that hash value is used as the key in the hash_table dictionary. The corresponding value 10 is stored in the dictionary with the calculated hash key.

It's important to note that the hash value calculated by the hash() function is not guaranteed to be unique for different objects. Collisions may occur where different objects produce the same hash value. However, Python's built-in hash table implementation handles collisions internally, so you don't need to worry about it in most cases.


### *Resources:*

**Reading**

[Intro to Hash Tables](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)

[basics of hash tables](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)

[hash table wiki](https://en.wikipedia.org/wiki/Hash_table)

**Videos**

[what is a hash table?](https://www.youtube.com/watch?v=MfhjkfocRR0)

## Things I want to know more about