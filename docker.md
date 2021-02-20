//ubuntu version check on docker container  
 cat /etc/lsb-release
docker run -d -p 80:80 docker/getting-started  #first time starts docker, -d detached mode, -p gives port number
docker run hello-world  #hello-world image container is created and started with run command
docker run -it ubuntu:20.04 #create, run a ubuntu container and loggin into the terminal
docker ps # only running containers
docker ps -a  # present and past containers, all containers
docker start 4aaa5b87e65f  # starts a stopped container based on container id
docker exec -ti 4aaa5b87e65f bash  # connect running container on a terminal, -t running container on terminal
doskey /History  # check history in windows command
