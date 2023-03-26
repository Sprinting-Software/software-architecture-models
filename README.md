# The C5 Model for software architecture diagramming

An open-sourced lean model for software architecture diagrams. 

## About this document

This open-source project sets out to create a standard model for software architecture diagrams. Creating agreement and consensus in the industry about diagramming standards for software architecture is challenging for many reasons. Using the approach, techniques and platforms from the open-source community seems obvious. 

This intiative is called the C5 Model for Software Architecture Diagrams inspired by the C4-model: https://c4model.com/
## What makes up a model for software architecture diagramming 

Let us define a model for software architecture diagramming, in short 'a model', to be a coherent set of concepts and notation in the following sense: 

- concepts: a set of unambiguously defined concepts within software architecture 
- notation: a standardized notation for how to depict these concepts in diagrams

One challenge of software architecture in general is the difficulty of defining the core concepts concisely and a **model** should go head-first on this challenge. 

Hence, the **concepts** should be be defined as consicely as possible, yet the definitions should be unambigious and clear by anyone reading them. 
In addition, the definitions of concepts should explain the relationship between the concepts so they make up a semantic network (also called a knowledge graph). 

Once the concepts are established in this way, we have solid ground under the **notation**, which must explain how each concept and each relationship between them can be depicted. If the various concepts can be depicted in several different ways, these variations should be explained as well. 

## Core Concepts

In this section, we will Capitalize the Concepts to be defined, we will use **bold** to define a term and we will use *italic* when we assume some a priori knowledge of the reader. 

- **Component**: A **Component** is a *deployable unit of software*. 

- **System**: A **System** is a set of Components that together constitutes a *coherent whole*. 

- **Sub-component**: A **Sub-Component** is an *inner part* of a Component or of another Sub-Components. 

- **Deployment Node**: A Component can be *built and deployed* into a **Deployment Node**, which brings the component from *code* into a *running state*. Said differently, the Deployment Node acts as the *runtime container* for the Component. When all Components within a System are deployed, the use cases of the System can be realized. 

## Relationships between the concepts

The following shows the relationships between the concepts.

```
     System
        |
        |
       / \
     Component  >--<  Deployment-node
        |
        |
       / \
     Sub-component >-|
             \ /     |
              |______|

```

## Notation

![](images/legend.png)

## Appendix

### Elaboration of the core concepts

TBD

The relationship between the is constituted by one or more distinct and non-overlapping **components** which are tangible parts of the code-base with clear boundaries. A **system** is the highest level of abstraction and describes something that delivers value to its users, whether they are human or not. Systems provides a strong organising factor in enterprises. Often teams, departments or business units are organized around the system landscape as well as access control and service-ownership. 

Each components can be separately deployed into a running state and when all components are deployed they will interact in ways that realize the use-cases of the system.

The set of all Sub-Components within a Component should constitute a partition of the Component. 

