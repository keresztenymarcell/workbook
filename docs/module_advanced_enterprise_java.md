# Enterprise module (Java branch)

### Java Enterprise and Spring

#### What are the possible uses of reflection?

#### What is Spring?
The Spring Framework (Spring) is an open-source application framework that provides infrastructure support for developing Java applications. One of the most popular Java Enterprise Edition (Java EE) frameworks, Spring helps developers create high performing applications using plain old Java objects.



#### What is Spring Boot?
#### What is the major difference between the Standard edition (JSE) and Enterprise edition (JEE)? You can choose Spring (Spring Boot) instead of JavaEE. Focus on comparing them.
#### What are the advantages of the Spring Framework? Focus on the Core part.
1. Spring enables the developers to develop enterprise applications using POJOs (Plain Old Java Object). The benefit of developing the applications using POJO is, that we do not need to have an enterprise container such as an application server but we have the option of using a robust servlet container.
2. Spring comes with some of the existing technologies like ORM framework, logging framework, J2EE and JDK Timers etc, Hence we don’t need to integrate explicitly those technologies.
3. Spring provides an abstraction layer on existing technologies like servlets, jsps, jdbc, jndi, rmi, jms and Java mail etc., to simplify the develpment process.

#### What is a servlet? What is the purpose of DispatcherServlet in Spring?
A servlet is a Java programming language class that is used to extend the capabilities of servers that host applications accessed by means of a request-response programming model. Although servlets can respond to any type of request, they are commonly used to extend the applications hosted by web servers. For such applications, Java Servlet technology defines HTTP-specific servlet classes.

Simply put, in the Front Controller design pattern, a single controller is responsible for directing incoming HttpRequests to all of an application's other controllers and handlers.
Spring's DispatcherServlet implements this pattern and is, therefore, responsible for correctly coordinating the HttpRequests to their right handlers.

#### When do you use RestControllers, when just simple Controllers?
The main difference between the @Restcontroller and the @Controller is that the @Restcontroller combination of the @Controller and @ResponseBody annotation. 
- RestController: RestController is used for making restful web services with the help of the @RestController annotation.
#### What is Spring Application Context?
One of the main features of the Spring framework is the IoC (Inversion of Control) container. The Spring IoC container is responsible for managing the objects of an application. It uses dependency injection to achieve inversion of control.

The interfaces BeanFactory and ApplicationContext represent the Spring IoC container. Here, BeanFactory is the root interface for accessing the Spring container. It provides basic functionalities for managing beans.

On the other hand, the ApplicationContext is a sub-interface of the BeanFactory. Therefore, it offers all the functionalities of BeanFactory.

Furthermore, it provides more enterprise-specific functionalities. The important features of ApplicationContext are resolving messages, supporting internationalization, publishing events, and application-layer specific contexts. This is why we use it as the default Spring container.
#### What are the main ways to define a bean in the Application Context?
1. Java Based Configuration


2. Annotation Based Configuration


3. XML Based Configuration
#### Difference between .jar and .war files.
- Jar file: A file with Java classes, associated metadata and resources such as text, images aggregated into one file.
- War file: A file that is used to distribute a collection of JAR files, JSP, Servlet, XML files, static web pages like HTML and other resources that constitute a web application.

#### What are the major differences between Maven, Ant and Gradle?
#### What is Maven used for?
#### What does a pom.xml file contains in Maven?
The pom. xml file contains information of project and configuration information for the maven to build the project such as dependencies, build directory, source directory, test source directory, plugin, goals etc. Maven reads the pom. xml file, then executes the goal.

### Object Relational Mapping, JPA

#### What is an ORM? What are the benefits, when to use?
Object-Relational Mapping (ORM) is a technique that lets you query and manipulate data from a database using an object-oriented paradigm. When talking about ORM, most people are referring to a library that implements the Object-Relational Mapping technique, hence the phrase "an ORM".

An ORM library is a completely ordinary library written in your language of choice that encapsulates the code needed to manipulate the data, so you don't use SQL anymore; you interact directly with an object in the same language you're using.
#### What is the difference between JDBC and JPA? Which are the advantages and disadvantages of each? Give a general overview.
1. JDBC: 
    - JDBC is a programming-level interface for Java applications that communicate with a database. An application uses this API to communicate with a JDBC manager. It's the common API that our application code uses to communicate with the database. Beyond the API is the vendor-supplied, JDBC-compliant driver for the database we're using.
2. JPA: 
    - JPA is a Java standard that allows us to bind Java objects to records in a relational database. It's one possible approach to Object Relationship Mapping(ORM), allowing the developer to retrieve, store, update, and delete data in a relational database using Java objects. Several implementations are available for the JPA specification.

#### What is Hibernate? What are the advantages, limitations?
Hibernate ORM (or simply Hibernate) is an object–relational mapping tool for the Java programming language. It provides a framework for mapping an object-oriented domain model to a relational database. Hibernate handles object–relational impedance mismatch problems by replacing direct, persistent database accesses with high-level object handling functions.

Advantages: 
- Open source, lightweight
- Fast performance
- DB independent query
- Automatic table creation
- Simplifies Complex joins

Limitations: 
- Performace cost: slower then JDBC
- Not allow multiple inserts
- Learning curve
- Not good for small projects

#### Name 3 different annotations used in JPA, what can they do for you?
- @Id: tell which column is the id
- @OneToOne: annotate a one to one db relationship
- @Table: give specific table name
#### What is object-relational impedance mismatch?


#### What is a JpaRepository? What are the 2 main methods to define queries in them?
#### Why is the Set preferred over List when we want to store OneToMany relations?
The lookup time in a Set is O(1) while in a list is O(n), and set doesnt allow duplications.
#### What kind of inheritance strategies are available? Which annotations are used to solve this?
