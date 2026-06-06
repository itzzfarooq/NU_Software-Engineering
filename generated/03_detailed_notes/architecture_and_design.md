# Architecture and Design - Detailed Notes

## What is Design? The Software Design Manifesto

Design is where you stand with a foot in two worlds — the world of technology and the world of people and human purposes — and you try to bring the two together. It is the place where creativity rules, where stakeholder requirements, business needs, and technical considerations all come together in the formulation of a product or system.

Design is the "HOW":
- How will the system be constructed?
- How will the solution work?
- How will the modules interact with one another?

---

## Characteristics of Good Design

Three fundamental characteristics define good design:

| Characteristic | Description |
|----------------|-------------|
| **Firmness** | A program should not have any bugs that inhibit its function |
| **Commodity** | A program should be suitable for the purposes for which it was intended |
| **Delight** | The experience of using the program should be a pleasurable one |

To accomplish these characteristics, you must practice **diversification** and then **convergence**.

### Diversification & Convergence

- **Diversification** is the acquisition of alternatives — the raw material of design: components, component solutions, and knowledge
- Once this diverse set of information is assembled, you **choose elements** that meet the requirements defined by requirements engineering and the analysis model
- As this occurs, alternatives are considered and rejected and you **converge** on "one particular configuration of components, and thus the creation of the final product"

---

## Why Design Matters

Design allows you to model the system or product that is to be built. This model can be assessed for quality and improved before code is generated, tests are conducted, and end users become involved in large numbers. **Design is the place where software quality is established.**

---

## Design Process

Software designing is an **art**. It is a **creative process**. Software design is an **iterative process** through which requirements are translated into a blueprint for constructing the software.

Key characteristics:
- Design begins at a **high level of abstraction** that can be directly traced back to the data, functional, and behavioral requirements
- As design iteration occurs, subsequent refinement leads to design representations at much **lower levels of abstraction**
- It is the most difficult and challenging task
- Throughout the design process, the quality of the evolving design is assessed with a series of **technical reviews**

---

## Stages of Design

The design process follows three stages with feedback loops:

```
┌─────────────────────────┐
│ STAGE 1:                │
│ UNDERSTAND THE PROBLEM  │
│ "Looking with different │
│ angles to discover the  │
│ design requirements"    │
└───────────┬─────────────┘
            │
            ▼
┌─────────────────────────┐
│ STAGE 2:                │
│ IDENTIFY ONE OR MORE    │
│ SOLUTIONS               │
│ "Choosing the most      │
│ appropriate solution"   │
└───────────┬─────────────┘
            │
            ▼
┌─────────────────────────┐
│ STAGE 3:                │
│ SOLUTION ABSTRACTION    │
│ "Use graphical, formal  │
│ or other descriptive    │
│ notations to describe   │
│ the components"         │
└─────────────────────────┘
```

---

## Design Engineering Process

Steps followed in design engineering:
1. Software specifications are transformed into **design models**
2. Models describe the details of **data structures, system architecture, interface, and components**
3. Design product is then **reviewed for quality** before moving to the next phase
4. A design model and specification document is produced — containing models, architecture, interfaces, and components

---

## Design Model Pyramid

Design model elements are not always developed in a sequential fashion. Preliminary architectural design sets the stage, followed by interface design and component-level design which often occur in parallel.

```
        /\
       /  \        Component-level Design
      /    \
     /------\      Interface Design
    /        \
   /----------\    Architectural Design
                Data/Class Design

   + Deployment-level Design (follows all others)
```

### Design Elements

| Element | Description |
|---------|-------------|
| **Data/Class Design** | Creates a model of data and objects represented at a high level of abstraction |
| **Architectural Design** | Depicts the overall layout of the software |
| **Interface Design** | Tells how information flows into and out of the system and how it is communicated among components. Includes user interface, external interfaces, and internal interfaces |
| **Component-level Design** | Describes the internal detail of each software component by way of data structure definitions, algorithms, and interface specifications |
| **Deployment-level Design** | Indicates how software functionality and subsystems will be allocated within the physical computing environment |

---

## Good Design vs Bad Design

| Bad Design | Good Design |
|------------|-------------|
| A design that is vague about underlying requirements | Good design is the one in which all the customer's requirements are incorporated |
| When you make a change in one piece of code and it breaks some other part which you never expected | Good designs are ones that are easily readable, easily maintainable, easily understood (good interface) |
| Bad user interface would add pain and complexity for user; implicit requirements are unmentioned (e.g., ease of use, maintainability) | A good software has the right amount of separation of concerns and modularity (the code encapsulated in the right logical tiers/modules/layers) making it maintainable |

> "A product's quality is a function of how much it changes the world for the better." — User satisfaction is more important than anything in determining software quality.

> "Writing a clever piece of code that works is one thing; designing something that can support a long-lasting business is quite another."

---

## The 10 Design Concepts

1. Abstraction
2. Architecture
3. Design Patterns
4. Modularity
5. Information Hiding
6. Functional Independence
7. Refinement
8. Refactoring
9. OO Design Concepts
10. Design Classes

---

### 1. Abstraction

IEEE defines abstraction as: **"A view of a problem that extracts the essential information relevant to a particular purpose and ignores the remainder of the information."**

An abstraction of a component describes the **external behavior** of that component without bothering with the internal details that produce the behavior. It is essential for partitioning.

---

### 2. Architecture

The overall structure of the software and the ways in which the structure provides conceptual integrity for a system. A set of properties should be specified as part of an architectural design:

| Property | Description |
|----------|-------------|
| **Structural properties** | Defines the components of a system (e.g., modules, objects) and the manner in which those components are packaged and interact with one another |
| **Extra-functional properties** | Addresses how the design architecture achieves requirements for performance, reliability, security, adaptability, and other system characteristics |
| **Families of related systems** | The design should have the ability to reuse architectural building blocks |

---

### 3. Philippe Kruchten's 4+1 View Model

Multiple views of stakeholders help reduce complexity through **separation of concern**.

```
    ┌──────────────┐
    │   Logical    │
    │    View      │──── Functionality provided to end users
    └──────┬───────┘
           │
    ┌──────┴───────┐
    │  Scenarios   │
    │   (+1 View)  │──── Sequence of interaction (use cases)
    └──────┬───────┘
           │
    ┌──────┴───────┐
    │   Process    │
    │    View      │──── System process/behavior — how they communicate
    └──────────────┘

    ┌──────────────┐     ┌──────────────┐
    │ Development  │     │   Physical   │
    │    View      │     │    View      │
    └──────────────┘     └──────────────┘
    Implementation       From system
    view from            engineer's
    developer's eye      point
```

| View | Audience | Description |
|------|----------|-------------|
| **Logical View** | End users | Functionality provided to end users |
| **Development View** | Developers | Implementation view from developer's eye |
| **Process View** | System integrators | System process/behavior — how they communicate |
| **Physical View** | System engineers | From system engineer's point |
| **Scenarios (+1)** | All | Sequence of interaction — connects all four views |

---

### 4. Design Patterns

A design structure that solves a particular design problem within a specific context. A common solution to a common problem in a given context — a template acts as a pattern for designing.

It provides a description that enables a designer to determine:
- Whether the pattern is **applicable**
- Whether the pattern can be **reused**
- Whether the pattern can serve as a **guide** for developing similar patterns

#### Pattern-Based Software Design

| Pattern Level | Purpose |
|---------------|---------|
| **Architectural patterns** | Define the overall structure of software; indicate relationships among subsystems and components; define rules for specifying relationships |
| **Design patterns** | Address a specific element of the design (aggregation, relationships, inter-component communication). Include creational, structural, and behavioral patterns |
| **Coding patterns** | Describe language-specific patterns that implement algorithmic or data structure elements, interface protocols, or communication mechanisms |

---

### 5. Modularity

Separately named and addressable components (i.e., modules) that are integrated to satisfy requirements (**divide and conquer principle**).

Benefits:
- Makes software **intellectually manageable** (grasp control paths, span of reference, number of variables, overall complexity)
- Helps to **plan development** more effectively
- **Accommodate changes** easily
- Conduct **testing and debugging** effectively and efficiently
- Conduct **maintenance** more easily

---

### 6. Information Hiding

The designing of modules so that the **algorithms and local data** contained within them are **inaccessible to other modules**. This enforces access constraints to both procedural (implementation) detail and local data structures.

```
┌─────────────────────────────────┐
│           MODULE                │
│  ┌───────────────────────────┐  │
│  │ Algorithms                │  │
│  │ Data Structure            │  │ ◄── Hidden from clients
│  │ Details of External       │  │
│  │   Interface               │  │
│  │ Resource Allocation       │  │
│  │   Policy                  │  │
│  └───────────────────────────┘  │
│         SECRET: A specific      │
│         design decision         │
├─────────────────────────────────┤
│     Controlled Interface        │ ◄── Visible to clients
└─────────────────────────────────┘
```

---

### 7. Functional Independence

Modules that have a **"single-minded" function** and an aversion to excessive interaction with other modules. Measured by **coupling** and **cohesion**.

- **High cohesion** — a module performs only a single task
- **Low coupling** — a module has the lowest amount of connection needed with other modules

---

### 8. Coupling (Worst to Best)

Coupling is a measure of **interconnection among modules**. It depends on:
- The interface complexity between modules
- The reference to shared data
- The manner in which modules are called (e.g., parameters passed)

| Type | Description | Quality |
|------|-------------|---------|
| **Content coupling** | One module modifies or relies on the internal workings of another module | Worst |
| **Common coupling** | Multiple modules have access to the same shared data | Bad |
| **Control coupling** | One module passes an execution control (e.g., a flag) to another module | Moderate |
| **Stamp coupling** | Modules communicate via composite data items | Good |
| **Data coupling** | Modules communicate via simple data items (parameters) | Better |
| **No coupling** | Modules are completely independent | Best |

---

### 9. Cohesion (Best to Worst)

Cohesion is a measure of the **relative functional strength** of a module.

| Type | Description | Quality |
|------|-------------|---------|
| **Functional cohesion** | All elements contribute to a single, well-defined task | Best |
| **Sequential cohesion** | Output of one component serves as input to another | Good |
| **Communicational cohesion** | Elements are grouped because they operate on the same data | Good |
| **Procedural cohesion** | Elements are grouped because they always follow a specific sequence of execution | Moderate |
| **Temporal cohesion** | Elements are grouped because they are processed at the same time | Bad |
| **Logical cohesion** | Elements are logically related but their functions are unrelated | Worse |
| **Coincidental cohesion** | Elements are unrelated and grouped by chance | Worst |

---

### 10. Refinement vs Refactoring

| Concept | Description |
|---------|-------------|
| **Refinement** | Elaboration of details; a process of elaboration; helps the designer to postpone decisions about details until later in the design process |
| **Refactoring** | A re-structuring of the design; a technique for reorganizing the class hierarchy to separate concerns and remove duplication of effort |

---

## OO Design Concepts

| Concept | Description |
|---------|-------------|
| **Module** | A component of a system, a logically separable part of the code |
| **Abstraction** | Description that identifies the essential characteristics of an object that distinguish it from all other kinds of objects, providing clear conceptual boundaries |
| **Encapsulation** | Packaging the complete contents of a class into a module. Hides the internal data and methods that implement the object's operations and exposes only those features essential for users to know |
| **Inheritance** | A mechanism by which a special kind of sub-class acquires the properties and behaviors of a generic class |
| **Association** | A relationship between classes that specifies how objects of one class can be linked to objects of another class |

---

## Design Classes

Four types of design classes:

| Class Type | Description |
|------------|-------------|
| **Boundary classes** | Provide the interface between the system and its actors (users or external systems) |
| **Entity classes** | Manage data that is long-lived and often persistent |
| **Control classes** | Mediate between boundary and entity classes |
| **Interface classes** | Provide user interface and external system interfaces (variation of boundary classes) |

---

## Key Connections

- **Abstraction** leads to **Information Hiding** — by abstracting away details, we hide implementation secrets
- **Modularity** + **Information Hiding** = **Functional Independence**
- **Coupling** and **Cohesion** measure the quality of **Functional Independence**
- **Design Patterns** provide reusable solutions at architectural, design, and coding levels
- **Refinement** is progressive elaboration; **Refactoring** is restructuring existing design
- The **4+1 View Model** provides multiple perspectives for complex system architecture
- **OO Design Concepts** (abstraction, encapsulation, inheritance, association) build upon modularity and information hiding
