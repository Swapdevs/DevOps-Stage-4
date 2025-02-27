FROM openjdk:17
WORKDIR /app
COPY . .
RUN ./mvnw package -DskipTests
EXPOSE 8083
CMD ["java", "-jar", "target/users-api-0.0.1-SNAPSHOT.jar"]
