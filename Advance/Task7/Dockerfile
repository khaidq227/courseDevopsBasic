### BUILD image
FROM maven:3-jdk-11
# create app folder for sources
RUN mkdir -p /app-obo
WORKDIR /app-obo
COPY pom.xml /app-obo
#run all required dependencies into project
RUN mvn dependency:go-offline
#Copy source code
COPY src /app-obo/src
# Build application
CMD [ "mvn" , "spring-boot:run"]