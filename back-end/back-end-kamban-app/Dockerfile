# Dockerfile pour l'application Spring Boot avec JDK 8

# Étape 1 : Compilation de l'application avec Maven
# FROM maven:3.8.4-openjdk-8-slim AS build
# WORKDIR /app
# COPY . /app
# RUN mvn clean package -DskipTests

# Étape 2 : Exécution de l'application
# FROM openjdk:8-jre-slim
# WORKDIR /app
# COPY --from=build /app/target/back-end-kamban-app-0.0.1-SNAPSHOT.jar /app/back-end-kamban-app.jar
# ENTRYPOINT ["java", "-jar", "/app/back-end-kamban-app.jar"]


# Build stage
#FROM openjdk:8-jre-slim AS build
#WORKDIR /build
#COPY . .
#RUN ./mvnw package -D maven.test.skip

FROM maven:3.8.4-openjdk-8-slim AS build
WORKDIR /app
COPY . /app
RUN mvn clean package -DskipTests


# package stage

FROM openjdk:8-jre-slim AS deploy
WORKDIR /app
COPY --from=build /build/target/*.jar app.jar
EXPOSE 8000
ENTRYPOINT ["java", "-jar", "app.jar"]