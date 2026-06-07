# Confusion Map: Easily Confused Concepts in Software Engineering

---

## 1. Verification vs Validation

| Aspect | Verification | Validation |
|--------|-------------|------------|
| What it answers | "Are we building the product RIGHT?" | "Are we building the RIGHT product?" |
| Focus | Conformance to specification | Meeting user/customer needs |
| Activity type | Static + dynamic checks against spec | Dynamic testing with real users |
| When performed | Throughout development | At the end (acceptance testing) |
| Example | Checking code matches design docs | User testing to see if the system solves their problem |

**Exam Traps:**
- Trap: Questions that say "verification checks the final product" -- NO, validation checks the final product against user needs
- Trap: Remember the exact phrasing: "building the product right" (Verification) vs "building the right product" (Validation)
- Trap: Both use testing, but verification checks spec conformance, validation checks user satisfaction

---

## 2. Waterfall vs Agile

| Aspect | Waterfall | Agile |
|--------|-----------|-------|
| Planning | Plan-driven; all phases planned upfront | Incremental planning; adapts as you go |
| Requirements | Fixed, defined at start | Emergent, changeable |
| Delivery | Single delivery at end | Frequent small deliveries (every 2-4 weeks) |
| Customer involvement | Mainly at beginning and end | Continuous throughout |
| Documentation | Heavy documentation | Minimal; working code over docs |
| Change handling | Difficult, costly | Easy, expected |
| Best for | Large systems, safety-critical, stable reqs | Small-medium projects, changing reqs |

**Exam Traps:**
- Trap: Waterfall is NOT always bad; it's appropriate for large systems engineering projects where coordination is needed across multiple sites
- Trap: Agile is NOT "no planning" -- it's incremental planning
- Trap: Most real projects use a MIX of both approaches
- Trap: Incremental development can be plan-driven OR agile -- they are NOT synonymous

---

## 3. Functional vs Non-Functional Requirements

| Aspect | Functional Requirements | Non-Functional Requirements |
|--------|------------------------|----------------------------|
| What it describes | WHAT the system does | HOW the system does it (constraints, qualities) |
| Examples | "User can login", "System generates report" | "Response time < 2s", "99.9% uptime", "Must use AES-256" |
| Testability | Directly testable via input-output | Often subjective, harder to test |
| Priority | Must-have | Define quality level |
| Relation | Define specific behavior | Constrain how behavior is delivered |

**Exam Traps:**
- Trap: "System must be available 24/7" is NON-functional (reliability/availability), not functional
- Trap: "System must use a relational database" is NON-functional (constraint), not about a specific feature
- Trap: "User can search for products" is functional; "Search results must appear within 1 second" is non-functional
- Trap: Non-functional requirements often CROSS-CUT multiple functional requirements

---

## 4. Unit Testing vs Integration Testing vs System Testing

| Aspect | Unit Testing | Integration Testing | System Testing |
|--------|-------------|-------------------|----------------|
| Scope | Individual component/module | Interactions between components | Entire system as a whole |
| Performed by | Developers | Developers/Integration team | Separate testing team |
| Focus | Internal logic, code coverage | Interface compatibility | End-to-end functionality |
| Environment | Isolation (mocks/stubs) | Combined components | Full production-like environment |
| Timing | During development | After unit testing | After integration testing |

**Exam Traps:**
- Trap: Integration testing is NOT the same as system testing -- integration checks INTERFACES between modules, system checks the WHOLE system against requirements
- Trap: Unit testing = defect testing; System testing = validation testing (typically)
- Trap: Acceptance testing is NOT the same as system testing -- acceptance is done BY or WITH the customer

---

## 5. Black Box vs White Box Testing

| Aspect | Black Box | White Box |
|--------|-----------|-----------|
| Knowledge | No knowledge of internal code/structure | Full knowledge of internal code/structure |
| Basis | Requirements, specifications | Code structure, logic paths |
| What is tested | Input-output behavior, functionality | Internal paths, branches, conditions |
| Coverage | Requirements coverage | Code coverage (statement, branch, path) |
| Typical techniques | Equivalence partitioning, boundary value analysis | Basis path testing, branch coverage |
| Tester | Usually independent testers | Usually developers |

**Exam Traps:**
- Trap: Black box does NOT mean "no testing" -- it means testing based on external behavior only
- Trap: White box testing CANNOT prove absence of errors, only that paths execute correctly
- Trap: Both approaches are COMPLEMENTARY, not competing
- Trap: Path testing (basis path testing) is a WHITE BOX technique

---

## 6. LOC (Lines of Code) vs Function Points (FP)

| Aspect | LOC | Function Points |
|--------|-----|-----------------|
| Measures | Physical size (lines of source code) | Functional size (functionality delivered) |
| Language dependence | YES -- depends on programming language | NO -- language independent |
| Ease of calculation | Easy to count | Difficult, requires analysis |
| Timing | Available after coding | Available from requirements |
| Use case | Estimating effort for known tech stack | Comparing across languages/technologies |

**Exam Traps:**
- Trap: LOC is NOT a measure of productivity -- a verbose programmer shows higher LOC but not necessarily more productivity
- Trap: FP can be converted to LOC (e.g., 1 FP ~ 60 LOC for Java) for estimation purposes, but this varies by language
- Trap: FP is calculated using 5 information domain values (EI, EO, EQ, ILF, EIF) adjusted by 14 complexity factors
- Trap: LOC is best for estimation when you have historical data for the SAME language

---

## 7. COCOMO vs Function Points

| Aspect | COCOMO | Function Points |
|--------|--------|-----------------|
| Type | Algorithmic cost estimation model | Size estimation technique |
| Input | KLOC (size) + cost drivers | Information domain values (EI, EO, EQ, ILF, EIF) |
| Output | Effort (PM), development time, staff size | FP count (can then estimate effort) |
| Modes | Organic, Semi-detached, Embedded | N/A (applies to any project) |
| Formula | Effort = a(KLOC)^b | FP = UFP x [0.65 + 0.01 x SUM(Fi)] |

**Exam Traps:**
- Trap: FP feeds INTO COCOMO -- you can convert FP to KLOC and then use COCOMO
- Trap: COCOMO has THREE models: Application Composition, Early Design, Post-Architecture
- Trap: The exponent b in COCOMO accounts for NON-LINEAR increase in effort as size grows
- Trap: Organic = small team, familiar project; Embedded = tight constraints, unfamiliar

---

## 8. Proactive vs Reactive Risk Management

| Aspect | Proactive | Reactive |
|--------|-----------|----------|
| Approach | Anticipate risks before they occur | React to risks when they happen |
| Planning | Formal risk analysis, contingency plans | Crisis management, fire-fighting |
| Strategy | Avoidance and mitigation | Fix-on-failure |
| Cost | Lower long-term (prevention) | Higher long-term (damage control) |
| Mindset | "What might go wrong?" | "Don't worry, I'll think of something" |

**Exam Traps:**
- Trap: Reactive is NOT always wrong -- some risks are unpredictable, but proactive is preferred
- Trap: Proactive doesn't mean ALL risks are avoided -- it means having contingency plans
- Trap: Risk mitigation = reduce probability/impact; Contingency plan = what to do IF it happens
- Trap: Risk exposure (RE) = Probability x Impact (Cost) -- formula for quantifying risk priority

---

## 9. Coupling vs Cohesion

| Aspect | Coupling | Cohesion |
|--------|----------|----------|
| Definition | Interdependence between modules | Unity of purpose WITHIN a module |
| Goal | LOW coupling (minimize connections) | HIGH cohesion (single purpose) |
| Measurement | How much modules depend on each other | How related the elements inside a module are |
| Good design | Loose coupling | Strong/high cohesion |
| Types (worst to best) | Content > Common > Control > Stamp > Data | Coincidental < Logical < Temporal < Procedural < Communicational < Sequential < Functional |

**Exam Traps:**
- Trap: HIGH cohesion is good; LOW coupling is good -- they are OPPOSITE in what "high" means
- Trap: Coupling and cohesion are TRADE-OFFS -- sometimes low coupling forces lower cohesion and vice versa
- Trap: Data coupling (passing simple data) is BEST; Content coupling (modifying internal data of another module) is WORST
- Trap: Functional cohesion (all elements contribute to single function) is BEST

---

## 10. Plan-driven vs Agile

| Aspect | Plan-driven | Agile |
|--------|-------------|-------|
| Process | All activities planned in advance, measured against plan | Planning is incremental, easy to change process |
| Flexibility | Low -- changes require plan revision | High -- embraces change |
| Predictability | High -- clear milestones and deliverables | Lower -- evolving scope |
| Documentation | Comprehensive | Minimal, just-in-time |
| Team role | Defined roles, hierarchical | Self-organizing, cross-functional |

**Exam Traps:**
- Trap: Plan-driven is NOT the same as Waterfall -- plan-driven INCREMENTAL development exists
- Trap: Most practical processes include ELEMENTS of BOTH
- Trap: Plan-driven is essential for safety-critical systems with regulatory requirements
- Trap: Agile requires highly skilled, self-organizing teams -- not suitable for all organizations

---

## 11. Validation Testing vs Defect Testing

| Aspect | Validation Testing | Defect Testing |
|--------|-------------------|----------------|
| Goal | Show software meets requirements | Find faults/defects in software |
| Test case design | Reflects expected/normal usage | Deliberately obscure, edge cases |
| Successful test | System operates as intended | System performs INCORRECTLY (exposes defect) |
| Orientation | Customer-facing | Developer-facing |
| Timing | Release testing, acceptance testing | Development testing (unit, integration) |

**Exam Traps:**
- Trap: In validation testing, SUCCESS = correct behavior; In defect testing, SUCCESS = incorrect behavior found
- Trap: This is counterintuitive -- a "successful defect test" is one that FINDS A BUG
- Trap: Both are part of the overall V&V process

---

## 12. User Testing vs Release Testing

| Aspect | User Testing | Release Testing |
|--------|-------------|-----------------|
| Who performs it | End users or potential users | Separate testing team (not developers) |
| Environment | User's own environment | Developer's/lab environment |
| Purpose | Establish confidence in real-world use | Validate system before release |
| Types | Alpha (at developer site), Beta (at user site) | Functional, reliability, performance testing |
| Timing | After system testing | Before user testing |

**Exam Traps:**
- Trap: Release testing is PRIMARILY VALIDATION testing; development testing is primarily DEFECT testing
- Trap: Alpha testing = at DEVELOPER site with users present; Beta testing = at USER site
- Trap: Acceptance testing is a type of user testing (formal handover)
- Trap: Release testing is BLACK BOX testing (tester doesn't have source code access)