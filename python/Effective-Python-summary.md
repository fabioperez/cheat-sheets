## Table of Contents

* [Pythonic Thinking](#1-pythonic-thinking)
  - [Item 1: Know Which Version of Python You're Using](#item-1-know-which-version-of-python-youre-using)
  - [Item 3: Know the Differences Between `bytes`, `str` and `unicode`](#item-3-know-the-differences-between-bytes-str-and-unicode)
  - [Item 4: Write Helper Functions Instead of Complex Expressions](#item-4-write-helper-functions-instead-of-complex-expressions)
  - [Item 5: Know How to Slice Sequences](#item-5-know-how-to-slice-sequences)
  - [Item 6: Avoid Using `start`, `end` and `stride` in a Single Slice](#item-6-avoid-using-start-end-and-stride-in-a-single-slice)
  - [Item 7: Use List Comprehensions Instead of map and filter](#item-7-use-list-comprehensions-instead-of-map-and-filter)
  - [Item 8: Avoid More Than Two Expressions in List Comprehensions](#item-8-avoid-more-than-two-expressions-in-list-comprehensions)
  - [Item 10: Prefer `enumerate` Over `range`](#item-10-prefer-enumerate-over-range)
  - [Item 11: Use `zip` to Process Iterators in Parallel](#item-11-use-zip-to-process-iterators-in-parallel)
  - [Item 12: Avoid `else` Blocks After `for` and `while` Loops](#item-12-avoid-else-blocks-after-for-and-while-loops)
* [Functions](#2-functions)

  - [Item 14: Prefer Exceptions to Returning `None`](#item-14-prefer-exceptions-to-returning-none)

## 1. Pythonic Thinking

### Item 1: Know Which Version of Python You're Using

* Check which version of Python you are using:

  - From the command line: `python --version`
  - Inside Python: `import sys; print(sys.version)`

* Prefer Python 3 over Python 2.


### Item 3: Know the Differences Between `bytes`, `str` and `unicode`

* **Python 3**: two types represent sequences of characters:
  - `bytes`: contain raw 8-bit values.
  - `str`: contain Unicode characters.

* **Python 2**: two types represent sequences of characters:
  - `str`: contain raw 8-bit values.
  - `unicode`: contain Unicode characters.
  
* `str` instances in Python 2 and `unicode` instances in Python 3 do not have an associated binary encoding.

* The `encode` method converts Unicode chars to binary data.

* The `decode` method converts binary data to Unicode chars.

* In Python 3, UTF-8 is the default encoding when dealing with files handles. In Python 2, file operations use binary encoding. To read/write binary data to files with Python 3, use the `'rb'`/`'wb'` modes.


### Item 4: Write Helper Functions Instead of Complex Expressions

* Python syntax allows us to write very complex expressions in dense blocks of code. These blocks are hard to read, understand and maintain.

* Complex expressions should be written inside helper functions. This will keep the code more readable and maintainable.

* `if` / `else` expressions are more readable than using Boolean operators (e.g. `or`, `and`) in expressions.


### Item 5: Know How to Slice Sequences

* Avoid using `0` to index the start of a list and `len(somelist)` to index its end.

* Slicing deals with indices that are outside of the list boundaries. Errors aren't generated in these cases.

* When assigning to a slice, the slice will be replaced by the right-hand side operand of the assignment. The the right-hand side operand size can be different from the slice size.


### Item 6: Avoid Using `start`, `end` and `stride` in a Single Slice

* Specifying `start`, `end` and `stride` in a slice can be confusing.

* Avoid negative stride values as they are confusing. If possible, use positive stride values without `start` or `end` indices.

* If you need to use `start`, `end` and `stride` in a single slice, it's better to use two assignments: one to slice and another to stride.


### Item 7: Use List Comprehensions Instead of map and filter

* List comprehensions are clearer than `map` and `filter` as they don't require `lambda` expressions.

* List comprehensions can be used for mapping and filtering.

* Dictionaries and sets can also use comprehensions.


### Item 8: Avoid More Than Two Expressions in List Comprehensions

* List comprehensions support multiple levels of looping.

* List comprehensions with more than two expressions should be avoided. `if`s and `for`s should be used instead.


### Item 10: Prefer `enumerate` Over `range`

* If you want to iterate a list and get the index of the elements, use `enumerate` instead of `range`:

```
for i in some_list:
    print("{}: {}".format(i, some_list[i]))
```
```
for i, element in enumerate(some_list):
    print("{}: {}".format(i, element))
```


### Item 11: Use `zip` to Process Iterators in Parallel

* If you want to iterate multiple iterators simultaneously, use `zip` (or `izip` from `itertools` for Python 2).

* `zip` truncates iterators that are larger than the smallest provided iterator. Use `zip_longest` from `itertools` to iterate through everything.

* **Python 3**: `zip` is a lazy generator that produces tuples.

* **Python 2**: `zip` is not a generator, so the full result as a list of tuples is returned. Instead, use `izip` from `itertools`.


### Item 12: Avoid `else` Blocks After `for` and `while` Loops

* It's possible to use `else` after `for` and `while` loops to check if these loops ended. That is, if the loops were not broken.

* This should be avoided as the behavior can be confusing. Instead, write helper functions.

## 2. Function


### Item 14: Prefer Exceptions to Returning `None`

* To handle an error inside a function, don't return `None`. Instead, raise exceptions to indicate special situations.
