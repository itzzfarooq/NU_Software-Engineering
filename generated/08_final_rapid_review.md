# Final Rapid Review — Software Engineering Exam

**Purpose:** Last 30-60 minutes before the exam. High-density, highest-yield material only.

---

## 1. SE Introduction & Fundamentals

**One-paragraph summary:** Software engineering is the discipline concerned with all aspects of software production from specification through maintenance. Software costs are dominated by maintenance (not development). Good software must be maintainable, dependable, efficient, and acceptable. Four fundamental activities: specification, development, validation, evolution. Generic products are marketed to any customer; custom products are commissioned for specific customers.

**Key definitions:**
- **Software engineering:** Engineering discipline concerned with all aspects of software production
- **Generic product:** Stand-alone systems marketed to any buyer (developer owns spec)
- **Customized product:** Commissioned by specific customer (customer owns spec)
- **Maintenance costs:** Often several times development costs for long-life systems

**8 Application types:** Stand-alone, interactive transaction-based, embedded control, batch processing, entertainment, modeling/simulation, data collection, systems of systems

**ACM/IEEE Ethics — 8 Principles:** PUBLIC, CLIENT & EMPLOYER, PRODUCT, JUDGMENT, MANAGEMENT, PROFESSION, COLLEAGUES, SELF

---

## 2. Software Process Models

**One-paragraph summary:** A software process is a structured set of activities (specification, design, validation, evolution). Three main models: Waterfall (plan-driven, sequential, documentation-heavy, inflexible), Incremental Development (concurrent activities, interleaved, customer feedback, structure degrades), Integration & Configuration (reuse-based, COTS, faster delivery but requirements compromises). Most large systems use elements of all three.

**Waterfall vs Incremental — know cold:**

| Aspect | Waterfall | Incremental |
|--------|-----------|-------------|
| Planning | All planned upfront | Incremental |
| Feedback | After each phase | Continuous |
| Change | Expensive | Cheap |
| Visibility | High (documents) | Low |
| Structure | Clean | Degrades without refactoring |
| Best for | Stable requirements, large multi-site | Evolving requirements, small teams |

**Requirements Engineering Process (iterative cycle):** Elicitation & Analysis → Specification → Validation → (back to elicitation). Produces: requirements document, system descriptions.

---

## 3. Agile Development

**One-paragraph summary:** Agile emerged from dissatisfaction with 1980s/90s heavyweight methods. Focus on code over design, iterative development, working software delivery, responding to change. Agile manifesto has 4 values and 5 principles. XP is the most influential agile method with practices: user stories, pair programming, TDD, continuous integration, refactoring, sustainable pace.

**Agile Manifesto — 4 Values (must memorize):**
1. Individuals and interactions > processes and tools
2. Working software > comprehensive documentation
3. Customer collaboration > contract negotiation
4. Responding to change > following a plan

**5 Agile Principles:** Customer involvement, Incremental delivery, People not process, Embrace change, Maintain simplicity

**XP Practices:** Pair programming, TDD, continuous integration, refactoring, collective ownership, sustainable pace, on-site customer, small releases, simple design

**User Stories format:** "As a [role], I want [feature], in order to [benefit]" — written on cards, broken into tasks, estimated by team

**Refactoring:** Improving code structure without changing behavior. XP says don't anticipate changes — refactor continuously instead.

**TDD cycle:** Write failing test → Write code to pass → Refactor → Repeat

---

## 4. Software Testing

**One-paragraph summary:** Testing shows presence of defects, not their absence. Two goals: validation testing (system works as expected) and defect testing (expose faults). Verification = "building the product right" (conformance to spec). Validation = "building the right product" (meeting user needs). Testing stages: development (unit, component, system), release testing (separate team), user testing (alpha/beta).

**Critical distinction — Verification vs Validation:**
- **Verification:** "Are we building the product right?" — conforms to specification
- **Validation:** "Are we building the right product?" — meets real user needs

**Static vs Dynamic verification:**
- **Inspections (static):** Examine code/docs without execution. Catch errors that mask other errors. Check standards, portability, maintainability. Cannot check non-functional attributes.
- **Testing (dynamic):** Execute with test data. Reveals runtime behavior.

**Testing Stages:**
1. **Unit testing:** Individual components in isolation (defect testing)
2. **Component testing:** Integrated units, focus on interfaces
3. **System testing:** Complete system, focus on component interactions
4. **Release testing:** Separate team, complete system before release
5. **User testing:** Users test in their own environment (alpha/beta)

**Object class testing:** Test all operations, set/interrogate all attributes, exercise all states. Inheritance makes testing harder.

---

## 5. Path Testing & Basis Path Testing

**One-paragraph summary:** Path testing ensures every path through a program executes at least once. Start with program flow graph (nodes=decisions, arcs=control flow). Basis path testing uses McCabe's cyclomatic complexity to determine independent paths. Steps: draw control graph → find basis set → generate test cases.

**McCabe's Cyclomatic Complexity formula:**
```
V(G) = E - N + 2P
```
Where: E = edges, N = nodes, P = connected components (usually 1)

**Alternative:** V(G) = number of decision nodes + 1

**Binary search example:** 14 nodes, 15 edges → V(G) = 15 - 14 + 2 = 3 independent paths

---

## 6. Project Management

**One-paragraph summary:** Project management ensures software delivered on time, within budget, meets requirements. Success criteria: on-time delivery, within budget, meets expectations, well-functioning team. Distinctions: product is intangible, projects are one-off, processes are variable. Universal activities: project planning, risk management, people management.

**Success criteria:** On time, within budget, meets customer expectations, coherent team

**Management distinctions:** Intangible product, one-off projects, variable processes

**WBS (Work Breakdown Structure):** Deliverable-oriented hierarchical decomposition. Lowest level = work packages. Not a schedule, not an org chart. Used for estimating, scheduling, monitoring.

---

## 7. Risk Management

**One-paragraph summary:** Risk is uncertainty with negative impact. Three categories: project risks (schedule/budget), technical risks (quality/performance), business risks (viability). Process: Identify → Analyze → Plan → Track → Control. Risk exposure = P × C. Reactive strategies (fire-fighting) vs proactive strategies (formal analysis). Seven principles: global perspective, forward-looking, open communication, integrated, continuous, shared vision, teamwork.

**Risk Exposure formula:**
```
RE = P × C
```
Where: P = probability of occurrence, C = cost/consequence

**Risk categories:** Project (schedule/resources), Product (quality/performance), Business (organization viability)

**Risk types:** Known (discoverable), Predictable (extrapolated from past), Unpredictable

**Probability levels:** Very low (<10%), Low (10-25%), Moderate (25-50%), High (50-75%), Very high (>75%)

**Impact levels:** Negligible, Marginal, Critical, Catastrophic

**Reactive vs Proactive:**
- **Reactive:** "Don't worry, I'll think of something" — fix on failure, crisis management
- **Proactive:** Formal risk analysis, correct root causes, contingency plans

---

## 8. Estimation

**One-paragraph summary:** Estimation determines size, effort, and cost. Two main methods: LOC (lines of code) and Function Points (FP). LOC is simple but language-dependent; FP is language-independent based on functionality. Wideband Delphi is consensus-based estimation technique.

**Key formulas:**
```
Expected Size = (S_opt + 4×S_ml + S_pess) / 6
```
```
Effort = Total LOC / Productivity Rate (LOC/pm)
```
```
Cost = Effort × Cost per person-month
```
```
FP = UFC × VAF
```
```
VAF = 0.65 + (0.01 × ΣFi)
```
```
UFC = Σ(Count × Weight)
```

**Function Point 5 information domain types:** External Inputs (EI), External Outputs (EO), External Inquiries (EQ), Internal Logical Files (ILF), External Interface Files (EIF)

**14 General System Characteristics (GSCs):** Data communications, Distributed data processing, Performance, Heavily used configuration, Transaction rate, Online data entry, End-user efficiency, Online update, Complex processing, Reusability, Installation ease, Operational ease, Multiple sites, Facilitate change

**Wideband Delphi steps:** Choose team → Kickoff meeting → Individual preparation → Estimation session (iterative rounds until convergence) → Assemble tasks → Review results

---

## 9. Project Scheduling

**One-paragraph summary:** Scheduling splits project into tasks, estimates time/resources, organizes concurrently. Techniques: Bar charts (Gantt), Activity networks (CPM/PERT). Critical path = longest path through network. Float = scheduling flexibility.

**Critical Path Analysis formulas:**
```
ES (Early Start): Forward pass — max EF of predecessors
EF (Early Finish): ES + Duration
LS (Late Start): LF - Duration
LF (Late Finish): Backward pass — min LS of successors
Total Float = LF - EF = LS - ES
Free Float = min(ES_successor) - ES - Duration
```

**Rules for activity networks:** Flow left to right, no loops, every activity needs ID, activity begins only when all predecessors done

---

## 10. Architecture Design

**One-paragraph summary:** Design is the creative process of translating requirements into a blueprint. Key concepts: abstraction, modularity, information hiding, functional independence, coupling, cohesion. Good design has firmness (no bugs), commodity (suitable for purpose), delight (pleasurable to use).

**Coupling types (worst to best):**
Content → Common → Control → Stamp → Data → No coupling

**Cohesion types (best to worst):**
Functional → Sequential → Communicational → Procedural → Temporal → Logical → Coincidental

**4+1 View Model (Kruchten):**
1. Logical View (end users) — functionality
2. Development View (programmers) — implementation
3. Process View (integrators) — concurrency/performance
4. Physical View (system engineers) — deployment
+ Scenarios (center) — use cases connecting all views

**Design classes:** Boundary (user interface), Entity (persistent data), Control (mediator), Interface (external systems)

**Architectural patterns:** Layered, Client-server, Repository, MVC

---

## 11. UI Design

**One-paragraph summary:** UI design applies golden rules: Place user in control, Reduce memory load, Make consistent interface. Four models: User model, Design model, Mental model (system perception), Implementation model. Effective design = mental model coincides with implementation model.

**Golden Rules (Mandel):**
1. **Place user in control:** Flexible interaction, interruptible/undoable, customizable, hide internals, direct manipulation
2. **Reduce memory load:** Don't test memory, meaningful defaults, intuitive shortcuts, real-world metaphors, progressive disclosure
3. **Consistent interface:** Meaningful context, family consistency, don't break expectations

**Design Issues:** Response time, Help facilities, Error handling, Menu/command labeling, Accessibility, Internationalization

**Revised Design Principles:** Anticipation, Communication, Consistency, Controlled autonomy, Efficiency, Focus, Fitt's Law, Latency reduction

---

## 12. Quality Management

**One-paragraph summary:** Quality management provides independent check on development. Quality team must be independent. Process-based quality: define process → develop product → assess quality → if not OK, improve process. Standards: product standards (documentation, coding) vs process standards (development lifecycle). ISO 9001 framework for quality management systems.

**Quality attributes:** Safety, Security, Reliability, Resilience, Robustness, Understandability, Testability, Adaptability, Modularity, Complexity, Portability, Usability, Reusability, Efficiency, Learnability

**Quality conflicts:** Cannot optimize all attributes — improving robustness may reduce performance. Quality plan must define most important attributes.

---

## Common Exam Questions — Quick Answers

| Question | Answer |
|----------|--------|
| Verification vs Validation? | V&V: building product right vs building right product |
| Waterfall best for? | Stable requirements, large multi-site projects |
| When to use Agile? | Evolving requirements, need rapid delivery |
| What is coupling? | Measure of interconnection between modules |
| What is cohesion? | Measure of functional strength of a module |
| Risk exposure formula? | RE = P × C |
| Cyclomatic complexity formula? | V(G) = E - N + 2P |
| FP formula? | FP = UFC × VAF |
| VAF range? | 0.65 to 1.35 |
| Critical path? | Longest path through activity network |
| Float formula? | Total Float = LF - EF |
| 4 Agile values? | Individuals, Working software, Customer collaboration, Responding to change |
| 4 SE activities? | Specification, Development, Validation, Evolution |
| Risk categories? | Project, Technical, Business |
| Testing reveals? | Presence of defects, not absence |
| Best coupling? | Data coupling (worst: content) |
| Best cohesion? | Functional (worst: coincidental) |
| WBS lowest level? | Work packages |
| Wideband Delphi steps? | 6 steps: Choose, Kickoff, Prepare, Session, Assemble, Review |

---

## Pitfall Warnings

- **Don't confuse** Waterfall with Plan-driven: Plan-driven ≠ Waterfall
- **Don't forget** Agile values "while there is value in items on the right, we value left more" — it doesn't dismiss documentation/plans
- **Don't mix up** verification and validation — memorize: Verification = spec conformance, Validation = user needs
- **Don't forget** testing can only show presence of defects, never absence
- **Don't confuse** unit testing with component testing — unit = isolation, component = integrated units
- **Don't forget** RE = P × C, not P + C
- **Don't forget** cyclomatic complexity = E - N + 2P
- **Don't confuse** coupling (interconnection) with cohesion (internal strength)
- **Don't forget** VAF range is 0.65 to 1.35, not 0 to 1
- **Don't confuse** total float with free float
- **Don't forget** critical path = longest path (determines project duration)
- **Don't mix up** known, predictable, and unpredictable risks
- **Don't forget** quality team must be independent from development team
- **Don't confuse** product standards with process standards
