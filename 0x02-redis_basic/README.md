# Redis Basics Project

Welcome to the **Redis Basics** project! This project provides a series of exercises to help you understand and implement fundamental Redis functionalities using Python. Below is a detailed overview of each task in this project.

## Table of Contents

1. [Installation](#installation)
2. [Usage](#usage)
3. [Tasks Overview](#tasks-overview)
   - [Task 0: Writing Strings to Redis](#task-0-writing-strings-to-redis)
   - [Task 1: Reading from Redis and Recovering Original Type](#task-1-reading-from-redis-and-recovering-original-type)
   - [Task 2: Incrementing Values](#task-2-incrementing-values)
   - [Task 3: Storing Lists](#task-3-storing-lists)
   - [Task 4: Retrieving Lists](#task-4-retrieving-lists)
   - [Task 5: Implementing an Expiring Web Cache and Tracker](#task-5-implementing-an-expiring-web-cache-and-tracker)

## Installation

To set up Redis and the Python client on Ubuntu 18.04, follow these steps:

1. Install Redis server:
    ```bash
    sudo apt-get -y install redis-server
    ```

2. Install the Python Redis client:
    ```bash
    pip3 install redis
    ```

3. Configure Redis to bind to localhost:
    ```bash
    sudo sed -i "s/bind .*/bind 127.0.0.1/g" /etc/redis/redis.conf
    ```

## Usage

To run the provided scripts, ensure you have a Redis server running and execute your Python files using Python 3.7 on Ubuntu 18.04.

```bash
python3 your_script.py
```

## Tasks Overview

### Task 0: Writing Strings to Redis

**Objective:**
- Implement a `Cache` class with the ability to store various types of data (strings, bytes, integers, floats) in Redis.

**Instructions:**
- Create a `Cache` class.
- In the `__init__` method, initialize a Redis client and flush the database.
- Implement a `store` method to store data with a randomly generated key.
- Ensure the `store` method is properly type-annotated.

**Example Usage:**
```python
cache = Cache()
key = cache.store(b"hello")
print(key)  # Outputs a random key
```

### Task 1: Reading from Redis and Recovering Original Type

**Objective:**
- Extend the `Cache` class to retrieve data and convert it back to its original format.

**Instructions:**
- Add a `get` method that takes a key and an optional conversion function (`fn`).
- Implement `get_str` and `get_int` methods to retrieve data as strings and integers, respectively.

**Example Usage:**
```python
value = cache.get(key, fn=lambda d: d.decode("utf-8"))
```

### Task 2: Incrementing Values

**Objective:**
- Implement a system to count how many times methods in the `Cache` class are called.

**Instructions:**
- Create a `count_calls` decorator to count the number of calls to a method.
- Apply the decorator to the `store` method.

**Example Usage:**
```python
cache.store(b"first")
print(cache.get(cache.store.__qualname__))  # Outputs '1'
```

### Task 3: Storing Lists

**Objective:**
- Implement a system to store the history of inputs and outputs for specific methods.

**Instructions:**
- Create a `call_history` decorator to store inputs and outputs in Redis lists.
- Apply the decorator to the `store` method.

**Example Usage:**
```python
inputs = cache._redis.lrange(f"{cache.store.__qualname__}:inputs", 0, -1)
outputs = cache._redis.lrange(f"{cache.store.__qualname__}:outputs", 0, -1)
```

### Task 4: Retrieving Lists

**Objective:**
- Implement a `replay` function to display the history of function calls.

**Instructions:**
- Use keys from previous tasks to generate the output format showing inputs and outputs of a function.

**Example Usage:**
```python
cache.store("foo")
cache.store("bar")
cache.store(42)
replay(cache.store)
```

### Task 5: Implementing an Expiring Web Cache and Tracker

**Objective:**
- Create a function to cache web page content and track access counts.

**Instructions:**
- Implement a `get_page` function to fetch and cache web pages.
- Track how many times a URL is accessed and cache the response for 10 seconds.

**Example Usage:**
```python
content = get_page("http://example.com")
```

---

## Repository

- **GitHub Repository:** [alx-backend-storage](https://github.com/paschalugwu/alx-backend-storage)
- **Project Directory:** `0x02-redis_basic`

## License

This project is licensed under the terms of the MIT license.

---

Feel free to reach out if you have any questions or need further assistance!

---

**Note:** Ensure your Python scripts comply with the coding standards and include necessary documentation for modules, classes, and functions.
