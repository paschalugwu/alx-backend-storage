# 0x01-NoSQL

This project focuses on working with NoSQL databases, specifically MongoDB. Below you will find a guide to the tasks, objectives, and requirements for effectively managing and manipulating NoSQL databases using MongoDB.

## Table of Contents

1. [Introduction](#introduction)
2. [Learning Objectives](#learning-objectives)
3. [Requirements](#requirements)
4. [Installation Guide](#installation-guide)
5. [Tasks](#tasks)
    - [0. List all databases](#0-list-all-databases)
    - [1. Create a database](#1-create-a-database)
    - [2. Insert document](#2-insert-document)
    - [3. All documents](#3-all-documents)
    - [4. All matches](#4-all-matches)
    - [5. Count](#5-count)
    - [6. Update](#6-update)
    - [7. Delete by match](#7-delete-by-match)
    - [8. List all documents in Python](#8-list-all-documents-in-python)
    - [9. Insert a document in Python](#9-insert-a-document-in-python)
    - [10. Change school topics](#10-change-school-topics)
    - [11. Where can I learn Python?](#11-where-can-i-learn-python)
    - [12. Log stats](#12-log-stats)

## Introduction

This project is part of the Back-end specialization curriculum, focusing on NoSQL databases, particularly MongoDB. It aims to provide practical experience in interacting with MongoDB through both command line and Python scripts.

## Learning Objectives

By the end of this project, you should be able to:

- Understand what NoSQL databases are and their benefits.
- Differentiate between SQL and NoSQL databases.
- Comprehend ACID properties and document storage concepts.
- Perform CRUD (Create, Read, Update, Delete) operations in MongoDB.
- Use MongoDB efficiently through its shell and Python scripts.

## Requirements

- **MongoDB Command File:**
  - Files interpreted/compiled on Ubuntu 18.04 LTS using MongoDB 4.2.
  - Files must end with a new line and start with a comment `// my comment`.
  - README.md is mandatory.

- **Python Scripts:**
  - Files interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7 and PyMongo 3.10.
  - Files must end with a new line and start with `#!/usr/bin/env python3`.
  - Must adhere to pycodestyle (version 2.5.*).
  - Include documentation for modules and functions.
  - Ensure scripts are not executed when imported.

## Installation Guide

To set up MongoDB 4.2 on Ubuntu 18.04:

```bash
$ wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | sudo apt-key add -
$ echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.2.list
$ sudo apt-get update
$ sudo apt-get install -y mongodb-org
$ sudo mkdir -p /data/db
$ sudo service mongod start
$ mongo --version
$ pip3 install pymongo
```

## Tasks

### 0. List all databases

Create a script to list all databases in MongoDB using the `mongo` shell command.

**File:** `0-list_databases`

### 1. Create a database

Create or use a database named `my_db`.

**File:** `1-use_or_create_database`

### 2. Insert document

Write a script to insert a document into the `school` collection with the attribute `name` set to "Holberton school".

**File:** `2-insert`

### 3. All documents

List all documents in the `school` collection.

**File:** `3-all`

### 4. All matches

List all documents in the `school` collection where `name` equals "Holberton school".

**File:** `4-match`

### 5. Count

Display the number of documents in the `school` collection.

**File:** `5-count`

### 6. Update

Update documents in the `school` collection with `name="Holberton school"` to add a new attribute `address` with value "972 Mission street".

**File:** `6-update`

### 7. Delete by match

Delete all documents in the `school` collection where `name="Holberton school"`.

**File:** `7-delete`

### 8. List all documents in Python

Write a Python function to list all documents in a collection.

**File:** `8-all.py`

### 9. Insert a document in Python

Write a Python function to insert a new document in a collection based on keyword arguments.

**File:** `9-insert_school.py`

### 10. Change school topics

Write a Python function to change all topics of a school document based on the name.

**File:** `10-update_topics.py`

### 11. Where can I learn Python?

Write a Python function that returns a list of schools having a specific topic.

**File:** `11-schools_by_topic.py`

### 12. Log stats

Write a Python script that provides stats about Nginx logs stored in MongoDB, including the count of logs and the count of logs by HTTP method.

**File:** `12-log_stats.py`

---

For detailed implementation and code, refer to the respective files in the repository.

**Repository:** [GitHub - alx-backend-storage](https://github.com/paschalugwu/alx-backend-storage)

**Directory:** `0x01-NoSQL`

---

This README.md provides an overview and efficient explanations for each task related to MongoDB operations. Follow the instructions for each task to practice and complete the project successfully.
