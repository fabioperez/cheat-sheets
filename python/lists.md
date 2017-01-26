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

## References

* https://developers.google.com/edu/python/lists
