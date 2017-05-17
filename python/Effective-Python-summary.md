## Table of Contents

* [Pythonic Thinking](#1-pythonic-thinking)
  - [Item 3: Know the Differences Between `bytes`, `str` and `unicode`](#item-3-know-the-differences-between-bytes-str-and-unicode)
  - [Item 7: Use List Comprehensions Instead of map and filter](#item-7-use-list-comprehensions-instead-of-map-and-filter)
  - [Item 8: Avoid More Than Two Expressions in List Comprehensions](#item-8-avoid-more-than-two-expressions-in-list-comprehensions)

## 1. Pythonic Thinking

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

* In Python 3, UTF-8 is the default encoding when dealing with files handles.
In Python 2, file operations use binary encoding. To read/write binary data
to files with Python 3, use the `'rb'`/`'wb'` modes.

### Item 7: Use List Comprehensions Instead of map and filter

* List comprehensions are clearer than `map` and `filter` as they don't require `lambda` expressions.

* List comprehensions can be used for mapping and filtering.

* Dictionaries and sets can also use comprehensions.

### Item 8: Avoid More Than Two Expressions in List Comprehensions

* List comprehensions support multiple levels of looping.

* List comprehensions with more than two expressions should be avoided. `if`s and `for`s should be used instead.
