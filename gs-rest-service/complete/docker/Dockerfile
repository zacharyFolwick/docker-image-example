FROM alpine/git as clone
WORKDIR /app
RUN git clone https://github.com/spring-guides/gs-rest-service.git

FROM maven:3.5-jdk-8-alpine as build
#FROM maven:3-amazoncorretto-17
WORKDIR /app
COPY --from=clone /app/gs-rest-service /app
WORKDIR /app/complete
RUN mvn install
RUN mvn clean package -Dmaven.test.skip

FROM openjdk:17-jdk-alpine
COPY --from=build /app/complete/target/*.jar /app.jar
ENTRYPOINT ["java","-jar","/app.jar"]


EXPOSE 8080
