# Interview

## Java

### Data Structure
---
How many collection do you know ?

    List, Set, Queue

Implementation ?

    LinkedList, ArrayList
    HashSet, LinkedHashSet, EnumSet, TreeSet
    PriorityQueue

List Complexity ?

| Implementation | Add  | Contains | Get    | Remove   |
| -------------- |:----:|:--------:|:------:|:--------:|
| LinkedList     | O(1) | O(n)     |  O(n)  | O(1)     |
| ArrayList      | O(1) | O(n)     |  O(1)  | O(n)     |

Set Complexity ?

| Implementation | Add  | Contains | Next    |
| -------------- |:----:|:--------:|:-------:|
| HashSet        | O(1) | O(1)     |  O(h/n) |
| LinkedHashSet  | O(1) | O(1)     |  O(1)   |
| EnumSet        | O(1) | O(1)     |  O(1)   |
| TreeSet        | O(log n | O(log n)     |  O(log n)   |

Queue ?

| Implementation | Offer     | Peak     | Poll       | Size     |
| -------------- |:---------:|:--------:|:----------:|:--------:|
| PriorityQueue  | O(log n)  | O(1)     |  O(log n)  | O(1)     |


What is a map ? 

    Key Value datastructure

Implementation ?

    HashMap, EnumMap, TreeMap

Set Complexity

| Implementation | Get  | ContainsKey | Next    |
| -------------- |:----:|:-----------:|:-------:|
| HashMap        | O(1) | O(1)        |  O(h/n) |
| EnumMap        | O(1) | O(1)        |  O(1)   |
| TreeMap        | O(log n) | O(log n)|  O(log n)   |

What should be done by a developer to use correctly Maps ?

    Implemente hashCode() and equals() on the class, and make sure the methods are immutable.

Why ?

    Because hashCode() is require in order to access find the buck of element E and equals() is require in order to find the element in the list. With a mutable object the element E will be lost and produce a memory leak.

### Generics
---
    Generics allow you to abstract over types. The most common examples are container types, such as those in the Collections hierarchy.
    
```java
new LinkedList<T>();
new LinkedList<? extends Integer>();
new LinkedList<? super Number>();
```

### Composition vs Inheritence
---
    Single Inheritance is not the Problem
    Composition is easier to maintain
    Composition generates more code (delegate)

```java
class A extends B {
 ...
}

class A {
    private B b;
}
```

### Other
---

What is the difference between class and interface ?

    An interface provides a contract, whereas a class provides an implementation of a contract.
    We can extends multiple interfaces, but only 1 class

What is an excepttion ?

    Object create when an error occured

What do you think about Exception driven developpment ?

    ITs SHIT ! because it's slow, not maintainable and wrong

### Scope
---
| Modifier 	| Class | Package | Subclass | World |
|-----------|:-----:|:-------:|:--------:|:-----:|
|public     |   Y   |  Y      |      Y   |   Y   |
|protected  |	Y   |  Y      |      Y   |	 N   |
|default    |	Y   |  Y      |      N   |   N   |
|private    |   Y 	|  N      |      N   |	 N   |

### Java 8 ?
---
    Functional API
    Lambda Expression
    default and static method in Interface 
    java time api
    forEach
    concurrency api improvement
    IO improvement
    Optional

### Java 9 ?
---
    jigsaw / module-info.java
    Function API works with Optional
    JShell
    Immutable Factory Methods
    private methods in interfaces
    Process API
    Try with Ressource
    Reactive Streams (Flow)
    CompletableFuture API
    Enhanced @Deprecated Annotation (add @forRemoval)
    HTTP 2 client

## Spring
What the main functionnality of Spring Core ?
    
    Dependency Injection and Inversion of Control

What are the different part of Spring Framework ?

    Core
    Web
    Data Access (JDBC, ORM, JMS, AMQP, Transaction)
    Web (Servlet, Web, Portlet)
    AOP, Aspects

What is the difference between @Autowired vs @Inject (JSR 330)

    There are no differncies, @Inject is the new standard, @Autowired is the first version

How do you configure your project to use @Autowired ?

```java
@Configuration
@ComponentScan("com.package")```
```

```xml
<context:annotation-config />
```

How spring find the correct bean when using `@Autowired` ?

    by Type injections

When do we use the `@Qualifier` ?

    by Name injection

What happens if you have twice the same bean declared with Java Config ?

    compile : ok
    runtime : throws `NoUniqueBeanDefinitionException` -> Can use `@Primary`

What happens if you have twice the same bean declared in xml ?

    compile : ok
    runtime : ok

## Testing

Who write tests and what does he uses ?

    The developper, QA, Business Analyste
    Uses of Jenkins, JUnit, Seleniums, Cucumber, Jbehave

What type of test you can write ?

    Unit, integration, end to end (e2e)

What is the difference between them ?

    unit : test on unit (instance of a class)
    integration : test at least 2 differnets components that comunicates
    e2e : test as much as possible the complete application

Is 100% coverage useful ?

    Open question to test the candidate

What is Jenkins ?

    Continuous Integration Server

What is the usage of @Before ?

    Execute a method before each test

How to execute an instruction like "start db" only once per class ?

    Use @BeforeClass

What is new in JUnit 5 ?

    Junit platform + Junit Jupiter + Junit vintage
    @DisplayName
    @BeforeEach
    @BeforeAll
    @Disabled
    @Tag
    @ParameterizedTest

## Databases

What is the standard language to talk to Databases ?

    Structured Query Language

What is the diference with No-SQL ?

    NO-SQL use a specific language different from SQL in order to achieve a give task ex: LDAP, Neo4j (CypherQL), MangoDB

What is JDBC ?

    Java Database Connnectivity defines how a client should access the DB and provides methods for CRUD operations

What is JPA ?
    
    Java Persistence API allow the tranformation from object to database and vice versa used for ORM and provides methods for CRUD operations

What is ORM ?

    Stands for Object-Relational Mapping which is a database Abstraction Layer

Do you know any ?

    Hibernate, QueryDSL

How Hiberante works ?

    HQL and Criteria API
    Use the SessionFactory
    Implementation of JPA
    Has 2 levels of cache where second is optional
    Manages transactions
    Query-level cache

What must be done to use the 2nd level of Cache ?

    Choose concurrency strategy
    Choose cache provider

What's the advantage of QueryDSL ?

    Allows for generation of type-safe queries very close to SQL

## Front Web

## Web

What is HTML ?

    XML based language to structure a web page

What is CSS ?

    Application of a set of rule on HTML in order to modify it's aspect

What is Boostrap or B.E.M ?

    Boostrap is ready to use css stylesheets
    BEM is a naming convention to improve maintenability and css liking

What is Javascript ?

    Scripting language most of the time executed on client side and able to dynamically control the HTML page using event.

What is NodeJS ?

    Javascript for server using V8 engine from Google Chrome.

What is NPM ?

    Node package manager for dependency of Javascript application

## REpresentation State Transfer API
    
Do you know any HTTP verbs ?

    GET : read a resource
    PUT : update a given resource or create if does not exists
    POST : create a new resource
    DELETE : delete the resource

What is the status code send back to the client in case of an error ?

    5xx

What is the status code send back to the client in case of client error ?

    4xx

How can we manage atomic operation with multiple REST api ?

    Very complicated ! Anti-pattern ALERT ALERT !!!

## Ecosystem
### Libs
    guava, vavar.io, yoda time, lombock, commons lang

### Maven

How Maven works ?

    Build tool for jvm application
    dependency resolution [A->D->Cv1, B->Cv2] -> Cv2 shortest path
    
What is the name of the plugin responsible to compile ?

    maven-compiler-plugin

What is the name of the plugin responsible to run unit test ?

    maven-surefire-plugin

What is the name of the plugin responsible to run integration test ?

    maven-failsafe-plugin

What are the main phase of maven life cycle ?

    validate, compile, test, package, verify, install, deploy

### Mercurial

What is Mercurial for ?

    Source Control Management tool


## Others
What is Docker, rkt ?

    container technology
    Build, Ship, Run any App anywhere

What is Docker Swarm, Kubernetes ?

    cluster management and orchetrator

Swarm vs K8s ?

    Swarm runs only docker images whereas K8S any images

## Object Principle & Design Patterns
     1 DRY (Don't repeat yourself) — avoids duplication in code
     2 Encapsulate what changes — hides implementation detail, helps in maintenance
     3 Open Closed design principle — open for extension, closed for modification
     4 SRP (Single Responsibility Principle) — one class should do one thing and do it well
     5 DIP (Dependency Inversion Principle) — don't ask, let framework give to you
     6 Favor Composition over Inheritance — code reuse without cost of inflexibility
     7 LSP (Liskov Substitution Principle) — sub type must be substitutable for super type
     8 ISP (Interface Segregation Pricinciple) — avoid monilithic interface, reduce pain on client side
     9 Programming for Interface — helps in maintenance, improves flexibility
    10 Delegation principle — don't do all things by yourself, delegate it

## Agility

Describe SCRUM

    daily standup
    retrospective 
    demo for business
    code review
    grooming

## General

* How do you deal with bugs ?
* How do you deal with production issues ?
* Do you use linux ?
* Do you have a github ?
* Do you have personal projects ?