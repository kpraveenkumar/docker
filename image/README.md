### Image
docker image ls
docker image rm hello-world:latest
docker pull hello-world:latest

### Build own image

docker build image -t myalpine:latest ./Dockerfile

### Using third party registry quay.io

docker image tag kpraveenkumar89/myalpine:latest quao.io/kpraveenkumar89/myalpine:latest

docker push quao.io/kpraveenkumar89/myalpine:latest
