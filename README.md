# Docker-troubleshoot  
Record some probelms, when using Docker.(Just README file here)  

##some Docker **command ** 

docker ps  
(Show running containers)  
docker ps -a   
docker ps -a --filter "ancestor=sha256:1a86f4dacc3fb28abda390e303fab1bc0849683bd2bb932095a3de43cafe1659"  
(Show all containers created based on this image, including running and stopped ones.)  

For delete image:  
docker stop <container_id>  
docker rm <container_id>  

##some **problem**

