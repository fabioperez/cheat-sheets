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
  - [Item 17: Be Defensive When Iterating Over Arguments](#item-17-be-defensive-when-iterating-over-arguments)
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
  - [Item 31: Use Descriptors for Reusable `@property` Methods](#item-31-use-descriptors-for-reusable-property-methods)
  - [Item 32: Use `__getattr__`, `__getattribute__`, and `__setattr__` for Lazy Attributes](#item-32-use-__getattr__-__getattribute__-and-__setattr__-for-lazy-attributes)
  - [Item 33: Validate Subclasses with Metaclasses](#item-33-validate-subclasses-with-metaclasses)
  - [Item 34: Register Class Existence with Metaclasses](#item-34-register-class-existence-with-metaclasses)
  - [Item 35: Annotate Class Attributes with Metaclasses](#item-35-annotate-class-attributes-with-metaclasses)
  
* [Built-in Modules](#6-built-in-modules)
  - [Item 42: Define Function Decorators with `functools.wraps`](#item-42-define-function-decorators-with-functoolswraps)
  - [Item 43: Consider contextlib and `with` Statements for Reusable `try`/`finally` Behavior](#item-43-consider-contextlib-and-with-statements-for-reusable-tryfinally-behavior)
  - [Item 44: Make `pickle` Reliable with `copyreg`](#item-44-make-pickle-reliable-with-copyreg)
  - [Item 45: Use `datetime` Instead of `time` for Local Clocks](#item-45-use-datetime-instead-of-time-for-local-clocks)
  - [Item 46: Use Built-in Algorithms and Data Structures](#item-46-use-built-in-algorithms-and-data-structures)
  - [Item 47: Use `decimal` When Precision Is Paramount](#item-47-use-decimal-when-precision-is-paramount)
  - [Item 48: Know Where to Find Community-Built Modules](#item-48-know-where-to-find-community-built-modules)

* [Collaboration](#7-collaboration)
  - [Item 49: Write Docstrings for Every Function, Class, and Module](#item-49-write-docstrings-for-every-function-class-and-module)
  - [Item 50: Use Packages to Organize Modules and Provide Stable APIs](#item-50-use-packages-to-organize-modules-and-provide-stable-apis)
  - [Item 51: Define a Root `Exception` to Insulate Callers from APIs](#item-51-define-a-root-exception-to-insulate-callers-from-apis)
  - [Item 52: Know How to Break Circular Dependencies](#item-52-know-how-to-break-circular-dependencies)
  - [Item 53: Use Virtual Environments for Isolated and Reproducible Dependencies](#item-53-use-virtual-environments-for-isolated-and-reproducible-dependencies)

* [Production](#8-production)
  - [Item 55: Use repr Strings for Debugging Output](#item-55-use-repr-strings-for-debugging-output)
  - [Item 56: Test Everything with `unittest`](#item-56-test-everything-with-unittest)
  - [Item 57: Consider Interactive Debugging with pdb](#item-57-consider-interactive-debugging-with-pdb)
  - [Item 59: Use `tracemalloc` to Understand Memory Usage and Leaks](#item-59-use-tracemalloc-to-understand-memory-usage-and-leaks)

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



### Item 17: Be Defensive When Iterating Over Arguments

* An iterator produces its results a single time only.

* When an iterator does not have more items to be iterated, it will produce a [`StopIteration`](https://docs.python.org/3/library/exceptions.html#StopIteration) exception on the next [`next`](https://docs.python.org/3/library/functions.html#next) call.

* No errors are produced when an exhausted iterator is iterated with `for`.

* One solution is making a copy of the iterator by calling it as an argument to list(). However, this will consume the entire iterator, which may be inefficient and cause memory errors.

* A better alternative is to provide a new container class implementing the [iterator protocol](https://docs.python.org/3/library/stdtypes.html#iterator-types).

#### Iterator vs iterable

> An **iterable** is an object that has an `__iter__` method which returns an **iterator**, or which defines a `__getitem__` method that can take sequential indexes starting from zero (and raises an `IndexError` when the indexes are no longer valid). So an *iterable* is an object that you can get an iterator from.
> An **iterator** is an object with a [`next`](https://docs.python.org/2/library/stdtypes.html#iterator.next) (Python 2) or [`__next__`](https://docs.python.org/3/library/stdtypes.html#iterator.__next__) (Python 3) method.
> Whenever you use a `for` loop, or `map`, or a list comprehension etc. in Python, the next method is called automatically to get each item from the **iterator**, thus going through the process of **iteration**.
> [Source](https://stackoverflow.com/questions/9884132/what-exactly-are-pythons-iterator-iterable-and-iteration-protocols)

Example: [lists are iterables, but not iterators](https://stackoverflow.com/questions/13054057/confused-with-python-lists-are-they-or-are-they-not-iterators).


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

*  Use the [`@property`](https://docs.python.org/3/library/functions.html#property) decorator and its corresponding `setter` to add special behavior (type checking, value checking, modifying internal state etc.) to attributes.

*  Avoid weird side effects when using `@property`.

*  Don't use slow / complex behaviors with `@property`.


### Item 30: Consider `@property` Instead of Refactoring Attributes

* Extend existing attributes functionality with `@property`.

* Refactor a class when it uses `@property` too much.


### Item 31: Use Descriptors for Reusable `@property` Methods

* When you read an attribute of a Python object -- let's say `obj.attr`, Python will lookup the value in the object dictionary (`obj.__dict__['attr']`). If it doesn't found it, it will look in the class (`type(obj).__dict__['attr']`) dict, and then it will continue through the base classes of `type(obj)`.

* Objects that have a definition for any of [`__get__()`](https://docs.python.org/3/reference/datamodel.html#object.__get__), [`__set__()`](https://docs.python.org/3/reference/datamodel.html#object.__set__), or [`__delete__()`](https://docs.python.org/3/reference/datamodel.html#object.__delete__) are called [descriptors](https://docs.python.org/3/howto/descriptor.html). These special functions can define additional behavior for when you get, set or delete an object.

* When reading the attribute of an object that has `__get__()` defined, instead of only accessing the value of the attribute in the dict, `__get__()` will be executed: `obj.__dict__['attr'].__get__(obj, type(obj))`. The behaviors for `__set__()` and `__delete__()`.

* Descriptors work like the `@property` decorator, but can be reused.

* If you set a class member as a descriptor class, be careful when using `__get__()`, `__set__()`, and `__delete__()`. It may be necessary to store values in a dictionary where the keys are the instance of the class who has the decorators as class members.

* Use a [`WeakKeyDictionary`](https://docs.python.org/3/library/weakref.html) to keep avoid memory leaks when bookkeeping with descriptors.


### Item 32: Use `__getattr__`, `__getattribute__`, and `__setattr__` for Lazy Attributes

* [`__getattr__`](https://docs.python.org/3/reference/datamodel.html#object.__getattr__) is called every  time an attribute can't be found in an object's instance dictionary (that is, the object attributes). It's not called if the attribute exists. More formally, it is called when the default attribute access raises an `AttributeError`.

* [`__getattribute__`](https://docs.python.org/3/reference/datamodel.html#object.__getattribute__) is called every time an attribute is accessed, even if it exists in `__dict__`. `__getattr__` will be called if `__getattribute__` raises `AttributeError` or explicitly calls it.

* [`__setattr__`](https://docs.python.org/3/reference/datamodel.html#object.__setattr__) is called every time an attribute is assigned to an object.

* `__getattr__` can be used for lazy initialization. That is, it can be used to add an attribute on its first access.

* `__getattribute__` is called every time an object's attribute is accessed, even if they exist in the attribute dictionary. It's called by the [`hasattr`](https://docs.python.org/3/library/functions.html#hasattr) and [`getattr`]((https://docs.python.org/3/library/functions.html#getattr)) methods.

* To avoid infinite recursion in `__getattribute__` and `__setattr__`, call these methods from `super()` for subclasses.

* [`setattr`](https://docs.python.org/3/library/functions.html#setattr) adds an attribute to an object. `setattr(x, 'foobar', 123)` is equivalent to `x.foobar = 123`.

* [`getattr`](https://docs.python.org/3/library/functions.html#getattr) gets the value of an attribute. `getattr(x, 'foobar')` is equivalent to `x.foobar`.


### Item 33: Validate Subclasses with Metaclasses

* [Metaclasses](https://docs.python.org/3/reference/datamodel.html#metaclasses) are defined by inheriting from `type`.

* Metaclasses are associated with classes by passing the `metaclass` argument to class definitions. Example: `class Foo(metaclass=MetaFoo):`.

* Metaclasses have access to the name of the class, the parent classes, and all class attributes defined in the class's body.

*  Metaclasses can be used to enforce style and behavior in classes.

See also: [What are metaclasses in Python?
](https://stackoverflow.com/questions/100003/what-are-metaclasses-in-python/6581949)


### Item 34: Register Class Existence with Metaclasses

* [`__new__`](https://docs.python.org/3/reference/datamodel.html#object.__new__) is used to create an instance of a class (i.e. an object). [`__init__`](https://docs.python.org/3/reference/datamodel.html#object.__init__) is called right after the creation of an instance, and it is used to initialize it.

* Class registration can be automatically performed with metaclasses and the `__new__` method.


### Item 35: Annotate Class Attributes with Metaclasses

* Metaclasses can be used to annotate or modify properties after a class is defined, but before it is used.


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


### Item 45: Use `datetime` Instead of `time` for Local Clocks

* Use the [`datetime`](https://docs.python.org/3/library/datetime.html) built-in module to operate with time zones.

* `datetime` has more features than [`time`](https://docs.python.org/3/library/time.html).

* `datetime` doesn't have all time zones. To work with alternative time zones, use `pytz` or `pendulum`.

* Always represent and store time in UTC and do time zone conversion as the last step, when necessary.

References
* https://stackoverflow.com/questions/7479777/difference-between-python-datetime-vs-time-modules


### Item 46: Use Built-in Algorithms and Data Structures

* Python has several algorithms and data structures already implemented as built-in modules.

* They are well-maintained and tested, so it's better to use them instead of implementing from scratch (unless you want to create optimized versions, or for practicing).

* Some examples are: [OrderedDict](https://docs.python.org/3/library/collections.html#collections.OrderedDict), [Double-Ended Queue (deque)](https://docs.python.org/3/library/collections.html#collections.deque), [defaultdict](https://docs.python.org/3/library/collections.html#collections.defaultdict), [Heap Queue (heapq)](https://docs.python.org/3/library/heapq.html), [bisect](https://docs.python.org/3/library/bisect.html), and [itertools](https://docs.python.org/3/library/itertools.html).


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


### Item 50: Use Packages to Organize Modules and Provide Stable APIs

* Packages are defined by adding an `__init__.py` file in a directory.

* Packages are modules that contain other modules.

* A module is a single file, whereas a package is a collection of modules in an hierarchy.

* [PEP 420](https://www.python.org/dev/peps/pep-0420/) introduces Implicit Namespace Packages.

* The first use of packages is to help divide your modules into separated namespaces.

* Packages can be aliased:

    ```
    from package_a.utils import func1
    from package_b.utils import func1 as func1_b
    ```

* The second use of packages is to provide stable APIs.

* The default behaviour of `from foo import *` is to load every symbol that doesn't start with `_`.

* Python can limit APIs by using the `__all__` special attribute. `__all__` is a list of every name that will be accessible in the public API (`from foo import *`).

* Avoid `from foo import *`: 
  * `import *` hides source names for new readers of the code.
  * `import *` overwrites conflicting names.

* Instead, import the top-level module, and use it as a prefix (e.g. `import foo; foo.func`).


### Item 51: Define a Root `Exception` to Insulate Callers from APIs

* Python has a builtin hierarchy of exceptions for the language and the standard library.

* For APIs, it's better to define your own hierarchy of `Exception`s instead of using builtin exceptions (e.g. `class MyAPIException(Exception)`).

* Having a root exception in a module makes it easy for API users to catch all exceptions raised by the API.

* If API users catch a root API, they can investigate if they should be catching a more specific exception instead, and thus using the API more correctly.

* If a non-root exception is thrown by the API, there's a bug in its implementation. Root Exceptions make it easier to find these bugs.


### Item 52: Know How to Break Circular Dependencies

* When a module is imported, Python will search in the following order:
    1. Searches for the module in locations from `sys.path`.
    2. Loads the code from the module and ensures it compiles.
    3. Creates a corresponding empty module object.
    4. Inserts the module into `sys.modules`.
    5. Run the code in the module object to define its contents.

* Circular dependencies may occur. Example: In file `foo.py`, you `import bar`, and in file `bar.py` you `import foo`. This will throw an `AttributeError`.

* One solution to circular dependencies is to add imports in the middle of a source code. However, this goes against PEP-8.

* A second solution is to avoid running code inside modules. Only define functions, classes, and constants. Then, you define a configure function that will be called after every import. Example:

    ```
    import foo
    import bar

    foo.configure()
    bar.configure()
    ```

* The third and simplest solution is to do **dynamic imports**, that is, imports inside functions. However, this should be avoided since the overhead of running imports inside functions can make the code slow when used in loops.

* The best solution is to refactor mutual dependencies into a separated module.


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


### Item 56: Test Everything with `unittest`

* Use the [`unittest`](https://docs.python.org/3/library/unittest.html) builtin module to create unit tests.

* Tests can be defined by inheriting from [`TestCase`](https://docs.python.org/3/library/unittest.html#unittest.TestCase).

* To define an unit test, create a method inside the class with its name starting with `test`.

* Write unit tests AND integration tests.

* [`setUp`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.setUp), and [`tearDown`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.tearDown) may be used to provide behaviors before and after all tests from a test class run.

* Python 3 has a builtin module to create mock objects for testing: [`unittest.mock`](https://docs.python.org/3/library/unittest.mock.html).


### Item 57: Consider Interactive Debugging with pdb

* To debug a program in Python, use [pdb](https://docs.python.org/3/library/pdb.html).

* The program will stop where you put the following line and it will open the Python shell:
  ```import pdb; pdb.set_trace()```
  
* It's possible to run some debugging commands such as `bt` (traceback); `up` and `down` (move scope along call stack); `step`, `next`, `return`, `continue` to continue with the execution of the program. It's also possible to run new Python commands and modify the state of the program.

### Item 59: Use `tracemalloc` to Understand Memory Usage and Leaks

* CPython uses reference counting and cycle-detection for memory management.

* The [`gc`](https://docs.python.org/3/library/gc.html) module provides an interface to Python's garbage collector.

* `gc.get_objects()` lists every object known to the garbage collector. However, it doesn't tell anything about the allocation of these objects.

* Python 3.4 introduced the [`tracemalloc`](https://docs.python.org/3/library/tracemalloc.html) module, which has the capability of tracing back to the allocation of an object. 
