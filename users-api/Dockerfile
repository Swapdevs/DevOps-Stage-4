FROM maven:3.8.6-openjdk-11 AS build
WORKDIR /app
COPY pom.xml .
RUN mvn dependency:resolve
COPY . .
RUN mvn package -DskipTests
EXPOSE 8081
CMD ["java", "-jar", "target/users-api.jar"]
