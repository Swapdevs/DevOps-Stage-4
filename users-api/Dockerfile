# Dockerfile for Users API
FROM openjdk:8-jdk-alpine
WORKDIR /app
COPY . .
RUN ./mvnw package -DskipTests
EXPOSE 8081
CMD ["java", "-jar", "target/users-api.jar"]