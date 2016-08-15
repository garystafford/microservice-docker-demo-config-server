# Builds the Config Server using Spring Boot with Docker

FROM frolvlad/alpine-oraclejdk8:slim

MAINTAINER Gary A. Stafford <garystafford@rochester.rr.com>
ENV REFRESHED_AT 2016-08-13

VOLUME /tmp
ADD config-server-0.1.0.jar app.jar
RUN sh -c 'touch /app.jar'
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]
