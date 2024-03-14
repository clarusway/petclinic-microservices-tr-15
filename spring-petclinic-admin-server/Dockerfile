FROM openjdk:11-jre
ARG DOCKERIZE_VERSION=v0.7.0
ENV SPRING_PROFILES_ACTIVE docker,mysql
ADD https://github.com/jwilder/dockerize/releases/download/${DOCKERIZE_VERSION}/dockerize-alpine-linux-amd64-${DOCKERIZE_VERSION}.tar.gz dockerize.tar.gz
RUN tar -xzf dockerize.tar.gz
RUN chmod +x dockerize
COPY admin.jar /app.jar
EXPOSE 9090
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]

# curl  -u admin:123 -L -X GET http://54.88.187.50:8081/repository/maven-releases/org/springframework/samples/petclinic/admin/spring-petclinic-admin-server/2.1.2/spring-petclinic-admin-server-2.1.2.jar