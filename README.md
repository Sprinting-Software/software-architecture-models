# The C5 Model for software architecture diagramming

An open-sourced lean model for software architecture diagrams. 

## About this document

This open-source project sets out to create a standard model for software architecture diagrams. 
Creating agreement and consensus in the industry about diagramming standards for software architecture is challenging for many reasons. Using the approach, techniques and platforms from the open-source community seems obvious. 

This intiative is called the C0 Model for Software Architecture Diagrams inspired by the C4-model: https://c4model.com/

The C designates Concepts and 0 designates notation

## What makes up a model for software architecture diagramming 

Let us define a model for software architecture diagramming, in short 'a model', to be a coherent set of concepts and notation in the following sense: 

- concepts: a set of unambiguously defined concepts within software architecture 
- notation: a standardized notation for how to depict these concepts in diagrams

One challenge of software architecture in general is the difficulty of defining the core concepts concisely and a **model** should go head-first on this challenge. 

Hence, the **concepts** should be be defined as consicely as possible, yet the definitions should be unambigious and clear by anyone reading them. If they fail being so, the model is not useful. 

In addition, the definitions of concepts should explain the relationship between the concepts so they make up a semantic network (also called a knowledge graph). 

Once the concepts are established in this way, we have a solid ground for the **notation**, which must explain how each concept and each relationship between them can be depicted. If the various concepts can be depicted in several different ways, these variations should be explained as well. 

A model should be selective in what concepts are included in the model because the purpose is to create an inner core of concepts that are truly unambigous and fully understood by everyone using the model. Naturally, around every model being adopted there will be an informal language used on an every day basis. Allowing such informal language to develop freely is an important objective of a model. You may say that the model should strive to formalize just enough to provide a solid ground of core concepts to allow an informal conversation to grow out of it. 

# The C4 model

This page is in full attributed to the original author of the C4-model, Simon Brown. It is a brief recap of the C4-model in a format that complies with the approach in this material. All formulations are copies and remixes of the original text from [the C4 Model](https://c4model.com).

## Core concepts

A software system is made up of one or more containers (applications and data stores), each of which contains one or more components, which in turn are implemented by one or more code elements (classes, interfaces, objects, functions, etc). And people may use the software systems that we build.

More formally, we can define it as this: 

- ** Software System **: A **Software System** is the highest level of abstraction and describes something that delivers value to its users, whether they are human or not. This includes the software system you are modelling, and the other software systems upon which your software system depends (or vice versa). In many cases, a software system is "owned by" a single software development team.
- ** Container**: a **Container** represents an application or a data store. A container is something that needs to be running in order for the overall software system to work. 
- ** Component**: A **component** is a grouping of related functionality encapsulated behind a well-defined interface. All components inside a container typically execute in the same process space. Hence, components are NOT separately deployable units.
- ** Person**: A **Person** represents one of the human users of your software system (e.g. actors, roles, personas, etc).

## Relationships between the concepts

By putting together the definitions from the previous section we can rephrase it with an emphasis on the relationships between the concepts. 

- A Software System is **composed** of Containers
- A Container is **composed** of Components. 
- A Component is **composed** of Code Elements
- A Person **uses** your system. 

The following diagram depicts the relationships between the core concepts using one-to-many relationships "--<" and many-to-many relationships ">--<".

```
                            usage
        Software System  >---------<  Person
             |
composition  | 
            / \    
          Container
             |     
composition  |     
            / \                      
          Component 
             |     
composition  |     
            / \    
        Code Element
```


It is worth noticing the following: 

- The concepts of Software System, Container, Component and Code Element makes up a set of *hierarchical abstractions*. Alternatively you can say that Software System, Container, Component and Code Element makes up a tree-structure.

## Notation

The C4-model is notation-agnostic in theory. It is clearly stated on [the C4 Model](https://c4model.com) that the focus of the model is on the concepts and that notation can be selected freely. 

In reality, the notation of C4 in many organizations follows the conventions established on [the C4 Model](https://c4model.com) which can be summarized as follows: 

// Put in the legend diagram

An alternative way to illustrate the notation is the following diagram:


## Elaboration of core concepts

In real terms, a Container is something like:
- Server-side web application: A Java EE web application running on Apache Tomcat, an ASP.NET MVC application running on Microsoft IIS, a Ruby on Rails application running on WEBrick, a Node.js application, etc.
- Client-side web application: A JavaScript application running in a web browser using Angular, Backbone.JS, jQuery, etc.
- Client-side desktop application: A Windows desktop application written using WPF, an OS X desktop application written using Objective-C, a cross-platform desktop application written using JavaFX, etc.
- Mobile app: An Apple iOS app, an Android app, a Microsoft Windows Phone app, etc.
- Server-side console application: A standalone (e.g. "public static void main") application, a batch process, etc.
- Serverless function: A single serverless function (e.g. Amazon Lambda, Azure Function, etc).
- Database: A schema or database in a relational database management system, document store, graph database, etc such as MySQL, Microsoft SQL Server, - - Oracle Database, MongoDB, Riak, Cassandra, Neo4j, etc.
- Blob or content store: A blob store (e.g. Amazon S3, Microsoft Azure Blob Storage, etc) or content delivery network (e.g. Akamai, Amazon CloudFront, etc).
- File system: A full local file system or a portion of a larger networked file system (e.g. SAN, NAS, etc).
- Shell script: A single shell script written in Bash, etc.
etc

A Container is essentially a context or boundary inside which some code is executed or some data is stored. And each container is a separately deployable/runnable thing or runtime environment, typically (but not always) running in its own process space. Because of this, communication between containers typically takes the form of an inter-process communication.

If you're using a language like Java or C#, the simplest way to think of a Component is that it's a collection of implementation classes behind an interface. Aspects such as how those components are packaged (e.g. one component vs many components per JAR file, DLL, shared library, etc) is a separate and orthogonal concern.

# The C5 model

## Core Concepts

In this section, we will Capitalize the Concepts to be defined, we will use **bold** to designate the point of definition and we will use *italic* when we assume some a priori knowledge of the reader. If the a priori knowledge is not well understood, we refer to the FAQ section.

- **Component**: A **Component** is a *deployable unit of software*. 

- **System**: A **System** is a set of Components that together constitutes a *coherent whole*. 

- **Elements**: An **Element** is an *inner part* of a Component or of another Element. 

- **Deployment Node**: A **Deployment Node** is a *runtime container* for the Component or for another Deployment Node. When all Components within a System are deployed in Deployment Nodes, the use cases of the System can be realized. 

## Relationships between the concepts

By putting together the definitions from the previous section we can rephrase it with an emphasis on the relationships between the concepts. 

- A System is **composed** of Components
- A Component is **composed** of Elements. 
- A Component is **deployed** on a Deployment Node

The following diagram depicts the relationships between the core concepts using one-to-many relationships "--<" and many-to-many relationships ">--<".

```
          System
             |
composition  | 
            / \       deployment
          Component  >---------<  Deployment Node --|
             |                              \ /     | composition
composition  |                               |______| 
            / \                      
          Element --|
            \ /     | composition
             |______|

```

It is worth noticing the following: 

- The concepts of System, Component and Element makes up a set of *hierarchical abstractions*. Alternatively you can say that System, Component and Elements makes up a tree-structure.
- The structure of System, Component and Element should follow the MECE principle, meaning that Components should be Mutually Exclusive and Collectively Exhaustive of a System. The same apply for Elements within a Component and for Elements within an Element. We can borrow the mathematical notion of "partition" and say that System-Component-Element makes up a partitioning structure.

## Notation

![](images/legend.png)

# Appendix


## Frequently Asked Questions

Q: Why have we selected only four Core Concepts and how can we expect it to provide a vocabolary rich enough to reason about software architecture?

A: A key idea of the C5 model is that we need a solid foundation for the rest to build on. Hence, there are plenty of other necessary notions such as solution, application, product and service, all of which brings important nuances to a discussion. However, the more concepts we include in the model, the less are the chances that it will resonate fully. If even a single concept is not resonating well with people inside an organization, the model will loose its validity. 

Q: Why is Code Elements not included as a Core Concept?

A: The notion of Code Elements (Classes, types etc.) are of course very important. However, Code Elements are in fact  to be of a different kind than the notions of components, systems and deployment nodes and for this reason it is not part of the core concepts of the C5 model. 

Q: Why is the model not providing a standard for diagrams types such as Context Diagram, Integration Diagram etc?

A: Creating a standard for architecture diagrams may be important on its own right. Such a standard should establish a set of standard diagrams each having a specific standard name, a designation of what concepts and relationships are in focus. Although such a standard for diagrams is very valuable, it is a natural extension building on top of the foundation laid by the core concepts and notation provided by the model. 

Q: Why do we need the System concept? Why do we need a higher-level structure on top of components? The notion of Components is useful, tangible and easily understandable, the notion of System is not. 

A: It is true that the notion of System is harder to comprehend than the notion of component. Furthermore, it is not always clear whether we need it at all. In particular, on a simple software platform with few components, it may suffice to deal with components without ever considering any higher level structure. As things grow and you need a larger organization around a software platform, the need to collect Components in natural groups will emerge. 


## Elaboration of the core concepts

### More about the System concept

The idea of a Software System can be hard to comprehend because it is rather abstract and to some may seem arbitrary. 
Some would say that we don't need any other concept that 

### More about the Component concept

The Component concept is one of the most difficult concepts to establish because it is 

The relationship between the constituted by one or more distinct and non-overlapping **components** which are tangible parts of the code-base with clear boundaries. A **system** is the highest level of abstraction and describes something that delivers value to its users, whether they are human or not. Systems provides a strong organising factor in enterprises. Often teams, departments or business units are organized around the system landscape as well as access control and service-ownership. 

Each components can be separately deployed into a running state and when all components are deployed they will interact in ways that realize the use-cases of the system.

The set of all Sub-Components within a Component should constitute a partition of the Component. 

