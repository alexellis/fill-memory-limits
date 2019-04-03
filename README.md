## fill-memory

Generate a large file

```
dd if=/dev/urandom of=10mb.bin count=10 bs=1m
```

Deploy the function

```
faas-cli template store pull golang-middlware
faas-cli deploy
```

Generate some load:

```
hey -c 10 -n 10 -m POST -D 10mb.bin http://127.0.0.1:31112/function/mem-reader
```
