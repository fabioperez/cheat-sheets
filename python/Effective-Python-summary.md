## Table of Contents

* Pythonic Thinking
  - [Item 3: Know the Differences Between `bytes`, `str` and `unicode`](#Item-3-Know-the-Differences-Between-bytes-str-and-unicode)

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
