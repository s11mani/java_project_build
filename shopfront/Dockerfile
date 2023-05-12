FROM centos:centos7 as base
ADD . /app
WORKDIR /app
RUN yum install maven -y
RUN mvn clean install
FROM openjdk:8-jdk-alpine
COPY --from=base /app/target/shopfront-0.0.1-SNAPSHOT.jar /app/app.jar
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app/app.jar"]
