# devopswithdocker

## 1.4: Missing Dependencies

```bash
docker run -d -it --name missing-dependencies ubuntu sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'

docker exec missing-dependencies sh -c 'apt-get update && apt-get -y install curl'

docker attach missing-dependencies    
```


## 1.5: Sizes of Images

```bash
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```
