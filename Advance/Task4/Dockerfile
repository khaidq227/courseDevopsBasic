FROM maven:ibmjava-alpine
RUN mkdir -p /app/source
COPY . /app/source
WORKDIR /app/source
RUN mvn clean package

FROM openjdk:8-alpine
COPY --from=0 /app/source/target/*.jar /app/websocket-demo-0.0.1-SNAPSHOT.jar
EXPOSE 8080
CMD ["java","-Djava.security.egd=file:/dev/./urandom", "-jar", "/app/websocket-demo-0.0.1-SNAPSHOT.jar"]