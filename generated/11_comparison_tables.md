# Software Engineering — Comparison Tables for Exam Preparation

---

## 1. Verification vs Validation

| Aspect | Verification | Validation |
|--------|-------------|------------|
| **Purpose** | Confirm the software conforms to its specification | Confirm the software meets user's real requirements |
| **Key Question** | "Are we building the product right?" | "Are we building the right product?" |
| **Inputs** | Requirements specification, design documents, source code | User needs, expected environment, real-world scenarios |
| **Outputs** | Confirmation of conformance to spec | Confirmation that system is fit for purpose |
| **Methods** | Inspections, reviews, static analysis, walkthroughs | Testing with real/representative data, user acceptance testing |
| **When Performed** | Throughout development lifecycle | After development, before/after release |
| **Focus** | Internal correctness | External fitness for purpose |
| **Advantages** | Finds errors early;低成本; can be done without execution | Ensures customer satisfaction; validates real-world usage |
| **Disadvantages** | Cannot guarantee user satisfaction; limited to spec compliance | Expensive; late discovery of issues; depends on test data quality |
| **Use Cases** | Safety-critical systems, regulated industries, formal processes | All software systems, especially user-facing applications |
| **Exam Distinction** | Verification = spec conformance (inward-facing) | Validation = user satisfaction (outward-facing) |

---

## 2. Waterfall vs Incremental Development

| Aspect | Waterfall Model | Incremental Development |
|--------|----------------|------------------------|
| **Purpose** | Sequential, phase-by-phase development with complete documentation | Iterative delivery with interleaved specification, development, validation |
| **Inputs** | Complete requirements upfront | Outline description / initial requirements |
| **Outputs** | Complete system delivered at end | Working increments delivered throughout |
| **Structure** | Linear, sequential phases flowing downward | Concurrent/parallel activities with feedback loops |
| **Customer Involvement** | Minimal during development; heavy at start and end | Continuous feedback and involvement |
| **Change Handling** | Difficult and expensive to accommodate changes | Easy and低成本 to accommodate changes |
| **Visibility of Progress** | Clear milestones at phase boundaries | Continuous but harder to measure |
| **Advantages** | Clear structure; good documentation; easy to manage; suits large distributed teams | Rapid delivery; early customer feedback; lower cost of change |
| **Disadvantages** | Inflexible partitioning; difficult to respond to changing requirements; late delivery | Process not visible; system structure degrades without refactoring |
| **Use Cases** | Large systems engineering projects with stable requirements; multi-site development | Projects with evolving requirements; customer-facing products |
| **Exam Distinction** | Plan-driven; separate phases; complete before next | Interleaved activities; concurrent; feedback loops |

---

## 3. Plan-driven vs Agile Development

| Aspect | Plan-driven Development | Agile Development |
|--------|------------------------|-------------------|
| **Purpose** | All activities planned in advance; progress measured against plan | Planning is incremental; process adapts to changing requirements |
| **Planning** | Upfront comprehensive planning | Just-in-time, iterative planning |
| **Requirements** | Fully specified before development | User stories; evolve over time |
| **Documentation** | Extensive documentation required | Light documentation; working software over docs |
| **Customer Role** | Involved at start (requirements) and end (acceptance) | Continuous involvement throughout |
| **Team Structure** | Hierarchical (analyst → designer → coder → tester) | Self-organizing, cross-functional teams |
| **Delivery** | Single delivery at end | Frequent incremental deliveries (2-4 weeks) |
| **Testing** | Separate phase after implementation | Test-driven development (TDD); continuous testing |
| **Design** | Upfront architecture and design | Simple design; evolves with each iteration |
| **Refactoring** | Done at end if needed | Continuous refactoring every hour/half-hour |
| **Advantages** | Predictable schedule/budget; clear documentation; suits regulated environments | Adaptive; faster delivery; customer satisfaction; higher quality |
| **Disadvantages** | Inflexible; late feedback; high cost of change | Less predictable; requires disciplined team; harder to scale |
| **Use Cases** | Large enterprise systems; safety-critical; contractual projects | Startups; web/mobile apps; projects with uncertain requirements |
| **Exam Distinction** | "Plan the work, work the plan" | "Embrace change; deliver early and often" |

---

## 4. Functional vs Non-Functional Requirements

| Aspect | Functional Requirements | Non-Functional Requirements |
|--------|------------------------|----------------------------|
| **Purpose** | Define what the system should do (services, behaviors) | Define how well the system should perform (quality attributes) |
| **Focus** | System functionality and features | System quality and constraints |
| **Inputs** | User needs, business processes, use cases | Performance standards, regulatory requirements, platform constraints |
| **Outputs** | Detailed feature specifications | Quality standards, performance metrics, compliance checklists |
| **Examples** | "User can register an account"; "System generates reports" | "Response time < 2 seconds"; "99.9% uptime"; "Support 1000 concurrent users" |
| **Testability** | Directly testable through functional tests | Measured through benchmarks, load tests, compliance audits |
| **Dependencies** | May depend on non-functional requirements | Often constrain functional requirements |
| **Advantages** | Clear, measurable, directly testable | Ensure system quality and reliability |
| **Disadvantages** | May miss quality aspects | Often vague, hard to measure, conflict with each other |
| **Use Cases** | All software systems; requirements specification documents | Performance engineering; system architecture; quality assurance |
| **Exam Distinction** | "What the system does" (functional) | "How well the system does it" (non-functional) |

---

## 5. Unit Testing vs Integration Testing vs System Testing

| Aspect | Unit Testing | Integration Testing | System Testing |
|--------|-------------|-------------------|----------------|
| **Purpose** | Test individual components in isolation | Test combined components for interface defects | Test complete system against requirements |
| **Scope** | Single module, function, or method | Multiple integrated modules | Entire system end-to-end |
| **Performed By** | Developers | Developers + testers | Separate testing team |
| **Input** | Individual code units | Integrated modules/subsystems | Complete system |
| **Output** | Verified individual components | Verified interfaces and interactions | Verified system behavior |
| **Focus** | Internal logic, data paths, boundary conditions | Interface defects, communication errors, data flow | System behavior, performance, security, compliance |
| **Automation** | Highly automatable (JUnit, NUnit) | Partially automatable | Mostly manual; some automated load tests |
| **Advantages** | Fast; finds bugs early; isolated testing | Catches interface errors; validates integration | Validates complete system behavior |
| **Disadvantages** | Cannot find system-level issues | Complex setup; environment-dependent | Late discovery; expensive; time-consuming |
| **Use Cases** | Every code change during development | After unit testing; before system testing | Before release; after integration testing |
| **Exam Distinction** | Isolated → individual modules | Combined → interfaces | Complete → end-to-end requirements |

---

## 6. Black Box vs White Box Testing

| Aspect | Black Box Testing | White Box Testing |
|--------|------------------|-------------------|
| **Purpose** | Test system behavior against specifications | Test internal code structure and logic |
| **Knowledge Required** | Requirements only; no code knowledge needed | Complete knowledge of code structure |
| **Approach** | Input-output testing; "what" the system does | Code-level testing; "how" the system works |
| **Test Design** | Based on requirements, use cases, user scenarios | Based on code paths, branches, conditions |
| **Coverage Metrics** | Requirements coverage, equivalence partitioning | Statement coverage, branch coverage, path coverage |
| **Performed By** | Testers, QA team, end users | Developers, technical testers |
| **Advantages** | User perspective; no code knowledge needed; effective for functional testing | Thorough code coverage; finds hidden errors; code optimization |
| **Disadvantages** | Limited code coverage; cannot find code-level bugs | Requires programming skills; time-consuming; expensive |
| **Use Cases** | Acceptance testing, regression testing, system testing | Unit testing, code reviews, security testing |
| **Exam Distinction** | External view (behavior) | Internal view (structure) |

---

## 7. Validation Testing vs Defect Testing

| Aspect | Validation Testing | Defect Testing |
|--------|-------------------|----------------|
| **Purpose** | Show that software meets requirements | Discover faults and defects in software |
| **Goal** | Successful test = system performs correctly | Successful test = system performs incorrectly (exposes defect) |
| **Test Cases** | Reflect expected/normal system use | Deliberately obscure; need not reflect normal use |
| **Perspective** | Prove the system works | Break the system |
| **Focus** | Conformance with specification | Non-conformance with specification |
| **Test Data** | Normal, expected inputs | Edge cases, invalid inputs, stress conditions |
| **Advantages** | Builds confidence in system correctness | Finds hidden defects before deployment |
| **Disadvantages** | May miss edge cases and defects | Can be expensive; may not reflect real usage |
| **Use Cases** | Acceptance testing, release testing | Debugging, stress testing, security testing |
| **Exam Distinction** | "Show it works" | "Show it breaks" |

---

## 8. Inspections vs Testing

| Aspect | Inspections (Static Verification) | Testing (Dynamic Verification) |
|--------|----------------------------------|-------------------------------|
| **Purpose** | Analyze static system representation to discover problems | Exercise and observe product behavior |
| **Execution** | No system execution required | System must be executed with test data |
| **When Applied** | Before implementation (requirements, design, code) | After implementation (running system) |
| **Artifacts** | Requirements, design documents, source code, UML models | Running software, prototypes, deployed system |
| **Performed By** | Trained inspection team (moderator, reader, recorder, author) | Testers, developers, users |
| **Error Detection** | Can find errors early; not affected by error masking | Errors may mask other errors; only finds runtime issues |
| **Advantages** | Early detection; no test harness needed; can inspect incomplete systems; considers broader quality attributes | Tests actual behavior; validates non-functional characteristics (performance, usability) |
| **Disadvantages** | Cannot check non-functional characteristics; cannot validate real behavior | Late detection; expensive; requires test environment |
| **Use Cases** | Requirements review, design review, code inspection, compliance audits | Unit, integration, system, acceptance testing |
| **Exam Distinction** | Static (examine without running) | Dynamic (execute to observe) |

---

## 9. Generic vs Customized Products

| Aspect | Generic Products | Customized (Bespoke) Products |
|--------|-----------------|------------------------------|
| **Purpose** | Stand-alone systems marketed to any customer | Software commissioned by specific customer |
| **Specification Ownership** | Owned by software developer | Owned by the customer |
| **Change Decisions** | Made by developer (based on market needs) | Made by customer (based on their requirements) |
| **Target Market** | General market; multiple customers | Single customer; specific needs |
| **Examples** | MS Office, Adobe Photoshop, games, CAD software | Air traffic control, embedded systems, banking systems |
| **Development Focus** | Market-driven features; competitive advantage | Customer-specific requirements; custom solutions |
| **Revenue Model** | Licensing, subscriptions, one-time purchase | Contract-based; project-based billing |
| **Advantages** | Economies of scale; wider market; reusable | Tailored to exact needs; full control by customer |
| **Disadvantages** | May not meet all user needs; competition | Higher cost; longer development; unique (no reuse) |
| **Use Cases** | Consumer software, productivity tools, entertainment | Enterprise systems, government projects, specialized hardware |
| **Exam Distinction** | Developer owns spec; sold to many | Customer owns spec; built for one |

---

## 10. Coupling vs Cohesion

| Aspect | Coupling | Cohesion |
|--------|----------|---------|
| **Purpose** | Measure of interconnection between modules | Measure of functional strength within a module |
| **Direction** | Between modules (external) | Within a module (internal) |
| **Goal** | Minimize coupling (loose coupling is best) | Maximize cohesion (high cohesion is best) |
| **Depends On** | Interface complexity, shared data, calling mechanism | Single-mindedness of module function |
| **Measured By** | Coupling types (content → data, worst to best) | Cohesion types (coincidental → functional, worst to best) |
| **Impact of Good** | Changes in one module don't affect others; easier maintenance | Module does one thing well; easier to understand and test |
| **Impact of Poor** | Changes ripple across modules; fragile, hard to maintain | Module does many unrelated things; hard to understand, test, reuse |
| **Advantages** | Low coupling = independent modules; parallel development possible | High cohesion = focused, clear responsibility |
| **Disadvantages** | Tight coupling creates dependencies and maintenance nightmares | Low cohesion indicates poor design; code duplication |
| **Use Cases** | Architectural design; module decomposition; OO design | Module design; class design; component design |
| **Exam Distinction** | Coupling = "how connected are modules?" (external) | Cohesion = "how focused is a module?" (internal) |

---

## 11. Coupling Types (Content → Common → Control → Stamp → Data)

| Type | Description | Example | Worst/Best | Key Characteristic |
|------|-------------|---------|------------|-------------------|
| **Content Coupling** | One module modifies or relies on internal workings of another | Module A directly accesses data inside Module B | **WORST** | Direct internal access |
| **Common Coupling** | Multiple modules share the same global data | Global variable accessed by many modules | Very Poor | Shared global state |
| **Control Coupling** | One module passes execution control (flag) to another | Module A passes a flag to Module B to control its behavior | Poor | Control information passed |
| **Stamp Coupling** | Modules communicate via composite data items | Entire record passed when only one field needed | Fair | Unnecessary data passed |
| **Data Coupling** | Modules communicate via simple data items (parameters) | Function receives only the parameters it needs | **BEST** | Minimal, necessary data |
| **No Coupling** | Modules are completely independent | No interaction between modules | Ideal (rare) | Complete independence |

**Exam Tip:** Remember the mnemonic: **"CCCS D"** = Content, Common, Control, Stamp, Data (worst to best)

---

## 12. Cohesion Types (Functional → Sequential → Communicational → Procedural → Temporal → Logical → Coincidental)

| Type | Description | Example | Best/Worst | Key Characteristic |
|------|-------------|---------|------------|-------------------|
| **Functional Cohesion** | All elements contribute to a single, well-defined task | Math library with only mathematical functions | **BEST** | Single purpose |
| **Sequential Cohesion** | Output of one component serves as input to another | Data processing pipeline: read → transform → write | Very Good | Input-output chain |
| **Communicational Cohesion** | Elements grouped because they operate on the same data | All functions that process customer data | Good | Same data accessed |
| **Procedural Cohesion** | Elements grouped because they always follow a specific execution sequence | Steps in a login procedure | Fair | Sequential execution |
| **Temporal Cohesion** | Elements grouped because they are processed at the same time | All initialization routines | Poor | Same timing |
| **Logical Cohesion** | Elements logically related but functions unrelated | Module handling all "input" operations (file, keyboard, network) | Very Poor | Logically related |
| **Coincidental Cohesion** | Elements are unrelated and grouped by chance | Utility module with unrelated helper functions | **WORST** | No meaningful relationship |

**Exam Tip:** Remember the mnemonic: **"FSCPTLC"** = Functional, Sequential, Communicational, Procedural, Temporal, Logical, Coincidental (best to worst)

---

## 13. Reactive vs Proactive Risk Management

| Aspect | Reactive Risk Management | Proactive Risk Management |
|--------|------------------------|--------------------------|
| **Philosophy** | "Don't worry, I'll think of something" | Formal risk analysis and prevention |
| **Approach** | Fix on failure; react when risk strikes | Prevent and have contingency plans |
| **Timing** | After problems occur | Before problems occur |
| **Planning** | No upfront risk planning | Structured risk management process |
| **Steps** | 1. Wait for risk → 2. React → 3. Fix | 1. Identify → 2. Analyze → 3. Plan → 4. Track → 5. Control |
| **Resource Allocation** | Resources found and applied when risk strikes | Resources allocated based on risk priority |
| **Management Style** | Crisis management | Planned, controlled management |
| **Advantages** | No upfront cost; simple approach | Avoids crises; lower long-term cost; systematic |
| **Disadvantages** | Expensive when risks materialize; unpredictable outcomes; high stress | Upfront cost; requires expertise; may over-plan |
| **Use Cases** | Small projects; low-risk situations; most software teams (unfortunately) | Large projects; safety-critical; regulated industries |
| **Exam Distinction** | Reactive = "fire-fighting" | Proactive = "fire prevention" |

---

## 14. LOC vs Function Points (Estimation Methods)

| Aspect | Lines of Code (LOC) | Function Points (FP) |
|--------|-------------------|---------------------|
| **Purpose** | Measure software size by counting source code lines | Measure software size based on functionality delivered |
| **Unit** | Lines of code (LOC) | Function Points (FP) |
| **Language Dependency** | Highly dependent on programming language | Language-independent |
| **Measurement** | Count every line except blanks and comments | Count 5 information domain types (EI, EO, EQ, ILF, EIF) |
| **Complexity** | Simple to count; hard to compare across languages | Complex to count; comparable across languages |
| **When Used** | When language is known; historical LOC data available | Early in development; language not yet chosen |
| **Conversion** | Direct measurement | FP × Language Factor = LOC |
| **Productivity Metric** | LOC per person-month (LOC/pm) | FP per person-month (FP/pm) |
| **Advantages** | Easy to understand and count; widely used; concrete measure | Language-independent; focuses on functionality; better for early estimation |
| **Disadvantages** | Language-dependent; verbose code appears more productive; late measurement | Complex to count; subjective weighting; requires training |
| **Use Cases** | After language selection; team productivity tracking; project comparison | Early project estimation; cross-language comparison; vendor evaluation |
| **Exam Distinction** | LOC = "how much code" (implementation-focused) | FP = "how much functionality" (requirements-focused) |

---

## 15. Product Standards vs Process Standards

| Aspect | Product Standards | Process Standards |
|--------|------------------|-------------------|
| **Purpose** | Define quality criteria for software deliverables | Define how development activities should be conducted |
| **Focus** | The "what" (deliverables) | The "how" (activities) |
| **Examples** | Documentation standards, coding standards, naming conventions | Development lifecycle, review processes, testing procedures |
| **Scope** | Applied to software artifacts (code, docs, designs) | Applied to development activities and workflows |
| **Enforcement** | Checked during reviews and inspections | Followed throughout development |
| **Advantages** | Consistent deliverable quality; clear expectations | Consistent process execution; predictable outcomes |
| **Disadvantages** | May stifle creativity; overhead for small projects | Bureaucratic overhead; may not fit all projects |
| **Use Cases** | Code reviews, documentation audits, compliance checks | Project management, quality assurance, team coordination |
| **Exam Distinction** | Product = standards for artifacts | Process = standards for activities |

---

## 16. CPM vs PERT

| Aspect | CPM (Critical Path Method) | PERT (Program Evaluation and Review Technique) |
|--------|--------------------------|----------------------------------------------|
| **Full Name** | Critical Path Method / Critical Path Analysis | Program Evaluation and Review Technique |
| **Focus** | Deterministic activity durations | Probabilistic activity durations |
| **Duration Estimation** | Single estimated duration per activity | Three estimates: optimistic, most likely, pessimistic |
| **Time Estimate** | Exact (known duration) | Expected = (O + 4M + P) / 6 |
| **Best For** | Projects with known, predictable activities | Projects with uncertain activity durations |
| **Network Type** | Activity-on-Arrow (AOA) or Activity-on-Node (AON) | Activity-on-Arrow (AOA) |
| **Output** | Critical path and float values | Expected completion time and probability analysis |
| **Risk Analysis** | Limited | Includes probability of completion by certain date |
| **Advantages** | Simple; clear identification of critical activities | Handles uncertainty; provides probability estimates |
| **Disadvantages** | Doesn't account for uncertainty | More complex; requires statistical knowledge |
| **Use Cases** | Construction, manufacturing, well-defined projects | R&D, software projects, uncertain environments |
| **Exam Distinction** | CPM = deterministic (one duration) | PERT = probabilistic (three durations) |

---

## 17. Total Float vs Free Float

| Aspect | Total Float (TF) | Free Float (FF) |
|--------|-----------------|-----------------|
| **Purpose** | Amount of time an activity can be delayed without delaying project finish | Amount of time an activity can be delayed without delaying early start of successor |
| **Formula** | TF = LF - EF or TF = LS - ES | FF = MIN(ES_successor) - ES_activity - Duration_activity |
| **Scope** | Project-level impact | Activity-level impact |
| **Critical Path** | TF = 0 for critical path activities | FF = 0 for critical path activities |
| **Non-Critical Activities** | TF > 0; can be delayed without affecting project end date | FF ≤ TF; may be zero even if TF > 0 |
| **Resource Implications** | Can be used for resource leveling | Available for local scheduling flexibility |
| **Calculation** | After both forward and backward pass | After forward pass only |
| **Advantages** | Shows scheduling flexibility at project level | Shows immediate flexibility without cascading delays |
| **Disadvantages** | Using TF may delay other non-critical activities | Limited flexibility; may not account for all dependencies |
| **Use Cases** | Project scheduling; resource allocation; risk assessment | Activity scheduling; day-to-day management |
| **Exam Distinction** | TF = "flexibility for the project" | FF = "flexibility for the next activity" |

---

## 18. Risk Components (Performance vs Cost vs Support vs Schedule)

| Component | Description | Impact if Risk Materializes | Example |
|-----------|-------------|---------------------------|---------|
| **Performance Risk** | Degree of uncertainty that product will meet requirements and be fit for intended use | System fails to meet requirements; mission failure; significant degradation | Software doesn't meet response time requirements |
| **Cost Risk** | Degree of uncertainty that project budget will be maintained | Budget overrun; increased costs; financial shortages | Project costs exceed budget by 50% |
| **Support Risk** | Degree of uncertainty that software will be easy to correct, adapt, and enhance | Non-responsive or unsupportable software; maintenance nightmare | Code is unmaintainable; no documentation |
| **Schedule Risk** | Degree of uncertainty that project schedule will be maintained | Schedule delays; missed deadlines; unachievable schedule | Project delivered 6 months late |

**Impact Levels (for all components):**
- Negligible: Minor inconvenience
- Marginal: Some degradation, recoverable
- Critical: Significant degradation, questionable success
- Catastrophic: Mission failure, unacceptable losses

**Exam Tip:** The four components form a matrix with risk categories (Project, Technical, Business) for impact assessment.

---

## 19. XP vs Traditional Development

| Aspect | XP (Extreme Programming) | Traditional Development |
|--------|-------------------------|------------------------|
| **Team** | Self-organizing, whole team (customer included) | Hierarchical (analyst → designer → coder → tester → PM) |
| **Requirements** | User stories written by customers on index cards | Requirements captured by analyst, verified with customer |
| **Iterations** | Short cycles (1-4 weeks); working software each iteration | Long iterations (2-3 months); first iteration is design |
| **Acceptance Tests** | Written during iteration; easy for all to read | Written at initial level; used at end |
| **Programming** | Pair programming (two programmers, one workstation) | Individual coding assigned by team lead |
| **Testing** | Test-Driven Development (TDD): test first, code second | Test cases developed at prototype approval; QA tests code |
| **Ownership** | Collective code ownership (everyone works on everything) | Manager is responsible; individual module ownership |
| **Integration** | Continuous integration (multiple times per day) | Integration at end of module/project |
| **Pace** | Sustainable pace (no overtime; marathon not sprint) | 80/20 rule (burst then moderate then burst) |
| **Workspace** | Open workspace (collaborative tables, charts on walls) | Separate cubicles for each team member |
| **Design** | Simple design; evolves each iteration | Upfront architecture for whole project |
| **Refactoring** | Continuous (every hour/half-hour) | At end of project; initiated by QA team |
| **Documentation** | Light documentation; only when immediate need exists | Intensive documentation of diagrams and specifications |
| **Task Allocation** | Team selects tasks from backlog | PM/team lead assigns tasks |
| **Progress Tracking** | Burndown chart (daily remaining work) | Percentage of tasks completed |
| **Status Meetings** | Daily stand-up (3 things: done, planned, blocked) | Weekly meetings; everyone reports to PM |
| **Status Display** | Status board ("What's Working Well" / "What's Not Working") | Project status shown by number of tasks completed |

---

## 20. Risk Categories (Project vs Technical vs Business)

| Aspect | Project Risks | Technical Risks | Business Risks |
|--------|--------------|----------------|----------------|
| **Purpose** | Threaten the project plan | Threaten quality and timeliness | Threaten viability of software |
| **Focus** | Schedule, budget, resources | Technology, complexity, quality | Market, competition, strategy |
| **Impact if Real** | Schedule slip; cost increase | Implementation difficult or impossible | Product may not be viable |
| **Examples** | Staff turnover; unrealistic deadlines; scope creep | New technology; complex algorithms; integration issues | Market changes; competitor products; budget cuts |
| **Sub-categories** | Known, predictable, unpredictable risks | Technology maturity, complexity, dependencies | Market risk, strategic risk, sales risk, management risk, budget risk |
| **Assessment** | Plan-based analysis; historical data | Technical prototyping; expert judgment | Market research; business case analysis |
| **Mitigation** | Better planning; contingency buffers; resource allocation | Proof of concept; incremental integration; fallback technology | Market analysis; stakeholder engagement; financial planning |
| **Advantages of Identification** | Prevents delays and overruns | Prevents quality issues and rework | Prevents wasted investment |
| **Disadvantages if Ignored** | Project failure; budget overrun | Product failure; unusable system | Business failure; lost market opportunity |
| **Use Cases** | Project management; resource planning; scheduling | Architecture design; technology selection; quality assurance | Business case development; strategic planning; investment decisions |
| **Exam Distinction** | Project = "Can we deliver on time/budget?" | Technical = "Can we build it?" | Business = "Should we build it?" |

---

## Quick Reference: Key Mnemonics

| Concept | Mnemonic | Memory Aid |
|---------|----------|------------|
| Coupling (worst→best) | **CCCS D** | Content, Common, Control, Stamp, Data |
| Cohesion (best→worst) | **FSCPTLC** | Functional, Sequential, Communicational, Procedural, Temporal, Logical, Coincidental |
| Agile Values | **IWC R** | Individuals, Working software, Customer collaboration, Responding to change |
| V&V | **"Are we building the product right?" (V)** vs **"Are we building the right product?" (V)** | Verification = spec conformance; Validation = user satisfaction |
| Risk Components | **PCSS** | Performance, Cost, Support, Schedule |
| Risk Categories | **PTB** | Project, Technical, Business |
| Waterfall Phases | **RDIIO** | Requirements, Design, Implementation, Integration, Operation |
| Testing Stages | **DRU** | Development, Release, User |
