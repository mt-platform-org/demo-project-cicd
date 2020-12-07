#ARG OS_IMAGE=centos
#FROM $OS_IMAGE
FROM openjdk:8
ARG SAG_HOME
#ARG AA_VERSION=1.0
ENV SAG_HOME=${SAG_HOME:-/opt/softwareag}

#RUN echo "The OS image is $OS_IMAGE"

#RUN echo "The AA version is $AA_VERSION"

#RUN yum -y update && yum install  -y java-1.8.0-openjdk 

#RUN export BOOT_JAR_FILE_NAME=$(ls ./build/libs/*.jar)

#RUN  set -x \
#      && groupadd -r ug215385 \
#      && useradd -r -g ug215385 -m -d $SAG_HOME -s /bin/bash ug215385

EXPOSE 80

#USER ug215385

WORKDIR $SAG_HOME
#ADD --chown=ug215385:ug215385  ./build/libs/$BOOT_JAR_FILE_NAME $SAG_HOME/$BOOT_JAR_FILE_NAME
ADD /build/libs/springboot-ci-demo*.jar $SAG_HOME/spring-boot-demo.jar
#COPY --chown=ug215385:ug215385 /uitemplates $SAG_HOME/uitemplates
COPY /uitemplates $SAG_HOME/uitemplates

ENTRYPOINT ["java", "-jar","spring-boot-demo.jar"]

