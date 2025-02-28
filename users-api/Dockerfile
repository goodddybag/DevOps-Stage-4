# Stage 1: Build the JAR file
FROM maven:3.9.6-eclipse-temurin-8 AS build
WORKDIR /app

COPY pom.xml .
RUN mvn dependency:go-offline -B

COPY . .
RUN mvn clean package -DskipTests -B

# Stage 2: Run the application
FROM openjdk:8
WORKDIR /app

COPY --from=build /app/target/users-api-0.0.1-SNAPSHOT.jar users-api.jar

EXPOSE 8083

CMD ["java", "-jar", "users-api.jar"]
