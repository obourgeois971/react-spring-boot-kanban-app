FROM adoptopenjdk/maven-openjdk11:latest

COPY . /app/
RUN mkdir -p /back-end-kamban-app

WORKDIR /app/
RUN mvn clean package -Dmaven.test.skip=true
RUN chmod 777 target/back-end-kamban-app.war

CMD ["nohup",  "java",  "-jar",  "target/back-end-kamban-app.war",  ">",  "/back-end-kamban-app/back-end-kamban-app.log",  "2>1&"]