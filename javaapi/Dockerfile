FROM openjdk:8 AS build_img
WORKDIR /usr/src/app/
RUN apt update && apt install maven -y
COPY ./ ./
RUN mvn install -DskipTesks

FROM openjdk:8
WORKDIR /usr/src/app/
COPY --from=build_img /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar

EXPOSE 9000
ENTRYPOINT [ "java", "-jar", "book-work-0.0.1.jar" ]