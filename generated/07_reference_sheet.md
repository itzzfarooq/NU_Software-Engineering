# Exam Reference Sheet: Rapid-Lookup Format

---

## KEY DEFINITIONS

| Term | Definition |
|------|------------|
| **Software Engineering** | Engineering discipline concerned with ALL aspects of software production (specification through maintenance) |
| **Software Process** | Structured set of activities required to develop a software system |
| **Software Process Model** | Abstract representation of a process from a particular perspective |
| **Verification** | "Are we building the product RIGHT?" -- software conforms to specification |
| **Validation** | "Are we building the RIGHT product?" -- software does what user requires |
| **Software Testing** | Executing a program with artificial data to find errors (shows PRESENCE not ABSENCE) |
| **Refactoring** | Restructuring code to improve structure WITHOUT changing external behavior |
| **Risk** | An uncertainty that, if realized, has a negative impact on the project |
| **Risk Exposure (RE)** | RE = P x C (Probability x Cost/Impact) |
| **Coupling** | Measure of interdependence BETWEEN modules (want LOW) |
| **Cohesion** | Measure of relatedness WITHIN a module (want HIGH) |
| **WBS** | Deliverable-oriented hierarchy decomposing project into manageable components |
| **Work Package** | Group of related tasks at the same level within a WBS |
| **COCOMO** | Constructive Cost Model -- algorithmic cost estimation Effort = a(KLOC)^b |
| **Function Point** | Size measure based on 5 information domain values (EI, EO, EQ, ILF, EIF) |

---

## PROCESS MODEL SUMMARIES

### Waterfall Model
```
Requirements Definition
       |
       v
System & Software Design
       |
       v
Implementation & Unit Testing
       |
       v
Integration & System Testing
       |
       v
Operation & Maintenance
```
- Plan-driven, sequential phases
- Best for: well-understood requirements, large systems engineering
- Problem: inflexible, hard to accommodate change

### Incremental Development
```
Outline Description --→ Specification --→ Development --→ Validation
                                        ↕
                              Initial → Intermediate → Final
                              Version    Versions      Version
```
- Specification, development, validation interleaved
- Benefits: reduced cost of change, easier customer feedback, faster delivery
- Problems: process not visible, structure degrades without refactoring

### Integration & Configuration (Reuse-oriented)
```
Requirements Specification → Software Discovery/Evaluation → Requirements Refinement
  → Configure Application System → Adapt Components → Integrate System
```
- Based on reusing existing components (COTS, web services, object libraries)
- Advantages: reduced costs, faster delivery
- Disadvantages: requirements compromises, loss of control over evolution

### Spiral Model
- Iterative, risk-driven
- Each iteration: Identify objectives → Evaluate alternatives → Develop/verify → Plan next

---

## AGILE VS PLAN-DRIVEN COMPARISON

| Aspect | Plan-Driven | Agile |
|--------|-------------|-------|
| Planning | All planned upfront | Incremental |
| Requirements | Fixed, defined early | Emergent, changeable |
| Delivery | Single at end | Frequent (2-4 week iterations) |
| Customer involvement | Beginning and end | Continuous |
| Documentation | Heavy | Minimal |
| Change handling | Difficult/costly | Easy/expected |
| Team | Defined roles, hierarchical | Self-organizing, cross-functional |
| Best for | Safety-critical, large systems, stable requirements | Small-medium products, changing requirements |

---

## AGILE MANIFESTO (4 VALUES)

1. **Individuals & Interactions** over processes and tools
2. **Working Software** over comprehensive documentation
3. **Customer Collaboration** over contract negotiation
4. **Responding to Change** over following a plan

### Agile Principles (5 Key)
- Customer involvement
- Incremental delivery
- People not process
- Embrace change
- Maintain simplicity

### Extreme Programming (XP) Practices
- Incremental planning (story cards)
- Small releases
- Simple design
- Test-first development
- Refactoring
- Pair programming
- Collective ownership
- Continuous integration
- Sustainable pace
- On-site customer

### Scrum
- **Roles**: Scrum Master (facilitates), Product Owner (represents customer), Team (self-organizing)
- **Artifacts**: Product Backlog, Sprint Backlog, Burndown Chart
- **Events**: Sprint (2-4 weeks), Sprint Planning, Daily Standup, Sprint Review, Retrospective
- **Scrum ≠ XP**: Scrum manages process, XP provides technical practices

---

## TESTING STAGES

```
Module/Unit Testing → Integration Testing → System Testing → Acceptance Testing
(individual modules) (interactions)        (system as whole) (requirements)
```

### Testing Types
| Type | What | Who | Goal |
|------|------|-----|------|
| Unit Testing | Individual components | Developers | Defect testing |
| Integration Testing | Component interactions | Developers | Interface defects |
| System Testing | Entire system | Separate team | Validation |
| Acceptance Testing | Against requirements | Customer/Users | Acceptance |
| Release Testing | Release candidate | Separate team | Validation (black box) |
| User Testing | Real-world usage | End users | Confidence |
| Alpha Testing | At developer site | Potential users | Early feedback |
| Beta Testing | At user site | Users | Real-world validation |

### Black Box vs White Box
| Black Box | White Box |
|-----------|-----------|
| No code knowledge | Full code knowledge |
| Based on requirements/spec | Based on code structure |
| Input-output testing | Path, branch, condition testing |
| Equivalence partitioning, boundary value | Basis path testing |
| Tester independent | Usually developer |

---

## METRICS & FORMULAS

### LOC Three-Point Estimation
```
Expected LOC = (S_opt + 4 × S_most_likely + S_pess) / 6
```
- S_opt = optimistic, S_most_likely = most likely, S_pess = pessimistic
- Effort (person-months) = Total Expected LOC / Productivity (LOC/pm)
- Cost = Effort × Cost per person-month

### Function Point (FP) Calculation
```
UFP = Σ(Count × Weight) for: EI(3/4/6), EO(4/5/7), EQ(3/4/6), ILF(7/10/15), EIF(5/7/10)
CAF = 0.65 + (0.01 × ΣFi)    [Fi = 0-5, each of 14 factors; CAF range: 0.65-1.35]
FP = UFP × CAF
```
- **EI** = External Inputs, **EO** = External Outputs, **EQ** = External Inquiries
- **ILF** = Internal Logical Files, **EIF** = External Interface Files
- 14 Value Adjustment Factors (F1-F14) rated 0-5 each

### COCOMO Basic Model
```
Organic:        Effort = 2.4(KLOC)^1.05    TDEV = 2.5(Effort)^0.38
Semi-detached:  Effort = 3.0(KLOC)^1.12    TDEV = 2.5(Effort)^0.35
Embedded:       Effort = 3.6(KLOC)^1.20    TDEV = 2.5(Effort)^0.32
Avg Staff = Effort / TDEV
Cost = Effort × Cost per person-month
```

### Risk Exposure (RE)
```
RE = P × C
```
- P = Probability of risk occurrence
- C = Cost/impact if risk occurs

### CPM (Critical Path Method)
```
Total Float (TF) = LS - ES or LF - EF
Free Float (FF) = MIN(ES_successor) - ES_activity - Duration_activity
```
- ES = Early Start, EF = Early Finish, LS = Late Start, LF = Late Finish
- Critical Path = longest path through network (zero slack/float)

---

## KEY METHODOLOGIES

| Methodology | Focus | Key Practices |
|-------------|-------|---------------|
| **Waterfall** | Sequential phases | Requirements → Design → Implementation → Testing → Maintenance |
| **Incremental** | Interleaved activities | Multiple delivery increments |
| **XP** | Technical agile practices | TDD, pair programming, refactoring, continuous integration |
| **Scrum** | Project management | Sprints, daily standups, burndown charts, retrospectives |
| **Spiral** | Risk management | Iterative cycles with risk analysis |
| **RUP** | Unified Process | Phases: Inception, Elaboration, Construction, Transition |

---

## DESIGN CONCEPTS

### Quality Attributes of Good Software
- Maintainability, Dependability & Security, Efficiency, Acceptability

### Design Principles
1. Separation of concerns
2. Modularity
3. Abstraction
4. Information hiding
5. Reuse
6. High cohesion, low coupling

### Coupling Types (worst → best)
Content → Common → Control → Stamp → Data

### Cohesion Types (worst → best)
Coincidental → Logical → Temporal → Procedural → Communicational → Sequential → Functional

### Architectural Patterns
| Pattern | Description |
|---------|-------------|
| Layered | Hierarchical layers, each using services of layer below |
| Client-Server | Multiple clients request services from servers |
| MVC | Model (data), View (display), Controller (input) |
| Pipe-and-Filter | Sequential data processing through filters connected by pipes |
| Repository | Central data store shared by components |
| Blackboard | Central knowledge source with controller |
| Broker | Mediator between clients and servers |
| Microservices | Loosely coupled, independently deployable services |

### 4+1 Architectural View Model
- **Logical view** -- end users (classes, interactions)
- **Development view** -- programmers (packaging, layering)
- **Process view** -- integrators (performance, concurrency)
- **Physical view** -- system engineers (topology, deployment)
- **Scenarios** (center) -- use cases tying views together

---

## UI DESIGN GOLDEN RULES

1. **Place user in control** -- flexible interaction, undoable actions, customizable
2. **Reduce user's memory load** -- meaningful defaults, intuitive shortcuts, progressive disclosure
3. **Make interface consistent** -- across applications, predictable interactions

### UI Design Models
- **User model** -- profile of end users
- **Design model** -- design realization of user model
- **Mental model** -- user's perception of system
- **Implementation model** -- interface look & feel

---

## SOFTWARE PROCESS ACTIVITIES

```
Software Specification → Software Design & Implementation → Software Validation → Software Evolution
```

### Requirements Engineering
```
Elicitation & Analysis → Specification → Validation
```

### Design Process
```
Architectural Design → Interface Design → Component Design → Database Design
```

### Types of Maintenance
| Type | Purpose |
|------|---------|
| Corrective | Fixing bugs |
| Adaptive | Adapting to new environments |
| Perfective | Adding new features |

### Software Process Improvement (SPICE)
Capability levels: 0(Incomplete) → 1(Performed) → 2(Managed) → 3(Defined) → 4(Quantitatively managed) → 5(Optimizing)

---

## PROJECT MANAGEMENT

### Estimation Techniques
- Analogy, Expert Judgment, Parametric, Bottom-up, Three-point
- Estimate types: ROM (-25%/+75%), Budget (-10%/+25%), Definitive (-5%/+10%)

### Wideband Delphi Process
1. Choose team (3-7 members + moderator)
2. Kickoff meeting (brainstorm assumptions)
3. Individual preparation (independent estimates)
4. Estimation session (multiple rounds until convergence)
5. Assemble tasks
6. Review results

### Risk Management Steps
1. **Risk Identification** -- identify project, product, business risks
2. **Risk Analysis** -- assess probability and consequences
3. **Risk Planning** -- avoidance, minimization, contingency plans
4. **Risk Monitoring** -- track risks throughout project

### Risk Categories
- **Project risks** -- affect schedule/resources
- **Product risks** -- affect quality/performance
- **Business risks** -- affect organization

### CPM Scheduling Terms
- ES (Early Start), EF (Early Finish), LS (Late Start), LF (Late Finish)
- Total Float = LS - ES (delay without affecting project end)
- Critical Path = path with zero total float
- Free Float = delay without affecting successor's early start

---

## VERIFICATION & VALIDATION

- **Static V&V**: Inspections, reviews, walkthroughs (no code execution)
- **Dynamic V&V**: Testing (executing code with test data)
- Inspections can check conformance to specification but NOT conformance to customer's real requirements
- Inspections cannot check non-functional characteristics (performance, usability)

---

## COMMON EXAM FORMULAS (QUICK REFERENCE)

```
LOC_expected    = (opt + 4*ml + pess) / 6
FP              = UFP × [0.65 + 0.01 × ΣFi]
Effort (COCOMO) = a × (KLOC)^b
TDEV (COCOMO)   = c × (Effort)^d
RE              = P × C
TF              = LS - ES
FF              = min(ES_succ) - ES - Dur
```