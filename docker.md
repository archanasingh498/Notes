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







//mysql container creation  

docker pull mysql  #pull mysql image and download
 
docker images  #check images
 
docker ps -a  #check all containers
 
docker run --name sqlarchana -e MYSQL_ROOT_PASSWORD=my-secret-pw -d 2933adc350f3  #Start a mysql server instance
 
docker exec -ti f163a698e237 bash  #start an interactive terminal for the specific container


//connect to the database  

mysql -u root -p  

//enter the password  

//sql terminal opens up  

   create database sample;

    use sample;

    create table users(username varchar(30) not null, password varchar(30) not null, email varchar(50));

    insert into users values('user1', 'snEAk3', 'user1@coldmail.com');

    select * from users;

    exit;  #exits from the sql terminal
    
docker volume create mysqldata   #create a volume called mysqldata   

docker volume ls   #check volumes running  

docker run --name sqlarchana2 --mount source=mysqldata,target=/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d 2933adc350f3    #map the mysqldata volume to directory /var/lib/mysql, which is where the database files are kept.

docker exec -ti 9edcf63f266f bash   #start an interactive terminal for the specific container  

docker stop 9edcf63f266f   #stop the container  

docker rm 9edcf63f266f  #remove the container  

docker volume inspect --format "{{json .Mountpoint}}" mysqldata   #see where the data is being stored
