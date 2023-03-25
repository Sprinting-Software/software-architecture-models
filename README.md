# The C5 Model for software architecture diagramming

An open-sourced lean model for software architecture diagrams. 

## About this document

This open-source project sets out to create a standard model for software architecture diagrams. Creating agreement and consensus in the industry about diagramming standards for software architecture is challenging for many reasons. Using the approach, techniques and platforms from the open-source community seems obvious. 

This intiative is called the C5 Model for Software Architecture Diagrams inspired by the C4-model: https://c4model.com/
## what makes up a model for software architecture diagramming 

a model for software architecture diagramming constitutes of the following parts:

- concepts: a set of accurately defined concepts and the relationships between them
- notation: standardized notation for how to depict these concepts, their attributes and relationships 

## Core concepts

- **System**: A **system** is the highest level of abstraction and describes something that delivers value to its users, whether they are human or not. Systems provides a strong organising factor in enterprises. Often teams, departments or business units are organized around the system landscape as well as access control and service-ownership. 

- **Top-component or Component**: A system is constituted by one or more distinct and non-overlapping **components** which are tangible parts of the code-base with clear boundaries. Each components can be separately deployed into a running state and when all components are deployed they will interact in ways that realize the use-cases of the system.

- **Sub-component or Component**: A component is constituted by code which may have a logical structure which can be perceived as inner elements referred to as **sub-components**.

- **Deployment node**: A component can be deployed in a deployment node, which brings to live the component from code to a running thing.

## Relationships between core concepts

The following shows the relationships between the core concepts.

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

## Proposed legend

![](images/legend.png)
