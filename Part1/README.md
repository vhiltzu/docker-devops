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