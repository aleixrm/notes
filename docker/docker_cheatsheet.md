DOCKER CHEATSHEET
===

run docker:
```
$ docker run <image_name> <command_to_execute>
```

run docker interactively:
```
$ docker run -it <image_name> <command_to_execute>
```

remove docker container:
```
$ docker rm <container_id>
```

remove all docker exited containers:
```
$ docker rm $(docker ps -a -q -f status=exited)
```

run docker and delete container when exits:
```
$ docker run --rm <image_name> <command_to_execute>
```

check docker containers running:
```
$ docker ps
```

check docker containers history:
```
$ docker ps -a
```

download image:
```
$ docker pull <image_name>
```

list downloaded images
```
$ docker images
```

run docker container in detached mode, with random port assignation and declaring a name:
```
$ docker run -d -P --name <container_name> <image_name> <command_to_execute>
```

enumerate container ports:
```
$ docker port <container_name>
```

