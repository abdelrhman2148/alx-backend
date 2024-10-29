# 0x01. Caching

## Description

This project focuses on implementing different caching algorithms in Python to understand cache replacement policies and how caching systems work. A caching system is a component that stores data to fulfill future requests more efficiently. It is often used to improve application performance by storing temporary data that would otherwise require repeated calculations or fetches.

In this project, you will implement several caching algorithms using a common base class `BaseCaching`. Each caching system has different behaviors when it reaches the maximum cache size, and each is tested using Python scripts.

## Learning Objectives

By the end of this project, you should be able to explain:

- What a caching system is and its purpose.
- Different cache replacement policies, including:
  - **FIFO** (First-In, First-Out)
  - **LIFO** (Last-In, First-Out)
  - **LRU** (Least Recently Used)
  - **MRU** (Most Recently Used)
  - **LFU** (Least Frequently Used)
- The limitations of caching systems.

## Resources

- [Cache replacement policies - FIFO](https://en.wikipedia.org/wiki/Cache_replacement_policies#First-in,_first-out_(FIFO))
- [Cache replacement policies - LIFO](https://en.wikipedia.org/wiki/Cache_replacement_policies#Last-in,_first-out_(LIFO))
- [Cache replacement policies - LRU](https://en.wikipedia.org/wiki/Cache_replacement_policies#Least_recently_used_(LRU))
- [Cache replacement policies - MRU](https://en.wikipedia.org/wiki/Cache_replacement_policies#Most_recently_used_(MRU))
- [Cache replacement policies - LFU](https://en.wikipedia.org/wiki/Cache_replacement_policies#Least-frequently_used_(LFU))

## Requirements

- Python version: 3.7 (all files will be interpreted/compiled on Ubuntu 18.04 LTS)
- Files must end with a new line and begin with `#!/usr/bin/env python3`.
- Follow the `pycodestyle` style (version 2.5).
- All files must be executable.
- All modules, classes, and functions should have documentation.
- The base class `BaseCaching` defines the constants and storage dictionary for the caching system.

## Project Structure

### base_caching.py
Defines the base class `BaseCaching` with the following:
- A dictionary `cache_data` to store cached items.
- A constant `MAX_ITEMS` (default 4) which is the maximum number of items allowed in the cache.
- Abstract methods `put` and `get` to be implemented in subclasses.

### Caching Systems

1. **BasicCache**
   - A basic dictionary-based cache without a size limit.
   
2. **FIFOCache**
   - Implements a cache with a FIFO (First-In, First-Out) policy. Discards the oldest item in the cache when `MAX_ITEMS` is exceeded.
   
3. **LIFOCache**
   - Implements a cache with a LIFO (Last-In, First-Out) policy. Discards the most recently added item when `MAX_ITEMS` is exceeded.
   
4. **LRUCache**
   - Implements a cache with an LRU (Least Recently Used) policy. Discards the least recently accessed item when `MAX_ITEMS` is exceeded.
   
5. **MRUCache**
   - Implements a cache with an MRU (Most Recently Used) policy. Discards the most recently accessed item when `MAX_ITEMS` is exceeded.
   
6. **LFUCache** (Advanced)
   - Implements a cache with an LFU (Least Frequently Used) policy. Discards the least frequently accessed item when `MAX_ITEMS` is exceeded. If multiple items share the same frequency, the LRU policy is used as a tiebreaker.

### Example Usage

For each cache system, you can use the `put` and `get` methods to store and retrieve items based on the respective caching algorithm. Example usage and expected output for each cache system can be found in the project’s main test files.

## Setup and Installation

To use this project:

1. Clone the repository:

    ```bash
    git clone https://github.com/your_username/alx-backend.git
    ```

2. Navigate to the project directory:

    ```bash
    cd 0x01-caching
    ```

3. Run each cache system test with its respective main file. For example:

    ```bash
    python3 0-main.py
    ```

## License

This project is part of the ALX Software Engineering program and is provided for educational purposes.
