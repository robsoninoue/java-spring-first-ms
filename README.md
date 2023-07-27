# SOU Java

## Microservices with Java and Spring Boot

### What is Microservices?

Microservices are a architectural pattern in software development, where each part of an application is independent and is in a little service. The communication between these services are by an lightweight API.

### Why Microservices?

Agility in software delivery, scalability and resilience in production environment and easy to deploy.

### How to create a first Micro Service with Java and Spring

#### Pre requisites

- Java Development Kit JDK 17+ 
- IDE: IntelliJ, Eclipse, VScode, etc...
- Spring Tools (optional)
- Docker (optional)

#### Coding

- Install JDK and an IDE
- Go to https://start.spring.io/ to config your first WebApp.
- Add a `Spring Web` dependency
- Set project's metadata
- Click in generate buttom to download the project
- Unzip the file downloaded
- Open terminal and enter in unzipped folder
- Replace the code in `/demo/src/main/java/com/example/demo/DemoApplication.java` by this code:

    ```Java
    package com.example.demo;
    import org.springframework.boot.SpringApplication;
    import org.springframework.boot.autoconfigure.SpringBootApplication;
    import org.springframework.web.bind.annotation.GetMapping;
    import org.springframework.web.bind.annotation.RequestParam;
    import org.springframework.web.bind.annotation.RestController;

    @SpringBootApplication
    @RestController
    public class DemoApplication {
        public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
        }
        @GetMapping("/hello")
        public String hello(@RequestParam(value = "name", defaultValue = "World") String name) {
        return String.format("Hello %s!", name);
        }
    }
    ```
- For Linux/MacOS, on terminal enter:

    `./gradlew bootRun`

- For Windows enter:

    `.\gradlew.bat bootRun`

- Go to http://localhost:8080/hello to view the response of the application.

### Links

- [JDK - Java Development Kit](https://www.oracle.com/java/technologies/downloads/)
- [IntelliJ](https://www.jetbrains.com/idea/download/)
- [Eclipse](https://www.eclipse.org/downloads/)
- [VS Code](https://code.visualstudio.com/download)
- [Spring Tools](https://spring.io/tools)
- [Docker](https://docs.docker.com/get-docker/)