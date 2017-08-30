
## Select N random files

```
ls | sort -R | tail -$N | while read file; do
  # do something with $file
done
```

[Source](https://stackoverflow.com/a/414316/604734)
