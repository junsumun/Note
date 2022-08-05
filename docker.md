# Docker Note

**To create a container**
```
$ docker create <image name>
```

**To start a container**
```
$ docker start <container id>

options:
-a: Displays logs of the container
```

**A combined command of create and start**
```
$ docker run <image name>
```

**To list all containers**
```
$ docker ps

options:
-a: To list all running and stopped containers
```

**To stop a container**
```
$ docker stop <CONTAINER ID>
```

**To remove one or more containers**
```
$ docker rm <CONTAINER ID>
```

**To remove all stopped containers**
```
$ docker system prune
```

**To check logs of a container**
```
$ docker logs <container id>
```

**To stop a running container**
```
$ docker stop <container id>

note: docker kill <container id> command will be executed automatically after 10 seconds the docker stop command executed.
```

**Executing Commands in a Running Container**
```
First, start a main container ex. redis

$ docker run redis

this command will start a redis-server container and to execute commands inside this redis-server container

$ docker exec -it <container id> <command>

ex. docker exec -it redis-server-container-id redis-cli

options:
-it: allows us to provide input to the container
```

