FROM maven:3.9-eclipse-temurin-8 AS build

LABEL maintainer="antoine"

WORKDIR /usr/src/app

COPY . .

RUN mvn clean package -DskipTests

FROM eclipse-temurin:8-jre

COPY --from=build /usr/src/app/target/java-0.0.1-SNAPSHOT.jar .

CMD ["java", "-jar", "java-0.0.1-SNAPSHOT.jar"]
