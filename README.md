###### Build:  
![https://travis-ci.org/garystafford/microservice-docker-demo-config-server.svg?branch=master](https://travis-ci.org/garystafford/microservice-docker-demo-config-server.svg?branch=master)

###### Docker Hub:  
[![](https://images.microbadger.com/badges/version/garystafford/microservice-docker-demo-config-server.svg)](http://microbadger.com/images/garystafford/microservice-docker-demo-config-server "Get your own version badge on microbadger.com")   [![](https://images.microbadger.com/badges/image/garystafford/microservice-docker-demo-config-server.svg)](http://microbadger.com/images/garystafford/microservice-docker-demo-config-server "Get your own image badge on microbadger.com")

# Spring Cloud Config Server

#### Introduction
Spring Cloud Config Server, for an upcoming post on scaling microservices with the latest Spring and Docker features.

#### Technologies
* Java
* Spring Boot
* Gradle
* MongoDB
* Spring Cloud Config Server (migrating to Consul)
* Spring Cloud Netflix Eureka
* Spring Boot with Docker
* The Elastic Stack (Elasticsearch, Kibana, Logstash, and Beats)
* DockerHub
* Travis CI

#### Build Service
Build and start service locally
```bash
./gradlew clean build && \
  java -jar -Dspring.profiles.active=local \
  build/libs/config-server-0.1.0.jar

```

#### Building Images with Spring Boot
Change the `group` key in `build.gradle` to you DockerHub repository name, such as
```text
group = '<your_dockerhub_repo_name>'
```

Login to your Docker Hub account from command line
```bash
docker login
```

Build the Docker Image containing service jar
```bash
./gradlew clean build buildDocker
```
If `push = true` was set in the `buildDocker` method of the `build.gradle`, the images
is automatically pushed to your DockerHub account.

If you chose to set `push = false` within the `buildDocker` method of the `build.gradle`,
then use the following type of command to push the new Docker Image to DockerHub, after it is built.
```bash
docker push <your_dockerhub_repo_name>/user-service:latest
```

#### References
* https://github.com/Transmode/gradle-docker
