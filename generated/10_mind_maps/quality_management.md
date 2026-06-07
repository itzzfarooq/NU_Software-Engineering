# Quality Management - Mind Map

```
                           +========================================+
                           |        QUALITY MANAGEMENT             |
                           |  (Independent check on SW process)    |
                           +========================================+
                                        |
            +---------------------------+---------------------------+
            |                           |                           |
            v                           v                           v
+-----------------------++----------------------------++------------------------+
|  QUALITY ACTIVITIES   ||   QUALITY ATTRIBUTES       ||   STANDARDS            |
+-----------------------+|  (Non-functional chars)    |+------------------------+
|                       |+----------------------------+|
| 1. Quality Planning   | Security     Reliability    |  Encapsulate best      |
|    - Prioritize attr  | Safety       Resilience     |  practice              |
|    - Define assessm.  | Robustness   Understandab.  |  Define quality        |
|    - Produce plan     | Testability  Adaptability   |  Provide continuity    |
|                       | Modularity   Complexity     |                        |
| 2. Quality Assurance  | Portability  Usability      |  TYPES:                |
|    - Process-focused  | Reusability  Efficiency     |  International (ISO)   |
|    - Enforce standards| Learnability                |  National (ANSI, BSI)  |
|    - Independent team |                              |  Organizational        |
|                       |  [Conflicts inevitable]      |  Project-level         |
| 3. Quality Control    |  e.g. Robustness vs Perf.   |                        |
|    - Product-focused  |  Security vs Usability      |  +------------------+  |
|    - Inspect deliver. |                              |  | PRODUCT STDS     |  |
|    - Review reports   |                              |  | - Doc structure  |  |
|                       |                              |  | - Code style     |  |
+-----------------------+                              |  | - Forms/template |  |
                                                       |  +------------------+  |
                                                       |  +------------------+  |
                                                       |  | PROCESS STDS     |  |
                                                       |  | - Review conduct |  |
                                                       |  | - Release proc.  |  |
                                                       |  | - Change control |  |
                                                       |  +------------------+  |
                                                       +------------------------+
                                        |
            +---------------------------+---------------------------+
            |                           |                           |
            v                           v                           v
+------------------------++----------------------------++-------------------------+
| PROCESS-BASED QUALITY  ||       ISO 9001             || QUALITY CONFLICTS       |
+------------------------+|  (Framework for QMS)       |+-------------------------+
|                        |+----------------------------+|                         |
| Define Process         |                             | Cannot optimize all     |
|   -> Develop Product   | CORE PROCESSES:             | attributes at once      |
|   -> Assess Quality    | Business acquisition        |                         |
|   -> OK?               | Design & development        | Trade-off examples:     |
|      |-- Yes: Stdize   | Business management         |  - Security vs Usability|
|      |-- No: Improve   | Supplier management         |  - Robustness vs Perf.  |
|                        | Production & delivery       |  - Portability vs Speed |
| Quality BUILT IN       | Test, Service & support     |  - Modularity vs Effic. |
| through process, not   | Config & inventory mgmt     |                         |
| inspected in at end    |                             | RESOLUTION:             |
|                        | QA MANUAL ->                | Quality plan prioritizes|
|                        |   Project quality plans     | key attributes & defines|
|                        |                             | agreed assessment method|
|                        | CERTIFICATION:              |                         |
|                        |   External body certifies   |                         |
|                        |   conformance to ISO 9001   |                         |
|                        |   Often required by clients |                         |
|                        |                             |                         |
+------------------------++----------------------------++-------------------------+
                                        |
                            +-----------+-----------+
                            |                       |
                            v                       v
             +---------------------++------------------------+
             |  INDEPENDENT QA TEAM ||  PROBLEMS W/ STDS      |
             +---------------------++------------------------+
             |                     ||                        |
             | Objective view      || Seen as irrelevant     |
             | No developer bias   || Outdated if not main.  |
             | Reports honestly    || Can stifle creativity  |
             +---------------------++------------------------+
```

---

## Legend

| Symbol | Meaning |
|---|---|
| `+--+` / `\|` | Node boundary |
| `->` | Direction/flow |
| `v` | Branching downward |
| **Bold titles** | Main categories |

---

## How to Read This Map

1. Start at the root: **QUALITY MANAGEMENT**.
2. Four main branches radiate outward:
   - **QUALITY ACTIVITIES** (planning, assurance, control)
   - **QUALITY ATTRIBUTES** (non-functional characteristics + conflicts)
   - **STANDARDS** (product/process types + importance)
   - **PROCESS-BASED QUALITY**, **ISO 9001**, and **QUALITY CONFLICTS** form the right-side cluster
3. Two bottom nodes show **INDEPENDENT QA TEAM** and **PROBLEMS W/ STDS** as cross-cutting concerns.
4. Follow arrows and indentation to see sub-topics and key details.