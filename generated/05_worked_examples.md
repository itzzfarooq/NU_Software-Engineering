# Worked Examples & Reasoning Patterns — Software Engineering

---

## 1. REQUIREMENTS ANALYSIS

### Example 1: Analyzing Requirements from a Scenario

**Scenario:** A hospital wants a patient management system. The system must handle patient records, appointment scheduling, billing, and generate reports for insurance claims. The hospital has 200 staff across 3 departments, uses an existing lab system, and must comply with healthcare privacy regulations.

**Step 1: Identify stakeholder types**
- Primary users: Doctors, nurses, receptionists
- Secondary users: Billing department, hospital administrators
- External systems: Lab system, insurance providers
- Regulatory bodies: Healthcare privacy authority

**Step 2: Classify requirements**
- Functional: Patient record CRUD, appointment scheduling, billing, insurance reports
- Non-functional: Privacy compliance, response time (<2s for record lookup), availability (99.9%), usability for non-technical staff
- Constraints: Must integrate with existing lab system, must comply with privacy regulations

**Step 3: Identify risks in requirements**
- Integration risk: Lab system API may not be well-documented
- Regulatory risk: Privacy requirements may change
- Stakeholder risk: Different departments may have conflicting needs

**Reasoning:** Requirements analysis is iterative. The requirements engineering process follows: elicitation → specification → validation (with feedback loops). Always separate functional from non-functional, and identify constraints early.

---

### Example 2: Distinguishing Functional from Non-Functional Requirements

**Scenario:** An e-commerce website must:
(a) Allow users to search for products
(b) Display search results within 2 seconds
(c) Support 10,000 concurrent users
(d) Accept credit card payments
(e) Have a consistent color scheme across pages

**Analysis:**
| Requirement | Type | Reasoning |
|---|---|---|
| (a) Product search | Functional | Describes WHAT the system does |
| (b) Results within 2s | Non-functional (performance) | Describes HOW WELL it performs |
| (c) 10,000 concurrent users | Non-functional (scalability) | Describes capacity constraint |
| (d) Accept payments | Functional | Describes a system capability |
| (e) Consistent color scheme | Non-functional (usability) | Describes quality attribute |

**Key Pattern:** If it describes a behavior or capability → functional. If it describes a quality, constraint, or performance characteristic → non-functional.

---

## 2. DESIGN DECISIONS

### Example 3: Choosing Architecture Pattern

**Scenario:** You need to design:
(a) A word processor
(b) A traffic control system
(c) A data mining application that processes large datasets

**Analysis:**

| System | Pattern | Reasoning |
|---|---|---|
| (a) Word processor | MVC | Separate data model, view (document display), controller (user input) for flexibility |
| (b) Traffic control | Layered + Real-time | Safety-critical needs structured layers: hardware control → processing → monitoring → UI |
| (c) Data mining | Repository/Pipeline | Large datasets need centralized data store; processing is sequential pipeline |

**Reasoning:** Architecture pattern selection depends on: (1) system type and domain, (2) quality attributes needed (performance, safety, flexibility), (3) team structure, and (4) integration requirements.

---

### Example 4: Coupling/Cohesion Tradeoff Analysis

**Scenario:** A system has two modules:
- Module A: Calculates tax, generates invoice, sends email notification
- Module B: Reads customer database, passes entire Customer object to Module A

**Analysis:**

**Module A cohesion:** Temporal cohesion (operations grouped because they run together during checkout) → should be refactored into three separate modules (TaxCalculator, InvoiceGenerator, NotificationService) for functional cohesion.

**Module B → Module A coupling:** Stamp coupling (passing a composite Customer object when only tax-relevant fields are needed). Fix: pass only the required data items (customer address, purchase amount) → data coupling.

**Before (Bad):**
```
Module A: { calculateTax(), generateInvoice(), sendEmail() }
Module B passes: CustomerObject (with name, address, history, preferences...)
```

**After (Good):**
```
TaxCalculator: { calculateTax(amount, address) }  ← Functional cohesion
InvoiceGenerator: { generateInvoice(items, tax) }  ← Functional cohesion
NotificationService: { sendEmail(email, invoice) }  ← Functional cohesion

Module B passes: (amount, address, email)  ← Data coupling
```

**Key Principle:** Aim for high cohesion (single responsibility) and low coupling (simple data parameters).

---

## 3. PROCESS SELECTION

### Example 5: When to Use Which Process

**Scenario Match:**

| Scenario | Process | Why |
|---|---|---|
| Safety-critical avionics system with regulatory requirements | Waterfall | Requirements fixed upfront, complete specification needed, regulatory audit trail |
| Startup building a social media app | Agile/XP | Rapidly changing requirements, need for frequent delivery, customer feedback critical |
| Government contract requiring formal documentation | Plan-driven incremental | Documentation mandatory, but some iteration within phases is possible |
| Building a system from existing CRM + ERP components | Reuse-oriented | COTS components available, system can be assembled and configured |
| Large multi-site enterprise system | Plan-driven with incremental | Coordination across sites needs planning, but incremental delivery adds value |
| Medical device software | Waterfall | Safety-critical, regulatory compliance, requirements cannot change during development |

**Reasoning Pattern:**
1. Is the system safety-critical or regulated? → Waterfall/Plan-driven
2. Are requirements uncertain and changing? → Agile/Incremental
3. Can existing components be reused? → Integration & Configuration
4. Is the project large and distributed? → Plan-driven (for coordination)
5. Is rapid time-to-market critical? → Agile/XP

---

### Example 6: Hybrid Process Decision

**Scenario:** A bank wants to develop a new mobile banking app. Regulations require formal documentation and audit trails. But customer expectations demand rapid feature delivery.

**Solution:** Hybrid approach:
- Use plan-driven for core banking functions (regulatory compliance, security)
- Use agile sprints for UI/UX features (rapid iteration, user feedback)
- Maintain documentation standards throughout (satisfies both approaches)
- Use incremental delivery: core features first, then enhancements

**Reasoning:** Pure agile fails regulatory needs; pure waterfall fails speed needs. Hybrid combines strengths.

---

## 4. TESTING STRATEGIES

### Example 7: Unit Test Case Design

**Scenario:** A function `calculateDiscount(customerType, purchaseAmount)` returns:
- "premium" customers: 20% discount if purchase > $100, else 10%
- "regular" customers: 5% discount if purchase > $100, else 0%
- Invalid customerType: return -1 (error)

**Test Cases:**

| Test ID | Input | Expected Output | Rationale |
|---|---|---|---|
| TC1 | ("premium", 150) | 20% | Premium + high amount |
| TC2 | ("premium", 50) | 10% | Premium + low amount |
| TC3 | ("regular", 150) | 5% | Regular + high amount |
| TC4 | ("regular", 50) | 0% | Regular + low amount |
| TC5 | ("unknown", 100) | -1 | Invalid type (boundary) |
| TC6 | ("premium", 100) | 10% | Boundary: exactly $100 |
| TC7 | ("premium", 0) | 10% | Edge case: zero amount |
| TC8 | ("premium", -50) | Error | Negative amount |

**Reasoning:** Use equivalence partitioning (premium/regular/invalid × high/low amounts) + boundary value analysis ($100 boundary) + edge cases (zero, negative).

---

### Example 8: Basis Path Testing

**Scenario:** Given this pseudocode:
```
1: x = 0
2: while (x < 10) {
3:   if (x == 5) {
4:     print("found")
5:   }
6:   x = x + 1
7: }
8: print("done")
```

**Step 1: Draw flow graph**
- Node 1: x = 0
- Node 2: x < 10? (predicate)
- Node 3: x == 5? (predicate)
- Node 4: print("found")
- Node 5: x = x + 1
- Node 6: print("done")

**Step 2: Calculate cyclomatic complexity**
V(G) = predicate nodes + 1 = 2 + 1 = 3 independent paths

**Step 3: Identify basis paths**
- Path 1: 1→2→6 (loop never executes, x starts at 0, but 0<10 is true, so actually: 1→2→3→5→2→3→5→...→2→6)
- Let me redo: Actually x=0, 0<10 true, enter loop
- Path 1: 1→2→3→5→2→6 (x=0: x≠5, skip print, x becomes 1, repeat until x=10, exit)
- Path 2: 1→2→3→4→5→2→...→6 (x=5: print "found", continue)
- Path 3: 1→2→6 (hypothetical: if x started ≥10)

**Simplified basis paths:**
1. 1→2→3→5→2→6 (normal loop execution, x never equals 5)
2. 1→2→3→4→5→2→6 (x equals 5 at some iteration)
3. 1→2→6 (loop condition false initially — if x started at 10+)

**Test cases needed:**
- TC1: x starts at 0 → exercises path where x never hits 5
- TC2: Array where 5 exists → exercises print("found") path
- TC3: x starts at 10 → exercises immediate exit path

---

## 5. RISK MANAGEMENT

### Example 9: Risk Identification from Scenario

**Scenario:** A team is building a real-time traffic monitoring system using a new AI-based image recognition library. The project has a 6-month deadline, the team has 5 developers (2 new hires), and the client expects monthly demos.

**Identify risks by category:**

| Category | Risk | Type |
|---|---|---|
| Technology | AI library is new to the team, may have undocumented limitations | Technical risk |
| Technology | Real-time processing requirements may not be met by the AI library | Product risk |
| People | 2 new hires need training, may slow early development | Project risk |
| People | Key AI expert may leave (single point of failure) | Project risk |
| Requirements | Client expectations (monthly demos) may conflict with development pace | Project risk |
| Estimation | 6-month deadline may be too tight for new technology | Schedule risk |
| Business | If AI accuracy is poor, the product is useless | Business risk |

**Reasoning:** Systematically go through each risk checklist category: product size, business impact, customer characteristics, process definition, development environment, technology, staff size/experience.

---

### Example 10: Risk Exposure Calculation

**Scenario:** A project uses a cloud service that has a 15% chance of a 3-day outage during the project's critical testing phase. Each day of outage delays the project by 2 days and costs $5,000 in idle team costs.

**Calculation:**
- Probability (P) = 15% = 0.15
- Cost (C) = 3 days × 2 days delay/day × $5,000/day = $30,000
- Risk Exposure = P × C = 0.15 × $30,000 = $4,500

**Decision:** Is $4,500 exposure worth mitigating?
- Mitigation cost: Set up backup cloud provider = $2,000
- Since $4,500 > $2,000, mitigation is cost-effective.

**Reasoning:** Risk exposure quantifies the expected loss. Compare exposure to mitigation cost to make rational decisions.

---

### Example 11: Risk Planning Strategies

**For each identified risk, develop a strategy:**

| Risk | Avoidance | Minimization | Contingency |
|---|---|---|---|
| AI library limitations | Prototype early to discover issues | Design abstraction layer to isolate AI dependency | Switch to alternative library |
| New hire productivity | Hire experienced developers instead | Pair new hires with experienced mentors | Reallocate tasks to experienced team |
| 6-month deadline | Negotiate scope reduction upfront | Deliver minimum viable product first | Request deadline extension with client |
| Single point of failure | Cross-train team on AI components | Document all AI-related knowledge | Contract external AI consultant |

**Reasoning:** For each risk, think: (1) How to prevent it? (2) How to reduce its impact? (3) What if it happens anyway?

---

## 6. PROJECT MANAGEMENT DECISIONS

### Example 12: WBS Creation

**Scenario:** Build a student registration system with modules: login, course registration, grade viewing, and admin panel.

**Work Breakdown Structure:**

```
Student Registration System (Level 0)
├── Requirements (Level 1)
│   ├── Stakeholder interviews
│   ├── Requirements document
│   └── Requirements review
├── Design (Level 1)
│   ├── Architecture design
│   ├── Database design
│   ├── UI design
│   └── Interface specifications
├── Implementation (Level 1)
│   ├── Login module
│   ├── Course registration module
│   ├── Grade viewing module
│   └── Admin panel module
├── Testing (Level 1)
│   ├── Unit testing
│   ├── Integration testing
│   ├── System testing
│   └── User acceptance testing
└── Deployment (Level 1)
    ├── Environment setup
    ├── Data migration
    ├── Training
    └── Go-live support
```

**Reasoning:** WBS decomposes the project hierarchically. Each leaf node should be a manageable task with clear deliverables. Include ALL project work (not just coding).

---

### Example 13: Scheduling with Critical Path

**Given activities:**

| Activity | Duration | Predecessors |
|---|---|---|
| A | 5 | - |
| B | 4 | A |
| C | 5 | A |
| D | 6 | B |
| E | 3 | C |
| F | 4 | D, E |

**Step 1: Forward Pass (Early Start/Finish)**
- A: ES=0, EF=5
- B: ES=5, EF=9
- C: ES=5, EF=10
- D: ES=9, EF=15
- E: ES=10, EF=13
- F: ES=max(15,13)=15, EF=19

**Step 2: Backward Pass (Late Start/Finish)**
- F: LF=19, LS=15
- D: LF=15, LS=9
- E: LF=15, LS=12
- C: LF=12, LS=7
- B: LF=9, LS=5
- A: LF=min(5,7)=5, LS=0

**Step 3: Calculate Float**
- A: TF = 0-0 = 0 ✓ Critical
- B: TF = 5-5 = 0 ✓ Critical
- C: TF = 7-5 = 2
- D: TF = 9-9 = 0 ✓ Critical
- E: TF = 12-10 = 2
- F: TF = 15-15 = 0 ✓ Critical

**Critical Path: A → B → D → F = 19 days**
**Project Duration: 19 days**

---

## 7. ESTIMATION

### Example 14: LOC Estimation with PERT

**Scenario:** A module has historical data: Optimistic = 2000 LOC, Most Likely = 3500 LOC, Pessimistic = 5000 LOC. Organization productivity: 400 LOC/pm, cost: $10,000/pm.

**Step 1: Expected Size (PERT)**
Expected LOC = (2000 + 4×3500 + 5000) / 6
= (2000 + 14000 + 5000) / 6
= 21000 / 6
= 3500 LOC

**Step 2: Effort**
Effort = 3500 / 400 = 8.75 person-months

**Step 3: Cost**
Cost = 8.75 × $10,000 = $87,500

**Reasoning:** PERT formula weights the most likely estimate 4x, giving a weighted average. This accounts for estimation uncertainty.

---

### Example 15: Function Point Estimation — Full Walkthrough

**Scenario:** An inventory management system has:
- EIs: 8 (average complexity, weight 4)
- EOs: 12 (average complexity, weight 5)
- EQs: 6 (simple complexity, weight 3)
- ILFs: 4 (complex, weight 15)
- EIFs: 3 (average, weight 7)

14 GSC ratings sum to: ΣFi = 38

**Step 1: Calculate UFC**
| Component | Count | Weight | Total |
|---|---|---|---|
| External Inputs | 8 | × 4 | 32 |
| External Outputs | 12 | × 5 | 60 |
| External Inquiries | 6 | × 3 | 18 |
| Internal Logical Files | 4 | × 15 | 60 |
| External Interface Files | 3 | × 7 | 21 |
| **UFC** | | | **191** |

**Step 2: Calculate VAF**
VAF = 0.65 + (0.01 × 38) = 0.65 + 0.38 = 1.03

**Step 3: Calculate FP**
FP = 191 × 1.03 = 196.73 ≈ 197 FP

**Step 4: Convert to LOC (Java: 46 LOC/FP)**
LOC = 197 × 46 = 9,062 LOC

**Step 5: Convert to Effort (500 LOC/pm)**
Effort = 9,062 / 500 = 18.1 person-months

**Step 6: Convert to Cost ($8,000/pm)**
Cost = 18.1 × $8,000 = $144,800

**Complete Chain:** FP → LOC → Effort → Cost

---

### Example 16: Wideband Delphi Walkthrough

**Scenario:** 3 estimators estimate 4 tasks. Round 1 estimates:

| Task | Est. A | Est. B | Est. C |
|---|---|---|---|
| T1 | 10 | 8 | 15 |
| T2 | 5 | 7 | 6 |
| T3 | 12 | 10 | 8 |
| T4 | 3 | 4 | 5 |

**Round 1 Analysis:**
- T1: Range 8-15 (large spread → needs discussion)
- T2: Range 5-7 (small spread → close to consensus)
- T3: Range 8-12 (moderate spread)
- T4: Range 3-5 (small spread)

**After discussion, Round 2:**
| Task | Est. A | Est. B | Est. C |
|---|---|---|---|
| T1 | 12 | 11 | 12 |
| T2 | 6 | 6 | 6 |
| T3 | 10 | 10 | 9 |
| T4 | 4 | 4 | 4 |

**Convergence achieved.** Final estimates (average):
- T1: (12+11+12)/3 = 11.7 days
- T2: 6 days
- T3: (10+10+9)/3 = 9.7 days
- T4: 4 days
- **Total: 31.4 days**

**Key Steps:**
1. Choose team (3-7 members)
2. Kickoff meeting (brainstorm assumptions, agree on units)
3. Individual preparation (each estimates independently)
4. Estimation session (multiple rounds, discuss disagreements, revise)
5. Assemble tasks (compile final estimates)
6. Review results

---

## 8. ARCHITECTURE TRADEOFFS

### Example 17: Choosing Between Patterns

**Scenario:** Design a system for:
(a) An online store with product catalog, shopping cart, and payment
(b) A hospital patient monitoring system
(c) A text editor with syntax highlighting

**Analysis:**

**(a) Online Store → MVC Pattern**
- Model: Product catalog, cart, orders (data)
- View: Web pages, product listings, checkout form (presentation)
- Controller: Handle user actions, route requests (input handling)
- Why: Clean separation allows changing UI without affecting business logic

**(b) Hospital Monitoring → Layered + Real-time**
- Layer 1: Sensor data acquisition (hardware interface)
- Layer 2: Data processing and analysis (real-time processing)
- Layer 3: Alert generation (business logic)
- Layer 4: Monitoring dashboard (UI)
- Why: Safety-critical needs clear layers with strict interfaces; each layer can be verified independently

**(c) Text Editor → Component-based**
- Components: Buffer management, Syntax parser, Renderer, Undo manager
- Why: Text editing is inherently component-based; each concern is independent

---

### Example 18: Layered Architecture Tradeoffs

**Scenario:** You're designing a web application. Consider:

**Option 1: Two-tier (Client-Server)**
- Pros: Simple, low latency
- Cons: Client has business logic, hard to update, security risk

**Option 2: Three-tier (Client-Application Server-Database)**
- Pros: Separation of concerns, easier maintenance, better security
- Cons: Additional network hop, more complex deployment

**Option 3: N-tier (Microservices)**
- Pros: Independent scaling, technology diversity, fault isolation
- Cons: Distributed system complexity, network failures, data consistency challenges

**Decision Framework:**
| Factor | Choose Two-tier | Choose Three-tier | Choose N-tier |
|---|---|---|---|
| Team size | Small | Medium | Large |
| Scalability needs | Low | Medium | High |
| Update frequency | Rare | Regular | Continuous |
| Data sensitivity | Low | Medium-High | High |
| Budget | Tight | Moderate | Flexible |

---

## EXAM STRATEGY SUMMARY

### Pattern Recognition for Exam Questions

| Question Contains | Likely Topic | Key Formulas/Concepts |
|---|---|---|
| "Calculate RE" | Risk Management | RE = P × C |
| "Draw the flow graph" / "Find independent paths" | Path Testing | V(G) = predicate nodes + 1 |
| "Calculate UFC/FP" | Function Point Estimation | UFC = Σ(count × weight), FP = UFC × VAF, VAF = 0.65 + 0.01×ΣFi |
| "Estimate LOC/Effort/Cost" | LOC Estimation | Effort = LOC / Productivity, Cost = Effort × Rate |
| "Find ES/EF/LS/LF/Float" | Project Scheduling | TF = LF - EF, Critical path = longest path |
| "Identify coupling/cohesion type" | Architecture Design | Content→Common→Control→Stamp→Data (coupling); Functional→...→Coincidental (cohesion) |
| "Which process model?" | Software Processes | Waterfall (fixed req), Agile (changing req), Reuse (COTS available) |
| "Risk identification" | Risk Management | Check categories: Technology, People, Requirements, Estimation, Tools |
| "Write test cases" | Testing | Equivalence partitioning + Boundary value analysis |
| "What type of risk?" | Risk Management | Project (schedule), Product (quality), Business (viability) |
