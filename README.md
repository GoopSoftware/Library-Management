# Library App

A Java-based library management system that organizes books onto shelves, handles different book types (Print and EBook), and supports loading books from CSV files.

## Overview

This project demonstrates object-oriented programming principles including:
- **Inheritance** — `PrintBook` and `EBook` extend an abstract `Book` class
- **2D Arrays** — Books stored in a `Book[shelves][slots]` array
- **Encapsulation** — Private fields with public getters/setters
- **Abstract Methods** — Late fee calculation varies by book type
- **CSV Parsing** — Load books from external files

## Project Structure

```
LibraryApp/
├── LibraryBookShelf.java   # Main entry point + Library, Book classes
└── README.md               # This file
```

## Classes

| Class | Description |
|-------|-------------|
| `Library` | Manages book storage on shelves, tracks capacity |
| `Book` | Abstract base class for all books |
| `PrintBook` | Physical books (21-day loan, $0.25/day late fee) |
| `EBook` | Digital books (14-day loan, $0.10/day late fee) |
| `BookLoader` | Parses CSV files and populates the library |

## Usage

### Running the App

```bash
javac CS2050Reschke/M02/LibraryApp/*.java
java CS2050Reschke.M02.LibraryApp.LibraryBookShelf
```

### CSV File Format

To load books from a CSV file, use `BookLoader.loadFromCsv(library, "filename.csv")`:

```
title,author,year,type
```

- **type**: `P` for PrintBook, `E` for EBook

Example:
```
Clean Code,Robert Martin,2008,P
Deep Learning,Ian Goodfellow,2016,E
```

## Features

- Add books to library shelves (fills row by row)
- Display all books with shelf/slot locations
- View book count per shelf
- Find and display oldest book(s) by publication year
- Calculate late fees based on book type
- Export library contents to file
- Robust CSV parsing with error handling and summary reports

## Sample Output

```
------------------------------------------------------------
All books in Test Library
Shelf Slot Book Details
------------------------------------------------------------
1 1 "Unmasking AI" by Joy Buolamwini (2023) [Print, 21 days, $0.25/day]
1 2 "Hello World" by Hannah Fry (2018) [EBook, 14 days, $0.10/day]
...

Oldest books in Test Library
Earliest publication year: 1975
"The Mythical Man-Month" by Fred Brooks (1975) [Print, 21 days, $0.25/day]
"Computer Lib / Dream Machines" by Ted Nelson (1975) [Print, 21 days, $0.25/day]
```

## Requirements

- Java 8 or higher
- No external dependencies
