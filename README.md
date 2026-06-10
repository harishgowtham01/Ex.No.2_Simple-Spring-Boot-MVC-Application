# Ex No: 02 – Simple Spring Boot MVC Application

### Name: Harish Gowtham E
### Register Number: 2305002009
### Reg No: 2305002001

## AIM

To develop a Simple Spring Boot MVC (Model-View-Controller) Application that uses a Controller to handle HTTP requests, a Model to pass data, and a View (Thymeleaf) to render dynamic HTML pages.

## ALGORITHM

1. Create a new Spring Boot project using Spring Initializr.
2. Add the required dependencies:

   * Spring Web
   * Thymeleaf
3. Create the main application class using the `@SpringBootApplication` annotation.
4. Create a Controller class using the `@Controller` annotation.
5. Define a method to handle HTTP GET requests using `@GetMapping`.
6. Use the `Model` object to pass data from the controller to the view.
7. Create an HTML page inside the `templates` folder.
8. Use Thymeleaf expressions to display dynamic data.
9. Run the Spring Boot application.
10. Open a browser and access the application through the specified URL.
11. Verify the output.

---

## PROJECT STRUCTURE

```text
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
```

---

## PROGRAM

### pom.xml

```xml
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

        <!-- Thymeleaf -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-thymeleaf</artifactId>
        </dependency>
    </dependencies>

</project>
```

### MvcApplication.java

```java
package com.example.mvc;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class MvcApplication {

    public static void main(String[] args) {
        SpringApplication.run(MvcApplication.class, args);
    }
}
```

### HomeController.java

```java
package com.example.mvc;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HomeController {

    @GetMapping("/")
    public String homePage(Model model) {
        model.addAttribute("message", "Welcome to Spring Boot MVC!");
        return "index";
    }
}
```

### index.html

```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Spring MVC</title>
</head>
<body>
    <h1 th:text="${message}">Default Message</h1>
</body>
</html>
```

### application.properties

```properties
server.port=8081
```

---

## OUTPUT

<img width="680" height="680" alt="image" src="https://github.com/user-attachments/assets/28ff4f53-7d59-448e-827d-4651445c6c46" />

<img width="681" height="403" alt="image" src="https://github.com/user-attachments/assets/e32c910f-3c4d-46c6-8a9c-e33eaa6cc667" />


## RESULT

Thus, a Simple Spring Boot MVC Application using Controller, Model, and Thymeleaf View was developed and executed successfully.
