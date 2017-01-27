# Python lists

### basics
```
l = []
l = list() # slower than []

l = [1, 2, 3]
print(l[0]) # 1

l[1] = 1000
print(l) # [1, 1000, 3]
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

TODO

## list comprehension

```
# [<operation(var)> for <var> in <list> if <condition>]
l = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
squared_evens = [x**2 for x in l if x % 2 == 0]
# [4, 16, 36, 64, 100]

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
