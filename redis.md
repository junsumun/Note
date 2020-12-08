# Redis note

**docker-compose.yml example**

```yml
version: "3.8"
services:
  redis:
    container_name: wai-redis-local
    image: "redis:latest"
    ports:
      - 6379:6379
    volumes:
      - ./config/redis.conf:/redis.conf
    command: [ "redis-server", "/redis.conf" ]
    expose:
      - "6379"
```

**GET and SET**
```
$ SET foo 100 // sets foo to 100
$ GET foo // gets the value of foo
```

```
$ SET bar "Hello" // sets bar to "hello"
$ GET bar // gets the value of bar
```

```
$ SET server:name someserver // sets server:name to someserver
$ SET server:port 8080 // sets server:port to 8080

$ GET server:name // gets the value of the server:name -> someserver
$ GET server:port // gets the value of the server:port -> 8080
$ GET server // gets the value of the server -> nil
```

**MSET**
```
$ MSET key1 "Hello" key2 "World" // sets multiple key-value pairs.
$ GET key1 // returns "Hello"
$ GET key2 // returns "World"
```

**APPEND**
```
$ APPEND key1 " People" // append " People" string to the value of key1. 12 -> length of the appended word
$ GET key1 // returns "Hello People"

// Append string values to an intger value
$ SET a 1
$ APPEND a "one" // 4 -> length of the appended word
$ GET a // returns "1one"
```

**RENAME**
```
$ RENAME key1 message // rename the key name "key1" to the key name "message"
$ GET key1 // returns nill
$ GET message // returns "Hello People"
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

**EXPIRE**
```
$ SET greeting "Hello World"
$ EXPIRE greeting 50 // sets an expiry of 50 seconds to the greeting key. 1 -> if success

```

**SETEX**
```
$ SETEX greeting 50 "Hello World" // sets a value and expiry to the greeting key at the same time. 
```

**PERSIST**
```
$ PERSIST greeting // removes the expiry of the key. 1 -> if success
```

**TTL**
```
$ TTL greeting // gets the remaining time of key expiry in seconds. 45 -> after 5 seconds passed since first expiry set.
$ TTL gretting // -2 -> after 50 seconds and the key no longer exists.
$ TTL foo // -1 -> the key does not have an expiry.
```

**LPUSH**
```
$ LPUSH people "Brad" // Creates a list called people and adds "Brad" to the left. 1 -> number of elements in the list
$ LPUSH people "Jen" // adds "Jen" to the left ex. Jen - Brad. 2 -< number of elements in the list
$ LPUSH people "Tom" // adds "Tom" to the left ex. Tom - Jen - Brad.
```

**RPUSH**
```
$ RPUSH people "Harry" // adds "Harry" to the right ex. Tom - Jen - Brad - Harry.
```

### **LIST TYPE**

**LPOP**
```
$ LPOP people // removes an element from the left side of the list. "Tom" -> returns the removed element
$ LRANGE people 0 -1 // Jen - Brad - Harry
```

**RPOP**
```
$ RPOP people // removes an element from the right side of the list. "Harry" -> returns the remove element
$ LRANGE people 0 -1 // Jen - Brad
```

**LINSERT**
```
$ LRANGE people 0 -1 // Jen - Brad
$ LINSERT people BEFORE Brad "Junsu" // inserts new "Junus" value before the Brad value to people list.
```

**LRANGE**
```
$ LRANGE people 0 -1 // returns all the elements in the people list. 1) "Tom" 2) "Jen" 3) "Brad"
$ LRANGE people 0 1 // returns all the elments that are withing range of 0 to 1. 1) "Tom" 2) "Jen"
```

**LLEN**
```
$ LLEN people // gets the length of people list. returns 3
```
