# README
```
This is php server with mysql and phpmyadmin using docker
ps: the phpmyadmin a bit slow response after `compose up`
```

## Make sure docker already running first in your computer

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
docker compose down -v
```