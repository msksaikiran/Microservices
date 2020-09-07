# Microservices
Microservices with Spring Cloud Advanced Demo Project Twitter
In this project I'm demonstrating you the most interesting features of Spring Cloud Project for building microservice-based architecture to discuss some additional aspects like API documentation, configuration, testing or storing data.

Getting Started
Currently you may find here some examples of microservices implementation using different projects from Spring Cloud. All the examples are divided into the branches and described in a separated articles on my blog. Here's a full list of available examples:

Using Swagger2 for building API documentation and exposing it for all the microservices on API gateway, which is in that case Netlix Zuul. The example is available in the branch master. Detailed description can be found here: Microservices API Documentation with Swagger2
Using Spring Cloud Contract for consumer-driven contract testing in microservices architecture and embedded Mongo simulating database in component testing. The example is available in the branch testing. A detailed description can be found here: Testing Java Microservices.
Using Hoverfly library for testing APIs and for simulating communication between microservices in component testing. The tests with Hoverfly will include examples with static configuration through IP address and dynamic with Eureka discovery. The example is available in the branch hoverfly. A detailed description can be found here: Testing REST API with Hoverfly.
Using Spring Cloud Config on the client and server side for providing distributed configuration across microservices. These example will discuss some more advanced features. A detailed description can be found here: Microservices Configuration With Spring Cloud Config.
Usage
In the most cases you need to have Maven and JDK8+. The best way to run the sample applications is with IDEs like IntelliJ IDEA or Eclipse. For the some of examples you need to run MongoDB on Docker container, so you also need to have Docker installed on your local machine.

Architecture
Our sample microservices-based system consists of the following modules:

gateway-service - a module that Spring Cloud Netflix Zuul for running Spring Boot application that acts as a proxy/gateway in our architecture.
config-service - a module that uses Spring Cloud Config Server for running configuration server.
discovery-service - a module that depending on the example it uses Spring Cloud Netflix Eureka.
account-service - a module containing the first of our sample microservices that allows to perform CRUD operations on MongoDB repository of customer's accounts
customer-service - a module containing the second of our sample microservices that allows to perform CRUD operations on MongoDB repository of customers. It communicates with account-service and product-service.
product-service - a module containing the third of our sample microservices that allows to perform CRUD operations on MongoDB repository of products.
transfer-service - a module containing the fourth of our sample microservices that allows to perform CRUD operations on MongoDB repository making cash transfers between customer accounts. It communicates with both account-service.

The following picture illustrates an approach to a contract and component testing in our sample architecture described above.

Testinghttps://camo.githubusercontent.com/578454470f639f39e87fdda39171b4623356cef4/68747470733a2f2f70696f74726d696e6b6f77736b692e66696c65732e776f726470726573732e636f6d2f323031372f30342f74657374696e676d6963726f7365727669636573322e706e67

The whole sample architecture is visible on the picture below. Each microservice has its own database as shown on the following picture. For simplification in my articles I'm using a single database run on Docker container and multiple collections.

Architecture
