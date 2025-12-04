# CS106L Assignments Summary

This document provides a comprehensive overview of all assignments for Stanford CS106L (Standard C++ Programming) Fall 2025.

[中文版本 (Chinese Version)](./作业说明.md)

---

## Quick Reference Table

| Assignment | Topic | Due Date | Key Concepts | Deliverables |
|------------|-------|----------|--------------|--------------|
| A0 | Setup | Oct 10 | Environment setup, Git, compilation | Feedback form |
| A1 | SimpleEnroll | Oct 17 | Streams, CSV parsing, references | `main.cpp` |
| A2 | Marriage Pact | Oct 25 | STL containers, pointers, sets, queues | `main.cpp`, `short_answer.txt` |
| A3 | Make a Class | Nov 1 | Classes, constructors, const-correctness | `class.h`, `class.cpp`, `sandbox.cpp`, `short_answer.txt` |
| A4 | Ispell | Nov 8 | STL algorithms, ranges, lambda functions | `spellcheck.cpp` |
| A5 | Treebook | Nov 15 | Operator overloading, SMFs, RAII | `user.h`, `user.cpp` |
| A6 | Explore Courses | Nov 22 | `std::optional`, monadic operations | `main.cpp` |
| A7 | Unique Pointer | Dec 6 | Smart pointers, move semantics, templates | `unique_ptr.h`, `main.cpp`, `short_answer.txt` |

---

## Assignment 0: Setup

**Goal**: Set up development environment for the entire quarter.

**Tasks**:
1. Install Python 3.8+
2. Install VSCode with C/C++ extension
3. Install C++ compiler (GCC/MinGW)
4. Clone course repository via Git
5. Compile and run first C++ program

**Compilation**: `g++ -std=c++23 main.cpp -o main`

---

## Assignment 1: SimpleEnroll

**Goal**: Parse CSV data to identify offered/not offered CS courses using streams.

**Tasks**:
1. Fill in `Course` struct
2. Implement `parse_csv` - read CSV and create Course objects
3. Implement `write_courses_offered` - filter and write offered courses
4. Implement `write_courses_not_offered` - write remaining courses

**Key Concept**: C++ streams (`ifstream`, `ofstream`, `stringstream`), CSV parsing

**Compilation**: `g++ -std=c++20 main.cpp -o main`

---

## Assignment 2: Marriage Pact

**Goal**: Practice STL containers and pointers for a matching algorithm.

**Tasks**:
1. Implement `get_applicants` - parse names into `std::set`/`std::unordered_set`
2. Implement `find_matches` - find names with matching initials, store pointers in `std::queue`
3. Implement `get_match` - select one match from queue
4. Answer short questions about sets and pointers

**Key Concept**: STL containers, iterators, pointers, hash functions

**Compilation**: `g++ -std=c++20 main.cpp -o main`

---

## Assignment 3: Make a Class

**Goal**: Design and implement a custom C++ class.

**Requirements**:
1. Custom constructor with parameters
2. Default constructor
3. Private member fields
4. Private member functions
5. Public getter (marked `const`)
6. Public setter

**Tasks**:
1. Create class in `class.h` (declaration) and `class.cpp` (definition)
2. Instantiate class in `sandbox.cpp`
3. Answer questions about const-correctness

**Key Concept**: Class design, constructors, access modifiers, const-correctness

**Compilation**: `g++ -std=c++20 main.cpp class.cpp -o main`

---

## Assignment 4: Ispell (Spell Checker)

**Goal**: Implement spell checker using STL algorithms and ranges **without any loops**.

**Tasks**:
1. Implement `tokenize` - split input into tokens using:
   - `find_all` to find whitespace
   - `std::transform` to create tokens
   - `std::erase_if` to remove empty tokens

2. Implement `spellcheck` - identify misspellings using:
   - `std::ranges::views::filter` to skip correct words
   - `std::ranges::views::transform` to generate suggestions
   - Levenshtein distance to find one-edit-away words

**Key Concept**: STL algorithms, C++20 ranges/views, lambda functions, functional programming

**Compilation**: `g++ -std=c++20 main.cpp spellcheck.cpp -o main`

---

## Assignment 5: Treebook

**Goal**: Implement operator overloads and special member functions for a social media User class.

**Tasks**:
1. **Part 1**: Implement `operator<<` as friend function
2. **Part 2**: Implement special member functions:
   - Destructor `~User()`
   - Copy constructor
   - Copy assignment operator
   - Delete move constructor
   - Delete move assignment operator
3. **Part 3**: Implement operators:
   - `operator+=` (add friend, symmetric)
   - `operator<` (compare alphabetically)

**Key Concept**: Operator overloading, Rule of Five, deep copy, friend functions, RAII

**Compilation**: `g++ -std=c++20 main.cpp user.cpp -o main`

---

## Assignment 6: Explore Courses

**Goal**: Practice `std::optional` and monadic operations.

**Tasks**:
1. Include `<optional>` header
2. Implement `find_course` returning `std::optional<Course>`
3. Use monadic operations **without conditionals**:
   - Choose 2 from: `and_then`, `transform`, `or_else`
   - Chain operations to produce output string
   - Use `.value()` or `.value_or()` at the end

**Key Concept**: `std::optional`, monadic operations, functional programming

**Compilation**: `g++ -std=c++23 main.cpp -o main`

---

## Assignment 7: Unique Pointer

**Goal**: Implement custom `unique_ptr` to understand RAII and smart pointers.

**Tasks**:
1. **Part 1**: Implement `unique_ptr` class:
   - Basic pointer interface (constructors, `operator*`, `operator->`, `operator bool`)
   - Special member functions (destructor, delete copy, implement move)
   
2. **Part 2**: Implement `create_list` function:
   - Convert `std::vector<T>` to linked list
   - Use `std::move` for ownership transfer
   - Build list backwards from tail to head

3. Answer short questions about RAII, move semantics, and recursion limits

**Key Concept**: RAII, smart pointers, move semantics, `std::move`, templates

**Compilation**: `g++ -std=c++20 main.cpp -o main`

---

## Compilation Commands Summary

```bash
# Assignment 0
g++ -std=c++23 main.cpp -o main

# Assignment 1
g++ -std=c++20 main.cpp -o main

# Assignment 2
g++ -std=c++20 main.cpp -o main

# Assignment 3
g++ -std=c++20 main.cpp class.cpp -o main

# Assignment 4
g++ -std=c++20 main.cpp spellcheck.cpp -o main

# Assignment 5
g++ -std=c++20 main.cpp user.cpp -o main

# Assignment 6
g++ -std=c++23 main.cpp -o main

# Assignment 7
g++ -std=c++20 main.cpp -o main
```

**Windows Note**: May need to add `-static-libstdc++` flag and use `./main.exe`

---

## Key C++ Concepts Covered

1. **Environment & Tools**: Git, compilation, VSCode
2. **I/O & Streams**: File I/O, CSV parsing, string streams
3. **STL Containers**: `vector`, `set`, `unordered_set`, `queue`
4. **Classes**: Design, constructors, access modifiers, const-correctness
5. **Algorithms**: STL algorithms, ranges, views, no-loop programming
6. **Memory Management**: Pointers, RAII, smart pointers, Rule of Five
7. **Operator Overloading**: Arithmetic, comparison, stream operators
8. **Modern C++**: `std::optional`, monadic operations, move semantics
9. **Templates**: Class templates, function templates
10. **Functional Programming**: Lambda functions, captures, chaining

---

## Submission Process

For all assignments:
1. Complete the feedback form (link provided in each assignment)
2. Submit code files on Paperless
3. May resubmit multiple times before deadline
