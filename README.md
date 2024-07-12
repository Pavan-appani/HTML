# HTML
detailed experience on HTML
HTML (HyperText Markup Language) is the standard markup language used to create web pages. It structures the content on the web with elements represented by tags. Basic tags include:

<html>: The root element of an HTML page.
<head>: Contains meta-information about the HTML document.
<title>: Sets the title of the web page.
<body>: Contains the content of the HTML document such as text, images, links, etc.
<h1> to <h6>: Header tags used to define headings.
<p>: Defines a paragraph.
<a>: Defines a hyperlink.
<img>: Embeds an image.
<div>: Defines a division or section.
<span>: Used to group inline elements.
Overview of Java
Java is a high-level, class-based, object-oriented programming language that is designed to have as few implementation dependencies as possible. It is widely used for building enterprise-scale applications.

Integrating HTML with Java
Java can be integrated with HTML in various ways to create dynamic and interactive web applications. Here are a few common methods:

1. Servlets
Servlets are Java programs that run on a web server, handle client requests, and generate dynamic web content. A servlet can generate HTML content and send it to the client's browser.

java

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


### 2. JSP (JavaServer Pages)
JSP allows embedding Java code directly into HTML pages. It is used to create dynamic web content by combining HTML and Java.

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


### 
Sure! Here's an overview of using HTML with Java:

Overview of HTML
HTML (HyperText Markup Language) is the standard markup language used to create web pages. It structures the content on the web with elements represented by tags. Basic tags include:

<html>: The root element of an HTML page.
<head>: Contains meta-information about the HTML document.
<title>: Sets the title of the web page.
<body>: Contains the content of the HTML document such as text, images, links, etc.
<h1> to <h6>: Header tags used to define headings.
<p>: Defines a paragraph.
<a>: Defines a hyperlink.
<img>: Embeds an image.
<div>: Defines a division or section.
<span>: Used to group inline elements.
Overview of Java
Java is a high-level, class-based, object-oriented programming language that is designed to have as few implementation dependencies as possible. It is widely used for building enterprise-scale applications.

Integrating HTML with Java
Java can be integrated with HTML in various ways to create dynamic and interactive web applications. Here are a few common methods:

1. Servlets
Servlets are Java programs that run on a web server, handle client requests, and generate dynamic web content. A servlet can generate HTML content and send it to the client's browser.

Example:

java
Copy code
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

### 2. JSP (JavaServer Pages)
JSP allows embedding Java code directly into HTML pages. It is used to create dynamic web content by combining HTML and Java.

Example:

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
Spring Boot is a framework for building web applications with Java, and Thymeleaf is a templating engine for rendering HTML. Together, they provide a powerful way to create dynamic web applications.

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






