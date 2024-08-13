# FROM openjdk:8-jre-slim AS deploy

FROM openjdk:8
ARG JAR_FILE=/build/libs/*.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java", "-jar", "app.jar"]
EXPOSE 8080-8081