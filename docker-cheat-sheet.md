`docker build -t <image_name> .` // the . is important because it takes the Dockerfile from this dir  
`docker ps` // show all running containers  
`docker ps -a` //show all containers  
`docker run -d -P <image_name>` // background  
`docker stop/start/restart <existing_container_name>`  
`docker exec -it <existing_container_name> bash` // opens a terminal in a running container
`docker rm <existing_container_name>`  
`docker rmi <image_name>`  
`docker commit <existing_container_name> <image_name>`  
`docker run -d -it -p localport:remoteport -v <localcodepath>:<remotecodepath> <containername>`  
