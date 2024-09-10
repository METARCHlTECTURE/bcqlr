---
title: Notes on CS61A, Structure and Interpretation of Computer Programs
categories: 05-Languages
tags: Notes Ongoing
---

Textbook: [SICP](https://mitp-content-server.mit.edu/books/content/sectbyfn/books_pres_0/6515/sicp.zip/full-text/book/book-Z-H-4.html) [Composing Programs](https://www.composingprograms.com/)   



## Lecture 1 Welcome

Expressions
  - `can` describe a computation and evaluates to a value.
  - everything could be expressed using a call expression.
  - `call expressions`:
    - could be done by listing the name of the operator and operands.

Operators and operands
  - `are` expressions.
  - finally are evaluated to values.

```python
>>> from math import max
>>> max(7.5, 9.5) # operator: max operands: 7.5, 9.5
9.5 # value
```

Interpreters
  - `can` provide a prompt, where it waits an expression typed, evaluate it, and then displays its value.
  - The way programming languages work is that they interpret expressions by applying `evaluations procedures`, over and over again procedurally.

Evaluation procedures
  1. Evaluate the operator and then the operand subexpressions.
  2. **Apply the function** that is the value of the operator subexpression **to the arguments** that are the values of the operand subexpression.

## Lecture 2 Functions

### Name, binding, and the enviroment

In Python, we can establish new bindings using the assignment statement, which contains a name to the left of = and a value to the right:

```python
# [the name] = [any expressions]
>>> radius = 10
>>> radius
10
```

When the name is bound, the expressions are evaluated, and **only the value** is given to the name.

```python
>>> from math import pi
>>> area, circumference = pi * radius * radius, 2 * pi * radius
>>> area
314.1592653589793
>>> radius = 10000000 # radius changed
>>> area # area is not related to radius
314.1592653589793


```


## About Python

A Programming Language contains:
  - `Values`
  - `Primitive operations` (on values)
  - `Combining mechanisms`
  - (Predefined) `libraries` including useful staffs
  - Definational Mechanisms 

Python Values:
  - **Integers**
    - Decimal (base 10): 0 -1
    - Binary (base 2): 0b1011
    - Octal (base 8): 0o20
    - Hexadecimal (base 16): 0xFF
  - **Boolean values**: `True`, `False`
  - **NoneType** (null): `None`
  - **Functions**, defined with `def` and `lambda`
  - **Strings**: "Say \\"hello\\"!"
  - **Tuples**
    - Empty tuple: ()
    - Non-empty tuple: (1, "fe", (2, 3))
    - Tuple comprehension
  - **Ranges**: range(11), range(2, 8)
  - **Lists**
    - Empty List: []
    - Non-empty List: [1, "fe", (2, 3)]
    - List comprehension: [i `for` i `in` range(30) `if` i % 3 == 0]
  - **Dictionaries**
    - Empty Dictionary: {}
    - Non-empty Dictionary: {"one" : 1, "two" : 2}
    - Dictionary comprehension: {x: x**2 for x in (2, 4, 6)} {k:v*2 for (k,v) in dict1.items()}
  - Sets**
    - Empty set: set([])
    - Non-empty Set: { 1, 2 }
    - Set Comprehension: { x for x in range(20) if prime(x) }