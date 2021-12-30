# devopswithdocker

## 1.4: Missing Dependencies

```bash
docker run -d -it --name missing-dependencies ubuntu sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'

docker exec missing-dependencies sh -c 'apt-get update && apt-get -y install curl'

docker attach missing-dependencies    
```


## 1.5: Sizes of Images

```bash
docker exec -it 4bf sh -c 'tail -f ./text.log'
```

```bash
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```
## 1.6: Hello DockerHub

```bash
> docker run -it devopsdockeruh/pull_exercise
Unable to find image 'devopsdockeruh/pull_exercise:latest' locally
latest: Pulling from devopsdockeruh/pull_exercise
8e402f1a9c57: Pull complete 
5e2195587d10: Pull complete 
6f595b2fc66d: Pull complete 
165f32bf4e94: Pull complete 
67c4f504c224: Pull complete 
Digest: sha256:7c0635934049afb9ca0481fb6a58b16100f990a0d62c8665b9cfb5c9ada8a99f
Status: Downloaded newer image for devopsdockeruh/pull_exercise:latest
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
```
## 1.7: Two Line Dockerfile

### Dockerfile
```bash
FROM devopsdockeruh/simple-web-service:alpine
CMD server
```
### Shell
```bash
docker build . -t web-server
docker run web-server
```

## 1.8: Image for Script

### Dockerfile
```bash
FROM ubuntu:18.04

RUN apt-get update; apt-get install -y curl

COPY image-script.sh .

CMD ./image-script.sh
```

### Shell
```bash
docker build . -t ubuntu:curler

docker run -it ubuntu:curler
```


## 1.9: Volumes

```bash
docker run -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service
```
