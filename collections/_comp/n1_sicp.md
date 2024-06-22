---
title: SICP + CS61A
---

Textbook: [SICP](https://mitp-content-server.mit.edu/books/content/sectbyfn/books_pres_0/6515/sicp.zip/full-text/book/book-Z-H-4.html) [Composing Programs](https://www.composingprograms.com/)   

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
