# Spring PetClinic Application

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/officialdarnyc/spring-petclinic-mono) [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=7517918)

This repository is derived from the original [Spring PetClinic](https://github.com/spring-projects/spring-petclinic) version.

## Understanding the Spring Petclinic application with a few diagrams

[See the presentation here](https://speakerdeck.com/michaelisvy/spring-petclinic-sample-application)

## Run Petclinic locally

Spring Petclinic is a [Spring Boot](https://spring.io/guides/gs/spring-boot) application built using [Maven](https://spring.io/guides/gs/maven/) or [Gradle](https://spring.io/guides/gs/gradle/). You can build a jar file and run it from the command line (it should work just as well with Java 17 or newer):

```bash
git clone https://github.com/officialdarnyc/spring-petclinic-mono.git
cd spring-petclinic-mono
./mvnw package
java -jar target/*.jar
```

You can then access the Petclinic at <http://localhost:8080/>.

<img width="1042" alt="petclinic-screenshot" src="https://cloud.githubusercontent.com/assets/838318/19727082/2aee6d6c-9b8e-11e6-81fe-e889a5ddfded.png">

Or you can run it from Maven directly using the Spring Boot Maven plugin. If you do this, it will pick up changes that you make in the project immediately (changes to Java source files require a compile as well - most people use an IDE for this):

```bash
./mvnw spring-boot:run
```

> NOTE: If you prefer to use Gradle, you can build the app using `./gradlew build` and look for the jar file in `build/libs`.

## Building a Container

From the root directory, run the command to build the container image:

```bash
docker build -t petclinic-app . -f Dockerfile
```

## Deploy using Docker Compose

1. Download the compose file:
```bash
curl -L https://raw.githubusercontent.com/officialdarnyc/spring-petclinic-mono/main/docker-compose.yml -O
```

2. Set your `MYSQL_PASSWORD` environment variable in your shell
```bash
export MYSQL_PASSWORD="<your-db-password>"
```

3. Run the command to deploy the petclinic app and a MySQL DB server:
```bash
docker compose up -d
```
4. Access the app using `http://<your-public-ip>:8080`. If running on local PC, visit [http://localhost:8080](http://localhost:8080) in your browser to access the app.


