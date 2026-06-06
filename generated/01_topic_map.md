# Software Engineering Course — Topic Map

## 1. Software Engineering Introduction

- 1.1 What is Software Engineering — Definition, scope, and distinction from programming
- 1.2 Software Products — Generic vs. custom/bespoke products, product specification
- 1.3 Attributes of Good Software — Maintainability, dependability, efficiency, usability, acceptability
- 1.4 Process Activities — Specification, development, validation, evolution
- 1.5 Application Types — Stand-alone, interactive, embedded,批处理, entertainment, systems
- 1.6 SE Fundamentals — Generic engineering principles applied to software
- 1.7 Professional Ethics — ACM/IEEE Code of Ethics, responsibilities to public, clients, profession

## 2. Software Processes

- 2.1 Waterfall Model — Plan-driven, sequential stages, documentation-heavy, strengths/weaknesses
- 2.2 Incremental Development — Iterative delivery, overlapping activities, customer feedback
- 2.3 Reuse-Oriented / Integration & Configuration — COTS-based development, component assembly
- 2.4 Process Activities — Real-world activities: specification, design, validation, evolution
- 2.5 Requirements Engineering — Elicitation, analysis, specification, validation, management
- 2.6 Design Process — Architectural design, interface design, component design, database design

## 3. Agile Software Development

- 3.1 Agile Manifesto — 4 values (individuals, working software, customer collaboration, responding to change)
- 3.2 Agile Principles — 12 principles underlying the manifesto
- 3.3 Plan-Driven vs. Agile — When to use each; hybrid approaches
- 3.4 XP (Extreme Programming) Practices — Pair programming, TDD, continuous integration, refactoring
- 3.5 User Stories — Story cards, acceptance criteria, story points, planning poker
- 3.6 Refactoring — Improving code structure without changing behavior
- 3.7 Test-Driven Development (TDD) — Red-green-refactor cycle
- 3.8 17 Differences Between Agile and Plan-Driven — Comprehensive comparison table

## 4. Software Testing

- 4.1 Testing Goals — Finding defects, building confidence, ensuring requirements met
- 4.2 Verification vs. Validation — Verification (are we building the product right?) vs. Validation (are we building the right product?)
- 4.3 Inspections vs. Testing — Static analysis (reviews, inspections) vs. dynamic execution
- 4.4 Testing Stages — Development testing, release testing, user testing (alpha/beta)
- 4.5 Unit / Component Testing — Testing individual modules in isolation
- 4.6 Integration Testing — Testing combined components for interface defects
- 4.7 System Testing — Testing complete system against requirements
- 4.8 Path Testing — Statement, branch, path coverage
- 4.9 Basis Path Testing — McCabe's cyclomatic complexity, independent path calculation

## 5. Project Management

- 5.1 Success Criteria — On time, on budget, meets requirements, stakeholder satisfaction
- 5.2 Management Distinctions — Project management vs. technical management vs. people management
- 5.3 Universal Management Activities — Planning, organizing, staffing, monitoring, controlling
- 5.4 Risk Management Process — Identification, analysis, planning, tracking
- 5.5 Risk Classification — Project, technical, and business risks
- 5.6 People Management — Team selection, motivation, communication, leadership styles

## 6. Risk Management

- 6.1 Risk Definition — Conditions or events with uncertain outcomes that affect project objectives
- 6.2 Risk Categorization — Project risks (schedule/budget), technical risks (technology/complexity), business risks (market/viability)
- 6.3 Management Paradigm — Identify → Analyze → Plan → Track → Control
- 6.4 Reactive vs. Proactive Strategies — Fire-fighting vs. upfront prevention
- 6.5 7 Principles of Risk Management — Early, continuous, transparent, structured, flexible, integrated, communication
- 6.6 Risk Exposure — RE = P × C (Probability × Cost/consequence)
- 6.7 Risk Table — Ranking risks by exposure for prioritized mitigation
- 6.8 Mitigation / Monitoring / Management — Three-tier response strategy

## 7. Estimation

- 7.1 Project Estimation Fundamentals — Decomposition, historical data, expert judgment
- 7.2 Wideband Delphi Technique — 6-step consensus-based estimation (plan, explain, estimate, discuss, re-estimate, aggregate)
- 7.3 LOC Estimation — Lines of Code based sizing and productivity metrics
- 7.4 Function Point Estimation — 5 information domain types (EI, EO, EQ, ILF, EIF)
- 7.5 14 General System Characteristics (GSCs) — Data communications, distributed processing, performance, etc.
- 7.6 UFC and VAF Formulas — Unadjusted Function Point count and Value Adjustment Factor
- 7.7 Cost Calculation — FP-based effort and cost estimation

## 8. Project Scheduling

- 8.1 Work Breakdown Structure (WBS) — Hierarchical decomposition of project scope
- 8.2 Scheduling Process — Identifying tasks, ordering dependencies, estimating durations, resource allocation
- 8.3 Bar Charts (Gantt Charts) — Visual timeline with dependencies and milestones
- 8.4 Activity Networks — PERT/CPM network diagrams
- 8.5 CPM / PERT — Critical Path Method and Program Evaluation and Review Technique
- 8.6 Critical Path Analysis — Identifying longest path through network
- 8.7 Forward and Backward Pass — Earliest start/finish and latest start/finish calculation
- 8.8 Float / Slack Calculation — Total float and free float; scheduling flexibility

## 9. Architecture Design

- 9.1 Design Concepts — Abstraction, modularity, information hiding, functional independence
- 9.2 Coupling — Five types (content, common, control, stamp, data) from tightest to loosest
- 9.3 Cohesion — Seven types (coincidental, logical, temporal, procedural, communicational, sequential, functional)
- 9.4 Refinement vs. Refactoring — Top-down refinement vs. code restructuring
- 9.5 OO Design — Encapsulation, inheritance, polymorphism, design with classes
- 9.6 Design Classes — Entity, boundary, control classes (ECB pattern)
- 9.7 Architectural Patterns — Layered, client-server, repository, MVC
- 9.8 4+1 View Model — Logical, process, development, physical views + scenario use case

## 10. UI Design

- 10.1 Golden Rules — Three principles: Place user in control, Minimize user memory load, Strive for consistency
- 10.2 UI Design Models — Mental model, design model, user's model, system image
- 10.3 Task Analysis — Understanding user tasks and workflows
- 10.4 Interface Design Steps — Task analysis, content design, layout design, interaction design
- 10.5 Design Issues — Response time, help systems, error handling, internationalization
- 10.6 Interface Design Principles — Feedback, constraints, consistency, affordances
- 10.7 Aesthetic Design — Visual hierarchy, alignment, proximity, whitespace, typography

## 11. Quality Management

- 11.1 Quality Attributes — Reliability, efficiency, integrity, usability, maintainability, flexibility, testability, portability, reusability, interoperability
- 11.2 Quality Conflicts — Trade-offs between competing quality attributes
- 11.3 Process-Based Quality — Quality achieved through quality processes (not just inspection)
- 11.4 Standards — Product standards (documentation, coding) vs. process standards (development lifecycle)
- 11.5 ISO 9001 — Quality management system standard; requirements for certification

## 12. Testing Tools

- 12.1 JMeter Load Testing — Creating test plans, thread groups, samplers, listeners
- 12.2 Performance Testing — Throughput, response time, scalability testing with JMeter
