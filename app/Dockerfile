# Stage 1: Build the app using Java 21
FROM eclipse-temurin:21-jdk AS build

WORKDIR /app
COPY . .

# Make Maven wrapper executable
RUN chmod +x mvnw

# Build the application
RUN ./mvnw clean package -DskipTests

# Stage 2: Run the built app
FROM eclipse-temurin:21-jdk

WORKDIR /app
COPY --from=build /app/target/*.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]
