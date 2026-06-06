# Software Engineering Course — Topic Priority Matrix

## Summary Table

| # | Topic | Importance | Difficulty | Exam Risk | Dependency | Study Order |
|---|-------|-----------|------------|-----------|------------|-------------|
| 1 | SE Introduction | High | Easy | Medium | None | 1 |
| 2 | Software Processes | Critical | Medium | Very High | High | 2 |
| 3 | Agile Development | Critical | Medium | Very High | Some | 3 |
| 4 | Software Testing | Critical | Medium | Very High | Some | 7 |
| 5 | Project Management | High | Easy | Medium | None | 4 |
| 6 | Risk Management | Critical | Hard | Very High | High | 5 |
| 7 | Estimation | High | Hard | High | Some | 6 |
| 8 | Project Scheduling | High | Hard | High | Some | 8 |
| 9 | Architecture Design | Critical | Hard | Very High | High | 9 |
| 10 | UI Design | Medium | Easy | Medium | None | 10 |
| 11 | Quality Management | High | Medium | High | Some | 11 |
| 12 | Testing Tools | Medium | Easy | Low | Some | 12 |

---

## Detailed Breakdown per Topic

### 1. Software Engineering Introduction

| Attribute | Value |
|-----------|-------|
| Importance | High |
| Difficulty | Easy |
| Exam Risk | Medium |
| Dependency Level | None |
| Study Order | 1 |

**Key Subtopics to Focus On:**
- Definition and scope of SE vs. programming
- Attributes of good software (maintainability, dependability, efficiency, usability)
- Process activities (specification, development, validation, evolution)
- ACM/IEEE Code of Ethics — memorize core principles

**Rationale:** Foundational but rarely tested in isolation; sets context for all other topics.

---

### 2. Software Processes

| Attribute | Value |
|-----------|-------|
| Importance | Critical |
| Difficulty | Medium |
| Exam Risk | Very High |
| Dependency Level | High |
| Study Order | 2 |

**Key Subtopics to Focus On:**
- Waterfall model: diagram, stages, when to use, strengths/weaknesses
- Incremental development: advantages over waterfall, feedback loops
- Reuse-oriented development: COTS, component-based, I&C workflow
- Requirements engineering: elicitation → analysis → specification → validation cycle
- Comparison of three process models (exam favorite)

**Rationale:** Almost always appears; students must compare and critique models. Heavily referenced by Agile and Testing topics.

---

### 3. Agile Software Development

| Attribute | Value |
|-----------|-------|
| Importance | Critical |
| Difficulty | Medium |
| Exam Risk | Very High |
| Dependency Level | Some |
| Study Order | 3 |

**Key Subtopics to Focus On:**
- 4 values of the Agile Manifesto (word them precisely)
- 12 principles — know the key ones (working software, customer collaboration, responding to change)
- XP practices (pair programming, TDD, refactoring, continuous integration, planning game)
- User stories: format, acceptance criteria, estimation (story points, velocity)
- 17 differences between agile and plan-driven (memorize for essay questions)
- When to use agile vs. plan-driven

**Rationale:** High exam weight; essay questions frequently ask for comparisons and practical application.

---

### 4. Software Testing

| Attribute | Value |
|-----------|-------|
| Importance | Critical |
| Difficulty | Medium |
| Exam Risk | Very High |
| Dependency Level | Some |
| Study Order | 7 |

**Key Subtopics to Focus On:**
- Verification vs. Validation (with examples — a classic exam question)
- Inspections vs. testing: when to use each, costs and benefits
- Three testing stages: development, release, user (alpha/beta)
- Unit → integration → system testing progression
- Path testing: statement, branch, path coverage
- Basis path testing: McCabe's cyclomatic complexity formula (V(G) = E - N + 2)

**Rationale:** Core topic tested across MCQs, short answers, and essays. Cyclomatic complexity calculations appear frequently.

---

### 5. Project Management

| Attribute | Value |
|-----------|-------|
| Importance | High |
| Difficulty | Easy |
| Exam Risk | Medium |
| Dependency Level | None |
| Study Order | 4 |

**Key Subtopics to Focus On:**
- Three types of management: project, technical, people
- Universal activities: planning, organizing, staffing, monitoring, controlling
- People management: team roles, communication, motivation theories
- Risk management as a PM activity (links to Topic 6)

**Rationale:** Foundational; provides vocabulary for Risk Management and Estimation topics.

---

### 6. Risk Management

| Attribute | Value |
|-----------|-------|
| Importance | Critical |
| Difficulty | Hard |
| Exam Risk | Very High |
| Dependency Level | High |
| Study Order | 5 |

**Key Subtopics to Focus On:**
- Risk definition and categorization (project, technical, business — with 3 examples each)
- Management paradigm: Identify → Analyze → Plan → Track → Control
- Reactive vs. proactive strategies (fire-fighting vs. prevention)
- 7 principles of risk management (memorize for essay)
- Risk Exposure formula: RE = P × C (practice calculations)
- Risk table construction and prioritization
- Mitigation, monitoring, management strategies

**Rationale:** Complex topic with high exam weight; RE calculations and essay questions on strategies are common.

---

### 7. Estimation

| Attribute | Value |
|-----------|-------|
| Importance | High |
| Difficulty | Hard |
| Exam Risk | High |
| Dependency Level | Some |
| Study Order | 6 |

**Key Subtopics to Focus On:**
- Wideband Delphi: 6 steps (plan, explain, estimate, discuss, re-estimate, aggregate)
- Function Point estimation: 5 information domain types (EI, EO, EQ, ILF, EIF)
- 14 GSCs and their rating scale (0-5)
- UFC = sum of weighted function types; VAF = 0.65 + 0.01 × ΣGSC_i; FP = UFC × VAF
- LOC-based estimation: productivity, size-effort relationship
- Cost calculation from FP

**Rationale:** Numerical calculations are high-probability exam items; Wideband Delphi steps and FP formula must be memorized.

---

### 8. Project Scheduling

| Attribute | Value |
|-----------|-------|
| Importance | High |
| Difficulty | Hard |
| Exam Risk | High |
| Dependency Level | Some |
| Study Order | 8 |

**Key Subtopics to Focus On:**
- WBS: purpose, hierarchical decomposition, work packages
- Bar charts vs. activity networks: when each is appropriate
- CPM and PERT: network construction, activity-on-node
- Forward pass (ES, EF) and backward pass (LS, LF) — practice calculations
- Float/total slack calculation: Float = LS - ES = LF - EF
- Critical path identification (zero-float activities)
- Scheduling with resource constraints

**Rationale:** Calculations (critical path, float) are high-probability exam items; network diagram construction may be required.

---

### 9. Architecture Design

| Attribute | Value |
|-----------|-------|
| Importance | Critical |
| Difficulty | Hard |
| Exam Risk | Very High |
| Dependency Level | High |
| Study Order | 9 |

**Key Subtopics to Focus On:**
- Four design concepts: abstraction, modularity, information hiding, functional independence
- Coupling types (content > common > control > stamp > data) — order from worst to best
- Cohesion types (coincidental < logical < temporal < procedural < communicational < sequential < functional) — order from worst to best
- OO design: encapsulation, inheritance, polymorphism
- ECB pattern: entity, boundary, control classes
- Architectural patterns: layered, client-server, repository, MVC
- 4+1 View Model: logical, process, development, physical + scenario

**Rationale:** Essay questions on coupling/cohesion ordering, pattern selection, and view model are very common; high exam weight.

---

### 10. UI Design

| Attribute | Value |
|-----------|-------|
| Importance | Medium |
| Difficulty | Easy |
| Exam Risk | Medium |
| Dependency Level | None |
| Study Order | 10 |

**Key Subtopics to Focus On:**
- Three Golden Rules: place user in control, minimize memory load, strive for consistency
- Four UI design models: mental model, design model, user's model, system image
- Task analysis methodology
- Interface design principles: feedback, constraints, consistency, affordances
- Design issues: response time, help, error handling

**Rationale:** Straightforward memorization; often appears as short-answer or MCQ.

---

### 11. Quality Management

| Attribute | Value |
|-----------|-------|
| Importance | High |
| Difficulty | Medium |
| Exam Risk | High |
| Dependency Level | Some |
| Study Order | 11 |

**Key Subtopics to Focus On:**
- Quality attributes: McCall's model categories (product revision, product transition, product operations)
- Quality conflicts: trade-offs between competing attributes (e.g., performance vs. maintainability)
- Process-based quality: quality of process determines quality of product
- Product standards vs. process standards
- ISO 9001: requirements, certification process, benefits

**Rationale:** Appears in MCQs and short answers; quality trade-off essays are common.

---

### 12. Testing Tools

| Attribute | Value |
|-----------|-------|
| Importance | Medium |
| Difficulty | Easy |
| Exam Risk | Low |
| Dependency Level | Some |
| Study Order | 12 |

**Key Subtopics to Focus On:**
- JMeter: test plan structure, thread groups, samplers, listeners
- Performance testing concepts: throughput, response time, scalability
- Load testing workflow in JMeter

**Rationale:** Low exam weight; primarily practical knowledge; may appear as bonus or supplementary content.

---

## Study Strategy Summary

**Phase 1 — Foundation (Days 1–3):** Topics 1, 2, 5, 3
**Phase 2 — Core Technical (Days 4–7):** Topics 6, 7, 4, 8
**Phase 3 — Design & Quality (Days 8–10):** Topics 9, 10, 11, 12
**Phase 4 — Review & Practice (Days 11–14):** Revisit all Critical topics, solve practice problems for Topics 6, 7, 8, 9
