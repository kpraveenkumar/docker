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
docker image rm 'image-name' 

### Hint

docker container run --rm hello-world  # Run and delete the container after run
docker container --name container1 hello-world # Will create container with customised name Container1

### Publishing a Service

docker container run nginx
docker container run -p 80:80 nginx # open browser with localhost to see the service
docker container run -p 8080:80 nginx # open browser with localhost:8080

### Data in a container

docker container run -p 80:80 --volume /media/praveen/coding/practise/docker/html:/usr/share/nginx/html nginx

### Isolation

docker achieves isolation through kernal namespaces.

There are three namespaces:
1. Mount (mnt)
2. Process ID (pid)
3. Network (net)

Create two containers with alpine image in two terminals

Try the following commands

1. ls -l
2. ps -ef
3. ipaddr

touch a file in container, which is not seen in another container
ipaddr of both containers will be different

### Container communication
docker container run -it --rm --name c2 alpine sh
docker container run -it --rm --name c1 alpine sh

ifconfig eth0

use ping ip-address of c2 in c1 to communicate with each other

docker container run -it --rm --name c3 --link c1 alpine sh

ping c1 will work in c3

### User defined networks

docker network ls

docker network create test

docker container run -it --rm --name c1 --network test alpine sh
docker container run -it --rm --name c2 --network test alpine sh

ping c1 and ping c2 will work in respective containers

### Hide legacy commands

export DOCKER_HIDE_LEGACY_COMMANDS=true 

in ~/.bashrc or ~/.zshrc
