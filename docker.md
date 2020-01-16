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
$ docker run -it --link redis:redis --rm redis redis-cli -h redis -p 6379 
```
[run command detail](https://docs.docker.com/engine/reference/commandline/run/)
