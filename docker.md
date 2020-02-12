# Docker Note

**To list containers**
```
$ docker ps 
```
-a: To list all running and stopped containers

**To stop a container**
```
$ docker stop <CONTAINER ID>
```

**To remove one or more containers**
```
$ docker rm <CONTAINER ID>
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

```
$ docker exec -it redis redis-cli
```
