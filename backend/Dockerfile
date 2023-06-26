FROM maven:3.8.4-openjdk-11-slim AS build
WORKDIR /backend
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests

FROM openjdk:11-jre-slim
WORKDIR /backend
COPY --from=build /backend/target/Lab2_Library_193238-0.0.1-SNAPSHOT.jar ./Lab2_Library_193238.jar
EXPOSE 8080
CMD ["java", "-jar", "Lab2_Library_193238.jar"]