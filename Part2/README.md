# Part 2

Skipping exercises 2.1-2.2 for now.

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