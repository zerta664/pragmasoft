FROM java:8

MAINTAINER Alena Pakhomova zerta664@gmail.com

RUN apt-get  update -y

RUN apt-get install wget git

RUN mkdir /spring
WORKDIR /spring

RUN cd /spring && git clone https://github.com/spring-projects/spring-petclinic.git

RUN cd spring-petclinic && ./mvnw package

RUN /bin/echo -e '#!/bin/bash \n java -jar /spring/spring-petclinic/target/*.jar  \n sleep 5 \n ' > /spring/run.sh
RUN chmod +x /spring/run.sh

ENTRYPOINT /spring/run.sh
