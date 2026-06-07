# Comparison Tables

---

## 1. Verification vs Validation

| Dimension | Verification | Validation |
|-----------|-------------|------------|
| **Purpose** | Ensure software conforms to specification | Ensure software meets user/customer needs |
| **Key Question** | "Are we building the product RIGHT?" | "Are we building the RIGHT product?" |
| **Inputs** | Requirements specification, design documents, code | User requirements, stakeholder needs |
| **Outputs** | Verification report, defect list, compliance status | Validation report, acceptance sign-off |
| **Advantages** | Catches errors early (in specs/design); systematic | Ensures real-world usefulness; involves users |
| **Disadvantages** | Cannot check if spec itself is wrong; limited to documented requirements | Time-consuming; expensive; happens late |
| **Use Cases** | Code reviews, inspections, walkthroughs, unit testing | Acceptance testing, beta testing, user testing |
| **Exam Distinction** | "Right" = Verification (both words start with consonants); "Product" word order: "building the product right" = V, "building the right product" = V |

---

## 2. Waterfall vs Agile

| Dimension | Waterfall | Agile |
|-----------|-----------|-------|
| **Purpose** | Structured sequential development for stable requirements | Adaptive incremental development for changing requirements |
| **Inputs** | Complete requirements specification, signed off | User stories, product backlog, evolving requirements |
| **Outputs** | Fully documented system at end of project | Working software increments every 2-4 weeks |
| **Advantages** | Clear milestones, predictable, good documentation, works for large distributed teams | Adaptable to change, fast delivery, high customer satisfaction, early ROI |
| **Disadvantages** | Inflexible, late feedback, costly changes, long delivery time | Less documentation, requires customer commitment, harder to scale, less predictable |
| **Use Cases** | Large systems engineering, safety-critical, multiple sites, regulatory compliance | Product development, startups, custom systems with engaged customer, web apps |
| **Exam Distinction** | Waterfall = REQUIREMENTS FIXED; Agile = REQUIREMENTS EMERGE. Waterfall = single delivery; Agile = frequent delivery. Not "good vs bad" -- each has appropriate contexts |

---

## 3. Functional vs Non-Functional Requirements

| Dimension | Functional Requirements | Non-Functional Requirements |
|-----------|------------------------|----------------------------|
| **Purpose** | Define specific system behavior and functionality | Define quality attributes, constraints, and performance criteria |
| **Inputs** | User needs, business processes, use cases | System quality goals, regulatory standards, technical constraints |
| **Outputs** | Functional specification, use case descriptions | Quality attribute scenarios, performance targets, security policies |
| **Advantages** | Directly testable; clear pass/fail; traceable to features | Prevent hidden quality problems; define "how well" not just "what" |
| **Disadvantages** | Cannot capture quality expectations; focus only on visible behavior | Often subjective/hard to measure; may conflict with each other |
| **Use Cases** | Login system, search feature, report generation, data entry | Response time < 2s, 99.9% uptime, AES-256 encryption, support 1000 concurrent users |
| **Exam Distinction** | Functional = "User can..." (action); Non-functional = "System shall..." + quality word (reliability, performance, security, usability). If it has a QUALIFIER (time, security level, etc.), it's likely non-functional |

---

## 4. Unit vs Integration vs System Testing

| Dimension | Unit Testing | Integration Testing | System Testing |
|-----------|-------------|-------------------|----------------|
| **Purpose** | Test individual components in isolation | Test interactions between connected components | Test the complete, integrated system |
| **Inputs** | Source code, component interfaces | Unit-tested components, interface specifications | Integrated system, requirements specification |
| **Outputs** | Pass/fail per unit, code coverage metrics | Interface defect reports, integration status | System validation report, performance metrics |
| **Advantages** | Fast feedback, easy debugging, high coverage of code | Catches interface mismatches early | End-to-end validation, real-world scenarios |
| **Disadvantages** | Misses integration issues; requires mocks/stubs | Can miss system-level issues; hard to isolate failures | Expensive, time-consuming, late in lifecycle |
| **Use Cases** | Developer testing methods/functions, TDD | Testing API contracts, module communication | Release testing, acceptance testing prep |
| **Exam Distinction** | Unit = ISOLATED component; Integration = INTERFACES between components; System = WHOLE system. They are SEQUENTIAL (unit → integration → system). Integration and system testing are often confused |

---

## 5. Black Box vs White Box Testing

| Dimension | Black Box Testing | White Box Testing |
|-----------|-------------------|-------------------|
| **Purpose** | Test functionality without knowledge of internal code | Test internal structure, logic paths, and code coverage |
| **Inputs** | Requirements, specifications, user stories | Source code, flow graphs, design documents |
| **Outputs** | Test results against expected outputs | Path coverage metrics, branch coverage, condition coverage |
| **Advantages** | Tests from user perspective; tester independent of developer; catches spec gaps | Ensures thorough code coverage; finds hidden logic errors; tests all paths |
| **Disadvantages** | Limited code coverage; may miss internal logic errors | Expensive; tests may duplicate what code already does; requires programming knowledge |
| **Use Cases** | Acceptance testing, release testing, system testing | Unit testing, security testing, path testing |
| **Exam Distinction** | Black Box = NO code access (spec-driven); White Box = FULL code access (structure-driven). They are COMPLEMENTARY, not competing. Path testing, branch testing, statement testing = White Box |

---

## 6. LOC vs Function Points

| Dimension | Lines of Code (LOC) | Function Points (FP) |
|-----------|---------------------|----------------------|
| **Purpose** | Measure physical size of software | Measure functional size of software |
| **Inputs** | Source code | Counts of EI, EO, EQ, ILF, EIF + 14 complexity factors |
| **Outputs** | Total LOC count, productivity (LOC/pm) | FP count, then estimated effort and cost |
| **Advantages** | Easy to count, widely understood, simple calculation | Language independent, available from requirements, comparable across projects |
| **Disadvantages** | Language-dependent, verbose code inflates size, only available after coding | Complex calculation, subjective factor ratings, requires training |
| **Use Cases** | Estimating effort for same language/team projects | Comparing projects across languages, early estimation before coding |
| **Exam Distinction** | LOC = PHYSICAL (code lines); FP = FUNCTIONAL (what system does). FP can be converted TO LOC for estimation. LOC is AVAILABLE LATE (after coding); FP is AVAILABLE EARLY (from requirements) |

---

## 7. Coupling vs Cohesion

| Dimension | Coupling | Cohesion |
|-----------|----------|----------|
| **Purpose** | Measure interdependence BETWEEN modules | Measure relatedness of elements WITHIN a module |
| **Inputs** | Module interfaces, dependencies, communication patterns | Module internal structure, data, operations |
| **Outputs** | Coupling level (data, stamp, control, common, content) | Cohesion level (functional, sequential, communicational, procedural, temporal, logical, coincidental) |
| **Advantages** | Low coupling → easier maintenance, reuse, testing | High cohesion → clearer purpose, easier to understand, modify |
| **Disadvantages** | Very low coupling can lead to duplication; too many interfaces | Over-cohesion can create monolithic modules |
| **Use Cases** | Designing module APIs, reducing dependency chains | Organizing code within modules, class design |
| **Exam Distinction** | Coupling = BETWEEN (inter-module); Cohesion = WITHIN (intra-module). HIGH cohesion is GOOD; LOW coupling is GOOD. They have OPPOSITE "good" directions. Best: Data coupling + Functional cohesion |

### Coupling Types (worst → best)
```
Content   →  Common   →  Control   →  Stamp   →  Data
(one modifies  (shared      (passing    (passing    (passing
 another's     global       control     data        simple
 data)         data)        flags)      structures) parameters)
```

### Cohesion Types (worst → best)
```
Coincidental  →  Logical  →  Temporal  →  Procedural  →  Communicational  →  Sequential  →  Functional
(arbitrary)   (same       (same time)  (execution     (same data)        (output of     (single
              category)                 order)                              one is input   purpose)
                                                                           of another)
```

---

## 8. Proactive vs Reactive Risk Management

| Dimension | Proactive Risk Management | Reactive Risk Management |
|-----------|--------------------------|--------------------------|
| **Purpose** | Anticipate and prevent risks before they occur | Respond to risks after they materialize |
| **Inputs** | Project plan, historical data, risk checklists, team expertise | Risk events that have already occurred |
| **Outputs** | Risk register, RMMM plan, contingency plans | Crisis action plans, damage reports, recovery plans |
| **Advantages** | Lower overall cost, controlled response, fewer surprises, better planning | Minimal upfront effort, only acts when needed |
| **Disadvantages** | Requires time/resources, may plan for risks that never materialize | Higher cost of damage control, crisis mode, schedule/budget overruns |
| **Use Cases** | Safety-critical systems, large projects, projects with high uncertainty | Small projects with limited budget, unpredictable risks that cannot be anticipated |
| **Exam Distinction** | Proactive = FORMAL RISK ANALYSIS performed upfront; Reactive = "DON'T WORRY I'LL THINK OF SOMETHING" approach. Reactive strategies: mitigation (plan resources), fix-on-failure, crisis management. Proactive: root cause correction, TQM, statistical SQA |

---

## 9. Validation Testing vs Defect Testing

| Dimension | Validation Testing | Defect Testing |
|-----------|-------------------|----------------|
| **Purpose** | Show software meets requirements | Discover faults/defects in software |
| **Inputs** | Expected usage scenarios, requirements | Edge cases, boundary conditions, unexpected inputs |
| **Outputs** | Confirmation of correct operation | Bug reports, failure descriptions |
| **Advantages** | Builds customer confidence, demonstrates compliance | Finds hidden bugs, improves reliability |
| **Disadvantages** | May miss edge-case defects | Can be destructive; many tests fail |
| **Use Cases** | Release testing, acceptance testing, demo | Unit testing, stress testing, security testing |
| **Exam Distinction** | In validation testing, SUCCESS = correct behavior (test passes). In defect testing, SUCCESS = incorrect behavior FOUND (test fails revealing bug). Counterintuitive but critical |

---

## 10. User Testing vs Release Testing

| Dimension | User Testing | Release Testing |
|-----------|-------------|-----------------|
| **Purpose** | Establish confidence in real-world conditions | Validate system before release to users |
| **Inputs** | Release candidate, user environment | Release candidate, system specification |
| **Outputs** | User feedback, bug reports, acceptance decision | Validation report, release decision |
| **Advantages** | Real-world usage uncovers unexpected issues; builds user trust | Systematic validation against spec; independent assessment |
| **Disadvantages** | Expensive, users may not be available or representative | May miss real-world usage patterns |
| **Use Cases** | Alpha testing (dev site), Beta testing (user site), acceptance testing | Pre-release quality gate, market-ready validation |
| **Exam Distinction** | Release testing is done by SEPARATE testing team (not developers); User testing involves END USERS. Release is BLACK BOX (no source access); User testing is in REAL environment |

---

## 11. Plan-Driven vs Agile

| Dimension | Plan-Driven | Agile |
|-----------|-------------|-------|
| **Purpose** | Predictable, repeatable process with clear milestones | Adaptive, responsive process for changing needs |
| **Inputs** | Complete requirements, project plan | User stories, product backlog, customer feedback |
| **Outputs** | Comprehensive documentation, final product | Working software increments, minimal docs |
| **Advantages** | Predictable schedule/budget, good for contracts, large teams | Fast feedback, adapts to change, customer satisfaction |
| **Disadvantages** | Inflexible, expensive to change, slow delivery | Less predictable, requires customer involvement, hard to scale |
| **Use Cases** | Safety-critical, regulatory, large distributed systems | Product development, startups, web applications |
| **Exam Distinction** | Plan-driven ≠ Waterfall. Plan-driven INCREMENTAL development exists. Most processes are HYBRID. Agile success depends on team skills and customer commitment |