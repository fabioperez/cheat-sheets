## Table of Contents

* [Pythonic Thinking](#1-pythonic-thinking)
  - [Item 1: Know Which Version of Python You're Using](#item-1-know-which-version-of-python-youre-using)
  - [Item 2: Follow the PEP 8 Style Guide](#item-2-follow-the-pep-8-style-guide)
  - [Item 3: Know the Differences Between `bytes`, `str` and `unicode`](#item-3-know-the-differences-between-bytes-str-and-unicode)
  - [Item 4: Write Helper Functions Instead of Complex Expressions](#item-4-write-helper-functions-instead-of-complex-expressions)
  - [Item 5: Know How to Slice Sequences](#item-5-know-how-to-slice-sequences)
  - [Item 6: Avoid Using `start`, `end` and `stride` in a Single Slice](#item-6-avoid-using-start-end-and-stride-in-a-single-slice)
  - [Item 7: Use List Comprehensions Instead of map and filter](#item-7-use-list-comprehensions-instead-of-map-and-filter)
  - [Item 8: Avoid More Than Two Expressions in List Comprehensions](#item-8-avoid-more-than-two-expressions-in-list-comprehensions)
  - [Item 9: Consider Generator Expressions for Large Comprehensions](#item-9-consider-generator-expressions-for-large-comprehensions)
  - [Item 10: Prefer `enumerate` Over `range`](#item-10-prefer-enumerate-over-range)
  - [Item 11: Use `zip` to Process Iterators in Parallel](#item-11-use-zip-to-process-iterators-in-parallel)
  - [Item 12: Avoid `else` Blocks After `for` and `while` Loops](#item-12-avoid-else-blocks-after-for-and-while-loops)
  - [Item 13: Take Advantage of Each Block in `try`/`except`/`else`/`finally`](#item-13-take-advantage-of-each-block-in-tryexceptelsefinally)

* [Functions](#2-functions)
  - [Item 14: Prefer Exceptions to Returning `None`](#item-14-prefer-exceptions-to-returning-none)
  - [Item 15: Know How Closures Interact with Variable Scope](#item-15-know-how-closures-interact-with-variable-scope)
  - [Item 16: Consider Generators Instead of Returning Lists](#item-16-consider-generators-instead-of-returning-lists)
  - [Item 18: Reduce Visual Noise with Variable Positional Arguments](#item-18-reduce-visual-noise-with-variable-positional-arguments)
  - [Item 19: Provide Optional Behavior with Keyword Arguments](#item-19-provide-optional-behavior-with-keyword-arguments)
  - [Item 20: Use `None` and Docstrings to Specify Dynamic Default Arguments](#item-20-use-none-and-docstrings-to-specify-dynamic-default-arguments)
  - [Item 21: Enforce Clarity With Keyword-Only Arguments](#item-21-enforce-clarity-with-keyword-only-arguments)
  
* [Classes and Inheritance](#3-classes-and-inheritance)
  - [Item 22: Prefer Helper Classes Over Bookkeeping with Dictionaries and Tuples](#item-22-prefer-helper-classes-over-bookkeeping-with-dictionaries-and-tuples)
  - [Item 23: Accept Functions for Simple Interface Instead of Classes](#item-23-accept-functions-for-simple-interface-instead-of-classes)
  - [Item 24: Use `@classmethod` Polymorphism to Construct Objects Generically](#item-24-use-classmethod-polymorphism-to-construct-objects-generically)
  - [Item 25: Initialize Parent Classes with `super`](#item-25-initialize-parent-classes-with-super)
  - [Item 26: Use Multiple Inheritance Only for Mix-in Utility Classes](#item-26-use-multiple-inheritance-only-for-mix-in-utility-classes)
  - [Item 27: Prefer Public Attributes Over Private Ones](#item-27-prefer-public-attributes-over-private-ones)
  - [Item 28: Inherit from `collections.abc` for Custom Container Types](#item-28-inherit-from-collectionsabc-for-custom-container-types)
  
* [Metaclasses and Attributes](#4-metaclasses-and-attributes)
  - [Item 29: Use Plain Attributes Instead of Get and Set Methods](#item-29-use-plain-attributes-instead-of-get-and-set-methods)
  - [Item 30: Consider `@property` Instead of Refactoring Attributes](#item-30-consider-property-instead-of-refactoring-attributes)
  
* [Built-in Modules](#6-built-in-modules)
  - [Item 42: Define Function Decorators with `functools.wraps`](#item-42-define-function-decorators-with-functoolswraps)
  - [Item 43: Consider contextlib and `with` Statements for Reusable `try`/`finally` Behavior](#item-43-consider-contextlib-and-with-statements-for-reusable-tryfinally-behavior)
  - [Item 44: Make `pickle` Reliable with `copyreg`](#item-44-make-pickle-reliable-with-copyreg)
  - [Item 47: Use `decimal` When Precision Is Paramount](#item-47-use-decimal-when-precision-is-paramount)
  - [Item 48: Know Where to Find Community-Built Modules](#item-48-know-where-to-find-community-built-modules)

* [Collaboration](#7-collaboration)
  - [Item 49: Write Docstrings for Every Function, Class, and Module](#item-49-write-docstrings-for-every-function-class-and-module)
  - [Item 53: Use Virtual Environments for Isolated and Reproducible Dependencies](#item-53-use-virtual-environments-for-isolated-and-reproducible-dependencies)

* [Production](#8-production)
  - [Item 55: Use repr Strings for Debugging Output](#item-55-use-repr-strings-for-debugging-output)
  - [Item 57: Consider Interactive Debugging with pdb](#item-57-consider-interactive-debugging-with-pdb)

## 1. Pythonic Thinking


### Item 1: Know Which Version of Python You're Using

* Check which version of Python you are using:

  - From the command line: `python --version`
  - Inside Python: `import sys; print(sys.version)`

* Prefer Python 3 over Python 2.


### Item 2: Follow the PEP 8 Style Guide

* Follow the [PEP 8](https://www.python.org/dev/peps/pep-0008/) style guide.


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


### Item 9: Consider Generator Expressions for Large Comprehensions

* List comprehensions create a new list, so they can be very slow for complex operations and can consume too much memory for large inputs.

* For these cases, use generator expressions instead of list comprehensions, since they act as iterators.

*  Generator expressions can be chained by using one expression inside another. This works very quickly.


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


### Item 13: Take Advantage of Each Block in `try`/`except`/`else`/`finally`

* The `finally` is executed even if an exception is raised.

* When `try` does not raise an exception, the `else` block will run.

* The `else` block ensures that some code won't be accidentally caught by the `except` block.


## 2. Functions


### Item 14: Prefer Exceptions to Returning `None`

* To handle an error inside a function, don't return `None`. Instead, raise exceptions to indicate special situations.


### Item 15: Know How Closures Interact with Variable Scope

* Functions can be nested.

* Functions are [first-class objects](https://stackoverflow.com/questions/245192/what-are-first-class-objects) in Python, so you can pass them as arguments to other functions.

* Nested functions can access local variables from the enclosing scope. If they do that when they are executed outside of this scope, they are called *closures*.

* Closures can't modify variables from the enclosing scope unless you declare them as `nonlocal` (Python 3). Python 2 doesn't support `nonlocal`, so lists -- since they are mutable -- can be used instead.

* `nonlocal` shoud be avoided if the closure behavior starts to get complex. Instead, classes can be used (see Item 23).


### Item 16: Consider Generators Instead of Returning Lists

* When creating a function that returns a large sequence of results, consider using a generator instead of a list.


### Item 18: Reduce Visual Noise with Variable Positional Arguments

* Python functions can have arbitrary positional arguments. To do so, use  `*args` as an argument to a function.

* Lists and tuples can be unpacked with the `*` operator.

* Using the `*` operator with generators can be hazardous, as the entire generator will be consumed before calling the function.

* Adding new positional parameters to functions with `*args` will require a change in every place that calls the function.


### Item 19: Provide Optional Behavior with Keyword Arguments

* Arguments can be passed by position or by keyword.

* Positional arguments must be specified before keyword arguments.

* Keyword arguments improve code readability.

* Some arguments can have a default value. Arguments that have a default value are optional.
    ```
    def func(a, b, c=20):
       print(a, b, c)

    func(1, 2)
    # 1 2 20

    func(1)
    # TypeError: func() missing 1 required positional argument: 'b'
    ```
     
* If an existing function is to be modified, use keyword arguments so you don't have to rewrite the existing calls to this functions.


### Item 20: Use `None` and Docstrings to Specify Dynamic Default Arguments

* Default arguments are evaluated only during the function definition when a module is loaded.

* Don't use dynamic values (functions, lists, dicts) as default arguments.

* Instead, use a default value of `None`, and inside the function modify the argument value if it is `None`. Use Docstrings to document default values.


### Item 21: Enforce Clarity With Keyword-Only Arguments

* In Python 3, to enforce the use of keyword-only arguments instead of positional ones, use `*` as the end of positional arguments.
    ```
    def some_func(a, b, c, *, d=0, e=1):
      print(a, b, c, d, e)  
     
    some_func(1, 2, 3)
    # 1 2 3 0 1
    
    some_func(1, 2, 3, 4) 
    # TypeError: some_func() takes 3 positional arguments but 4 were given
    ``` 
   
* Use `**kwargs` as an argument to a function that will receive a variable number of keyword arguments.

* The `**` operator can be used in dictionaries to unpack them to keyword arguments.


## 3. Classes and Inheritance

### Item 22: Prefer Helper Classes Over Bookkeeping with Dictionaries and Tuples

* Dictionarys are good for simple bookkeeping. However, the code can get messy if a more complex bookkeeping is necessary (e.g. dictionaries as values of other dictionary).

*  [`namedtuple`](https://docs.python.org/3/library/collections.html#collections.namedtuple) can be used as a simple data container, but it has some limitations: no default arguments; attributes accessible trough numerical indexes.


### Item 23: Accept Functions for Simple Interface Instead of Classes

* Functions accept functions as arguments (functions are first-class objects).

* Functions can keep state with stateful closures, but they are not very readable.

* The [`__call__`](https://docs.python.org/3/reference/datamodel.html#object.__call__) method allows objects to be called like functions.

* Use classes that implement `__call__` when a function that maintains state is needed.


### Item 24: Use `@classmethod` Polymorphism to Construct Objects Generically

* Python only supports one `__init__` (constructor) per class.

* Use `@classmethod` to define alternative constructors to classes. Class methods receive a class as their first parameter, allowing the construction of new instances. This allows the creation of objects in addition to `__init__`.


### Item 25: Initialize Parent Classes with `super`

* It's possible to call superclass constructors with ClassName.__init__(), but this may cause issues such as the diamond problem and confusion with the ordering of the calls.

* Instead, we should use `super().__init()__`. It solves the diamond problem by calling comon superclasses' `__init__`s only once and respecting the MRO (Method Resolution Order) for all superclasses.

* In Python 2, it's necessary to pass the class name and `self` to `super` (e.g. `super(ClassName, self).__init()__`). In Python 3, these arguments aren't needed (`super().__init()__`).

* To see the MRO of a class, run `ClassName.mro()`.


### Item 26: Use Multiple Inheritance Only for Mix-in Utility Classes

* Avoid multiple inheritance.

* Use [Mix-ins](https://stackoverflow.com/questions/533631/what-is-a-mixin-and-why-are-they-useful) to provide features to a class.

* Mix-ins can be composed (using multiple inheritance) to extend the classes behaviors.

* Override Mix-in methods in derived classes if necessary.


### Item 27: Prefer Public Attributes Over Private Ones

* Private attributes are defined by starting them with `__` (e.g. `__private_func()`). Python makes them private by renaming them to `_<ClassName>__<attribute_name>`, so they can be accessed if wanted (this can be checked with `instance.__dict__`).

* Fields starting with `_` are defined as protected by the PEP-8 convention. This means that these fields should be used externally with care.

* It's a good practice to document protected attributes to guide subclasses and instead of restrict they as private.

* Only use private attributes to avoid naming problems.


### Item 28: Inherit from `collections.abc` for Custom Container Types

* Sometimes, we want to extend some built-in types (e.g. creating a `list` with additional features). To do so, we can create a class that inherits from the desired type.

* Other times, you don't want to create subclasses of types, but want similar behaviors. For instance, you want to have sequence semantics but for data types that are not lists (e.g. trees). To do so, you can implement some special methods such as [`__getitem__`](https://docs.python.org/3/reference/datamodel.html#object.__getitem__) and [`__len__`](https://docs.python.org/3/reference/datamodel.html#object.__len__).

* To implement custom containers, use "abstract base classes" ([`collections.abc`](https://docs.python.org/3/library/collections.abc.html). This will require that you implement some abstract methods.

* `collections.abc` also provides mixins for your containers.


## 4. Metaclasses and Attributes


### Item 29: Use Plain Attributes Instead of Get and Set Methods

* Don't write getters / setters in Python. Instead, define public attributes on `__init__`.

*  Use the `@property` decorator and its corresponding `setter` to add special behavior (type checking, value checking, modifying internal state etc.) to attributes.

*  Avoid weird side effects when using `@property`.

*  Don't use slow / complex behaviors with `@property`.


### Item 30: Consider `@property` Instead of Refactoring Attributes

* Extend existing attributes functionality with `@property`.

* Refactor a class when it uses `@property` too much.


## 6. Built-in Modules


### Item 42: Define Function Decorators with `functools.wraps`

* Decorators add extra functionality to functions. It's possible to do something everytime -- before and after -- a function is called.

* Use [`functools.wraps`](https://docs.python.org/3/library/functools.html#functools.wraps) as a decorator to your own decorators. This will make `help()` and `type()` return the expected results for a decorated function.


### Item 43: Consider contextlib and `with` Statements for Reusable `try`/`finally` Behavior

* The [with](https://docs.python.org/3/reference/compound_stmts.html#the-with-statement) statement is used to wrap the execution of a block with methods defined by a [context manager](https://docs.python.org/3/reference/datamodel.html#context-managers).

* The `with` statement is a more convenient way to run a code in a special context (that requires preparation and cleanup) than `try`/`except`/`finally` statements.

* Context managers can be implemented by defining the methods `__enter__` and `__exit__` for a class.

* To implement a context manager for a function without defining a new class, use the [`contextmanager`](https://docs.python.org/3/library/contextlib.html#contextlib.contextmanager) decorator from [`contextlib`](https://docs.python.org/3/library/contextlib.html) (`from contextlib import contextmanager`). This allows the function to be used in `with` statements.

* A `with` statement can have a target, defined as a variable that goes after the `as` in a with statement.

    ```with open('file.txt', 'w') as f:``` 

References:
* https://stackoverflow.com/questions/3012488/what-is-the-python-with-statement-designed-for
* https://stackoverflow.com/questions/1984325/explaining-pythons-enter-and-exit


### Item 44: Make `pickle` Reliable with `copyreg`

* The [`pickle`](https://docs.python.org/3/library/pickle.html) module can be used to serialize/deserialize objects in Python.

* The `pickle` module is unsafe (in constrast, JSON is safe), so a Python program should only unpickle data from a trusted source.

* If you modify a class (e.g., add/remove attributes, rename the class etc.), unpickling a pickle of it may break the code. To prevent this, use [`copyreg`](https://docs.python.org/3/library/copyreg.html) to register pickle support functions.


### Item 47: Use `decimal` When Precision Is Paramount

* Python has a built-in module for fast correctly-rounded decimal floating point arithmetic: [`decimal`](https://docs.python.org/3/library/decimal.html). Use it when numerical precision and exact rounding is desired.


### Item 48: Know Where to Find Community-Built Modules

* Python has a central repository of modules, created and maintained by the community: the Python Package Index - PyPI (https://pypi.python.org/pypi).

* Use `pip` and `pip3` (Python 3) to install and manage packages from PyPI.

* `pip` is installed by default in Python 3.4.


## 7. Collaboration


### Item 49: Write Docstrings for Every Function, Class, and Module

* Python provides built-in support for attaching documentation to blocks of code. The documentation is available as the program runs with the `__doc__` attribute.

* The `help` built-in function can be used to display the documentation in the interactive interpreter.

* Docstrings can be converted to more readable formats with tools such as Sphinx.

* Write documentation for every module, class and function. Keep them updated. If necessary, use [`doctest`](https://docs.python.org/3/library/doctest.html).

* Try to follow [PEP 257 -- Docstring Conventions](https://www.python.org/dev/peps/pep-0257/).


### Item 53: Use Virtual Environments for Isolated and Reproducible Dependencies

* `pip` installs new packages globally.

* Python can only have a single global version of a module installed.

* `venv` (available in Python 3.4) or `virtualenv` (needs to be installed) can be used to create isolated versions of the Python environment, making environments reproducible.

* When using `venv`, packages are installed locally with `pip`.

* It's possible to dump all requirements of an environment with `pip freeze > requirements.txt`. To install from `requirements.txt`, use `pip install -r requirements.txt`.

* Check [virtualenv.md](virtualenv.md) for more information.


## 8. Production


### Item 55: Use repr Strings for Debugging Output

* [`print()`](https://docs.python.org/3/library/functions.html#print) is often used for debugging since it prints the human-readable string version of an object.However, `print()` hides type information, which can be useful sometimes.

* [`repr()`](https://docs.python.org/3/library/functions.html#repr) returns a string that contains a printable representation of an object. These strings can be evaluated as Python code with [`eval()`](https://docs.python.org/3/library/functions.html#eval).

* To have objects compatible with `str()` and `print()`, a class must implement the [`__str__`](https://docs.python.org/3/reference/datamodel.html#object.__str__) method.

* To have objects compatible with `repr()`, a class must implement the [`__repr__`](https://docs.python.org/3/reference/datamodel.html#object.__repr__) method.

* To provide the printable representation of an object of a class, implement the [`__repr__`](https://docs.python.org/3/reference/datamodel.html#object.__repr__) method.

* To print the public attributes of an object, use [`__dict__`](https://docs.python.org/3/library/stdtypes.html#object.__dict__).


### Item 57: Consider Interactive Debugging with pdb

* To debug a program in Python, use [pdb](https://docs.python.org/3/library/pdb.html).

* The program will stop where you put the following line and it will open the Python shell:
  ```import pdb; pdb.set_trace()```
  
* It's possible to run some debugging commands such as `bt` (traceback); `up` and `down` (move scope along call stack); `step`, `next`, `return`, `continue` to continue with the execution of the program. It's also possible to run new Python commands and modify the state of the program.
