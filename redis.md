# Redis note

**GET and SET**

```
$ SET foo 100 // sets foo to 100
$ GET foo // gets the value of foo
```

```
$ SET bar "Hello" // sets bar to "hello"
$ GET bar // gets the value of bar
```

**INCR and DECR**

```
$ INCR foo // increments the value of foo by one. 100 -> 101
$ DECR foo // decrements the value of food by one. 101 -> 100

$ INCR bar // gives an error since bar is a string.

$ INCR car // increments a non-set value. a default start value is 0 thus, 0 -> 1
$ DECR lol // decrements a non-set value. a default start value is 0 thus, 0 -> -1
```

**EXISTS**

```
$ EXISTS foo // checks a key exists. 1 -> it exists
$ EXISTS kor // 0 -> it does not exist.
```

**DEL**

```
$ DEL foo // deletes foo key. 1 -> if success
$ DEL foo // deletes foo key again. 0 -> failed to delete because it no longer exists.
```

**FLUSHALL**

```
$ FLUSHALL // deletes all the keys. OK -> if success
```
