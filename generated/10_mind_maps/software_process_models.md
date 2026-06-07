# Software Process Models - Mind Map

```
                                         +===========================================+
                                         |         SOFTWARE PROCESS MODELS           |
                                         |  A structured set of activities required  |
                                         |     to develop a software system.         |
                                         +===========================================+
                                                          |
          +---------------------------+-------------------+-------------------+--------------------------+
          |                           |                   |                   |                          |
          v                           v                   v                   v                          v
+====================+  +=========================+  +====================+  +====================+  +====================+
|    WATERFALL       |  |   INCREMENTAL            |  | REUSE-ORIENTED     |  |     SPIRAL         |  |    PROTOTYPING      |
|    MODEL           |  |   DEVELOPMENT            |  | (Integration &     |  |     MODEL          |  |                     |
| (Plan-driven,      |  |                          |  |  Configuration)    |  | (Risk-driven,      |  | (Early working      |
|  sequential)       |  | (Spec, dev, validation   |  |                    |  |  iterative)        |  |  model to clarify   |
|                    |  |  interleaved)             |  | (Assembled from    |  |                    |  |  requirements)      |
+====================+  +=========================+  |  existing COTS     |  +====================+  +====================+
          |                           |               |  components)        |            |                       |
          v                           v               +====================+            v                       v
+====================+  +=========================+          |               +====================+  +====================+
| PHASES:            |  | BENEFITS:                |          v               | QUADRANTS (each     |  | TYPES:              |
| - Requirements     |  | - Reduced cost of        |  +====================+  | loop):              |  | - Throw-away        |
|   definition       |  |   accommodating change   |  | KEY STAGES:         |  | 1. Determine        |  |   (clarify then     |
| - System/software  |  | - Easier customer        |  | - Requirements      |  |    objectives,      |  |   discard)          |
|   design           |  |   feedback               |  |   specification     |  |    alternatives,    |  | - Evolutionary      |
| - Implementation   |  | - More rapid delivery    |  | - Software          |  |    constraints      |  |   (gradually        |
|   & unit testing   |  |   of useful software     |  |   discovery &       |  | 2. Evaluate         |  |   refined into      |
| - Integration &    |  |                          |  |   evaluation        |  |    alternatives,    |  |   final system)     |
|   system testing   |  | PROBLEMS:                |  | - Requirements      |  |    identify &       |  |                     |
| - Operation &      |  | - Process not visible    |  |   refinement        |  |    resolve risks    |  | BENEFITS:           |
|   maintenance      |  |   (few deliverables)     |  | - Application       |  |    (prototyping,    |  | - Clarifies         |
|                    |  | - System structure       |  |   system config.    |  |    simulation)      |  |   ambiguous         |
| PROBLEMS:          |  |   degrades without       |  | - Component         |  | 3. Develop/verify   |  |   requirements      |
| - Inflexible to    |  |   refactoring            |  |   adaptation &      |  |    next-level       |  | - Early user        |
|   change           |  |                          |  |   integration        |  |    product          |  |   feedback          |
| - Late discovery   |  | CAN BE:                  |  +====================+  | 4. Plan next phase   |  | - Reduces risk of   |
|   of issues        |  | - Plan-driven            |          |               |    (review/commit)    |  |   wrong system      |
| - Slow delivery    |  | - Agile                  |          v               +====================+  |                     |
|                    |  +=========================+  | ADVANTAGES:            |           |          | PROBLEMS:            |
| APPROPRIATE FOR:   |                          | - Reduced costs       |           v          | - Users think        |
| - Stable reqs      |                          |   & risks             |  GUIDES DECISIONS:   |   prototype is       |
| - Large, multi-    |                          | - Faster delivery     |  - Risk analysis     |   final system       |
|   site projects    |                          | - Proven components   |    in every loop     | - Seen as wasted     |
| - Safety-critical  |                          |   (more reliable)     |  - Each loop adds    |   effort (throw-     |
|   / regulated      |                          |                       |    more complete     |   away)              |
|   systems          |                          | DISADVANTAGES:        |    version           | - Evolutionary can   |
+====================+                          | - Requirements        |  - Suitable for      |   degrade structure  |
                                                |   compromises         |    large, high-risk  +====================+
                                                |   inevitable          |    projects
                                                | - Loss of control     |
                                                |   over evolution      |
                                                | - Vendor lock-in      |
                                                +====================+

+==================================================================================================================+
| CORE CROSS-CUTTING CONCEPTS                                                                                      |
+==================================================================================================================+
|                                                                                                                  |
|  +---------------------------------------------------+  +---------------------------------------------------+  |
|  | PLAN-DRIVEN vs AGILE                               |  | SOFTWARE PROCESS ACTIVITIES                       |  |
|  | Plan-driven: Activities planned in advance.        |  |                                                    |  |
|  | Progress measured against plan.                    |  |  1. SPECIFICATION (Requirements Engineering)       |  |
|  | Agile: Planning is incremental. Easier to change.  |  |     - Elicitation & Analysis                       |  |
|  | Most practical processes combine both.             |  |     - Specification                                |  |
|  +---------------------------------------------------+  |     - Validation                                   |  |
|                                                          |  2. DESIGN & IMPLEMENTATION                        |  |
|  +---------------------------------------------------+  |     - Architectural design                         |  |
|  | TDD (Test Driven Development)                       |  |     - Interface design                             |  |
|  | Red: Write failing test                              |  |     - Component design                             |  |
|  | Green: Write code to pass                            |  |     - Database design                              |  |
|  | Refactor: Clean up code                              |  |  3. VALIDATION                                     |  |
|  |                                                      |  |     - Unit testing -> Integration -> System -> Accept|  |
|  | Drives testable design. Safety net for refactoring.  |  |     - 30-50% of development cost                   |  |
|  +---------------------------------------------------+  |  4. EVOLUTION                                      |  |
|                                                          |     - Corrective maint (bug fixes)                  |  |
|  +---------------------------------------------------+  |     - Adaptive maint (new environments)             |  |
|  | DESIGN PRINCIPLES                                    |  |     - Perfective maint (new features)               |  |
|  | - Separation of concerns                              |  |     - 60-70% of total system cost                  |  |
|  | - Modularity                                         |  |     - Refactoring: change structure, not function   |  |
|  | - Abstraction                                        |  +---------------------------------------------------+  |
|  | - Information hiding                                 |                                                     |
|  | - Reuse                                              |  +---------------------------------------------------+  |
|  | - Coupling & cohesion                                |  | PROCESS IMPROVEMENT: SPICE (ISO 15504)              |  |
|  +---------------------------------------------------+  |  Capability Levels:                                  |  |
|                                                          |    L0 Incomplete -> L1 Performed -> L2 Managed       |  |
|  +---------------------------------------------------+  |    L3 Defined -> L4 Quant Managed -> L5 Optimizing   |  |
|  | NO RIGHT OR WRONG PROCESS MODEL                      |  +---------------------------------------------------+  |
|  | Choice depends on: requirements stability, risk,     |                                                     |
|  | team distribution, regulatory needs, project size.   |  +---------------------------------------------------+  |
|  | Most large systems use elements from multiple models.|  | MAINTENANCE TYPES                                   |  |
|  +---------------------------------------------------+  |  Corrective: Fix bugs                                |  |
|                                                          |  Adaptive: Adapt to new env (OS, hardware)           |  |
|                                                          |  Perfective: Add new features                         |  |
|                                                          +---------------------------------------------------+  |
|                                                                                                                  |
+==================================================================================================================+
```

## Quick Reference: Selecting a Process Model

```
                     +----------------------------------+
                     | START:                           |
                     | "What kind of project is this?"  |
                     +----------------------------------+
                                  |
           +----------------------+----------------------+
           |                                             |
     REGULATED/SAFETY-CRITICAL                    CHANGING REQUIREMENTS
           |                                             |
           v                                             v
  +------------------+                          +-------------------+
  | WATERFALL MODEL  |                          | INCREMENTAL       |
  | (Full docs,      |                          | DEVELOPMENT       |
  |  traceability)   |                          | (Iterate fast)    |
  +------------------+                          +-------------------+
           |                                             |
           |                                             |
     HIGH RISK PROJECT                             COTS EXISTS?
           |                                             |
           v                                    +--------+--------+
  +------------------+                          |                 |
  | SPIRAL MODEL     |                         YES                NO
  | (Risk analysis   |                          |                 |
  |  in every loop)  |                          v                 v
  +------------------+                  +------------------+  +-------------------+
                                         | REUSE-ORIENTED  |  | INCREMENTAL       |
                                         | (Integrate COTS,|  | (Build from       |
                                         |  configure)     |  |  scratch)        |
                                         +------------------+  +-------------------+
                                                                        |
                                                                  UNCLEAR REQS?
                                                                        |
                                                                   +--------+
                                                                   | YES    |
                                                                   v
                                                            +------------------+
                                                            | PROTOTYPING     |
                                                            | (Clarify first) |
                                                            +------------------+
```