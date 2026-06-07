# Architecture & Design — Detailed Study Notes

---

## Topic Overview

Software architecture and design form the bridge between requirements (WHAT the system should do) and implementation (HOW the system is built). This topic covers the principles, patterns, and processes that guide engineers in creating high-quality software systems. It spans design concepts (abstraction, modularity, coupling, cohesion), architectural patterns (pipe-and-filter, layers, MVC, client-server, blackboard, broker, repository, virtual machine), architectural views (4+1 model, ISO/IEC/IEEE 42010), and application architectures (three-tier, SOA, microservices).

---

## Why This Topic Exists

Requirements tell us _what_ to build, but they do not tell us _how_ to build it. Design is the creative, iterative process that translates requirements into a blueprint for construction. Without disciplined design:

- Systems become brittle — a change in one place breaks something far away.
- Code becomes unmanageable — no clear structure, no separation of concerns.
- Quality attributes (performance, security, maintainability) are left to chance.
- Teams cannot work in parallel because there is no clear modular decomposition.

Good design is where software quality is _established_. It is the single most important factor determining whether a system can evolve over time.

---

## Core Concepts & Definitions

| Concept | Definition |
|---|---|
| **Design** | The process of defining the architecture, components, interfaces, and other characteristics of a system. |
| **Architecture** | The set of structures needed to reason about a system; the system's blueprint. Encompasses elements, interfaces, collaboration, composition, and decomposition into components. |
| **Abstraction** | A view of a problem that extracts essential information relevant to a purpose and ignores the remainder. Describes external behavior without internal details. |
| **Modularity** | Separately named and addressable components (modules) that are integrated to satisfy requirements. Follows the divide-and-conquer principle. |
| **Information Hiding** | Designing modules so that algorithms and local data contained within them are inaccessible to other modules. Enforces access constraints. |
| **Functional Independence** | Modules that have a single-minded function and minimal interaction with other modules. Measured by coupling and cohesion. |
| **Coupling** | A measure of the interdependencies among modules. Low coupling is preferred. Arises from content, common, control, stamp, and data coupling. |
| **Cohesion** | A measure of the degree to which elements within a module work together as a functional unit. High cohesion is preferred. |
| **Refinement** | Elaboration of data, functional, and behavioral representations from high-level abstraction down to implementation detail. |
| **Refactoring** | Reorganizing source code to improve its internal structure without changing external behavior. Primary objective is reducing complexity. |

---

## Quality Attributes Influenced by Architecture

| Attribute | Meaning |
|---|---|
| **Performance** | System's responsiveness to events within a given time constraint. |
| **Scalability** | Ability to handle a growing amount of work. |
| **Extensibility** | Ability to add new features or modify existing ones with minimal impact. |
| **Modifiability** | Ability to make changes with minimal impact on other components. |
| **Testability** | Ease with which the system can be tested. |
| **Reusability** | Ability to use components in other systems. |
| **Security** | Ability to protect against intentional or accidental intrusion. |
| **Data Integrity** | Accuracy and consistency of data. |

---

## The Design Process

### Stages of Design (Iterative Cycle)

```
                    ┌──────────────────────┐
                    │  UNDERSTAND THE       │
                    │  PROBLEM              │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │  IDENTIFY ONE OR     │
                    │  MORE SOLUTIONS      │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │  SOLUTION            │
                    │  ABSTRACTION         │
                    └──────────┬───────────┘
                               │
                               └─── (iterate back to understanding)
```

### Design Model Elements (Layered Pyramid)

| Layer | Description |
|---|---|
| **Data/Class Design** | Creates a model of data and objects at a high level of abstraction. |
| **Architectural Design** | Depicts the overall layout of the software. |
| **Interface Design** | Tells how information flows into/out of the system and among components. Includes UI, external interfaces, and internal interfaces. |
| **Component-Level Design** | Describes internal detail of each component: data structures, algorithms, interfaces. |
| **Deployment-Level Design** | Indicates how software functionality and subsystems are allocated within the physical computing environment. |

### Three Architectural Design Decisions

When making architectural decisions, address three concerns:

1. **Functional suitability** — Every decision is driven primarily by functional requirements. Use use-case diagrams.
2. **Quality of design** — Functionality is the same across designs; decisions must make the system stand out in quality (reusable, reliable).
3. **Construction constraints** — Determined by system type and design principles of the development team.

### Four Questions the Architect Must Answer

1. Who is the primary user of the system? (customer vs. client)
2. What is the primary functionality expected of the system? (core value-adding functionality)
3. What are the quality attributes expected? (non-functional requirements: security, reliability, scalability)
4. What are the design principles the system will adhere to?

---

## Design Concepts — Deeper Dive

### Abstraction

- IEEE definition: "A view of a problem that extracts essential information relevant to a particular purpose and ignores the remainder."
- An abstraction describes external behavior without internal details.
- Essential for **partitioning** — breaking a system into manageable pieces.

### Architecture

The overall structure of software providing conceptual integrity for a system. Three categories of properties:
- **Structural properties** — defines components and how they are packaged and interact.
- **Extra-functional properties** — addresses performance, reliability, security, adaptability.
- **Families of related systems** — ability to reuse architectural building blocks.

### Modularity

- Separately named and addressable components (modules).
- Makes software intellectually manageable.
- Helps with: planning development, accommodating changes, testing/debugging, maintenance.

### Information Hiding

- Algorithms and local data within a module are inaccessible to other modules.
- Each module has a **controlled interface**.
- The "secret" of a module is a specific design decision.

### Functional Independence (Coupling & Cohesion)

- **High cohesion** — a module performs only a single task. Elements within the module are strongly functionally related.
- **Low coupling** — a module has the lowest amount of connection needed with other modules. Modules have "aversion to excessive interaction."

| Coupling Type | Description (worst → best) |
|---|---|
| Content coupling | One module modifies local data of another (worst) |
| Common coupling | Modules share global data |
| Control coupling | One module passes control flags to another |
| Stamp coupling | Modules pass data structures containing more data than needed |
| Data coupling | Modules pass only necessary data (best) |

### Refinement

- **Procedural refinement** — decomposes a procedural representation into many levels of abstraction.
- **Data refinement** — starts with high-level data description and refines to actual data structures.

### Refactoring

- Reorganizes source code without changing external behavior.
- **Early refactoring** — focuses on program function, data architecture, classes.
- **Later refactoring** — focuses on algorithms and detailed processing logic.

### Design Classes (Four Types)

| Class Type | Purpose |
|---|---|
| **Interface classes** | Handle interaction with users and external systems. |
| **Entity classes** | Represent persistent data/business objects. |
| **Control classes** | Coordinate and sequence activities. |
| **Foundation classes** | Provide low-level utility services. |

---

## Architectural Patterns

### Pattern Comparison Table

| Pattern | Core Idea | Key Components | Strengths | Weaknesses | Best For |
|---|---|---|---|---|---|
| **Pipe-and-Filter** | Data flows through sequential processing steps | Filters (processors), Pipes (connectors) | Reusable filters, no shared state, simple linear processing | Limited to linear sequences, no shared state, rigid ordering | Data transformation pipelines, UNIX shell commands, compilers |
| **Layers** | System divided into hierarchical layers | Layer N (top) ... Layer N-4 (bottom) | Separation of concerns, encapsulation, change isolation | Performance overhead from layer crossing, potential for cascading changes | Enterprise applications, OS design, networking protocols |
| **MVC** | Separation into Model, View, Controller | Model (data/business logic), View (display), Controller (input handling) | Multiple views of same data, separation of concerns, testability | Complexity for simple UIs, tight coupling between View and Controller | Web applications, desktop UIs, mobile apps |
| **Client-Server** | Clients request services from servers | Clients (service requesters), Servers (service providers) | Scalability, reusability, security, maintainability | Network dependency, single point of failure, complexity | Web browsers, email, databases |
| **Blackboard** | Multiple knowledge sources share a central data store | Knowledge Sources, Blackboard, Controller | Solves complex, non-deterministic problems; flexible knowledge integration | Complex control logic, performance bottlenecks, difficult to test | AI systems, speech recognition, signal processing |
| **Broker** | Broker mediates client-server communication | Client, Broker (with Interface Repository), Server Object | Location transparency, decoupling, service discovery | Single point of failure, broker complexity, performance overhead | Distributed systems, CORBA, message-oriented middleware |
| **Repository** | Shared data store accessed by components | Central Repository, Active Components | Data sharing, well-defined interfaces, consistency | Single point of failure, bottleneck, components tightly coupled via data | Database systems, version control, CAD systems |
| **Virtual Machine** | Layered abstraction creating a pseudo-machine | Language/Platform VM, VM Support Library, Hardware | Portability, platform independence, security | Performance overhead, complexity | Java VM, interpreters, emulators |

### Detailed Pattern Explanations

#### 1. Pipe-and-Filter Pattern

Each processing step is encapsulated in a **filter** component. Data passes between adjacent components via **pipes**. Filters have no shared state — they are independent, reusable, and replaceable. Variants include process control systems and UNIX shell pipelines.

**Example:** A compiler where lexical analysis → parsing → semantic analysis → code generation are filters connected by pipes (intermediate representations).

#### 2. Layers Pattern

The system is divided into layers arranged hierarchically. Each layer:
- Uses services of the layer below
- Provides services to the layer above
- Is kept separate so changes in implementation of one layer do not affect others

The uppermost layer provides the user interface; the lowermost provides basic system utilities (communication, memory management).

**Example:** TCP/IP protocol stack, operating system architecture, enterprise application layers.

#### 3. Model-View-Controller (MVC) Pattern

Three components:

- **Model**: Core component managing data and business logic. Notifies views when data changes. Independent of the UI.
- **View**: Displays data from the model. Sends user actions to the controller. Can have multiple views of the same data.
- **Controller**: Handles user input, updates the model, selects the view to display.

**Data flow:** User input → Controller → (updates Model, selects View) → Model notifies View → View displays updated data.

#### 4. Client-Server Pattern

- **Server**: Always on, listens for requests, offers services.
- **Client**: Initiates communication, sends requests, receives responses.
- Communication happens over a network.
- Clients and servers are physically separate.

**Example:** Web browsers (clients) and web servers, email clients and mail servers.

#### 5. Blackboard Pattern

Three components:
1. **Knowledge Sources** — interact with the blackboard, activated by the controller.
2. **Blackboard** — contains knowledge from various sources; changes can lead to a solution.
3. **Controller** — waits for changes on the blackboard and acts on them.

**Example:** Speech recognition systems where multiple algorithms (phonetic, syntactic, semantic) collaborate on the same data.

#### 6. Broker Pattern

A **broker** acts as mediator between client and server:
- Forwards requests from client to server and responses back.
- Maintains an **interface repository** with information about server services.
- Hides communication details.
- Helps locate the server and manage communication.

**Variant — Message Broker Pattern:** Components communicate through a central hub (message broker) rather than directly. The broker routes messages from sender to appropriate receiver. Components do not need to know each other's location. Useful for decoupling and scalability.

#### 7. Repository Pattern

- A central data store (repository) is shared among components.
- Components access the store through well-defined interfaces.
- The repository is a **passive** component (does not initiate actions).
- Components are **active** (perform actions).
- Variants: Database, Blackboard.

**Example:** A database server where multiple application components read/write through SQL interfaces.

#### 8. Virtual Machine Pattern

- System is separated into layers, each constituting a pseudo-machine.
- Bottom layer: hardware.
- Top layer: language for the user.
- Intermediate layers provide support upward.
- Provides portability and platform independence.

**Example:** Java Virtual Machine (JVM) — Java bytecode runs on JVM regardless of underlying hardware.

---

## Architectural Views

### Why Multiple Views?

Complex systems cannot be understood from a single perspective. Different stakeholders need different views: end users care about functionality, developers about code organization, integrators about runtime behavior, and deployers about hardware mapping.

### Three Categories of Views

| View Category | Focus | Elements | Relationships | Used For |
|---|---|---|---|---|
| **Module Views** | Static organization of code | Modules | Uses, data, calls | Maintainability, portability, reusability |
| **Component-and-Connector Views** | Runtime behavior | Components, Connectors | Communication paths | Performance, reliability, availability |
| **Allocation Views** | Software-to-hardware mapping | Software components, Hardware nodes | Deployed-on, implemented-in | Deployment, implementation, work assignment |

### Module View Subtypes

1. **Decomposition views** — system as a hierarchy of modules decomposed until implementable.
2. **Uses views** — dependencies among modules; which modules use which others.
3. **Layered views** — system as a set of layers; each provides services above, uses services below.

### Component-and-Connector View Subtypes

1. **Pipe-and-filter views** — sequential data processing through pipes.
2. **Shared-memory views** — components communicate through shared memory.
3. **Layered views** — layers with services across boundaries.
4. **Client-server views** — clients request, servers provide.
5. **Communicating-processes views** — processes communicate via message passing.

### Allocation View Subtypes

1. **Deployment views** — mapping of software to hardware.
2. **Implementation views** — mapping of software to source code files.
3. **Work assignment views** — mapping of software to development teams.

---

## The 4+1 View Model (Kruchten)

This is the most commonly taught architectural view model. It organizes architecture into five concurrent views:

```
                    ┌─────────────────┐
                    │   LOGICAL VIEW  │
                    │  (End Users)    │
                    │  Classes, Use   │
                    │  Cases,         │
                    │  Interactions   │
                    └────────┬────────┘
                             │
         ┌───────────────────┼───────────────────┐
         │                   │                   │
         ▼                   ▼                   ▼
┌─────────────────┐  ┌─────────────┐  ┌─────────────────┐
│  DEVELOPMENT    │  │  SCENARIOS  │  │    PHYSICAL     │
│  VIEW           │  │  (Center)   │  │    VIEW         │
│  (Programmers)  │  │  Use Cases  │  │  (Sys Engineers)│
│  Components,    │  │  Tie Views  │  │  Topology,      │
│  Packages,      │  │  Together   │  │  Deployment     │
│  Layers         │  └─────────────┘  └─────────────────┘
└─────────────────┘                   │
                                      │
                                      ▼
                             ┌─────────────────┐
                             │   PROCESS VIEW  │
                             │  (Integrators)  │
                             │  Performance,   │
                             │  Concurrency,   │
                             │  Synchronization│
                             └─────────────────┘
```

| View | Audience | Focus | UML Diagrams | Pattern Used |
|---|---|---|---|---|
| **Logical View** | End Users | What the system does — functional requirements | Class diagrams, Object diagrams, Use-case diagrams, Interaction diagrams | Façade pattern |
| **Development View** | Programmers | How the system is organized — source code, modules, packages, layers | Package diagrams, Component diagrams | Layered pattern |
| **Process View** | System Integrators | Runtime behavior — processes, threads, communication, synchronization, concurrency | Activity diagrams | Pipe-and-filter pattern |
| **Physical View** | System Engineers | Where the system runs — hardware mapping, topology, deployment | Deployment diagrams | Master-slave pattern |
| **Scenarios** | All stakeholders | How views work together — validating and illustrating architecture | Use-case diagrams, Interaction diagrams | — |

### Key Insight: Scenarios at the Center

Scenarios (use cases) tie the four views together. They validate the architecture by walking through specific sequences of interactions. If a use case cannot be realized across the logical, development, process, and physical views, the architecture is incomplete or inconsistent.

---

## ISO/IEC/IEEE 42010 Standard

This is the international standard for architecture descriptions. Key concepts:

| Term | Definition |
|---|---|
| **System** | The entity being described, including its context and boundaries. |
| **Stakeholder** | An individual or organization with a concern about the system. |
| **Concern** | Any interest in the system relevant to one or more stakeholders. |
| **Architecture Viewpoint** | Specifies the kinds of models, techniques, and conventions for creating a view. |
| **Architecture View** | A representation of the system from the perspective of a viewpoint. |
| **Architecture Model** | A specific model used within a view. |

### What an Architecture Description Must Include

1. Complete identification of the system, boundaries, and context.
2. Definition of stakeholders and their concerns.
3. Selection of architecture viewpoints.
4. A set of architecture views.
5. Consistency between viewpoints and views.
6. Rationale for architecture decisions.
7. Consistency with system requirements.
8. Consistency with design principles.

**Important:** The standard does NOT prescribe specific viewpoints, views, modeling techniques, or rationale. It provides a framework — you choose what fits your system.

---

## Application Architectures

### Three-Tier Architecture

An extension of client-server that separates the application into three logical/physical tiers:

```
   ┌──────────────┐
   │ Presentation │  (Client: UI, user interaction)
   │    Tier      │
   └──────┬───────┘
          │
   ┌──────┴───────┐
   │ Application  │  (Server: business logic, processing)
   │    Tier      │
   └──────┬───────┘
          │
   ┌──────┴───────┐
   │   Data Tier  │  (Database: storage, retrieval)
   └──────────────┘
```

| Aspect | Presentation Tier | Application Tier | Data Tier |
|---|---|---|---|
| Responsibility | UI, user interaction | Business logic, processing | Data storage, retrieval |
| Scalability | Scale independently | Scale independently | Scale independently |
| Example | Web browser | Web/application server | Database server |

### Service-Oriented Architecture (SOA)

- A collection of services communicating over a network.
- Services are discrete units of functionality accessible remotely.
- Central **Enterprise Service Bus (ESB)** mediates communication.
- A **UDDI Registry** helps with service discovery.

**Principles:** Loose coupling, reusability, composability, statelessness.

| Benefit | Challenge |
|---|---|
| Flexibility — services can be replaced/updated independently | Complexity in design and implementation |
| Scalability — services scale independently | Performance — network latency |
| Interoperability — different technologies and platforms | Security — securing service communication |
| Reusability — services reused across applications | — |

### Microservices Architecture

- Application structured as a collection of loosely coupled, independently deployable services.
- Each microservice performs a specific business function.
- Communication through lightweight protocols (HTTP/REST, message queues).
- Each service can be developed, deployed, and scaled independently.
- An **API Gateway** provides a single entry point for clients.
- A **Message Broker** enables asynchronous communication between services.

| Benefit | Description |
|---|---|
| Scalability | Each service scales independently based on demand |
| Flexibility | Different technologies can be used for different services |
| Maintainability | Small, focused services are easier to understand and change |
| Resilience | Failure of one service does not cascade to others |

### Comparison: SOA vs. Microservices

| Aspect | SOA | Microservices |
|---|---|---|
| Service size | Larger, coarser-grained services | Smaller, fine-grained services |
| Communication | Often ESB (heavy middleware) | Lightweight (HTTP/REST, message queues) |
| Data management | Shared databases | Database-per-service |
| Deployment | Monolithic or shared deployment | Independent deployment |
| Governance | Centralized | Decentralized |

---

## Relationships Between Concepts

### Design → Architecture → Implementation

```
Requirements → Architectural Design (high-level structure)
                    ↓
              Interface Design (how components interact)
                    ↓
              Component-Level Design (internal details)
                    ↓
              Implementation (code)
```

### Patterns → Views → Stakeholders

Each architectural pattern can be viewed from multiple perspectives. For example, the Layered pattern appears in:
- **Logical view** as class hierarchies
- **Development view** as package/layer organization
- **Process view** as thread/process layers
- **Physical view** as tier deployment

### Cohesion & Coupling → Quality

Low coupling + High cohesion = Good design
- Changes are isolated (high cohesion limits scope of change)
- Components are loosely connected (low coupling limits ripple effects)

### Refinement ↔ Abstraction (Opposite Directions)

- **Abstraction** removes detail (bottom-up: from specific to general).
- **Refinement** adds detail (top-down: from general to specific).
- Both are essential; design alternates between them.

---

## Examples

### Example 1: Web Application Architecture (MVC + Three-Tier)

A typical web application combines patterns:
- **MVC** organizes the code within the application tier.
- **Three-tier** separates presentation (browser), application (server), and data (database).
- **Client-server** describes the browser-to-server communication.
- **Layers** organize the server-side code (controller layer, service layer, data access layer).

### Example 2: Compiler (Pipe-and-Filter + Blackboard)

A compiler might use:
- **Pipe-and-filter** for the front-end: Lexical analysis → Parsing → Semantic analysis.
- **Blackboard** for optimization: multiple optimization passes share a common intermediate representation.
- **Layers** for the back-end: High-level IR → Low-level IR → Machine code.

### Example 3: Enterprise Application (SOA + Broker)

- **SOA** defines business services (customer service, order service, payment service).
- **Broker** (ESB) mediates communication between these services.
- **Client-server** handles front-end and back-end communication.
- **Layers** organize each service internally.

---

## Common Mistakes & Exam Traps

| Mistake | Why It's Wrong | Correct Understanding |
|---|---|---|
| Confusing coupling with cohesion | They are two independent measures | Coupling = inter-module dependency; Cohesion = intra-module unity. Both matter. |
| Thinking MVC has only one view | MVC supports multiple views of the same model | The View component can have many views; Model notifies all views of changes. |
| Believing layers always improve performance | Layer crossing adds overhead | Layers improve maintainability but may reduce performance due to indirection. |
| Confusing blackboard with repository | Both use a central store | In repository, the store is passive; in blackboard, the store is active and knowledge sources share it with a controller. |
| Mixing up 4+1 views | Each view serves a different stakeholder | Logical (end user), Development (programmer), Process (integrator), Physical (deployer), Scenarios (all). |
| Assuming all architectural patterns are mutually exclusive | Systems often combine multiple patterns | A web app can use MVC + Layers + Client-Server + Three-Tier simultaneously. |
| Thinking microservices and SOA are the same | They differ in service granularity and governance | SOA = coarser, centralized; Microservices = finer, decentralized. |
| Forgetting that the 4+1 view names have specific patterns | Each view is associated with a pattern | Logical → Façade, Development → Layered, Process → Pipe-and-filter, Physical → Master-slave. |
| Confusing design patterns with architectural patterns | They operate at different scales | Architectural patterns define system structure; design patterns solve specific design problems within components. |
| Believing a "module" in module views is the same as a "component" in C&C views | Module = static code unit; Component = runtime computational unit | Module view is about code organization; C&C view is about runtime behavior. |

---

## Active Recall Questions

1. What are the five elements of the design model, from most abstract to most concrete?
2. Explain the difference between coupling and cohesion. Why is low coupling + high cohesion desirable?
3. What is the difference between abstraction and refinement?
4. List the four types of design classes and their purposes.
5. What are the three architectural design concerns?
6. Name the three categories of architectural views (module, C&C, allocation) and what each is used for.
7. Draw and label the 4+1 View Model from memory. What pattern is associated with each view?
8. Compare pipe-and-filter with layers: when would you choose one over the other?
9. Explain the three components of MVC and how data flows between them.
10. How does a broker pattern differ from a client-server pattern?
11. What is the role of the controller in the blackboard pattern?
12. What is the difference between a repository and a blackboard?
13. List three benefits and three challenges of SOA.
14. How do microservices differ from SOA?
15. What must an ISO/IEC/IEEE 42010 architecture description include?

---

## Potential Exam Questions

### Short Answer

1. Define "abstraction" as it relates to software design, and explain why it is essential for partitioning.
2. What is the difference between a module view and a component-and-connector view?
3. Explain the purpose of the scenarios view in the 4+1 model.
4. List and describe three types of coupling, ordered from worst to best.
5. What are the three components of the blackboard pattern? Briefly describe each.

### Essay / Design

6. You are designing a real-time data processing system that receives sensor readings, transforms them through multiple stages, and stores results. Which architectural pattern(s) would you choose? Justify your answer with reference to quality attributes.

7. A team is building a large enterprise application with multiple business units. Compare and contrast using a Service-Oriented Architecture versus a Microservices architecture. Under what conditions would you recommend each?

8. Using the 4+1 View Model, describe how you would document the architecture of an e-commerce web application. For each view, specify the audience, the UML diagrams you would use, and the key elements you would show.

9. Explain the relationship between the design concepts of information hiding, modularity, and functional independence. How do they work together to produce a maintainable system?

10. A system has components A, B, and C. A calls B directly, B and C share a global configuration file, and C modifies internal data structures of A. Analyze the coupling in this system. Which changes would you recommend and why?

---

## Topic Summary

Architecture and design transform requirements into a blueprint for construction. The key takeaways:

1. **Design is the "HOW"** — it answers how the system will be constructed, how modules interact, and how the solution works.
2. **Good design is characterized by** firmness (no bugs), commodity (fit for purpose), and delight (pleasurable experience).
3. **Design concepts** — abstraction, modularity, information hiding, coupling, cohesion, refinement, and refactoring — are the fundamental tools for creating quality software.
4. **Architectural patterns** provide reusable solutions to common structural problems. Each pattern has trade-offs; no single pattern fits all scenarios.
5. **Multiple views are essential** — the 4+1 model (Logical, Development, Process, Physical, Scenarios) ensures all stakeholder perspectives are addressed.
6. **Application architectures** (three-tier, SOA, microservices) extend basic patterns for modern distributed systems.
7. **Quality is designed in, not tested in** — architectural decisions directly impact performance, scalability, security, and maintainability.
8. **Systems combine patterns** — real-world systems rarely use a single pattern in isolation.

Remember: "Writing a clever piece of code that works is one thing; designing something that can support a long-lasting business is quite another."
