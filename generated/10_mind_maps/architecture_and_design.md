# Architecture & Design — Mind Map

```
                                      +============================================+
                                      |       SOFTWARE ARCHITECTURE & DESIGN       |
                                      |   The fundamental organization of a system |
                                      |  embodied in its components, relationships,|
                                      |  and the principles guiding its design.    |
                                      +============================================+


--- PANEL 1: DESIGN CONCEPTS ---

                          +============================================+
                          |           SOFTWARE DESIGN CONCEPTS         |
                          +============================================+
                                       |
          +----------------------------+----------------------------+
          |                            |                            |
          v                            v                            v
+====================+  +====================+  +====================================+
| CORE CONCEPTS      |  | DESIGN GOALS       |  | QUALITY ATTRIBUTES                  |
+--------------------+  +--------------------+  +------------------------------------+
| Abstraction        |  | Firmness (correct) |  | Performance                         |
| Modularity         |  | Commodity (useful)  |  | Security (data integrity)          |
| Information hiding |  | Delight (pleasure)  |  | Scalability                         |
| Coupling (low)     |                       |  | Extensibility / Modifiability       |
| Cohesion (high)    |                       |  | Testability                         |
+====================+                       |  | Reusability                         |
                                             +====================================+
+====================================+
| OBJECT-ORIENTED CONCEPTS          |
+------------------------------------+
| Encapsulation                     |
| Inheritance                        |
| Polymorphism                       |
| Interface vs Implementation       |
| Entity / Control / Boundary       |
| Foundation Classes                |
+====================================+


--- PANEL 2: ARCHITECTURAL PATTERNS ---

                          +============================================+
                          |          ARCHITECTURAL PATTERNS            |
                          |  A set of system-level decisions about     |
                          |  how components communicate and interact   |
                          +============================================+
                                       |
          +----------------------------+----------------------------+
          |                            |                            |
          v                            v                            v
+====================+  +====================+  +====================================+
| SHARED MEMORY      |  | VIRTUAL MACHINE   |  | OTHER STYLES                        |
+--------------------+  +--------------------+  +------------------------------------+
| Layered            |  | Interpreter        |  | Client/Server                       |
| Pipes & Filters    |                     |  | Broadcast                           |
| Blackboard         |                     |  +====================================+
+====================+                     |
                                           |
                +--------------------------+
                |
                v
+====================================+
| REPOSITORY        | CONTROL       |
+--------------------+---------------+
| Database          | Process Ctrl  |
| Blackboard        | Finite State  |
|                   | Machine       |
+====================================+

+----------------------------------------------------------+
| PATTERN CATEGORIES — SUMMARY TABLE                        |
+----------------------------------------------------------+
| CATEGORY     | PATTERNS                     | DESCRIPTION                         |
+==============+==============================+=====================================+
| SHARED       | Layered                      | Each layer provides services to the |
| MEMORY       |                              | layer above it                      |
|              +------------------------------+-------------------------------------+
|              | Pipes & Filters              | Data flows through processing steps |
|              +------------------------------+-------------------------------------+
|              | Blackboard                   | Shared data accessible to all       |
+--------------+------------------------------+-------------------------------------+
| VIRTUAL      | Interpreter                  | Executes program instructions       |
| MACHINE      |                              | abstractly                          |
+--------------+------------------------------+-------------------------------------+
| OTHER        | Client/Server                | Service providers and consumers     |
|              +------------------------------+-------------------------------------+
|              | Broadcast                    | One-to-many message distribution    |
+--------------+------------------------------+-------------------------------------+
| REPOSITORY   | Database                     | Structured data storage/retrieval   |
|              +------------------------------+-------------------------------------+
|              | Blackboard                   | Central data hub for agents         |
+--------------+------------------------------+-------------------------------------+
| CONTROL      | Process Control              | Feedback loop regulation            |
|              +------------------------------+-------------------------------------+
|              | Finite State Machine         | System behavior as state transitions|
+--------------+------------------------------+-------------------------------------+


--- PANEL 3: ARCHITECTURAL VIEWS (4+1 MODEL) ---

                          +============================================+
                          |      THE 4+1 VIEW MODEL  (Kruchten, 1995)  |
                          |   Five concurrent views of a system's     |
                          |   architecture, each addressing a         |
                          |   different stakeholder concern.          |
                          +============================================+

                              +====================================+
                              |         SCENARIOS                  |
                              |       (The "+1" view)              |
                              |   Ties all views together          |
                              |   via use cases & user stories     |
                              +====================================+
                                          |
            +-----------------------------+-----------------------------+
            |                             |                             |
            v                             v                             v
+====================+  +====================+  +====================+  +====================+
| LOGICAL VIEW       |  | DEVELOPMENT VIEW   |  | PROCESS VIEW       |  | PHYSICAL VIEW      |
+--------------------+  +--------------------+  +--------------------+  +--------------------+
| System's           |  | Software           |  | Runtime            |  | System's           |
| functional         |  | decomposition      |  | concurrency,       |  | hardware mapping   |
| structure          |  | into modules       |  | threads, sync      |  | & topology         |
+--------------------+  +--------------------+  +--------------------+  +--------------------+
| PATTERN:           |  | PATTERN:           |  | PATTERN:           |  | PATTERN:           |
| Façade Pattern     |  | Layered Pattern    |  | Pipe-and-Filter    |  | Master-Slave       |
|                    |  |                    |  |                    |  | Pattern            |
+--------------------+  +--------------------+  +--------------------+  +--------------------+
| Focus:             |  | Focus:             |  | Focus:             |  | Focus:             |
| Abstraction,       |  | Code organization, |  | Performance,       |  | Software-to-       |
| encapsulation      |  | reuse, modularity  |  | reliability,       |  | hardware mapping   |
|                    |  |                    |  | availability       |  |                    |
+====================+  +====================+  +====================+  +====================+


--- PANEL 4: APPLICATION ARCHITECTURES ---

+==========================================================================================================+
|                              APPLICATION ARCHITECTURE PATTERNS                                            |
+==========================================================================================================+
|                                                                                                           |
|  +=========================================+  +=========================================+                 |
|  |          SOA                             |  |          MICROSERVICES                  |                 |
|  |  (Service-Oriented Architecture)         |  |                                         |                 |
|  +-----------------------------------------+  +-----------------------------------------+                 |
|  | Enterprise Service Bus (ESB)            |  | Cloud-native                             |                 |
|  | UDDI Registry                           |  | API Gateway                              |                 |
|  | Coarse services                         |  | Message Broker                           |                 |
|  | Shared data                             |  | Independent deployment                   |                 |
|  +=========================================+  | Fine services                            |                 |
|                                                | DB-per-service                           |                 |
|  +=========================================+  +=========================================+                 |
|  |          THREE-TIER ARCHITECTURE        |                                                    |
|  +-----------------------------------------+                                                    |
|  | Web application pattern                 |                                                    |
|  | +---------------------------+           |                                                    |
|  | | PRESENTATION TIER (UI)   |           |                                                    |
|  | | Application TIER (Logic) |           |                                                    |
|  | | DATA TIER (Storage)      |           |                                                    |
|  | +---------------------------+           |                                                    |
|  +=========================================+                                                    |
|                                                                                                           |
+==========================================================================================================+


--- PANEL 5: ARCHITECTURAL VIEW CATEGORIES (ISO/IEC 42010 & BEYOND) ---

+==============================================================================================================+
|                                          VIEW CATEGORIES                                                      |
+==============================================================================================================+
|  MODULE VIEWS                  |  COMPONENT & CONNECTOR      |  ALLOCATION VIEWS                              |
|                                |  VIEWS                       |                                                 |
+================================+==============================+=================================================+
| • Decomposition views          | • Pipe-and-Filter views      | • Deployment views                              |
| • Uses views                   | • Shared-memory views        | • Implementation views                          |
| • Layered views                | • Layered views              | • Work assignment views                         |
|                                | • Client-server views        |                                                 |
|                                | • Communicating processes    |                                                 |
+--------------------------------+------------------------------+-------------------------------------------------+
| USED FOR:                      | USED FOR:                    | USED FOR:                                       |
| Maintainability, Portability,  | Performance, Reliability,    | Software-to-hardware mapping                     |
| Reusability, Modifiability     | Availability                 |                                                 |
+==============================================================================================================+

```

## Legend

```
+============================+  = Title / Root Node (Major topic)
|                            |
+============================+

+----------------------------+  = Sub-node (Properties, categories)
|                            |
+----------------------------+

│     = Vertical connector
├──   = Branch (has siblings below)
└──   = Final branch (no siblings below)
v     = Hierarchical connection (parent → child)

--- PANEL N ---  = Section divider between logical groupings
```

*End of Architecture & Design Mind Map*