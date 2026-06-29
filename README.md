# README
```
This is php server with mysql and phpmyadmin using docker
ps: the phpmyadmin a bit slow response after `compose up`
```

## Make sure docker already running first in your computer

## Access
```
server: localhost
phpmyadmin: localhost:8080
```

## Build image
```
docker build -t image_name:tag_name -f php/Dockerfile .
```

## Compose up
```
docker compose up -d
```

## Compose down
```
docker compose down -v  => turn-off server 
docker compose down -v  => turn-off server and remove data from volume
```