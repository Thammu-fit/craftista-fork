FROM maven:3.8.7-openjdk-18 AS builder

WORKDIR /app

COPY . .

RUN mvn package -DskipTests

FROM openjdk:22-ea-19-jdk-slim

WORKDIR /app

COPY --from=builder /app/target/*.jar app.jar

EXPOSE 8080

CMD ["java","-jar","app.jar"]

