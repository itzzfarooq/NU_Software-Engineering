# Software Engineering - Exam Reference Sheet

Quick-lookup compressed reference for exam revision.

---

## Key Definitions

| Term | Definition |
|------|-----------|
| Software Engineering | Application of systematic, disciplined, quantifiable approaches to software development, operation, and maintenance |
| Software Process | Structured set of activities required to develop a software system |
| Requirements Engineering | Process of discovering, analyzing, documenting, and validating software requirements |
| Verification | Are we building the product right? (conformance to specification) |
| Validation | Are we building the right product? (meets user needs) |
| Coupling | Degree of interdependence between modules (want LOW) |
| Cohesion | Degree to which tasks within a module are related (want HIGH) |
| Information Hiding | Concealing implementation details within modules |
| Abstraction | Hiding complexity by showing only essential features |
| Baseline | Formally reviewed and approved artifact; changes require formal control |
| Regression Testing | Re-testing after changes to ensure existing functionality still works |
| Risk Exposure | Quantified risk = probability × impact |
| Configuration Management | Managing versions, baselines, and configurations of software artifacts |

---

## Process Models

| Model | Key Characteristics | Best For |
|-------|-------------------|----------|
| Waterfall | Sequential, phase-based, document-driven, non-iterative | Stable, well-understood requirements |
| Incremental | Deliver system in small usable increments | Requirements can be prioritized; early delivery needed |
| Spiral | Risk-driven, iterative, each cycle includes risk analysis | Large, high-risk projects |
| V-Model | Each dev phase maps to a testing level | Safety-critical, regulated systems |
| Prototyping | Build prototypes to elicit/validate requirements | Unclear requirements; user interface design |
| RAD | Rapid application development, time-boxed, component reuse | Business applications with short deadlines |
| Agile | Iterative, incremental, adaptive, people-over-process, working software | Evolving requirements; small teams |

---

## Agile Frameworks

| Framework | Key Features |
|-----------|-------------|
| **XP** (Extreme Programming) | Pair programming, TDD, continuous integration, simple design, refactoring, customer on-site, small releases, collective ownership |
| **Scrum** | Sprints (2-4 weeks), roles (Product Owner, Scrum Master, Team), ceremonies (Sprint Planning, Daily Standup, Review, Retrospective), Backlog management |
| **Kanban** | Visual workflow (Kanban board), WIP limits, continuous flow (no sprints), pull system |
| **Crystal** | Family of methodologies scaled by project size/importance (Crystal Clear, Crystal Yellow, etc.) |
| **Lean** | Eliminate waste, amplify learning, decide as late as possible, deliver fast, empower team, build integrity in, see the whole |
| **FDD** | Feature-driven development; model-driven, component-based, builds feature list iteratively |

---

## XP Practices

| Practice | Description |
|----------|-------------|
| Pair Programming | Two developers on one workstation |
| Test-Driven Development (TDD) | Write tests before code |
| Continuous Integration | Integrate and test multiple times per day |
| Refactoring | Improve code structure without changing behavior |
| Simple Design | Code does only what is needed |
| Collective Ownership | Any developer can modify any code |
| Small Releases | Frequent, small, well-tested releases |
| Customer On-site | Customer available full-time |
| Coding Standards | Consistent style across team |
| Sustainable Pace | 40-hour week; avoid overtime |
| Metaphor | System described using everyday analogies |
| Spiking | Quick research/prototype to reduce risk |

---

## Requirements Types

| Type | Description | Example |
|------|-------------|---------|
| Functional | What the system should DO | "System shall calculate tax" |
| Non-Functional | Quality attributes/constraints | "Response time < 2 seconds" |
| Domain | Business rules/knowledge | "Tax rate is 7%" |
| User | How users interact with system | "User shall be able to export reports" |
| System | System-wide constraints | "System shall run on Linux" |

---

## Elicitation Techniques

| Technique | Best For | Limitation |
|-----------|----------|-----------|
| Interviews | Individual stakeholders, detailed requirements | Time-consuming, biased by interviewee |
| Questionnaires | Large groups, quick feedback | Low depth, misinterpretation |
| Observation (Ethnography) | Understanding actual work practices | Time-consuming, observer effect |
| Document Analysis | Understanding existing systems | Documents may be outdated |
| Brainstorming | Generating ideas, creative solutions | Can be dominated by vocal participants |
| Prototyping | Clarifying UI, validating requirements | May be mistaken for final product |
| Use Cases | Actor-system interactions | Doesn't capture non-functional requirements |
| JAD Sessions | Collaborative requirement gathering | Scheduling, group dynamics |

---

## Design Principles

| Principle | Description |
|-----------|-------------|
| **SRP** (Single Responsibility) | A class should have only one reason to change |
| **OCP** (Open-Closed) | Open for extension, closed for modification |
| **LSP** (Liskov Substitution) | Subtypes must be substitutable for their base types |
| **ISP** (Interface Segregation) | Many specific interfaces > one general interface |
| **DIP** (Dependency Inversion) | Depend on abstractions, not concretions |
| **DRY** (Don't Repeat Yourself) | Avoid code duplication |
| **KISS** (Keep It Simple) | Simplicity is preferred over complexity |
| **YAGNI** (You Aren't Gonna Need It) | Don't build features until needed |
| **Separation of Concerns** | Separate distinct features/concerns |
| **Modularity** | Divide system into discrete, manageable modules |

---

## Coupling Types (Worst → Best)

| Type | Description | Dependency |
|------|-------------|-----------|
| **Content** | One module modifies另一个's internal data | Worst |
| **Common** | Modules share global data | ↓ |
| **Control** | One module controls logic of another via flags | ↓ |
| **Stamp** | Modules share composite data structures | ↓ |
| **Data** | Modules communicate via parameters (data only) | Best |

**Remember**: Content → Common → Control → Stamp → Data (CCCS D)

---

## Cohesion Types (Best → Worst)

| Type | Description | Quality |
|------|-------------|---------|
| **Functional** | Module performs one well-defined task | Best |
| **Sequential** | Output of one task = input of next (data flow) | ↓ |
| **Communicational** | Tasks operate on same data | ↓ |
| **Procedural** | Tasks are ordered by control flow | ↓ |
| **Temporal** | Tasks done at same time | ↓ |
| **Logical** | Tasks are logically related (e.g., all input) | ↓ |
| **Coincidental** | No meaningful relationship between tasks | Worst |

**Remember**: Fun-Seq-Comm-Proc-Temp-Log-Coin

---

## Architectural Patterns

| Pattern | Description | Pros | Cons |
|---------|-------------|------|------|
| **Layered** | Organized in horizontal layers (UI, Logic, Data) | Separation of concerns, modularity | Performance overhead |
| **Client-Server** | Client requests, server provides services | Scalability, resource sharing | Network dependency |
| **MVC** | Model-View-Controller separation | Flexibility, parallel development | Complexity |
| **Repository** | Central data store accessed by components | Data consistency, shared access | Bottleneck, single point of failure |
| **Pipe-and-Filter** | Data flows through processing steps | Reusability, composability | Not suitable for interactive systems |
| **Event-Based** | Components communicate via events | Loose coupling, scalability | Testing complexity, event ordering |
| **Blackboard** | Knowledge sources collaborate via shared state | AI/heuristic problems | No standard control strategy |

---

## Testing Types

| Type | Description | Level |
|------|-------------|-------|
| **Unit** | Test individual components in isolation | Component |
| **Integration** | Test combined components | Component/System |
| **System** | Test complete system against requirements | System |
| **Acceptance** | Customer validates system meets needs | System |
| **Regression** | Re-test after changes | Any |
| **Smoke** | Quick check core functionality works | System |
| **Alpha** | Internal testing by development team | System |
| **Beta** | External testing by real users | System |
| **White-box** | Test based on internal code structure | Any |
| **Black-box** | Test based on specifications only | Any |
| **Gray-box** | Partial knowledge of internals | Any |

---

## Testing Levels (V-Model Mapping)

| Dev Phase | Test Level |
|-----------|-----------|
| Requirements | Acceptance Testing |
| System Design | System Testing |
| Architecture Design | Integration Testing |
| Module Design | Unit Testing |

---

## Test Coverage Criteria

| Criterion | Description |
|-----------|-------------|
| Statement Coverage | Every statement executed at least once |
| Branch Coverage | Every branch (true/false) taken at least once |
| Path Coverage | Every possible path through code executed |
| Condition Coverage | Every Boolean sub-expression evaluated to true and false |
| Loop Coverage | Loop tested with 0, 1, N, N+1 iterations |

---

## Metrics

| Metric | Description | Formula/Notes |
|--------|-------------|---------------|
| **LOC** | Lines of code (size measure) | Language-dependent |
| **FP** | Function Points (size measure) | Language-independent, based on user functions |
| **Effort** | Work done in person-months | PM = a × (KLOC)^b × EAF (COCOMO) |
| **Duration** | Calendar time to complete | Months = c × (Effort)^d |
| **Defect Density** | Defects per KLOC or per FP | Defects / Size |
| **Yield** | Percentage of defects found before release | Defects found before / Total defects |
| **MTTF** | Mean Time To Failure | Average time between failures (non-repairable) |
| **MTBF** | Mean Time Between Failures | Average time between failures (repairable) |
| **Availability** | Proportion of time system is operational | MTBF / (MTBF + MTTR) |
| **Risk Exposure** | Quantified risk value | Probability × Impact |
| **Schedule Variance** | deviation from planned schedule | (Actual - Planned) / Planned |
| **Cost Variance** | Deviation from planned cost | (Actual - Budget) / Budget |

---

## FP Calculation (Simplified)

| Component | Count | Weight (Simple/Average/Complex) |
|-----------|-------|---------------------------------|
| External Inputs (EI) | × | 3 / 4 / 6 |
| External Outputs (EO) | × | 4 / 5 / 7 |
| External Inquiries (EQ) | × | 3 / 4 / 6 |
| Internal Logical Files (ILF) | × | 7 / 10 / 15 |
| External Interface Files (EIF) | × | 5 / 7 / 10 |

**Unadjusted FP (UFP)** = Sum of all weighted counts

**Adjusted FP** = UFP × [0.65 + 0.01 × Σ(Fi)] where Fi = 14 complexity factors (0-5 each)

---

## COCOMO Formulas

| Level | Effort (PM) | Duration (Months) |
|-------|-------------|-------------------|
| **Basic** | PM = a × (KLOC)^b | TDEV = c × (PM)^d |
| **Intermediate** | PM = a × (KLOC)^b × EAF | TDEV = c × (PM)^d |
| **Detailed** | Phase-level breakdown | Phase-level breakdown |

**EAF** = Π(Ei) where Ei are effort multipliers (cost drivers)

**COCOMO II** uses: Size (KLOC or FP), Effort multipliers, Schedule multipliers

---

## Risk Categories

| Category | Examples |
|----------|---------|
| **Project** | Schedule slippage, budget overrun, staffing issues, political problems |
| **Product** | Requirements volatility, unrealistic performance targets, technology obsolescence |
| **Technical** | Requirements ambiguity, design flaws, integration failures, testing inadequacy |
| **Organizational** | Lack of sponsorship, resource conflicts, organizational change |
| **External** | Regulatory changes, market shifts, vendor issues, force majeure |

---

## Risk Response Strategies

| Strategy | When to Use | Example |
|----------|-------------|---------|
| **Avoid** | Eliminate the risk entirely | Change technology to avoid uncertain platform |
| **Mitigate** | Reduce probability or impact | Add testing, hire experts, use prototypes |
| **Transfer** | Shift risk to another party | Insurance, outsourcing, fixed-price contracts |
| **Accept** | Acknowledge and plan for it | Contingency reserves, workaround plans |

---

## WBS Levels

| Level | Description | Example |
|-------|-------------|---------|
| 1 | Major deliverable / project name | "E-Commerce System" |
| 2 | Sub-deliverable / phase | "User Module", "Payment Module" |
| 3 | Work package (smallest estimable unit) | "Design Login Page", "Implement Cart" |
| 4+ | Sub-tasks (optional) | "Create HTML", "Write CSS", "Write JS" |

**Key**: WBS is deliverable-oriented, not activity-oriented. Lowest level = work packages (cost/schedule estimated here).

---

## UI Design Principles

| Principle | Description |
|-----------|-------------|
| **Consistency** | Similar operations/elements behave similarly |
| **Visibility** | System status visible to user at all times |
| **Feedback** | Immediate response to user actions |
| **Constraints** | Prevent invalid user actions |
| **Affordance** | UI elements suggest how they should be used |
| **Mapping** | Controls correspond logically to their effects |
| **Simplicity** | Minimal UI; only essential elements shown |
| **Recovery** | Easy undo/redo of actions |
| **Learnability** | Easy for new users to become productive |
| **Efficiency** | Quick for experienced users to complete tasks |

---

## Quality Attributes (ISO 9126)

| Attribute | Description |
|-----------|-------------|
| **Functionality** | Does what it's supposed to do |
| **Reliability** | Operates under stated conditions for stated time |
| **Usability** | Ease of use, learning, and understanding |
| **Efficiency** | Resource usage relative to performance |
| **Maintainability** | Ease of modification/repair |
| **Portability** | Ability to transfer to another environment |

---

## Key Comparisons

### Waterfall vs Agile

| Aspect | Waterfall | Agile |
|--------|-----------|-------|
| Approach | Sequential | Iterative/Incremental |
| Requirements | Fixed upfront | Evolving |
| Documentation | Comprehensive | Just enough |
| Customer Involvement | At milestones | Continuous |
| Change Tolerance | Low | High |
| Delivery | End of project | Frequent increments |
| Risk Discovery | Late | Early |
| Best For | Stable requirements | Uncertain/changing requirements |

### Verification vs Validation

| Aspect | Verification | Validation |
|--------|-------------|-----------|
| Question | Are we building the product right? | Are we building the right product? |
| Focus | Conformance to spec | Meeting user needs |
| Methods | Reviews, inspections, testing | Testing, prototyping, user acceptance |
| Timing | Throughout development | Primarily at end |
| Static/Dynamic | Both | Primarily dynamic |

### QA vs QC vs Testing

| Aspect | QA | QC | Testing |
|--------|----|----|---------|
| Focus | Process | Product | Product |
| Orientation | Prevention | Detection | Detection |
| Goal | Defect prevention | Defect identification | Defect identification |
| Timing | Throughout lifecycle | After product creation | After product creation |
| Responsibility | Everyone | QC team | Test team |

### LOC vs FP

| Aspect | LOC | FP |
|--------|-----|-----|
| Language | Dependent | Independent |
| Measure | Physical size | Functional size |
| Counting | Easy | Complex |
| Bias | Language-biased | Language-neutral |
| Best For | Within-language comparison | Cross-language comparison |

### Top-Down vs Bottom-Up Integration

| Aspect | Top-Down | Bottom-Up |
|--------|----------|-----------|
| Direction | Main → Sub | Sub → Main |
| Stubs | Yes (simulate lower modules) | No |
| Drivers | No | Yes (simulate upper modules) |
| Early Testing | Main control logic | Low-level functions |
| Disadvantage | Low-level tested late | Main control tested late |

---

## Effort Estimation Approaches

| Approach | Description | When to Use |
|----------|-------------|-------------|
| **Expert Judgment** | Expert estimates based on experience | Quick estimates, small projects |
| **Analogy** | Compare to similar past projects | Similar projects available |
| **COCOMO** | Algorithmic model based on KLOC | Large projects, historical data |
| **Function Points** | Based on functional requirements | Early stage, language-independent |
| **Planning Poker** | Agile team consensus estimation | Agile projects |
| **Wideband Delphi** | Group estimation with consensus | Team-based, reduces individual bias |

---

## Formulas Quick Reference

| Formula | Expression |
|---------|-----------|
| Risk Exposure | RE = P(event) × Impact(event) |
| Function Points | FP = UFP × [0.65 + 0.01 × ΣFi] |
| COCOMO Effort | PM = a × (KLOC)^b |
| COCOMO Duration | TDEV = c × (PM)^d |
| Availability | A = MTBF / (MTBF + MTTR) |
| Defect Density | DD = Defects / KLOC |
| Yield | Y = Defects_found_before / Total_defects |
| Expected Size (Optimistic) | E = (O + 4M + P) / 6 |
| Variance (PERT) | V = ((P - O) / 6)^2 |
| Schedule Variance | SV = (Actual - Planned) / Planned |
| Cost Variance | CV = (Actual - Budget) / Budget |

---

## Common Symbols in UML

| Symbol | Meaning |
|--------|---------|
| → | Association |
| ▷ | Inheritance/Generalization |
| ◆ | Composition |
| ◇ | Aggregation |
| --▶ | Dependency |
| - - → | Realization/Implementation |
| + | Public |
| - | Private |
| # | Protected |
