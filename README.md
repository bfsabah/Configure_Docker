Configure docker 
Docker is a container runtime. Greatest example for micro services. It has just what ever needs, just it.
1. EC2 vm spin up 
2. sudo su - 
3. yum install docker -y 
4. docker images --> Will fail 
5. service docker status --> returns inactive (dead)
6. service docker start 
7. create docker hub account --> https://hub.docker.com/
8. search box look for tomcat image 
9. docker pull tomcat
10. Docker container can run in 2 modes --> 1) Foreground and 2) detached 
11. Foreground --> docker run --name tomcat-container -p 8080:8080 tomcat:latest --> If proccess is canceled docker container will die 
12. Detach --> docker run -d --name tomcat-container-1 -p 8081:8080 tomcat:latest
13. List docker containers --> docker ps 
14. List all container icluding exited containers --> docker ps -a 
15. docker container ls or docker container ls -a
16. Remove container --> docker stop container-name or id --> docker rm container-name or id
17. Remove image --> docker rmi image name or image id 
18. Dockerfile --> Is a definition for docker image
19. TOMCAT 404 NOT FOUND :  - docker exec -it tomcat-container-1 /bin/bash
20.                         - Copy all files in webapps.dist > webapps
21. docker stop 619110ddf2c5 {docker image ID} : to stop docker image
22. In Root dir, vim Dockerfile:
23
24. docker images {check in the list}
25. docker build -t myimage .
26. docker images - docker ps - docker stop {image id} - docker rm {image id}
27. to get in the container: docker exec -it {docker image} /bin/bash
28. ip addr {private ip}
29. cat /etc/passw
30. adduser...
31. usermod -aG
32. visudo , chown
33. docker system -prune
