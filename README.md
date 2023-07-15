*[English](README.md) ∙ [Русский](README-ru.md)*

## Programming paradigms

* **imperative** in which the programmer instructs the machine how to change its state
    * *structured and procedural* - most often we should be able to use the term interchangeably but with subtle
      differences. When higher level languages begun to get richer, one realized that all units of work should be broken
      into smaller tractable parts - that is when functions came into existence and programming became a hierarchy of
      functions and many at lower level could be re-used.
    * *object-oriented* which groups instructions with the part of the state they operate on.
* **declarative** in which the programmer merely declares properties of the desired result, but not how to compute it
    * *functional* in which the desired result is declared as the value of a series of function applications.
    * *logic* in which the desired result is declared as the answer to a question about a system of facts and rules.
    * *reactive* in which the desired result is declared with data streams and the propagation of change

### Object-oriented programming (OOP)

Alan Kay summarized five basic characteristics of Smalltalk, the first successful object-oriented language and one of
the languages upon which Java is based. These characteristics represent a pure approach to object-oriented programming:

1. Everything is an object. Think of an object as a fancy variable; it stores data, but you can “make requests” to that
   object, asking it to perform operations on itself. In theory, you can take any conceptual component in the problem
   you’re trying to solve (dogs, buildings, services, etc.) and represent it as an object in your program.
2. A program is a bunch of objects telling each other what to do by sending messages. To make a request of an object,
   you “send a message” to that object. More concretely, you can think of a message as a request to call a method that
   belongs to a particular object.
3. Each object has its own memory made up of other objects. Put another way, you create a new kind of object by making a
   package containing existing objects. Thus, you can build complexity into a program while hiding it behind the
   simplicity of objects.
4. Every object has a type. Using the parlance, each object is an instance of a class, in which “class” is synonymous
   with “type.” The most important distinguishing characteristic of a class is “What messages can you send to it?”
5. All objects of a particular type can receive the same messages. This is actually a loaded statement, as you will see
   later. Because an object of type “circle” is also an object of type “shape,” a circle is guaranteed to accept shape
   messages. This means you can write code that talks to shapes and automatically handle anything that fits the
   description of a shape. This substitutability is one of the powerful concepts in OOP.

Basic principles of structuring:

* *Abstraction* from implementation (?)
* *Encapsulation* prevents external code from being concerned with the internal workings of an object. This facilitates
  code refactoring, for example allowing the author of the class to change how objects of that class represent their
  data internally without changing any external code (as long as "public" method calls work the same way). It also
  encourages programmers to put all the code that is concerned with a certain set of data in the same class, which
  organizes it for easy comprehension by other programmers. Encapsulation is a technique that encourages decoupling.
* *Inheritance* allows classes to be arranged in a hierarchy that represents "is-a-type-of" relationships. All the data
  and methods available to the parent class also appear in the child class with the same names. This technique allows
  easy re-use of the same procedures and data definitions, in addition to potentially mirroring real-world relationships
  in an intuitive way. Rather than utilizing database tables and programming subroutines, the developer utilizes objects
  the user may be more familiar with: objects from their application domain.
* *Polymorphism* – is when calling code can be independent of which class in the supported hierarchy it is operating on
  – the parent class or one of its descendants. Meanwhile, the same operation name among objects in an inheritance
  hierarchy may behave differently.

### Aspect-oriented programming (AOP)

AOP is often referred to as a tool for implementing crosscutting concerns. The term crosscutting concerns refers to
logic in an application that cannot be decomposed from the rest of the application and may result in code duplication
and tight coupling. By using AOP for modularizing individual pieces of logic, known as concerns, you can apply them to
many parts of an application without duplicating the code or creating hard dependencies. Logging and security are
typical examples of crosscutting concerns that are present in many applications. Consider an application that logs the
start and end of every method for debugging purposes. You will probably refactor the logging code into a special class,
but you still have to call methods on that class twice per method in your application in order to perform the logging.
Using AOP, you can simply specify that you want the methods on your logging class to be invoked before and after each
method call in your application. It is important to understand that AOP complements object-oriented programming (OOP),
rather than competing with it. OOP is very good at solving a wide variety of problems that we, as programmers,
encounter. However, if you look at the logging example again, it is obvious to see where OOP is lacking when it comes to
implementing crosscutting logic on a large scale. Using AOP on its own to develop an entire application is practically
impossible, given that AOP functions on top of OOP. Likewise, although it is certainly possible to develop entire
applications by using OOP, you can work smarter by employing AOP to solve certain problems that involve crosscutting
logic:

* AOP Concepts As with most technologies, AOP comes with its own specific set of concepts and terms. The following are
  the core concepts of AOP:
    * *Joinpoints*: A joinpoint is a well-defined point during the execution of your application. Typical examples of
      joinpoints include a call to a method, the method invocation itself, class initialization, and object
      instantiation. Joinpoints are a core concept of AOP and define the points in your application at which you can
      insert additional logic using AOP.
    * *Advice*: The code that is executed at a particular joinpoint is the advice, defined by a method in your class.
      There are many types of advice, such as before, which executes before the joinpoint, and after, which executes
      after it.
    * *Pointcuts*: A pointcut is a collection of joinpoints that you use to define when advice should be executed. By
      creating pointcuts, you gain fine-grained control over how you apply advice to the components in your application.
      As mentioned previously, a typical joinpoint is a method invocation, or the collection of all method invocations
      in a particular class. Often you can compose pointcuts in complex relationships to further constrain when advice
      is executed.
    * *Aspects*: An aspect is the combination of advice and pointcuts encapsulated in a class. This combination results
      in a definition of the logic that should be included in the application and where it should execute.
    * *Weaving*: This is the process of inserting aspects into the application code at the appropriate point. For
      compile-time AOP solutions, this weaving is generally done at build time. Likewise, for runtime AOP solutions, the
      weaving process is executed dynamically at runtime. AspectJ supports another weaving mechanism called load- time
      weaving (LTW), in which it intercepts the underlying JVM class loader and provides weaving to the bytecode when it
      is being loaded by the class loader.
    * *Target*: An object whose execution flow is modified by an AOP process is referred to as the target object. Often
      you see the target object referred to as the advised object.
    * *Introduction*: This is the process by which you can modify the structure of an object by introducing additional
      methods or fields to it. You can use introduction AOP to make any object implement a specific interface without
      needing the object’s class to implement that interface explicitly.

## Data structures

* List
* Black-white tree
* BI-tree

## O-notation

## Algorithm complexity

## SOLID, DRY

## Programming patterns

## Software development process

Test-driven development (TDD)

Model Driven Architecture (MDA)

### Agile

Agile software development values. Based on their combined experience of developing software and helping others do that, the authors of the manifesto declared that they valued:[4]

* **Individuals and interactions** over processes and tools
* **Working software** over comprehensive documentation
* **Customer collaboration** over contract negotiation
* **Responding to change** over following a plan

Agile software development principles. The Manifesto for Agile Software Development is based on twelve principles:

1. Customer satisfaction by early and continuous delivery of valuable software.
2. Welcome changing requirements, even in late development.
3. Deliver working software frequently (weeks rather than months).
4. Close, daily cooperation between business people and developers.
5. Projects are built around motivated individuals, who should be trusted.
6. Face-to-face conversation is the best form of communication (co-location).
7. Working software is the primary measure of progress.
8. Sustainable development, able to maintain a constant pace.
9. Continuous attention to technical excellence and good design.
10. Simplicity—the art of maximizing the amount of work not done—is essential.
11. Best architectures, requirements, and designs emerge from self-organizing teams.
12. Regularly, the team reflects on how to become more effective, and adjusts accordingly.

## JSON, Protocol Buffers (Protobuf)

## Protocols

Open Systems Interconnection (OSI) model:

|      Layer     | Protocol data unit (PDU) |  Function  |
|----------------|--------------------------|------------|
| 7 Application  | Data                     | High-level protocols such as for resource sharing or remote file access, e.g. HTTP. |
| 6 Presentation | Data                     | Translation of data between a networking service and an application; including character encoding, data compression and encryption/decryption |
| 5 Session      | Data                     | Managing communication sessions, i.e., continuous exchange of information in the form of multiple back-and-forth transmissions between two nodes |
| 4 Transport    | Segment, Datagram        | Reliable transmission of data segments between points on a network, including segmentation, acknowledgement and multiplexing |
| 3 Network      | Packet                   | Structuring and managing a multi-node network, including addressing, routing and traffic control |
| 2 Data link    | Frame                    | Transmission of data frames between two nodes connected by a physical layer |
| 1 Physical     | Bit, Symbol              | Transmission and reception of raw bit streams over a physical medium |

- **Simple Object Access Protocol (SOAP)**
  Messaging protocol specification for exchanging structured information in the implementation of web services in computer networks. It uses XML Information Set for its message format, and can operate over any protocol such as HTTP, SMTP, TCP, UDP, JMS and message queues.
- **Advanced Message Queuing Protocol (AMQP)**
  AMQP is a binary, application layer protocol, designed to efficiently support a wide variety of messaging applications and 
  communication patterns. It provides flow controlled, message-oriented communication with message-delivery guarantees such as at- 
  most-once (where each message is delivered once or never), at-least-once (where each message is certain to be delivered, but may do so 
  multiple times) and exactly-once (where the message will always certainly arrive and do so only once),[4] and authentication and/or 
  encryption based on SASL and/or TLS. It assumes an underlying reliable transport layer protocol such as Transmission Control 
  Protocol (TCP).

  The AMQP specification is defined in several layers: (i) a type system, (ii) a symmetric, asynchronous protocol for the transfer of 
  messages from one process to another, (iii) a standard, extensible message format and (iv) a set of standardised but extensible 
  'messaging capabilities.'
- **Streaming Text Oriented Messaging Protocol (STOMP)**
  STOMP provides an interoperable wire format so that STOMP clients can communicate with any STOMP message broker to provide easy and 
  widespread messaging interoperability among many languages, platforms and brokers. It works over TCP.
- HTTP
- HTTPS
- TCP

## REST, RPC

Representational state transfer (REST) is a software architectural style that was created to guide the design and
development of the architecture for the World Wide Web. The term representational state transfer was introduced and
defined in 2000 by computer scientist Roy Fielding in his doctoral dissertation. It means that a server will respond
with the representation of a resource (today, it will most often be an HTML, XML or JSON document) and that resource
will contain hypermedia links that can be followed to make the state of the system change. Any such request will in turn
receive the representation of a resource, and so on.

* Client–server architecture The client-server design pattern enforces the principle of separation of concerns:
  separating the user interface concerns from the data storage concerns. Portability of the user interface is thus
  improved. In the case of the Web, a plethora of web browsers have been developed for most platforms without the need
  for knowledge of any server implementations. Separation also simplifies the server components, improving scalability,
  but more importantly it allows components to evolve independently (anarchic scalability), which is necessary in an
  Internet-scale environment that involves multiple organisational domains.
* Statelessness In computing, a stateless protocol is a communications protocol in which no session information is
  retained by the receiver, usually a server. Relevant session data is sent to the receiver by the client in such a way
  that every packet of information transferred can be understood in isolation, without context information from previous
  packets in the session. This property of stateless protocols makes them ideal in high volume applications, increasing
  performance by removing server load caused by retention of session information.
* Cacheability As on the World Wide Web, clients and intermediaries can cache responses. Responses must, implicitly or
  explicitly, define themselves as either cacheable or non-cacheable to prevent clients from providing stale or
  inappropriate data in response to further requests. Well-managed caching partially or completely eliminates some
  client–server interactions, further improving scalability and performance. The cache can be performed at the client
  machine in memory or browser cache storage. Additionally cache can be stored in a Content Delivery Network (CDN).
* Layered system A client cannot ordinarily tell whether it is connected directly to the end server or to an
  intermediary along the way. If a proxy or load balancer is placed between the client and server, it won't affect their
  communications, and there won't be a need to update the client or server code. Intermediary servers can improve system
  scalability by enabling load balancing and by providing shared caches. Also, security can be added as a layer on top
  of the web services, separating business logic from security logic. Adding security as a separate layer enforces
  security policies. Finally, intermediary servers can call multiple other servers to generate a response to the client.
* Code on demand (optional)
  Servers can temporarily extend or customize the functionality of a client by transferring executable code: for
  example, compiled components such as Java applets, or client-side scripts such as JavaScript.
* Uniform interface The uniform interface constraint is fundamental to the design of any RESTful system. It simplifies
  and decouples the architecture, which enables each part to evolve independently. The four constraints for this uniform
  interface are:
    * Resource identification in requests - Individual resources are identified in requests, for example using URIs in
      RESTful Web services. The resources themselves are conceptually separate from the representations that are
      returned to the client. For example, the server could send data from its database as HTML, XML or as JSON—none of
      which are the server's internal representation.
    * Resource manipulation through representations - When a client holds a representation of a resource, including any
      metadata attached, it has enough information to modify or delete the resource's state.
    * Self-descriptive messages - Each message includes enough information to describe how to process the message. For
      example, which parser to invoke can be specified by a media type.
    * Hypermedia as the engine of application state (HATEOAS) - Having accessed an initial URI for the REST
      application—analogous to a human Web user accessing the home page of a website—a REST client should then be able
      to use server-provided links dynamically to discover all the available resources it needs. As access proceeds, the
      server responds with text that includes hyperlinks to other resources that are currently available. There is no
      need for the client to be hard-coded with information regarding the structure of the server.

## Database

### SQL

### RDBMS

### NoSQL

### Database-migration tools

* Flyway
* Liquibase

## Math

## Java

### Data types 🐣

| Primitive type |  Size   |  Minimum  |     Maximum     |     Default     | Wrapper type |
|----------------|--------:|----------:|----------------:|----------------:|--------------|
| boolean        |  -      |     -     |        -        |           false | Boolean      |
| byte           | 8 bits  |      -128 |            +127 |         (byte)0 | Byte         |
| short          | 16 bits |     -2^15 |         +2^15-1 |        (short)0 | Short        |
| char           | 16 bits | Unicode 0 | Unicode 2^16- 1 | ‘\u0000’ (null) | Character    |
| int            | 32 bits |     -2^31 |         +2^31-1 |               0 | Integer      |
| long           | 64 bits |     -2^63 |         +2^63-1 |              0L | Long         |
| float          | 32 bits |   IEEE754 |         IEEE754 |            0.0f | Float        |
| double         | 64 bits |   IEEE754 |         IEEE754 |            0.0d | Double       |
| void           |    -    |     -     |        -        |        -        | Void         |

### Annotations

Meta Annotations:

* `@Retention` - Specifies how the marked annotation is stored, whether in code only, compiled into the class, or
  available at runtime through reflection.
* `@Documented` - Marks another annotation for inclusion in the documentation.
* `@Target` - Marks another annotation to restrict what kind of Java elements the annotation may be applied to.
* `@Inherited` - Marks another annotation to be inherited to subclasses of annotated class (by default annotations are
  not inherited by subclasses).
* `@Repeatable` - Specifies that the annotation can be applied more than once to the same declaration, since Java 8.

Built-in annotations:

* `@Override` - Checks that the method is an override. Causes a compilation error if the method is not found in one of
  the parent classes or implemented interfaces.
* `@Deprecated` - Marks the method as obsolete. Causes a compile warning if the method is used.
* `@SuppressWarnings` - Instructs the compiler to suppress the compile time warnings specified in the annotation
  parameters.
* `@SafeVarargs` - Suppress warnings for all callers of a method or constructor with a generics varargs parameter, since
  Java 7.
* `@FunctionalInterface` - Specifies that the type declaration is intended to be a functional interface, since Java 8.

### Collections

Table: Simple Container Taxonomy
![Table: Simple Container Taxonomy](./images/Simple_Container_Taxonomy.png)

HashMap

TreeMap

### Lambda and Streams

### Java memory model (JMM)

### Concurrency in java

Synchronization is required for reliable communication between threads as well as for mutual exclusion.

#### Package java.util.concurrent

### JMS

### JMX

### Exceptions

### Transactions

### Garbage collectors (GC)

*Garbage collectors* track each and every object available in the JVM heap space, and remove the unused ones.
Garbage collectors work on the concept of Garbage Collection Roots (GC Roots) to identify live and dead objects.

Examples of such Garbage Collection roots are:
- Classes loaded by system class loader (not custom class loaders).
- Live threads.
- Local variables and parameters of the currently executing methods.
- Local variables and parameters of JNI methods.
- Global JNI reference.
- Objects used as a monitor for synchronization.
- Objects held from garbage collection by JVM for its purposes.
- The garbage collector traverses the whole object graph in memory, starting from those Garbage Collection Roots and following references from the roots to other objects.

A standard Garbage Collection implementation involves three phases:

1. *Mark objects as alive.*
In this step, the GC identifies all the live objects in memory by traversing the object graph.
When GC visits an object, it marks it as accessible and thus alive. Every object the garbage collector visits is marked as alive. All the objects which are not reachable from GC Roots are garbage and considered as candidates for garbage collection.

2. *Sweep dead objects.*
After marking phase, we have the memory space which is occupied by live (visited) and dead (unvisited) objects. The sweep phase releases the memory fragments which contain these dead objects.

3. *Compact remaining objects in memory.*
The dead objects that were removed during the sweep phase may not necessarily be next to each other. Thus, you can end up having fragmented memory space.
Memory can be compacted after the garbage collector deletes the dead objects, so that the remaining objects are in a contiguous block at the start of the heap.
The compaction process makes it easier to allocate memory to new objects sequentially.

Generational garbage collection strategy.

As more and more objects are allocated, the list of objects grows, leading to longer garbage collection times. Empirical analysis of applications has shown that most objects in Java are short lived. 
Young Generation (Eden space, Survivor spaces) -> Old Generation (Tenured Generation)

Types of Garbage Collectors in the Java Virtual Machine:

* **Serial Garbage Collector**

  This is the simplest GC implementation, as it basically works with a single thread. As a result, this GC
  implementation freezes all application threads when it runs. Therefore, it's not a good idea to use it in
  multi-threaded applications, like server environments. However, there was an excellent talk given by Twitter engineers
  at QCon 2012 about the performance of Serial Garbage Collector, which is a good way to understand this collector
  better. The Serial GC is the garbage collector of choice for most applications that don't have small pause time
  requirements and run on client-style machines.

  `java -XX:+UseSerialGC`

* **Parallel Garbage Collector**

  It's the default GC of the JVM, and sometimes called Throughput Collector. Unlike Serial Garbage Collector, it uses
  multiple threads for managing heap space, but it also freezes other application threads while performing GC. If we use
  this GC, we can specify maximum garbage collection threads and pause time, throughput, and footprint (heap size). The
  numbers of garbage collector threads can be controlled with the command-line option -XX:ParallelGCThreads=<N>. The
  maximum pause time goal (gap [in milliseconds] between two GC) is specified with the command-line option -XX:
  MaxGCPauseMillis=<N>. The time spent doing garbage collection versus the time spent outside of garbage collection is
  called the maximum throughput target and can be specified by the command-line option -XX:GCTimeRatio=<N>. The maximum
  heap footprint (the amount of heap memory that a program requires while running) is specified using the option -Xmx<N>
  . Multiple threads are used for minor garbage collection in the Young Generation. A single thread is used for major
  garbage collection in the Old Generation.

  `java -XX:+UseParallelGC`

* **Concurrent mark sweep (CMS) Garbage Collector**

  The Concurrent Mark Sweep (CMS) implementation uses multiple garbage collector threads for garbage collection. It's
  designed for applications that prefer shorter garbage collection pauses, and can afford to share processor resources
  with the garbage collector while the application is running. Simply put, applications using this type of GC respond
  slower on average, but don't stop responding to perform garbage collection. A quick point to note here is that since
  this GC is concurrent, an invocation of explicit garbage collection, such as using System.gc() while the concurrent
  process is working, will result in Concurrent Mode Failure / Interruption. If more than 98% of the total time is spent
  in CMS garbage collection, and less than 2% of the heap is recovered, then an OutOfMemoryError is thrown by the CMS
  collector. If necessary, we can disable this feature by adding the option -XX:-UseGCOverheadLimit to the command line.
  This collector also has a mode known as an incremental mode, which is being deprecated in Java SE 8 and may be removed
  in a future major release. Support was removed in 14.0

* **Garbage First (G1) Garbage Collector**

  G1 is designed for applications running on multi-processor machines with large memory space. It's available from the
  JDK7 Update 4 and in later releases. G1 collector will replace the CMS collector, since it's more performance
  efficient. Unlike other collectors, the G1 collector partitions the heap into a set of equal-sized heap regions, each
  a contiguous range of virtual memory. When performing garbage collections, G1 shows a concurrent global marking
  phase (i.e. phase 1, known as Marking) to determine the liveness of objects throughout the heap. After the mark phase
  is complete, G1 knows which regions are mostly empty. It collects in these areas first, which usually yields a
  significant amount of free space (i.e. phase 2, known as Sweeping). That's why this method of garbage collection is
  called Garbage-First. Although G1 is also generational, it does not have separate regions for young and old
  generations. Instead, each generation is a set of regions, which allows resizing of the young generation in a flexible
  way. Since G1GC identifies the regions with the most garbage and performs garbage collection on that region first, it
  is called Garbage First.

  `java -XX:+UseG1GC`

* *C4 (Continuously Concurrent Compacting Collector)*

* *Shenandoah*

* **Z Garbage Collector**

  ZGC is a scalable low-latency garbage collector that debuted in Java 11 as an experimental option for Linux. JDK 14
  introduced ZGC under the Windows and macOS operating systems. ZGC has obtained the production status from Java 15
  onwards. ZGC performs all expensive work concurrently, without stopping the execution of application threads for more
  than 10 ms, which makes it suitable for applications that require low latency. It uses load barriers with colored
  pointers to perform concurrent operations when the threads are running, and they're used to keep track of heap usage.
  Reference coloring (colored pointers) is the core concept of ZGC. It means that ZGC uses some bits (metadata bits) of
  reference to mark the state of the object. It also handles heaps ranging from 8MB to 16TB in size. Furthermore, pause
  times don't increase with the heap, live-set, or root-set size. Similar to G1, Z Garbage Collector partitions the
  heap, except that heap regions can have different sizes.

  `java -XX:+UnlockExperimentalVMOptions -XX:+UseZGC`

* **EpsilonGC**

  Promises the lowest GC overhead possible. Epsilon handles memory allocation but does not implement any actual memory
  reclamation mechanism. Once the available Java heap is exhausted, the JVM will shut down.

  `java -XX:+UnlockExperimentalVMOptions -XX:+UseEpsilonGC`

### ORM: Hibernate, MyBatis and so on

### Spring

Spring is described as a lightweight framework for building Java applications.

Alternatives to Spring:

* JBoss Seam Framework
* Google Guice
* PicoContainer
* JEE 7 Container (JSR-342)
* Vert.x

#### Spring Boot

Spring Boot comes with out-of-the-box configurations for different types of Spring applications that are packed in
starter packages. It takes the guesswork out of manually gathering dependencies and provides some of the most common
features needed by most applications, such as metrics and health checks. Spring Boot also wraps up all dependencies a
Spring application needs, taking into account compatibility between versions.

#### Spring core (DI)

The core of the Spring Framework is based on the principle of inversion of control. IoC is a technique that externalizes
the creation and management of component dependencies. The injection of dependencies at runtime, led to IoC being
renamed by Martin Fowler as the much more descriptive dependency injection (DI).

Spring’s DI implementation is based on two core Java concepts: JavaBeans and interfaces. When you use Spring as the DI
provider, you gain the flexibility of defining dependency configuration within your applications in different ways (for
example, XML files, Java configuration classes, annotations within your code, or the new Groovy bean definition method).
JavaBeans (POJOs) provide a standard mechanism for creating Java resources that are configurable in a number of ways,
such as constructors and setter methods. In Chapter 3, you will see how Spring uses the JavaBean specification to form
the core of its DI configuration model; in fact, any Spring-managed resource is referred to as a bean. If you are
unfamiliar with JavaBeans, refer to the quick primer we present at the beginning of Chapter 3. Clearly designing and
coding an application to interfaces makes for a flexible application, but the complexity of wiring together an
application designed using interfaces is quite high and places an additional coding burden on developers. By using DI,
you reduce the amount of code you need to use an interface-based design in your application to almost zero. Likewise, by
using interfaces, you can get the most out of DI because your beans can utilize any interface implementation to satisfy
their dependency. The use of interfaces also allows Spring to utilize JDK dynamic proxies (the Proxy pattern) to provide
powerful concepts such as AOP for crosscutting concerns. In the context of DI, Spring acts more like a container than a
framework—providing instances of your application classes with all the dependencies they need—but it does so in a much
less intrusive way. Using Spring for DI relies on nothing more than following the JavaBeans naming conventions within
your classes— there are no special classes from which to inherit or proprietary naming schemes to follow. If anything,
the only change you make in an application that uses DI is to expose more properties on your JavaBeans, thus allowing
more dependencies to be injected at runtime.

Java Community Process (JCP) adopted JSR-330 (Dependency Injection for Java) in 2009. Benefits of using DI rather than a
more traditional approach:

* Reduced glue code: One of the biggest plus points of DI is its ability to dramatically reduce the amount of code you
  have to write to glue the components of your application together. Often this code is trivial, so creating a
  dependency involves simply creating a new instance of an object. However, the glue code can get quite complex when you
  need to look up dependencies in a JNDI repository or when the dependencies cannot be invoked directly, as is the case
  with remote resources. In these cases, DI can really simplify the glue code by providing automatic JNDI lookup and
  automatic proxying of remote resources.
* Simplified application configuration: By adopting DI, you can greatly simplify the process of configuring an
  application. You can use a variety of options to configure those classes that were injectable to other classes. You
  can use the same technique to express the dependency requirements to the “injector” for injecting the appropriate bean
  instance or property. In addition, DI makes it much simpler to swap one implementation of a dependency for another.
  Consider the case where you have a DAO component that performs data operations against a PostgreSQL database and you
  want to upgrade to Oracle. Using DI, you can simply reconfigure the appropriate dependency on your business objects to
  use the Oracle implementation rather than the PostgreSQL one.
* Ability to manage common dependencies in a single repository: Using a traditional approach to dependency management of
  common services—for example, data source connection, transaction, and remote services—you create instances (or lookup
  from some factory classes) of your dependencies where they are needed (within the dependent class). This will cause
  the dependencies to spread across the classes in your application, and changing them can prove problematic. When you
  use DI, all the information about those common dependencies is contained in a single repository, making the management
  of dependencies much simpler and less error prone.
* Improved testability: When you design your classes for DI, you make it possible to replace dependencies easily. This
  is especially handy when you are testing your application. Consider a business object that performs some complex
  processing; for part of this, it uses a DAO to access data stored in a relational database. For your test, you are not
  interested in testing the DAO; you simply want to test the business object with various sets of data. In a traditional
  approach, whereby the business object is responsible for obtaining an instance of the DAO itself, you have a hard time
  testing this, because you are unable to easily replace the DAO implementation with a mock implementation that returns
  your test data sets. Instead, you need to make sure your test database contains the correct data and uses the full DAO
  implementation for your tests. Using DI, you can create a mock implementation of the DAO object that returns the test
  data sets, and then you can pass this to your business object for testing. This mechanism can be extended for testing
  any tier of your application and is especially useful for testing web components where you can create mock
  implementations of HttpServletRequest and HttpServletResponse.
* Fostering of good application design:
  Designing for DI means, in general, designing against interfaces. A typical injection-oriented application is designed
  so that all major components are defined as interfaces, and then concrete implementations of these interfaces are
  created and hooked together using the DI container. This kind of design was possible in Java before the advent of DI
  and DI-based containers such as Spring, but by using Spring, you get a whole host of DI features for free, and you are
  able to concentrate on building your application logic, not a framework to support it.

Spring provides features for all layers of an application:

* Managing Transactions
* Aspect-Oriented Programming with Spring
* Spring Expression Language
* Validation in Spring
* Accessing Data in Spring
* Object/XML Mapping in Spring
* Simplifying and Integrating with JEE
* MVC in the Web Tier
* WebSocket Support
* Remoting Support
* Mail Support
* Job Scheduling Support
* Dynamic Scripting Support
* Simplified Exception Handling

#### Spring Transaction Management

As we mentioned earlier, the TransactionDefinition interface controls the properties of a transaction. Let’s take a more
detailed look at the TransactionDefinition interface, shown here, and describe its methods:

```java
package org.springframework.transaction;

import java.sql.Connection;

public interface TransactionDefinition {
    // Variable declaration statements omitted

    int getPropagationBehavior();

    int getIsolationLevel();

    int getTimeout();

    boolean isReadOnly();

    String getName();
}
```

We begin with getIsolationLevel(), which controls what changes to the data other transactions see. Table 9-1 lists the
transaction isolation levels you can use and explains what changes made in the current transaction other transactions
can access. The isolation levels are represented as static values defined in the TransactionDefinition interface.

Table 9-1. Transaction Isolation Levels

|      Isolation Level       | Description |
|----------------------------|-------------|
| ISOLATION_DEFAULT          | Default isolation level of the underlying data store. |
| ISOLATION_READ_UNCOMMITTED | Lowest level of isolation; it is barely a transaction at all because it allows this transaction to see data modified by other uncommitted transactions. |
| ISOLATION_READ_COMMITTED   | Default level in most databases; it ensures that other transactions are not able to read data that has not been committed by other transactions. However, the data that was read by one transaction can be updated by other transactions. |
| ISOLATION_REPEATABLE_READ  | Stricter than ISOLATION_READ_COMMITTED; it ensures that once you select data, you can select at least the same set again. However, if other transactions insert new data, you can still select the newly inserted data. |
| ISOLATION_SERIALIZABLE     | The most expensive and reliable isolation level; all transactions are treated as if they were executed one after another. |

The getPropagationBehavior() method specifies what happens to a transactional call, depending on whether there is an
active transaction. Table 9-2 describes the values for this method. The propagation types are represented as static
values defined in the TransactionDefinition interface.

Table 9-2. Transaction Isolation Levels

|     Propagation Type      | Description |
|---------------------------|-------------|
| PROPAGATION_REQUIRED      | Description Supports a transaction if one already exists. If there is no transaction, it starts a new one. Supports a |
| PROPAGATION_SUPPORTS      | transaction if one already exists. If there is no transaction, it executes nontransactionally. Supports a transaction if |
| PROPAGATION_MANDATORY     | one already exists. Throws an exception if there is no active transaction. Always starts a new transaction. If an active |
| PROPAGATION_REQUIRES_NEW  | transaction already exists, it is suspended. Does not support execution with an active transaction. Always executes |
| PROPAGATION_NOT_SUPPORTED | nontransactionally and suspends any existing transaction. Always executes nontransactionally even if an active |
| PROPAGATION_NEVER         | transaction exists. Throws an exception if an active transaction exists. Runs in a nested transaction if an active |
| PROPAGATION_NESTED        | transaction exists. If there is no active transaction, the execution is executed as if PROPAGATION_REQUIRED is set. |

When using annotation-based transaction management, the only annotation that we need to deal with is `@Transactional`.
In the previous code snippet, the `@Transactional` annotation is applied at the class level, which means that, by
default, Spring will ensure that a transaction is present before the execution of each method within the class. The
`@Transactional` annotation supports a number of attributes that you can provide to override the default behavior. Table
9-3 shows the available attributes, together with the possible and default values.

Table 9-3. Attributes for the @Transactional Annotation

|    Propagation Type    | Default Value | Possible Values  |
|------------------------|---------------|------------------|
| propagation            | Propagation.REQUIRED | Propagation.REQUIRED<br/>Propagation.SUPPORTS<br/>Propagation.MANDATORY<br/>Propagation.REQUIRES_NEW<br/>Propagation.NOT_SUPPORTED<br/>Propagation.NEVER<br/>Propagation.NESTED |
| isolation              | Isolation.DEFAULT (default isolation level of the underlying resource) | Isolation.DEFAULT<br/>Isolation.READ_UNCOMMITTED<br/>Isolation.READ_COMMITTED<br/>Isolation.REPEATABLE_READ<br/>Isolation.SERIALIZABLE |
| timeout                | TransactionDefinition.TIMEOUT_DEFAULT | An integer value larger than zero;<br/>indicates the number in seconds for timeout |
| readOnly               | (default transaction timeout in seconds of the underlying resource) | {true, false} |
| rollbackFor            | false | N/A |
| rollbackForClassName   | Exception classes for which the transaction will be rolled back | N/A |
| noRollbackFor          | Exception class names for which the transaction will be rolled back | N/A |
| noRollbackForClassName | Exception classes for which the transaction will not be rolled back | N/A |
| value                  | Exception class names for which the transaction will not be rolled back | N/A |

#### Spring AOP

Besides dependency injection (DI), another core feature that the Spring Framework offers is support for aspect-oriented
programming (AOP).

* *Types of AOP*:
  There are two distinct types of AOP: static and dynamic. In static AOP, like that provided by AspectJ’s1 compile-time
  weaving mechanisms, the crosscutting logic is applied to your code at compile time, and you cannot change it without
  modifying the code and recompiling. With dynamic AOP, such as Spring AOP, crosscutting logic is applied dynamically at
  runtime. This allows you to make changes to the AOP configuration without having to recompile the application. These
  types of AOP are complementary, and, when used together, they form a powerful combination that you can use in your
  applications.
* *Spring AOP architecture*: Spring AOP is only a subset of the full AOP feature set found in other implementations such
  as AspectJ. In this chapter, we take a high-level look at which features are present in Spring, how they are
  implemented, and why some features are excluded from the Spring implementation.
* *Proxies in Spring AOP*: Proxies are a huge part of how Spring AOP works, and you must understand them to get the most
  out of Spring AOP. In this chapter, we look at the two kinds of proxy: the JDK dynamic proxy and the CGLIB proxy. In
  particular, we look at the different scenarios in which Spring uses each proxy, the performance of the two proxy
  types, and some simple guidelines to follow in your application to get the most from Spring AOP.
* *Using Spring AOP*: In this chapter, we present some practical examples of AOP usage. We start off with a simple Hello
  World example to ease you into Spring’s AOP code, and we continue with a detailed description of the AOP features that
  are available in Spring, complete with examples.
* *Advanced use of pointcuts*: We explore the ComposablePointcut and ControlFlowPointcut classes, introductions, and
  appropriate techniques you should employ when using pointcuts in your application.
* *AOP framework services*: The Spring Framework fully supports configuring AOP transparently and declaratively. We look
  at three ways (the ProxyFactoryBean class, the aop namespace, and @AspectJ-style annotations) to inject declaratively
  defined AOP proxies into your application objects as collaborators, thus making your application completely unaware
  that it is working with advised objects.
* *Integrating AspectJ*: AspectJ is a fully featured AOP implementation. The main difference between AspectJ and Spring
  AOP is that AspectJ applies advice to target objects via weaving (either compile-time or load-time weaving), while
  Spring AOP is based on proxies. The feature set of AspectJ is much greater than that of Spring AOP, but it is much
  more complicated to use than Spring. AspectJ is a good solution when you find that Spring AOP lacks a feature you
  need.

##### Types of AOP

There are two distinct types of AOP: static and dynamic.

* Using Static AOP. In static AOP, the weaving process forms another step in the build process for an application. In
  Java terms, you achieve the weaving process in a static AOP implementation by modifying the actual bytecode of your
  application, changing and extending the application code as necessary. This is a well-performing way of achieving the
  weaving process because the end result is just Java bytecode, and you do not perform any special tricks at runtime to
  determine when advice should be executed. The drawback of this mechanism is that any modifications you make to the
  aspects, even if you simply want to add another joinpoint, require you to recompile the entire application. AspectJ’s
  compile-time weaving is an excellent example of a static AOP implementation.
* Using Dynamic AOP. Dynamic AOP implementations, such as Spring AOP, differ from static AOP implementations in that the
  weaving process is performed dynamically at runtime. How this is achieved is implementation-dependent, but as you will
  see, Spring’s approach is to create proxies for all advised objects, allowing for advice to be invoked as required.
  The drawback of dynamic AOP is that, typically, it does not perform as well as static AOP, but the performance is
  steadily increasing. The major benefit of dynamic AOP implementations is the ease with which you can modify the entire
  aspect set of an application without needing to recompile the main application code.
* Choosing an AOP Type. Choosing whether to use static or dynamic AOP is quite a hard decision. Both have their own
  benefits, and you are not restricted to using only one type. In general, static AOP implementations have been around
  longer and tend to have more feature-rich implementations, with a greater number of available joinpoints. Typically,
  if performance is absolutely critical or you need an AOP feature that is not implemented in Spring, you will want to
  use AspectJ. In most other cases, Spring AOP is ideal. Keep in mind that many AOP-based solutions such as transaction
  management are already provided for you by Spring, so check the framework capabilities before rolling your own! As
  always, let the requirements of your application drive your choice of AOP implementation, and don’t restrict yourself
  to a single implementation if a combination of technologies would better suit your application. In general, Spring AOP
  is less complex than AspectJ, so it tends to be an ideal first choice.

Table 1. Advice Types in Spring.

|    Advice Name   | Interface and description |
|------------------|---------------------------|
| Before           | `org.springframework.aop.MethodBeforeAdvice` Using before advice, you can perform custom processing before a joinpoint executes. Because a joinpoint in Spring is always a method invocation, this essentially allows you to perform preprocessing before the method executes. Before advice has full access to the target of the method invocation as well as the arguments passed to the method, but it has no control over the execution of the method itself. If the before advice throws an exception, further execution of the interceptor chain (as well as the target method) will be aborted, and the exception will propagate back up the interceptor chain.|
| After-Returning  | `org.springframework.aop.AfterReturningAdvice` After-returning advice is executed after the method invocation at the joinpoint has finished executing and has returned a value. The after- returning advice has access to the target of the method invocation, the arguments passed to the method, and the return value. Because the method has already executed when the after-returning advice is invoked, it has no control over the method invocation at all. If the target method throws an exception, the after- returning advice will not be run, and the exception will be propagated up to the call stack as usual. |
| After(finally)   | `org.springframework.aop.AfterAdvice` After-returning advice is executed only when the advised method completes normally. However, the after (finally) advice will be executed no matter the result of the advised method. The advice is executed even when the advised method fails and an exception is thrown. |
| Around           | `org.aopalliance.intercept.MethodInterceptor` In Spring, around advice is modeled using the AOP Alliance standard of a method interceptor. Your advice is allowed to execute before and after the method invocation, and you can control the point at which the method invocation is allowed to proceed. You can choose to bypass the method altogether if you want, providing your own implementation of the logic. |
| Throws           | `org.springframework.aop.ThrowsAdvice` Throws advice is executed after a method invocation returns, but only if that invocation threw an exception. It is possible for throws advice to catch only specific exceptions, and if you choose to do so, you can access the method that threw the exception, the arguments passed into the invocation, and the target of the invocation. |
| Introduction     | `org.springframework.aop.IntroductionInterceptor` Spring models introductions as special types of interceptors. Using an introduction interceptor, you can specify the implementation for methods that are being introduced by the advice. |

#### Spring JDBC

#### Spring WebFlux

### Vert.x

### Maven and Gradle

### Bootstrap ClassLoader ⭐

## GIT

## Kubernetes

## Message brokers

* Kafka
* RabbitMQ

## Practice

* https://leetcode.com
* https://www.hackerrank.com

## Architecture

## FAQ

## References

1. Pro Spring 5. An In-Depth Guide to the Spring Framework and Its Tools. Fifth Edition.
   *Iuliana Cosmina, Rob Harrop, Chris Schaefer, Clarence Ho.*
2. Effective Java. Third Edition. *Joshua Bloch.*
3. Thinking in Java, Fourth Edition. *Bruce Eckel.*
4. oracle.com
