# Final Rapid Review: 30-60 Minute Exam Prep

---

## HIGHEST-YIELD DEFINITIONS

- **Software Engineering**: All aspects of software production — specification, development, validation, evolution
- **Software Process**: Structured set of activities to develop software
- **Verification**: "Building the product RIGHT" (conforms to spec)
- **Validation**: "Building the RIGHT product" (meets user needs)
- **Testing**: Shows PRESENCE of errors, NOT absence
- **Refactoring**: Improve structure, no behavior change
- **Risk**: Uncertainty with negative impact if realized
- **Risk Exposure** = Probability × Cost
- **Coupling**: Inter-module dependency (want LOW)
- **Cohesion**: Intra-module unity (want HIGH)
- **WBS**: Deliverable-oriented hierarchy of project components
- **COCOMO**: Effort = a(KLOC)^b

---

## PROCESS MODEL DIFFERENCES TABLE

| Model | Planning | Change Handling | Requirements | Delivery | Best For |
|-------|----------|----------------|--------------|----------|----------|
| Waterfall | Full upfront | Difficult | Fixed | Single at end | Large systems, stable reqs |
| Incremental | Per increment | Easy | Emergent | Multiple | Rapid delivery needed |
| Spiral | Risk-driven | Flexible | Evolving | Iterative | High-risk projects |
| Agile | Minimal upfront | Very easy | Emergent | Frequent (2-4 wk) | Changing reqs, small-mid |

---

## CRITICAL FORMULAS

### LOC 3-Point Estimation
```
Expected LOC = (opt + 4×ml + pess) / 6
Effort (PM) = Total LOC / Productivity (LOC/pm)
Cost = Effort × Cost per PM
```

### Function Points
```
UFP = Σ(Count × Weight) for EI, EO, EQ, ILF, EIF
CAF = 0.65 + (0.01 × ΣFi)   [Fi = 0-5 each, 14 factors]
FP = UFP × CAF
```

### COCOMO Basic
```
Organic:       Effort = 2.4(KLOC)^1.05  | TDEV = 2.5(Eff)^0.38
Semi-detached: Effort = 3.0(KLOC)^1.12  | TDEV = 2.5(Eff)^0.35
Embedded:      Effort = 3.6(KLOC)^1.20  | TDEV = 2.5(Eff)^0.32
```

### Risk Exposure
```
RE = P × C
```

### CPM
```
TF = LS - ES
FF = min(ES_succ) - ES - Dur
Critical Path = longest path, zero TF
```

---

## MUST-KNOW CONCEPTS

### Agile Manifesto (4 values)
1. Individuals & interactions > processes & tools
2. Working software > comprehensive documentation
3. Customer collaboration > contract negotiation
4. Responding to change > following a plan

### XP Practices
- Story cards, test-first, pair programming, refactoring, continuous integration, collective ownership, simple design, small releases, sustainable pace, on-site customer

### Scrum Roles
- **Scrum Master**: Facilitates, protects team
- **Product Owner**: Customer voice, prioritizes backlog
- **Team**: Self-organizing, cross-functional (5-7 people)

### Scrum Events
- Sprint (2-4 wks), Sprint Planning, Daily Standup, Sprint Review, Retrospective

### 3 Golden UI Rules
1. Place user in control
2. Reduce memory load
3. Consistent interface

### 4 Core Software Activities
1. Specification
2. Design & Implementation
3. Validation
4. Evolution

### Design Principles
- Abstraction, modularity, information hiding, high cohesion, low coupling

### 3 Maintenance Types
- **Corrective**: Fix bugs
- **Adaptive**: New environments
- **Perfective**: New features

### 4 Risk Categories
- Project (schedule/resources), Product (quality), Business (viability), Technical (implementation)

### 3 COCOMO Models
- Application Composition, Early Design, Post-Architecture

### 3 COCOMO Modes
- Organic (familiar team/small), Semi-detached (mixed), Embedded (tight constraints/complex)

---

## QUICK-REFERENCE TABLES

### Testing Types
| Type | Scope | Who |
|------|-------|-----|
| Unit | Single module | Developer |
| Integration | Module interfaces | Developer |
| System | Entire system | Separate team |
| Acceptance | Requirements | Customer |
| Alpha | At dev site | Potential users |
| Beta | At user site | End users |

### Coupling (worst → best)
Content → Common → Control → Stamp → Data

### Cohesion (worst → best)
Coincidental → Logical → Temporal → Procedural → Communicational → Sequential → Functional

### 5 FP Information Domain Values
| Type | Simple | Average | Complex |
|------|--------|---------|---------|
| EI | 3 | 4 | 6 |
| EO | 4 | 5 | 7 |
| EQ | 3 | 4 | 6 |
| ILF | 7 | 10 | 15 |
| EIF | 5 | 7 | 10 |

### 14 Value Adjustment Factors (0-5 each)
F1-F14: communications, distributed processing, performance, configuration, transaction rate, online data entry, end-user efficiency, online update, complex processing, reusability, installation ease, operational ease, multiple sites, facilitate change

### CAF Range: 0.65 to 1.35

### SPICE Capability Levels
0 Incomplete → 1 Performed → 2 Managed → 3 Defined → 4 Quantitatively Managed → 5 Optimizing

### Estimate Types
- ROM: -25%/+75%
- Budget: -10%/+25%
- Definitive: -5%/+10%

### Cost Components
- Hardware/software, travel/training, effort costs (dominant), overheads

### Software Quality Attributes
Safety, Security, Reliability, Resilience, Robustness, Testability, Usability, Portability, Efficiency, Maintainability

---

## EXAM TRAPS TO AVOID

- Waterfall is NOT always bad (right for large/stable projects)
- Agile is NOT "no planning" (just incremental planning)
- Coupling wants LOW; Cohesion wants HIGH (opposite directions)
- Verification vs Validation: "right" vs "product" (remember the word order)
- Validation testing: SUCCESS = correct behavior; Defect testing: SUCCESS = finding BUG
- LOC is language-dependent; FP is language-independent
- COCOMO uses KLOC as input; FP can convert to KLOC
- Inspections are STATIC (no execution); Testing is DYNAMIC
- Most real projects use a MIX of plan-driven and agile
- Proactive risk management is preferred but reactive is sometimes necessary
- Integration testing checks INTERFACES; System testing checks entire system