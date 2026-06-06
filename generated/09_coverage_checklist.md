# Coverage Checklist — Software Engineering Course

**Purpose:** Verify complete topic coverage for exam preparation. Identify gaps.

---

## 1. SE Introduction & Fundamentals

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| What is Software Engineering | Yes | Ch1_Introduction.txt | Definition, scope, distinction from programming | High |
| Software Products (Generic vs Custom) | Yes | Ch1_Introduction.txt | Spec ownership differs | High |
| Attributes of Good Software | Yes | Ch1_Introduction.txt | Maintainability, dependability, efficiency, usability | High |
| 4 SE Process Activities | Yes | Ch1_Introduction.txt, Ch2_SW_Processes.txt | Specification, development, validation, evolution | High |
| Application Types (8 types) | Yes | Ch1_Introduction.txt | Stand-alone, embedded, batch, entertainment, etc. | High |
| SE Fundamentals | Yes | Ch1_Introduction.txt | Managed process, dependability, requirements management, reuse | High |
| Professional Ethics (ACM/IEEE) | Yes | Ch1_Introduction.txt | 8 principles: PUBLIC through SELF | High |
| Software Costs | Yes | Ch1_Introduction.txt | Maintenance > Development costs | High |
| SE vs CS vs System Engineering | Yes | Ch1_Introduction.txt | CS=theory, SE=practice, System=all aspects | Medium |

## 2. Software Process Models

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Software Process Definition | Yes | Ch2_SW_Processes.txt | Structured set of activities | High |
| Waterfall Model | Yes | Ch2_SW_Processes.txt | Sequential, plan-driven, 5 phases, inflexible | High |
| Incremental Development | Yes | Ch2_SW_Processes.txt | Concurrent, interleaved, feedback loops | High |
| Integration & Configuration | Yes | Ch2_SW_Processes.txt | Reuse-based, COTS, configure/adapt | High |
| Plan-driven vs Agile | Yes | Ch2_SW_Processes.txt, Ch3._Agile_SW_Dev.txt | Planning in advance vs incremental | High |
| Requirements Engineering Process | Yes | Ch2_SW_Processes.txt | Elicitation → Spec → Validation (iterative) | High |
| Design Process Model | Yes | Ch2_SW_Processes.txt | Inputs → Activities → Outputs | High |
| Process Activities (Real-world) | Yes | Ch2_SW_Processes.txt | Interleaved technical, collaborative, managerial | Medium |

## 3. Agile Software Development

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Agile Manifesto (4 values) | Yes | Ch3._Agile_SW_Dev.txt, 5-_Agile_Vs_Traditional.txt | Individuals, working software, collaboration, change | High |
| 5 Agile Principles | Yes | Ch3._Agile_SW_Dev.txt | Customer involvement, incremental, people, change, simplicity | High |
| Agile Applicability | Yes | Ch3._Agile_SW_Dev.txt | Product dev, custom dev within org | High |
| XP (Extreme Programming) | Yes | Ch3._Agile_SW_Dev.txt | Release cycle, practices | High |
| XP Practices | Yes | Ch3._Agile_SW_Dev.txt | Pair programming, TDD, refactoring, continuous integration | High |
| User Stories | Yes | Ch3._Agile_SW_Dev.txt | Story cards, acceptance criteria, task cards | High |
| Refactoring | Yes | Ch3._Agile_SW_Dev.txt, 5-_Agile_Vs_Traditional.txt | Continuous code improvement | High |
| Test-Driven Development | Yes | 5-_Agile_Vs_Traditional.txt | Red → Green → Refactor cycle | High |
| 17 Differences (Agile vs Traditional) | Yes | 5-_Agile_Vs_Traditional.txt | Team, requirements, iteration, testing, ownership, etc. | High |
| Sustainable Pace | Yes | Ch3._Agile_SW_Dev.txt, 5-_Agile_Vs_Traditional.txt | No overtime, marathon not sprint | Medium |

## 4. Software Testing

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Testing Goals | Yes | Ch8.Testing.txt | Validation vs defect testing | High |
| Verification vs Validation | Yes | Ch8.Testing.txt | Building right product vs building product right | High |
| Inspections vs Testing | Yes | Ch8.Testing.txt | Static vs dynamic verification | High |
| Testing Stages | Yes | Ch8.Testing.txt | Development, release, user testing | High |
| Unit/Component Testing | Yes | Ch8.Testing.txt | Individual components in isolation | High |
| Integration Testing | Yes | Ch8.Testing.txt | Testing combined components for interface defects | High |
| System Testing | Yes | Ch8.Testing.txt | Complete system against requirements | High |
| Object Class Testing | Yes | Ch8.Testing.txt | All operations, attributes, states | High |
| Automated Testing (JUnit) | Yes | Ch8.Testing.txt | Setup → Call → Assertion | High |
| Input-Output Model of Testing | Yes | Ch8.Testing.txt | Test data → System → Results | Medium |

## 5. Path Testing & Basis Path Testing

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Path Testing Objective | Yes | Path_Testing.txt | Execute every path at least once | High |
| Program Flow Graph | Yes | Path_Testing.txt | Nodes=decisions, Arcs=control flow | High |
| Basis Path Testing Steps | Yes | Path_Testing.txt | Draw graph → Find basis set → Generate tests | High |
| Cyclomatic Complexity | Yes | Path_Testing.txt | V(G) = E - N + 2P | High |
| Independent Paths | Yes | Path_Testing.txt | Binary search example (4 paths) | High |
| Flow Graph Construction | Yes | Path_Testing.txt | Binary search flow graph (14 nodes) | High |

## 6. Project Management

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Software Project Management | Yes | Ch22_Project_management.txt | Deliver on time, on budget, meets requirements | High |
| Success Criteria | Yes | Ch22_Project_management.txt | On time, within budget, meets expectations, team | High |
| Management Distinctions | Yes | Ch22_Project_management.txt | Intangible, one-off, variable processes | High |
| Universal Management Activities | Yes | Ch22_Project_management.txt | Planning, risk management, people management | High |
| Additional Activities | Yes | Ch22_Project_management.txt | Reporting, proposal writing | High |
| Factors Influencing PM | Yes | Ch22_Project_management.txt | Company size, customers, software type, culture | Medium |

## 7. Risk Management

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Risk Definition | Yes | week14_Risk_Management.txt, Ch22_Project_management.txt | Uncertainty with negative impact | High |
| Risk Categorization | Yes | week14_Risk_Management.txt, Ch22_Project_management.txt | Project, Technical, Business | High |
| Risk Sub-categories (Known/Predictable/Unpredictable) | Yes | week14_Risk_Management.txt | Three types | High |
| Business Risk Sub-types | Yes | week14_Risk_Management.txt | Market, Strategic, Sales, Management, Budget | High |
| Risk Management Process | Yes | week14_Risk_Management.txt, Ch22_Project_management.txt | Identify → Analyze → Plan → Track → Control | High |
| Risk Identification | Yes | week14_Risk_Management.txt, Chapter_28_Risk_1_1.txt | Checklist categories, generic vs product-specific | High |
| Risk Analysis/Projection | Yes | week14_Risk_Management.txt, Chapter_28_Risk_1_1.txt | Probability + Impact assessment | High |
| Risk Planning | Yes | week14_Risk_Management.txt, Ch22_Project_management.txt | Avoidance, minimization, contingency | High |
| Risk Monitoring | Yes | week14_Risk_Management.txt, Ch22_Project_management.txt | Regular assessment, progress meetings | High |
| Risk Exposure Formula | Yes | Chapter_28_Risk_1_1.txt | RE = P × C | High |
| Risk Table Construction | Yes | week14_Risk_Management.txt, Chapter_28_Risk_1_1.txt | Risk, Category, Probability, Impact, RMMM | High |
| Risk Components | Yes | Chapter_28_Risk_1_1.txt | Performance, Cost, Support, Schedule | High |
| Seven Principles | Yes | week14_Risk_Management.txt, Chapter_28_Risk_1_1.txt | Global, forward-looking, open, integrated, continuous, shared vision, teamwork | High |
| Reactive vs Proactive Strategies | Yes | week14_Risk_Management.txt, Chapter_28_Risk_1_1.txt | Fire-fighting vs formal analysis | High |
| Risk Strategies (Specific) | Yes | Ch22_Project_management.txt | Table of strategies for common risks | Medium |
| Impact Assessment Matrix | Yes | week14_Risk_Management.txt | Negligible/Marginal/Critical/Catastrophic | Medium |

## 8. Estimation

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Estimation Fundamentals | Yes | Estimation_2.txt, Estimation_Examples.txt | Size, effort, cost | High |
| LOC Estimation | Yes | SE-Week-13.txt, Estimation_Examples.txt | Lines of code, historical data | High |
| Three-Point Estimation Formula | Yes | SE-Week-13.txt, Estimation_Examples.txt | (S_opt + 4×S_ml + S_pess) / 6 | High |
| LOC-Based Estimation Examples | Yes | Estimation_Examples.txt | CAD software, login module examples | High |
| Function Point Analysis | Yes | SE-Week-13.txt, SE-Week-15_1.txt, Estimation_Examples.txt | 5 information domain types, 14 GSCs | High |
| FP Weighting Factors | Yes | SE-Week-13.txt, Estimation_Examples.txt | Simple/Average/Complex weights | High |
| UFC Calculation | Yes | SE-Week-13.txt, Estimation_Examples.txt | Σ(Count × Weight) | High |
| VAF/CAF Calculation | Yes | SE-Week-13.txt, SE-Week-15_1.txt, Estimation_Examples.txt | 0.65 + (0.01 × ΣFi) | High |
| 14 General System Characteristics | Yes | SE-Week-13.txt, SE-Week-15_1.txt, Estimation_Examples.txt | All 14 listed | High |
| FP-LOC Conversion | Yes | Estimation_Examples.txt | Language-specific factors | High |
| FP-Based Estimation Examples | Yes | Estimation_Examples.txt | Full walkthrough | High |
| Cost Components | Yes | Estimation_Examples.txt | Hardware, travel, effort, overheads | Medium |
| Costing vs Pricing | Yes | Estimation_Examples.txt | Cost ≠ price | Medium |
| Software Productivity | Yes | Estimation_Examples.txt | LOC/pm or FP/pm | Medium |

## 9. Estimation — Wideband Delphi

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Wideband Delphi Definition | Yes | Estimation_2.txt | Consensus-based estimation process | High |
| 6 Steps | Yes | Estimation_2.txt | Choose team, Kickoff, Prepare, Session, Assemble, Review | High |
| Convergence Process | Yes | Estimation_2.txt | Multiple rounds until estimates converge | High |
| Case Study (Chat App) | Yes | Estimation_2.txt | 3 members, 5 tasks, 3 rounds | High |
| Estimation Line Plot | Yes | Estimation_2.txt | Visual convergence diagram | High |
| Effort Estimation Sheet | Yes | Estimation_2.txt | Best, Worst, Average cases | High |

## 10. Project Scheduling

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Scheduling Process | Yes | Project_Scheduling.txt | Activities → Dependencies → Resources → Assign → Network/Bar Charts | High |
| Scheduling Problems | Yes | Project_Scheduling.txt | Productivity ≠ proportional, adding people to late project | High |
| Bar Charts (Gantt) | Yes | Project_Scheduling.txt | Schedule against calendar time | High |
| Activity Networks (AOA/AON) | Yes | Project_Scheduling.txt | Activities as arrows/nodes | High |
| CPM/PERT | Yes | Project_Scheduling.txt | Critical Path Method, Programme Evaluation Review Technique | High |
| Critical Path Analysis | Yes | Project_Scheduling.txt | Longest path through network | High |
| Forward Pass (ES/EF) | Yes | Project_Scheduling.txt | Early start/finish calculations | High |
| Backward Pass (LS/LF) | Yes | Project_Scheduling.txt | Late start/finish calculations | High |
| Total Float | Yes | Project_Scheduling.txt | LF - EF = LS - ES | High |
| Free Float | Yes | Project_Scheduling.txt | min(ES_successor) - ES - Duration | High |
| Network Rules | Yes | Project_Scheduling.txt | Left to right, no loops, IDs | High |
| Worked Examples | Yes | Project_Scheduling.txt | 8-activity and 6-activity examples | High |

## 11. Work Breakdown Structure (WBS)

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| WBS Definition | Yes | week_5.txt | Deliverable-oriented hierarchical decomposition | High |
| WBS Concepts | Yes | week_5.txt | Not constrained by sequence, lowest level = work packages | High |
| WBS Goals | Yes | week_5.txt | Visibility, correlation, ownership | High |
| When to Develop WBS | Yes | week_5.txt | After scope finalized, before project starts | High |
| WBS Benefits | Yes | week_5.txt | Cost/time/performance evaluation, responsibility assignment | High |
| Steps to Build WBS | Yes | week_5.txt | 9 steps from charter to assigning managers | High |
| WBS Formats | Yes | week_5.txt | Outline (indented) and Graphical Tree | High |
| WBS Pitfalls | Yes | week_5.txt | 5 common pitfalls | High |
| WBS Dictionary | Yes | week_5.txt | Companion document describing each element | High |
| WBS Levels | Yes | week_5.txt | CWBS (2-3 levels) vs PWBS (full) | High |
| Three Types of Work | Yes | week_5.txt | Product, Integration, Support | Medium |

## 12. Architecture Design

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Design Definition | Yes | Architecture_design.txt | Creative process, blueprint from requirements | High |
| Characteristics of Good Design | Yes | Architecture_design.txt | Firmness, Commodity, Delight | High |
| Design Process | Yes | Architecture_design.txt | Understand problem → Identify solutions → Abstraction | High |
| Design Model Elements | Yes | Architecture_design.txt | Data/class, Architectural, Interface, Component-level, Deployment | High |
| Design Goals | Yes | Architecture_design.txt | Implement requirements, readable, complete picture | High |
| Good vs Bad Design | Yes | Architecture_design.txt | Vague vs clear, fragile vs maintainable | High |
| Abstraction | Yes | Architecture_design.txt | Extract essential, ignore remainder | High |
| Architecture | Yes | Architecture_design.txt | Overall structure, structural/extra-functional properties | High |
| Design Patterns | Yes | Architecture_design.txt | Common solution to common problem, architectural/design/coding | High |
| Modularity | Yes | Architecture_design.txt | Divide and conquer, separately named components | High |
| Information Hiding | Yes | Architecture_design.txt | Algorithms and data inaccessible to other modules | High |
| Functional Independence | Yes | Architecture_design.txt | Single-minded function, low interaction | High |
| Coupling (5 types) | Yes | Architecture_design.txt | Content → Common → Control → Stamp → Data (worst to best) | High |
| Cohesion (7 types) | Yes | Architecture_design.txt | Functional → Sequential → Communicational → Procedural → Temporal → Logical → Coincidental | High |
| Refinement vs Refactoring | Yes | Architecture_design.txt | Elaboration vs restructuring | High |
| OO Design Concepts | Yes | Architecture_design.txt | Module, Abstraction, Encapsulation, Inheritance, Association | High |
| Design Classes (ECB) | Yes | Architecture_design.txt | Boundary, Entity, Control | High |
| 4+1 View Model | Yes | Architecture_design.txt | Logical, Development, Process, Physical + Scenarios | High |
| Architectural Patterns | Yes | Architecture_design.txt | Layered, Client-server, Repository, MVC | Medium |

## 13. UI Design

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Interface Design Introduction | Yes | UI_design_1.txt, se361_Chapter_11.txt | Easy to learn, use, understand | High |
| Typical Design Errors | Yes | se361_Chapter_11.txt | Inconsistency, memorization, no help | High |
| Golden Rules (3 principles) | Yes | UI_design_1.txt, se361_Chapter_11.txt | Control, Memory load, Consistency | High |
| Place User in Control | Yes | UI_design_1.txt, se361_Chapter_11.txt | Modes, flexible, interruptible, hide internals | High |
| Reduce Memory Load | Yes | UI_design_1.txt, se361_Chapter_11.txt | Defaults, shortcuts, real-world metaphors | High |
| Consistent Interface | Yes | UI_design_1.txt, se361_Chapter_11.txt | Context, family consistency, don't break expectations | High |
| UI Design Models (4) | Yes | UI_design_1.txt, se361_Chapter_11.txt | User, Design, Mental, Implementation | High |
| Effective Design | Yes | UI_design_1.txt | Mental model = Implementation model | High |
| Task Analysis | Yes | UI_design_2.txt, se361_Chapter_11.txt | What work, tasks, objects, sequence, workflow | High |
| Interface Design Steps | Yes | UI_design_2.txt, se361_Chapter_11.txt | Define objects/actions, events, states, interpretation | High |
| Design Issues | Yes | UI_design_2.txt, se361_Chapter_11.txt | Response time, Help, Error handling, Menu labeling | High |
| Response Time | Yes | UI_design_2.txt | Length and variability | High |
| Help Facilities | Yes | UI_design_2.txt | Availability, method, presentation, return | High |
| Error Handling | Yes | UI_design_2.txt | Explanatory, remedies, color coding | High |
| Revised Design Principles | Yes | UI_design_2.txt, se361_Chapter_11.txt | Anticipation, Communication, Consistency, Efficiency, Focus, Fitt's Law, Latency | High |
| Aesthetic Design | Yes | se361_Chapter_11.txt | White space, content emphasis, layout, geographic grouping | High |
| Web App Guidelines | Yes | UI_design_2.txt | Learnability, integrity, readability, track state, visible navigation | Medium |
| Interface Design Evolution | Yes | UI_design_2.txt | Iterative cycle: design → prototype → evaluate → modify | Medium |

## 14. Quality Management

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| Quality Management Activities | Yes | SE-Week-15_1.txt | Independent check on development | High |
| Quality Team Independence | Yes | SE-Week-15_1.txt | Must be independent from dev team | High |
| Software Quality Attributes | Yes | SE-Week-15_1.txt | Safety, Security, Reliability, etc. (15 attributes) | High |
| Quality Conflicts | Yes | SE-Week-15_1.txt | Cannot optimize all attributes, trade-offs | High |
| Process-Based Quality | Yes | SE-Week-15_1.txt | Define process → Develop → Assess → Improve/Standardize | High |
| Importance of Standards | Yes | SE-Week-15_1.txt | Best practice, framework, continuity | High |
| Product Standards | Yes | SE-Week-15_1.txt | Documentation, coding, project plan format | High |
| Process Standards | Yes | SE-Week-15_1.txt | Design review, code submission, change control | High |
| ISO 9001 | Yes | SE-Week-15_1.txt | Quality management system standard | High |
| ISO 9001 Certification | Yes | SE-Week-15_1.txt | Quality manual, external body certification | High |

## 15. Testing Tools (JMeter)

| Topic | Covered? | Source File(s) | Key Points | Confidence |
|-------|----------|----------------|------------|------------|
| JMeter Installation | Yes | SE-Week-13.txt | Java install, JMeter download, setup | High |
| Creating Test Plans | Yes | SE-Week-13.txt | Test plan configuration | High |
| HTTP Request Samplers | Yes | SE-Week-13.txt | HomePage, MAIN requests | High |
| Listeners (View Results, Graph) | Yes | SE-Week-13.txt | Table and graphical results | High |
| Load Test Execution | Yes | SE-Week-13.txt | Running tests, interpreting results | High |
| Performance Metrics | Yes | SE-Week-13.txt | Throughput, latency, sample time | Medium |

---

## Summary

| Major Topic | Coverage | Confidence |
|-------------|----------|------------|
| 1. SE Introduction | Complete | High |
| 2. Software Processes | Complete | High |
| 3. Agile Development | Complete | High |
| 4. Software Testing | Complete | High |
| 5. Path/Basis Path Testing | Complete | High |
| 6. Project Management | Complete | High |
| 7. Risk Management | Complete | High |
| 8. Estimation (LOC/FP) | Complete | High |
| 9. Wideband Delphi | Complete | High |
| 10. Project Scheduling | Complete | High |
| 11. WBS | Complete | High |
| 12. Architecture Design | Complete | High |
| 13. UI Design | Complete | High |
| 14. Quality Management | Complete | High |
| 15. Testing Tools (JMeter) | Complete | Medium |

**Overall Coverage: 100%** — All topics from the course have extracted content and review notes.

**Areas of Medium Confidence (may need extra review):**
- JMeter practical details (tool-specific)
- Some architectural patterns (Layered, Client-server, Repository, MVC — covered but not deeply)
- ISO 9001 certification specifics
- Some risk strategies tables

**Source Files Used:**
1. Ch1_Introduction.txt
2. Ch2_SW_Processes.txt
3. Ch3._Agile_SW_Dev.txt
4. Ch8.Testing.txt
5. Path_Testing.txt
6. Ch22_Project_management.txt
7. Chapter_28_Risk_1_1.txt
8. week14_Risk_Management.txt
9. week_5.txt
10. Estimation_2.txt
11. Estimation_Examples.txt
12. Project_Scheduling.txt
13. Architecture_design.txt
14. UI_design_1.txt
15. UI_design_2.txt
16. se361_Chapter_11.txt
17. SE-Week-13.txt
18. SE-Week-15_1.txt
19. 5-_Agile_Vs_Traditional_17_differences.txt
