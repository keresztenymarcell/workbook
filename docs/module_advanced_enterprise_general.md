# General enterprise questions

## Software engineering

### Architectures

#### What is n-tier (or multi-tier) architecture?

N-tier architecture is also called multi-tier architecture because the software is engineered to have the processing, data management, and presentation functions physically and logically separated. 
- Presentation tier
- Business tier
- Data tier

#### What are microservices? Advantages and disadvantages?
 
Microservices are an architectural and organizational approach to software development where software is composed of small independent services that communicate over well-defined APIs. 

#### What is Separation of Concerns?
In computer science, separation of concerns (SoC) is a design principle for separating a computer program into distinct sections.
A program that embodies SoC well is called a modular program. Modularity, and hence separation of concerns, is achieved by encapsulating information inside a section of code that has a well-defined interface. Encapsulation is a means of information hiding. Layered designs in information systems are another embodiment of separation of concerns (e.g., presentation layer, business logic layer, data access layer, persistence layer)

#### What is a layered design and why is it important in enterprise applications?
Layered architectures are said to be the most common and widely used architectural framework in software development. It is also known as an n-tier architecture and describes an architectural pattern composed of several separate horizontal layers that function together as a single unit of software. 

## Advantages

- The framework is simple and easy to learn and implement.
- There is reduced dependency because the function of each layer is separate from the other layers.
- Testing is easier because of the separated components, each component can be tested individually.



#### What is Dependency Injection?
Dependency injection is basically providing the objects that an object needs (its dependencies) instead of having it construct them itself. It's a very useful technique for testing, since it allows dependencies to be mocked or stubbed out.

## Possible ways
- Constructor
- Setter
- Interface 

## Advantages 
- Helps unit testing
- Extending code becomes easier
- Boiler plate code is reduced


#### What is the DAO pattern? When and how to implement?
The Data Access Object (DAO) pattern is a structural pattern that allows us to isolate the application/business layer from the persistence layer (usually a relational database but could be any other persistence mechanism) using an abstract API.



#### What is SOA? When to use?
Service-Oriented Architecture (SOA) is a stage in the evolution of application development and/or integration. It defines a way to make software components reusable using the interfaces. Different from Microservices.

Advantages:

- Service reusability: In SOA, applications are made from existing services. Thus, services can be reused to make many applications.
- Easy maintenance: As services are independent of each other they can be updated and modified easily without affecting other services.
- Platform independent: SOA allows making a complex application by combining services picked from different sources, independent of the platform.
- Availability: SOA facilities are easily available to anyone on request.
- Reliability: SOA applications are more reliable because it is easy to debug small services rather than huge codes
- Scalability: Services can run on different servers within an environment, this increases scalability



### Testing

#### What are unit test, integration test, system test, regression test, acceptance test? What is the major difference between these?
- UNIT TESTING is a type of software testing where individual units or components of a software are tested. The purpose is to validate that each unit of the software code performs as expected. Unit Testing is done during the development (coding phase) of an application by the developers. Unit Tests isolate a section of code and verify its correctness. A unit may be an individual function, method, procedure, module, or object.

- INTEGRATION TESTING is defined as a type of testing where software modules are integrated logically and tested as a group. A typical software project consists of multiple software modules, coded by different programmers. The purpose of this level of testing is to expose defects in the interaction between these software modules when they are integrated.

- SYSTEM TESTING is a level of testing that validates the complete and fully integrated software product. The purpose of a system test is to evaluate the end-to-end system specifications. Usually, the software is only one element of a larger computer-based system. Ultimately, the software is interfaced with other software/hardware systems. System Testing is actually a series of different tests whose sole purpose is to exercise the full computer-based system.

- REGRESSION TESTING is defined as a type of software testing to confirm that a recent program or code change has not adversely affected existing features. Regression Testing is nothing but a full or partial selection of already executed test cases which are re-executed to ensure existing functionalities work fine.

- USER ACCEPTANCE TESTING (UAT) is a type of testing performed by the end user or the client to verify/accept the software system before moving the software application to the production environment. UAT is done in the final phase of testing after functional, integration and system testing is done. Done by Client or End Users. 



#### What is code coverage? Why is it used? How you can measure?
Code coverage is a software testing metric that determines the number of lines of code that is successfully validated under a test procedure, which in turn, helps in analyzing how comprehensively a software is verified.
Code coverage is one such software testing metric that can help in assessing the test performance and quality aspects of any software.

Benefits: 
- Easy maintenance of code base
- Exposure of bad code
- Faster time to market

- Code Coverage Percentage = (Number of lines of code executed by a testing algorithm/Total number of lines of code in a system component) * 100.


#### What does mocking mean? How would you do it 'manually' (i. e. without using any fancy framework)?
Mocking is primarily used in unit testing. An object under test may have dependencies on other (complex) objects. To isolate the behavior of the object you want to replace the other objects by mocks that simulate the behavior of the real objects. This is useful if the real objects are impractical to incorporate into the unit test.


In Java for example, we can use polymorphism in our advantage. We could create a child class of the class which we want to mock and override its method. 

#### What is a test case? What is an assertion? Give examples!
A Test Case is a set of actions executed to verify a particular feature or functionality of your software application. A Test Case contains test steps, test data, precondition, postcondition developed for specific test scenario to verify any requirement.





#### What is TDD? What are the benefits?


#### What are the unit testing best practices? (Eg. how many assertion should a test case contain?)
#### What is arrange/act/assert pattern?

### DevOps

#### What is continuous integration? Why is CI important?
#### Why are tests important in the CI workflow?
#### Name some software that help the CI workflow!
#### What is Continuous Delivery?
#### What is Continuous Deployment?
#### What is DevOps?

### Software Methodologies

#### What kind of software-lifecycle models do you know?
- Waterfall Model.
- V-Shaped Model.
- Iterative Model.
- Spiral Model.
- Big Bang Model.
- Agile Model.
#### What is a UML diagram? What kind of diagram types do you know?
UML is a standardized modeling language that can be used across different programming languages and development processes, so the majority of software developers will understand it and be able to apply it to their work.

1. Structural Diagrams: 
    - Class Diagram : Shows static structure of the classes including classes, their attributes and behaviour and relationships between them.
    - Component Diagram: Breaks down the system into components, and visualizes the relationship between them.
    - Deployment Diagrams: Show how software is deployed on hardware components in a system.
    - Object Diagram: Shows examples of data structures in a specific time. You could use a class diagram to show a structure and then show an Object Diagram as test cases.
    - Package Diagram: Shows dependencies between packages.
2. Behavioral Diagrams:
    - Use Case Diagram: Shows how users would interact with the system.
    - Sequence Diagram: Shows the order in which objects interact. This way, you can visually represent simple runtime scenarios.
    - Activity Diagram: Visualize the steps performed in a use case—the activities can be sequential, branched, or concurrent. 
    - State Diagram: ...
    - Communication Diagram: ...

#### What is a UML class diagram? What are the typical elements?
Shows static structure of the classes including classes, their attributes and behaviour and relationships between them.
 - Rectangle: Represents a class, its attributes(with visibility) and behaviours.
 - Arrow: Inharitance
 - Black Diamond Arrow: Composition
 - White Diamon Arrow: Aggregation
 - Line: Association 

#### What kind of design patterns do you know? Bring at least 3 examples.
1. Builder Pattern: 
    - To create an object, you execute a series of these steps on a builder object. The important part is that you don’t need to call all of the steps. You can call only those steps that are necessary for producing a particular configuration of an object.
2. Factory Pattern: 
    - 

3. Singleton Pattern: 
    - Singleton is a creational design pattern that lets you ensure that a class has only one instance, while providing a global access point to this instance.


 #### What is the purpose of the Iterator Pattern?
 In object-oriented programming, the iterator pattern is a design pattern in which an iterator is used to traverse a container and access the container's elements. The iterator pattern decouples algorithms from containers; in some cases, algorithms are necessarily container-specific and thus cannot be decoupled.
#### What do you know about the SOLID principles?
#### How would you separate data storage code and business logic code (which uses stored data) in an application?

## Computer science

### Data Structures
#### What is the difference between Stack and Queue data structure?
#### What is a graph? What are simple graphs? What are directed graphs? What are weighted graphs?
#### What are trees? What are binary trees? What are binary search trees?
#### How can you store graphs in programs? What are the advantages/disadvantages per each?
#### What are graph traversal algorithms? What is BFS, how does it work? What is DFS, how does it work?
#### How does dictionary work?
#### Why is it important for keys in a hashmap to have an immutable type? (Consider string for example.)

### Algorithms
#### What is QuickSort? Describe the main logic of this sorting algorithm.

## Software design

### Security

#### What is OAuth2?
he OAuth (open authorization) protocol was developed by the Internet Engineering Task Force and enables secure delegated access. It lets an application access a resource that is controlled by someone else (end user). This kind of access requires Tokens, which represent delegated right of access. Usually it uses JWT (JsonWebToken) as the acces token.


#### What is Basic Authentication?
HTTP Basic Authentication requires that the server request a user name and password from the web client and verify that the user name and password are valid by comparing them against a database of authorized users. In the HEADER.
#### What is CORS, why it’s needed in browsers?


#### How can you initialize a CSRF attack?
#### What is JWT used for? Where to store it on client side?

### Threaded programming

#### When do you need to use threads in an application?
1.  Parallel Programming
One of the main reasons to use threads in Java is to make a task run parallel to another task like drawing and event handling.

2. To take full advantage of CPU power.
Another common reason for using multiple threads in Java is to improve the throughput of the application by utilizing full CPU power.

3. For reducing response time
You can also use multiple threads to reduce response time by doing fast computation by dividing a big problem into smaller chunks and processing them by using multiple threads.

4. To sever multiple clients at the same time.
One of the most common scenarios where using multiple threads significantly improves an application's performance is a client-server application.



#### What is a daemon thread?
Daemon thread in Java is a low-priority thread that runs in the background to perform tasks such as garbage collection. Daemon thread in Java is also a service provider thread that provides services to the user thread. Its life depends on the mercy of user threads i.e. when all the user threads die, JVM terminates this thread automatically.

In simple words, we can say that it provides services to user threads for background supporting tasks. It has no role in life other than to serve user threads.
#### What is the difference between concurrent and parallel execution of code?
- Concurrency is when two tasks can start, run, and complete in overlapping time periods. Parallelism is when tasks literally run at the same time, eg. on a multi-core processor.

- Concurrency is the composition of independently executing processes, while parallelism is the simultaneous execution of (possibly related) computations.

- Concurrency is about dealing with lots of things at once. Parallelism is about doing lots of things at once.

#### What is the most important problem developers are faced when using threads?
- Unpredictable results− Multithreaded programs can sometimes lead to unpredictable results as they are essentially multiple parts of a program that are running at the same time.

- Testing Complications− Testing is a complicated process i multithreaded programs as compared to single threaded programs. This is because defects can be timing related and not easy to identify.


#### In what kind of situations can deadlocks occur?
In concurrent computing, deadlock is any situation in which no member of some group of entities can proceed because each waits for another member, including itself, to take action, such as sending a message or, more commonly, releasing a lock. 

#### What are possible ways to prevent deadlocks from occurring?


#### What does critical section or critical region mean in the context of concurrent programming?
