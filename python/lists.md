# Python lists

### basics
```
l = []
l = list() # slower than []

l = [1, 2, 3]
print(l[0]) # 1

l[1] = 1000
print(l) # [1, 1000, 3]

# check if a list is empty
if l:
  print("Not empty")
if not l:
  print("Empty")
```

### for / in

```
letters = ['a', 'b', 'c']
for l in letters:
    print(l)
# a
# b
# c

'b' in letters # True
'd' in letters # False

# for with indices (enumerate)
seasons = ['Spring', 'Summer', 'Fall', 'Winter']
list(enumerate(seasons))
[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
list(enumerate(seasons, start=1))
[(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]
```

### range

```
for i in range(3):
    print(i)  
# 0
# 1
# 2

# range(stop)
list(range(3)) # [0, 1, 2]
# range(start, stop[, step])
list(range(1,5)) # [1, 2, 3, 4]
list(range(1,8,2)) # [1, 3, 5, 7]
```

## list methods

TODO

## slices

```
a = list(range(10))
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
a[:5]
# [0, 1, 2, 3, 4]
a[7:]
# [7, 8, 9]
a[1:4]
# [1, 2, 3]
a[-4:-1]
[6, 7, 8]
```

### the result of a slice is a new list

```
a = list(range(5))
# [0, 1, 2, 3, 4]
b = a[2:]
# [2, 3, 4]
b[1] = 'a'
# [2, 'a', 4]
print(a)
# [0, 1, 2, 3, 4]
```

### copy a list

```
b = a
b is a # True
b = a[:]
b is a # False
```

### modifying a list without allocating a new list

```
a = list(range(5))
# [0, 1, 2, 3, 4]
b = a
a = [1, 2, 3]
b is a # False

a = list(range(5))
# [0, 1, 2, 3, 4]
b = a
a[:] = [1, 2, 3]
b is a # True
print(b)
# [1, 2, 3]
```

## list comprehension

```
# [<operation(var)> for <var> in <list> if <condition>]
l = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
squared_evens = [x**2 for x in l if x % 2 == 0]
# [4, 16, 36, 64, 100]

# if+else
# [<operation_true(var)> if <condition> else <operation_false(var)> for <var> in <list>]
l = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
[x**2 if x % 2 == 0 else x**3 for x in l]
# [1, 4, 27, 16, 125, 36, 343, 64, 729, 100]   
 

# nested list comprehension
# [<operation(var)> for <var1> in <list1> for <var2> in <list2> if <conditional>]
# equivalent to:
# for <var1> in <list1>:
#   for <var2> in <list2>:
#     if <conditional>:
#       <operation(var)>
l = [[1,2,3],[4,5,6]]
[x for sl in l for x in sl]
# [1, 2, 3, 4, 5, 6]
```

## References

* https://developers.google.com/edu/python/lists
