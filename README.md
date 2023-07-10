# Python Command Overview for handling files

This project serves as a comprehensive guide to executing shell commands and handling files using Python.
Installation. You can install Python through the official website: https://www.python.org/downloads/

## Table of Contents

- [Installation](#installation-requiments)
- [Usage](#usage)
- [Install Requirements](#Install-requirements)
- [Shell Commands with Python](#shell-commands-with-python)
  - [Creating and writing to a file](#creating-and-writing-to-a-file)
  - [Reading from a file](#reading-from-a-file)
  - [Appending to an existing file](#appending-to-an-existing-file)
  - [Deleting a file](#deleting-a-file)
  - [Checking if a file exists](#checking-if-a-file-exists)
  - [Creating a directory](#creating-a-directory)
- [Large File Handling](#large-file-handling)
  - [Opening a file](#opening-a-file)
  - [Reading a file line by line](#reading-a-file-line-by-line)
  - [Reading a specific number of lines](#reading-a-specific-number-of-lines)
  - [Searching within a large file](#searching-within-a-large-file)
  - [Writing to a large file](#writing-to-a-large-file)
  - [Splitting files](#splitting-files)
- [Handling Specific File Formats](#handling-specific-file-formats)
  - [Reading PDF files](#reading-pdf-files)
  - [Reading Word documents](#reading-word-documents)
  - [Reading Excel files](#reading-excel-files)
  - [Reading HTML files](#reading-html-files)
- [Credits](#credits)
- [Useful Resources](#useful-resources)





## Install requiments
```python
pip install PyPDF2 python-docx pandas beautifulsoup4
```
## Usage
This project can be used as a reference guide for executing shell commands and file handling in Python.
Shell Commands with Python

This project makes use of Python to execute shell commands. Here are some of the Python commands used in this project:

## Creating and writing to a file

```python

with open("filename.txt", "w") as f:
    f.write("Hello, World!")
```
### Reading from a file

```python

with open("filename.txt", "r") as f:
    print(f.read())
```
### Appending to an existing file

```python

with open("filename.txt", "a") as f:
    f.write("More text.")
```
### Deleting a file

```python

import os
os.remove("filename.txt")
```
### Checking if a file exists

```python

import os
os.path.exists("filename.txt")
```
### Creating a directory

```python
import os
os.mkdir("directory_name")
```
## Large File Handling

Working with large files requires a different set of Python commands. Here are some examples:

### Opening a file

```python

file = open('large_file.txt', 'r')
```
### Reading a file line by line

```python

with open('large_file.txt', 'r') as file:
    for line in file:
        print(line)
```
### Reading a specific number of lines

```python

from itertools import islice
with open('large_file.txt', 'r') as file:
    head = list(islice(file, 5))
```
### Searching within a large file

```python

with open('large_file.txt', 'r') as file:
    for line in file:
        if 'some_text' in line:
            print(line)
```
### Writing to a large file

```python

with open('large_file.txt', 'w') as file:
    file.write('some_text')
```
### Splitting files

```python

chunk_size = 1000000  # 1 MB
with open('large_file.txt', 'r') as file:
    chunk = file.read(chunk_size)
    while chunk:
        with open('chunk.txt', 'w') as chunk_file:
            chunk_file.write(chunk)
        chunk = file.read(chunk_size)
```
## Handling Specific File Formats

Python can read various file formats using specific libraries. Here are some examples:

### Reading PDF files

```python

import PyPDF2

with open('example.pdf', 'rb') as file:
    reader = PyPDF2.PdfFileReader(file)
    page = reader.getPage(0)
    print(page.extract_text())
```
### Reading Word documents

```python

from docx import Document

doc = Document('example.docx')
for para in doc.paragraphs:
    print(para.text)
```
### Reading Excel files

```python

import pandas as pd

data = pd.read_excel('example.xlsx')
print(data)
```
### Reading HTML files

```python

from bs4 import BeautifulSoup

with open("example.html") as fp:
    soup = BeautifulSoup(fp, 'html.parser')
print(soup.prettify())
```
## Credits
This README was generated with the help of ChatGPT4, an AI developed by OpenAI & [Volkan Sah](https://github.com/volkansah).

## Usefull
- [Python Modul Overview](https://github.com/VolkanSah/Python-Modules-Overview)
- [Python XPath Tutorial](https://github.com/VolkanSah/Python-XPath-Tutorial)
