FROM maven:3.9.8-eclipse-temurin-21 AS build

WORKDIR /app

COPY src /app/src

COPY pom.xml /app

RUN mvn clean install -DskipTests

#####

FROM openjdk:21

COPY --from=build /app/target/*.jar /app/app.jar

WORKDIR /app

EXPOSE 8080
CMD ["java", "-jar", "app.jar"]
