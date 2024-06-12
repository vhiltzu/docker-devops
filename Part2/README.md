# Part 2

Skipping exercises 2.1-2.2 and 2.11 for now.

### 2.3

Please see `docker-compose-2-3.yaml`.

And the commands without detaching:
```
$ cd <path-to-material-apps>/
$ ls -l
...
docker-compose.yaml
...
$ docker compose build
...
$ docker compose up
```

### 2.4

Please see `docker-compose-2-4.yaml`.

### 2.5

```
$ docker compose up --scale compute=1
```
Failed!

```
$ docker compose up --scale compute=2
```
Success!

```
$ docker compose up --scale compute=3
```
Success!

### 2.6

Please see `docker-compose-2-6.yaml`.

### 2.7

Please see `docker-compose-2-7.yaml`.

### 2.8

Please see `docker-compose-2-8.yaml`.

### 2.9

Please see `docker-compose-2-9.yaml` and both Dockerfiles `Dockerfile-2-9-front` and `Dockerfile-2-9-back`.

### 2.10

I have completed these exercises inside a virtual machine running Ubuntu Desktop 22.04.04. There is no extra ports open. The only one is 80/tcp.