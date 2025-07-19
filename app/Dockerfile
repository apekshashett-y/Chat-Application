# Use an official JDK image
FROM openjdk:17

# Set working directory
WORKDIR /app

# Copy the jar file from target directory
COPY target/*.jar app.jar

# Expose port (Render will set PORT as env var)
EXPOSE 8080

# Run the jar file
ENTRYPOINT ["java", "-jar", "app.jar"]
