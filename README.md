# HTML
Repository Structure
css
Copy code
html-java-integration/
├── servlets/
│   └── src/
│       └── main/
│           └── java/
│               └── com/
│                   └── example/
│                       └── HelloServlet.java
│           └── webapp/
│               └── WEB-INF/
│                   └── web.xml
├── jsp/
│   └── src/
│       └── main/
│           └── webapp/
│               └── hello.jsp
├── spring-boot-thymeleaf/
│   └── src/
│       └── main/
│           └── java/
│               └── com/
│                   └── example/
│                       └── HelloController.java
│           └── resources/
│               └── templates/
│                   └── hello.html
│           └── application.properties
│           └── Application.java
└── README.md

### 1. Servlets
HelloServlet.java
java
Copy code
package com.example;

import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet("/hello")
public class HelloServlet extends HttpServlet {
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        out.println("<html><body>");
        out.println("<h1>Hello, World!</h1>");
        out.println("</body></html>");
    }
}
web.xml
xml
Copy code
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd" version="3.1">
    <servlet>
        <servlet-name>HelloServlet</servlet-name>
        <servlet-class>com.example.HelloServlet</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>HelloServlet</servlet-name>
        <url-pattern>/hello</url-pattern>
    </servlet-mapping>
</web-app>


### 2. JSP
hello.jsp
jsp
Copy code
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
    <title>Hello JSP</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <%
        String name = "Java";
        out.println("<p>Welcome to " + name + "!</p>");
    %>
</body>
</html>

        
 ### 3. Spring Boot with Thymeleaf
HelloController.java
java
Copy code
package com.example;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HelloController {
    @GetMapping("/hello")
    public String hello(Model model) {
        model.addAttribute("name", "Spring Boot");
        return "hello";
    }
}
hello.html
html
Copy code
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Hello Spring Boot</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>Welcome to <span th:text="${name}"></span>!</p>
</body>
</html>
Application.java
java
Copy code
package com.example;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Application {
    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}
application.properties
properties
Copy code
spring.thymeleaf.cache=false
spring.thymeleaf.enabled=true
README.md
markdown
Copy code
# HTML and Java Integration

This repository demonstrates the integration of HTML with Java using three different methods: Servlets, JSP, and Spring Boot with Thymeleaf.

## 1. Servlets

### Running the Servlet Example
1. Navigate to the `servlets` directory.
2. Compile the Java code and deploy it on a web server like Apache Tomcat.
3. Access the servlet at `http://localhost:8080/hello`.

## 2. JSP

### Running the JSP Example
1. Navigate to the `jsp` directory.
2. Deploy the JSP file on a web server that supports JSP, such as Apache Tomcat.
3. Access the JSP page at `http://localhost:8080/hello.jsp`.

## 3. Spring Boot with Thymeleaf

### Running the Spring Boot Example
1. Navigate to the `spring-boot-thymeleaf` directory.
2. Run the Spring Boot application using `mvn spring-boot:run` or your preferred method.
3. Access the Thymeleaf page at `http://localhost:8080/hello`.

## Prerequisites
- Java Development Kit (JDK)
- Apache Tomcat (for Servlets and JSP examples)
- Maven (for Spring Boot example)

## License
This project is licensed under the MIT License.
