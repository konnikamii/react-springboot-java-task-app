FROM openjdk:23-jdk-slim

WORKDIR /app

COPY .mvn .mvn
COPY mvnw pom.xml ./

COPY src src

RUN chmod +x ./mvnw && ./mvnw dependency:go-offline -B
RUN ./mvnw clean package -DskipTests -B

EXPOSE 8080
ENTRYPOINT ["java", "-jar", "target/app-0.0.1-SNAPSHOT.jar"]