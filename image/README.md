### Image
docker image ls
docker image rm hello-world:latest
docker pull hello-world:latest

### Build own image

docker build image -t myalpine:latest ./Dockerfile
