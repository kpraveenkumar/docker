# docker
Learn Docker-https://www.docker.com/get-started
https://docker-curriculum.com/

## Learn Docker

### Hello World
docker container run hello-world

### Starting your First shell

docker container run alpine sh
docker container run -it alpine sh    # Run interactively

cat /etc/os-release
uname -r

### Finding images

https://hub.docker.com

Use Official Tag docker images

### Contianer ls

docker container ls -a # List all containers
hostname # hostname of the container
docker container start 'Container name' # start the container
docker container attach 'Container name' # attach/open the running container
docker container run 'image name' # Will always start new container
docker container run -itd 'image name' # Will start new container in detached mode

### Container rm - Cleanup

docker container rm 'hostname'  # Remove the container with hostname
docker container rm $(docker container ls -aq) # Remove all containers
docker image ls
docker image rm 

