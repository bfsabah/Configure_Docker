Configure docker 

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
23. FROM centos
    RUN cd /etc/yum.repos.d/
    RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
    RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
    RUN yum -y install java
    RUN mkdir /opt/tomcat/
    WORKDIR /opt/tomcat
    ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.69/bin/apache-tomcat-9.0.69.tar.gz /opt/tomcat
    RUN tar xvzf apache-tomcat-9.0.69.tar.gz
    RUN mv apache-tomcat-9.0.69/* /opt/tomcat
    EXPOSE 8080
    CMD ["/opt/tomcat/bin/catalina.sh", "run"]
24. docker images {check in the list}

