# Part 1

## Exercises

### 1.1
`$ docker ps -a`
```
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                     PORTS     NAMES
3f9eae7b78fb   redis     "docker-entrypoint.s…"   About a minute ago   Exited (0) 5 seconds ago             cranky_lamarr
66a2d14f15e2   httpd     "httpd-foreground"       About a minute ago   Exited (0) 4 seconds ago             festive_northcutt
0b293c1c17d4   nginx     "/docker-entrypoint.…"   4 minutes ago        Up 4 minutes               80/tcp    determined_wu
```

### 1.2
`$ docker ps -a`
```
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```

Images before

`$ docker image ls`
```
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
nginx         latest    92b11f67642b   3 weeks ago     187MB
httpd         latest    ac45b24b92cc   8 weeks ago     167MB
redis         latest    170a1e90f843   2 months ago    138MB
```

and after `docker image rm ...`

`$ docker image ls`
```
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
```

### 1.3

`$ docker run -d -it --name simple-web-service  devopsdockeruh/simple-web-service:ubuntu`
...
```
$ docker exec -it simple-web-service bash
root@a8828c91f26e:/usr/src/app# tail -f ./text.log
2024-04-15 11:19:57 +0000 UTC
2024-04-15 11:19:59 +0000 UTC
2024-04-15 11:20:01 +0000 UTC
2024-04-15 11:20:03 +0000 UTC
2024-04-15 11:20:05 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```

### 1.4

```
$ docker run --name=ubuntu --rm -it ubuntu sh -c 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done'
Input website:
helsinki.fi
Searching..
<html>
<head><title>301 Moved Permanently</title></head>
<body>
<center><h1>301 Moved Permanently</h1></center>
<hr><center>nginx/1.22.1</center>
</body>
</html>
Input website:
```

And installed curl after `docker run --name=ubuntu ...` command using `docker exec -it ubuntu bash` and then `apt update && apt install curl -y`.

### 1.5

The size of non alpine image is almost 100 MB (about 83 MB) and the alpine image needs about 15 MB. The alpine image alternative for the `sh` command is `/bin/sh` e.g. `$ docker exec -it <container name> /bin/sh`.

### 1.6

```
$ docker run -it devopsdockeruh/pull_exercise
```

```
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
```

### 1.7

Please see `Dockerfile-ex-1-7`

### 1.8

Please see `Dockerfile-ex-1-8`.

And the commands:
```
$ docker build . -t web-server
[+] Building 0.2s (5/5) FINISHED
...
 => => naming to docker.io/library/web-server

$ docker run web-server
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. ...
```

### 1.9

```
$ touch text.log
$ docker run --rm -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service
```

### 1.10

```
$ docker run --rm -p 80:8080 devopsdockeruh/simple-web-service server
```

### 1.11

Please see `Dockerfile-ex-1-11`.

And the commands:
```
$ docker build -t spring-example .
```