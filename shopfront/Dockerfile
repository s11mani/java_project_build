FROM s11mani/centos:mvn-installed as base
ADD . /app
WORKDIR /app
RUN mvn clean install
FROM openjdk:8-jre-alpine
EXPOSE 8010
COPY --from=base /app/target/shopfront-0.0.1-SNAPSHOT.jar /app/app.jar
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app/app.jar"]
