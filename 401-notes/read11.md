# What is Spring Boot

Spring Boot is a project that is built on the top of the Spring Framework. It provides an easier and faster way to set up, configure, and run both simple and web-based applications.

##### It is a Spring module that provides the RAD (Rapid Application Development) feature to the Spring Framework. It is used to create a stand-alone Spring-based application that you can just run because it needs minimal Spring configuration.

![](https://static.javatpoint.com/springboot/images/what-is-spring-boot.png)


### Advantages of Spring Boot
  - It creates stand-alone Spring applications that can be started using Java -jar.
  - It tests web applications easily with the help of different Embedded HTTP servers such as Tomcat, Jetty, etc. We don't need to deploy WAR files.
  - It provides opinionated 'starter' POMs to simplify our Maven configuration.
  - It provides production-ready features such as metrics, health - checks, and externalized configuration. There is no requirement for XML configuration.
  - It offers a CLI tool for developing and testing the Spring Boot application.
  - It offers the number of plug-ins.
  - It also minimizes writing multiple boilerplate codes (the code that has to be included in many places with little or no alteration), XML configuration, and annotations.
  - It increases productivity and reduces development time.


**Spring MVC and Thymeleaf**
* Spring MVC application contains:
  - @Controller classes - responsible for preparing a model map with data and selecting a view to be rendered
  - model map allows for the complete abstraction of the view technology, and in the case of Thymeleaf, it is transformed into a Thymeleaf context object that makes all the defined variables available to expressions executed in templates
  - Spring model attributes:
    * model attributes - Spring MVC calls the pieces of data that can be accessed during the execution of views 
    * context variables - Thymeleaf language version of model attributes
  - Request parameters
    * Request parameters - easily accessed in Thymeleaf views, and passed from the client to server
  - Session attributes 
    * Session attributes - can be accessed by using the session. prefix or using #session
  - ServletContext attributes 
    * ServletContext attributes - shared between requests and sessions, and to access ServletContext attributes in Thymeleaf you can use the #servletContext. prefix
  - Spring beans
    * Thymeleaf allows accessing beans registered at the Spring Application Context with the @beanName syntax