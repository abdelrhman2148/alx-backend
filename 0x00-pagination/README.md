# Pagination Project

## Description
This project involves the implementation of pagination in a back-end system using Python. The tasks focus on designing simple pagination mechanisms, incorporating hypermedia metadata, and ensuring that the system is resilient to deletions in the dataset. The project also emphasizes the use of CSV data files and Python's built-in libraries, ensuring data is properly paginated and accessed efficiently.

## Learning Objectives
By the end of this project, you will be able to:
- Implement pagination with page and page_size parameters.
- Understand and apply hypermedia pagination concepts.
- Build a deletion-resilient pagination system.
- Write functions and methods with appropriate documentation and type annotations.

## Requirements
- All files will be interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7.
- All code must adhere to the pycodestyle style (version 2.5.*).
- All files should end with a new line.
- The first line of every file should be: `#!/usr/bin/env python3`.
- Each function and module must include proper documentation.
- Type annotations are mandatory for all functions and coroutines.

## Setup
The dataset used for this project is the `Popular_Baby_Names.csv` file, which contains baby names along with other related information. This file will serve as the dataset for pagination tasks.

## Tasks

### 0. Simple Helper Function
Write a function `index_range` that calculates the start and end index for a given page and page size. It returns a tuple of two values corresponding to the indexes that determine the range of items for the given page.

### 1. Simple Pagination
Implement a `Server` class to paginate the dataset from the `Popular_Baby_Names.csv` file. The class should include a method `get_page`, which returns a specific page of data based on the `page` and `page_size` parameters.

### 2. Hypermedia Pagination
Extend the previous task by implementing a `get_hyper` method. This method returns the paginated data along with metadata like current page, next page, previous page, and total pages.

### 3. Deletion-Resilient Hypermedia Pagination
Implement a `get_hyper_index` method to ensure that the pagination remains accurate even if some rows are deleted from the dataset between requests. The method should provide details on the current index, next index, page size, and the actual page of data.

## Usage
To use the pagination system, run the respective Python scripts with the required parameters (page, page_size). For example:

```bash
$ ./0-main.py
$ ./1-main.py
$ ./2-main.py
$ ./3-main.py
```

Each script will demonstrate the functionality of the pagination methods and return the appropriate results.

## Repository
- GitHub repository: `alx-backend`
- Directory: `0x00-pagination`
