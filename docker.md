# Docker Note

**To list containers**
```
$ docker ps 
```

**To stop a container**
```
$ docker stop <CONTAINER ID>
```

**To create a new container**
```
$ docker run -p 6379:6379 --name redis -d redis
```
-p: Allows a public access to the port
-d: runs in the background
[run command detail](https://docs.docker.com/engine/reference/commandline/run/)

**To access to a redis-cli**
```
$ docker run -it --link redis:redis --rm redis redis-cli -h redis -p 6379
```
-rm: deletes a container when the container gets exited
