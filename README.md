# Exp_2_Simple-Spring-Boot-MVC-Application

## AIM:
To develop a Simple Spring Boot MVC (Model-View-Controller) Application that uses a Controller to handle HTTP requests, a Model to pass data, and a View (Thymeleaf) to render dynamic HTML pages.

## ALGORITHM:
Create a New Spring Boot Project:

Use Spring Initializr

Add dependencies:

Spring Web

Thymeleaf

Set Up Project Structure:

Create the main class annotated with @SpringBootApplication

Create a Controller class using @Controller

Add HTML templates under src/main/resources/templates

Create a Controller:

Define a method to handle HTTP GET requests using @GetMapping

Return a view name (HTML page name) from the controller

Pass data to the view using Model object

Create a Model (Optional):

Define a simple POJO class if you need to pass structured data to the view

Create View Pages (HTML using Thymeleaf):

Create an HTML file inside the templates folder

Use Thymeleaf syntax (e.g., ${name}) to render dynamic content

Run the Application:

Run the Spring Boot application from your IDE or command line

Access the Application:

Open a browser and navigate to http://localhost:8080/
## PROGRAM
spring-mvc-demo/
├── src/
│   └── main/
│       ├── java/
│       │   └── com.example.mvc/
│       │       ├── MvcApplication.java
│       │       └── HomeController.java
│       └── resources/
│           ├── templates/
│           │   └── index.html
│           └── application.properties
├── pom.xml

### pom.xml :

<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>spring-mvc-demo</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <name>Spring MVC Demo</name>

    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>3.1.2</version>
    </parent>

    <dependencies>
        <!-- Spring Web -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>

        <!-- Thymeleaf for View Rendering -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-thymeleaf</artifactId>
        </dependency>
    </dependencies>
</project>

### MvcApplication.java (Main Class):

```

package com.example.exp2;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Exp2Application {

    public static void main(String[] args) {
        SpringApplication.run(Exp2Application.class, args);
    }
}

```

### HomeController.java (Controller):

```

package com.example.exp2;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HomeController {

    @GetMapping("/")
    public String homePage(Model model) {

        model.addAttribute(
                "message",
                "Welcome to Spring Boot MVC!"
        );

        return "index";
    }
}

```
### index.html (View – inside src/main/resources/templates/):

```

<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">

<head>
    <title>Spring Boot MVC</title>

    <style>
        body {
            font-family: Arial;
            text-align: center;
            margin-top: 100px;
            background-color: #f2f2f2;
        }

        .container {
            background: white;
            padding: 30px;
            margin: auto;
            width: 60%;
            border-radius: 10px;
        }

        button {
            padding: 10px 20px;
            margin: 10px;
            cursor: pointer;
        }
    </style>
</head>

<body>

<div class="container">

    <h1 th:text="${message}"></h1>

    <p>Welcome to our first MVC app!</p>

    <button onclick="showMessage()">
        Click for Alert
    </button>

    <button onclick="changeText()">
        Change Text
    </button>

</div>

<script>
    function showMessage() {
        alert("Welcome to Spring Boot MVC!");
    }

    function changeText() {
        document.querySelector("p").innerHTML =
            "Text changed successfully!";
    }
</script>

</body>
</html>

```

### application.properties:

```

spring.application.name=exp2
server.port=8082

```

## Output

<img width="1517" height="712" alt="image" src="https://github.com/user-attachments/assets/4d2f51e2-7fb5-4fe8-a32d-823dbc8bf0c6" />

## Result

The Simple Spring Boot MVC Application was successfully developed and executed. The Controller handled the HTTP request, the Model passed data to the View, and Thymeleaf rendered the dynamic HTML page successfully in the browser. The application displayed the welcome message along with the personalized greeting.


