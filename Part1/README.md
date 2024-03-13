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

and after
`$ docker image ls`
```
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
```

### 1.3