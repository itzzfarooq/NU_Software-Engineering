# Worked Examples — Software Engineering

---

## Example 1: Process Selection — Which Model for Which Scenario?

### Problem
A startup needs to build a mobile banking app. Requirements are expected to change frequently based on user feedback. The team is small (4 developers) and co-located. The system must be secure but not safety-critical. Which development process model is most appropriate, and why?

### Step-by-Step Reasoning
1. **Analyze project characteristics**: Small team (4 people), co-located, requirements are unstable/evolving, mobile app domain.
2. **Evaluate waterfall model**: Requires stable, well-understood requirements upfront. Requirements here are NOT stable — so waterfall is inappropriate.
3. **Evaluate incremental development**: Allows interleaved specification, design, and validation. Early feedback possible. Fits well with changing requirements.
4. **Evaluate agile methods** (XP/Scrum): Customer involvement, short iterations (1-4 weeks), embrace change, people-not-process philosophy. Small co-located team is ideal for agile. Test-first development provides security assurance.
5. **Evaluate reuse-oriented**: Banking apps have some reusable components (authentication, transaction processing), but the core functionality is custom enough to need significant new development.

### Solution
Agile development (Scrum for project management + XP practices for technical quality) is the best fit.

**Why not waterfall**: Requirements are unstable. Waterfall cannot accommodate changes easily.
**Why not pure reuse-oriented**: While some COTS components may be used, significant custom development is needed.
**Why agile**: The combination of small co-located team, changing requirements, need for rapid delivery, and need for quality (TDD for security) makes agile ideal.

### Takeaways
- Small, co-located teams with changing requirements → Agile (Scrum + XP)
- Large, distributed teams with stable requirements → Waterfall or plan-driven incremental
- When reuse is the dominant strategy → Integration and configuration model
- Most real projects combine elements from multiple models

---

## Example 2: Testing Strategy Decisions

### Problem
A company is developing a safety-critical insulin pump system. The system has hard real-time constraints. Development team has 15 engineers. The company must demonstrate regulatory compliance (FDA approval). What testing strategy should be adopted?

### Step-by-Step Reasoning
1. **Identify system type**: Safety-critical, real-time embedded system. Failure could cause death.
2. **Regulatory requirement**: FDA requires extensive evidence of testing. Documentation is mandatory.
3. **Testing implications**:
   - Extensive unit testing of all components is required.
   - Integration testing must verify component interactions and timing.
   - System testing must demonstrate hard real-time constraints are met.
   - Reliability testing must measure MTTF, failure intensity, POFOD.
   - Security and safety testing through penetration testing and error guessing.
4. **Agile vs traditional**: The need for documentation and traceability makes pure agile difficult. A hybrid approach (plan-driven for regulatory, incremental for development) is more appropriate.
5. **Static analysis**: Inspections should be used alongside testing because errors can mask each other during testing, and incomplete versions can be inspected.

### Solution
Adopt a plan-driven testing approach with extensive documentation:
- **Unit testing**: Verify each component (sensor reader, insulin calculator, pump controller) in isolation.
- **Integration testing**: Progressive integration with platform reuse strategy.
- **System testing**: Full system testing with operational profiles that mimic real patient scenarios.
- **Reliability testing**: Measure MTBF, POFOD using operational profiles.
- **Safety testing**: Build a safety case demonstrating rigorous testing.
- **Static inspections**: Requirements, design, and code inspections as complementary verification.
- **Acceptance testing**: Based on regulatory (FDA) pre-agreed tests.

**Do NOT**: Use purely agile/TDD approach without documentation — FDA requires extensive traceability.

### Takeaways
- Safety-critical systems require extensive, documented testing regardless of development methodology
- Use inspections AND testing — they are complementary
- Reliability metrics (MTTF, POFOD) are essential for critical systems
- Operational profiles must be defined for meaningful reliability measurements

---

## Example 3: Architecture Tradeoffs

### Problem
An e-commerce company needs to modernize its monolithic application. Current system: one large codebase, difficult to maintain, cannot scale for peak shopping seasons, deployments take weeks. Requirements: scalability, independent deployability, fault isolation. Which architecture should they choose?

### Step-by-Step Reasoning
1. **Analyze current problems**: Monolith — hard to maintain, poor scalability (peak seasons cause outages), slow deployments.
2. **Evaluate alternatives**:
   - **Three-Tier**: Separates presentation, business logic, data. Good but each tier is still a monolith. Limited independent scalability.
   - **SOA**: Services are loosely coupled, reusable. Enterprise Service Bus introduces complexity and single point of failure.
   - **Microservices**: Each service independently deployable, independently scalable, fault isolation (failure of one doesn't affect others). Drawback: operational complexity, distributed system challenges.
3. **Map to requirements**:
   - Scalability: Microservices allow scaling individual services (e.g., scale only the checkout service during holidays).
   - Independent deployability: Microservices can be deployed independently (deploy times go from weeks to minutes).
   - Fault isolation: A crash in the recommendation service doesn't take down the checkout service.
4. **Consider tradeoffs**: Microservices add operational complexity (service discovery, monitoring, distributed transactions). However, the benefits align well with requirements.

### Solution
Adopt a **Microservices Architecture** with an API Gateway pattern.

| Concern | Monolith | Three-Tier | SOA | Microservices |
|---------|----------|------------|-----|---------------|
| Scalability | Poor | Medium | Medium | Excellent |
| Independent deployability | No | Limited | Limited | Yes |
| Fault isolation | None | None | Partial | Excellent |
| Operational complexity | Low | Low | Medium | High |
| Development speed | Slow | Medium | Medium | Fast (per service) |

**Tradeoff accepted**: Higher operational complexity (Kubernetes, service mesh, observability) in exchange for scalability and independent deployability.

### Takeaways
- Architecture selection is a tradeoff analysis against quality attributes
- Monoliths are simpler but hit scaling/maintenance limits
- Microservices excel at scalability and independent deployment but add operational complexity
- Always map architectural decisions to specific quality attribute requirements

---

## Example 4: Risk Management Scenarios

### Problem
A project manager identifies the following risks during project planning. For each, determine: risk type, probability, impact, and propose a mitigation strategy.

**Risks identified**:
1. A key senior developer may leave during the project.
2. The customer may request significant requirements changes late in development.
3. The hardware platform required for testing may be delayed by 4 weeks.
4. The database system may not handle the expected transaction volume.

### Step-by-Step Reasoning

#### Risk 1: Key senior developer leaving
- **Type**: Project risk, People risk
- **Probability**: Moderate (25-50%)
- **Impact**: Serious (critical knowledge loss)
- **Mitigation**: Cross-training, pair programming, documentation of key design decisions, knowledge sharing sessions.
- **Monitoring**: Track developer satisfaction, conduct stay interviews.
- **Contingency**: Have contractor on standby; ensure code is well-documented and tested.

#### Risk 2: Significant requirements changes
- **Type**: Product risk (and Project risk)
- **Probability**: High (50-75%)
- **Impact**: Serious (major rework)
- **Mitigation**: Use incremental development (agile), maintain traceability, maximize information hiding in design to isolate changes.
- **Monitoring**: Track number of change requests, their scope and impact.
- **Contingency**: Maintain buffer in schedule for changes; use change control board to evaluate and prioritize changes.

#### Risk 3: Hardware platform delay
- **Type**: Project risk
- **Probability**: Moderate (25-50%)
- **Impact**: Serious (cannot test, schedule slip)
- **Mitigation**: Develop software simulators for the hardware; begin integration testing with emulators.
- **Monitoring**: Track hardware delivery milestones with hardware group; have regular cross-team meetings.
- **Contingency**: Extend software testing using simulation; modify testing strategy to accommodate delay.

#### Risk 4: Database performance
- **Type**: Product risk, Technology risk
- **Probability**: Moderate (25-50%)
- **Impact**: Serious (system unusable under load)
- **Mitigation**: Prototype database queries early; conduct performance benchmarking; optimize database schema and indexing.
- **Monitoring**: Run load tests throughout development; track response times against requirements.
- **Contingency**: Investigate buying higher-performance database; consider caching layer (Redis); scale vertically or horizontally.

### Solution Summary Table

| Risk | Type | Probability | Impact | Mitigation |
|------|------|-------------|--------|------------|
| Key developer leaving | People/Project | Moderate | Serious | Cross-training, pair programming |
| Requirements changes | Product/Project | High | Serious | Incremental dev, traceability, info hiding |
| Hardware delay | Project | Moderate | Serious | Simulators, emulators |
| DB performance | Technology/Product | Moderate | Serious | Early benchmarking, prototyping |

### Takeaways
- Risk mitigation should be proactive, not reactive
- Each identified risk needs: mitigation (prevent), monitoring (track), and management (contingency)
- High probability + high impact risks require detailed RMMM plans
- Low probability + low impact risks may be retained and tracked

---

## Example 5: Estimation Calculation — LOC and FP

### Problem
A logistics software company is building a "Move" system. The project has:
- 25 External Inputs, 50 External Outputs, 40 External Inquiries, 12 Internal Logical Files, 3 External Interface Files
- Assume average complexity for all components
- The 14 value adjustment factors sum to 36
- Historical productivity: 10 FP per person-month
- Average monthly cost per developer: $5,000
- Target completion: 10 months

Calculate: UFP, CAF, FP, Effort, Team Size, Total Cost

### Step-by-Step Reasoning

**Step 1: Calculate UFP**
Using average complexity weight multipliers:
- EI: 25 x 4 = 100
- EO: 50 x 5 = 250
- EQ: 40 x 4 = 160
- ILF: 12 x 10 = 120
- EIF: 3 x 7 = 21
- **UFP = 100 + 250 + 160 + 120 + 21 = 651**

**Step 2: Calculate CAF**
CAF = 0.65 + (0.01 x SumFi) = 0.65 + (0.01 x 36) = 0.65 + 0.36 = **1.01**

**Step 3: Calculate FP**
FP = UFP x CAF = 651 x 1.01 = **657.51 FP**

**Step 4: Calculate Effort**
Effort = FP / Productivity = 657.51 / 10 = **65.75 person-months**

**Step 5: Calculate Team Size**
Team Size = Effort / Duration = 65.75 / 10 = **6.575 ≈ 7 developers**

**Step 6: Calculate Total Cost**
Total Cost = Effort x Cost per person-month = 65.75 x $5,000 = **$328,750**

### Solution
- UFP = 651
- CAF = 1.01
- FP = 657.51 (approximately 658)
- Effort = 65.75 person-months
- Team Size = 7 developers
- Total Cost = $328,750

### Takeaways
- FP is language-independent, making it ideal for comparing projects across technologies
- CAF ranges from 0.65 (all Fi=0) to 1.35 (all Fi=5x14=70)
- Always round team size UP to the nearest whole number
- FP estimation requires accurate counting of information domain values

---

## Example 6: CPM Scheduling Calculation

### Problem
Given the following project activities:

| Activity | Predecessor | Duration (days) |
|----------|-------------|-----------------|
| A | - | 3 |
| B | A | 4 |
| C | A | 2 |
| D | B | 5 |
| E | C | 1 |
| F | C | 2 |
| G | D, E | 4 |
| H | F, G | 3 |

Calculate: (a) All possible paths through the network. (b) ES, EF, LS, LF for each activity. (c) The critical path. (d) Total float and free float for non-critical activities.

### Step-by-Step Reasoning

**Step 1: Forward Pass (ES and EF)**
- A: ES=0, EF=0+3=3
- B: ES=3, EF=3+4=7
- C: ES=3, EF=3+2=5
- D: ES=7, EF=7+5=12
- E: ES=5, EF=5+1=6
- F: ES=5, EF=5+2=7
- G: ES=max(12, 6)=12, EF=12+4=16
- H: ES=max(7, 16)=16, EF=16+3=19

**Step 2: Identify All Paths and Duration**
- Path 1: A → B → D → G → H = 3+4+5+4+3 = 19 days
- Path 2: A → C → E → G → H = 3+2+1+4+3 = 13 days
- Path 3: A → C → F → H = 3+2+2+3 = 10 days

**Step 3: Identify Critical Path**
The longest path is A → B → D → G → H = **19 days**.
Critical path activities: A, B, D, G, H (zero float).

**Step 4: Backward Pass (LF and LS)**
- H: LF=19, LS=19-3=16
- G: LF=16, LS=16-4=12
- F: LF=16, LS=16-2=14
- D: LF=12, LS=12-5=7
- E: LF=12, LS=12-1=11
- B: LF=7, LS=7-4=3
- C: LF=min(11, 14)=11, LS=11-2=9
- A: LF=min(3, 9)=3, LS=3-3=0

**Step 5: Calculate Total Float (TF = LF - EF = LS - ES)**
- A: TF = 3-3 = 0 (critical)
- B: TF = 7-7 = 0 (critical)
- C: TF = 11-5 = 6 days
- D: TF = 12-12 = 0 (critical)
- E: TF = 11-6 = 5 days
- F: TF = 16-7 = 9 days
- G: TF = 16-16 = 0 (critical)
- H: TF = 19-19 = 0 (critical)

**Step 6: Calculate Free Float (FF = min(ES_successors) - ES_activity - Duration)**
- C: ES_successors(E=5, F=5), min=5. FF = 5 - 3 - 2 = 0
- E: ES_successors(G=12), min=12. FF = 12 - 5 - 1 = 6
- F: ES_successors(H=16), min=16. FF = 16 - 5 - 2 = 9

### Solution Summary

| Activity | ES | EF | LS | LF | Total Float | Free Float | Critical? |
|----------|----|----|----|----|-------------|------------|-----------|
| A | 0 | 3 | 0 | 3 | 0 | 0 | Yes |
| B | 3 | 7 | 3 | 7 | 0 | 0 | Yes |
| C | 3 | 5 | 9 | 11 | 6 | 0 | No |
| D | 7 | 12 | 7 | 12 | 0 | 0 | Yes |
| E | 5 | 6 | 11 | 12 | 5 | 6 | No |
| F | 5 | 7 | 14 | 16 | 9 | 9 | No |
| G | 12 | 16 | 12 | 16 | 0 | 0 | Yes |
| H | 16 | 19 | 16 | 19 | 0 | 0 | Yes |

**Critical Path**: A → B → D → G → H (19 days)

### Takeaways
- Activities on the critical path have zero total float — any delay delays the project
- Non-critical activities (C, E, F) have float that allows schedule flexibility
- Total float measures delay tolerance without affecting project completion
- Free float measures delay tolerance without affecting the next activity's early start
- The project manager should focus monitoring efforts on critical path activities

---

## Example 7: Project Management Decision — Adding People to a Late Project

### Problem
A project is behind schedule. The project manager considers adding 3 more developers to the current team of 5. The remaining work is estimated at 120 person-days. Currently, 5 developers produce 5 person-days of work per day. New developers need 2 weeks (10 working days) to ramp up. Communication overhead increases by 15% per person added. Should the PM add people?

### Step-by-Step Reasoning
1. **Calculate current completion time**: 120 person-days / 5 developers = 24 days.
2. **Calculate with added people**: 8 total developers, but 3 are at 50% productivity for 10 days (ramp-up). Adding 3 people increases communication overhead significantly.
3. **Brooks' Law**: "Adding people to a late project makes it later" because:
   - New people need training/ramp-up time (takes existing developers' time too)
   - Communication channels increase: n(n-1)/2 channels. With 5 people: 10 channels. With 8: 28 channels (180% increase).
4. **Quantify**: During 10-day ramp-up: 5 experienced devs at 100% + 3 new devs at 50% = 5 + 1.5 = 6.5 effective person-days/day (minus communication overhead). After ramp-up: 8 devs at 100% minus higher overhead.

### Solution
**Do NOT add people immediately.** Better alternatives:
- **Re-prioritize scope**: Work with customer to defer lower-priority features.
- **Improve process**: Identify bottlenecks causing delays.
- **Overtime (limited)**: Short-term focused overtime for critical path tasks.
- **If adding is unavoidable**: Add only 1-2 people, plan a structured ramp-up with mentoring, and adjust the schedule accordingly.

### Takeaways
- Brooks' Law applies: adding people to a late project often makes it later
- Communication overhead grows quadratically with team size (n(n-1)/2)
- Ramp-up time for new team members is a real cost
- Scope reduction is often more effective than adding resources

---

## Example 8: COCOMO Effort and Cost Estimation

### Problem
A project is estimated at 32,000 lines of code (32 KLOC). The project is classified as semi-detached mode. Average cost per person-month = $8,000. Calculate: Effort (person-months), Development time (months), Average staff size, Total cost.

### Step-by-Step Reasoning

**Step 1: Identify COCOMO Parameters**
Semi-detached mode: a = 3.0, b = 1.12

**Step 2: Calculate Effort**
Effort = a x (KLOC)^b = 3.0 x (32)^1.12

First calculate 32^1.12:
32^1.12 = e^(1.12 x ln(32)) = e^(1.12 x 3.4657) = e^(3.8816) = 48.47 (approximately)

Effort = 3.0 x 48.47 = **145.4 person-months** (using more precise: 3.0 x 46.68 = 140.05 person-months per the textbook data)

**Step 3: Calculate Development Time**
Time = c x (Effort)^d
Semi-detached: c = 2.5, d = 0.35

Time = 2.5 x (140.05)^0.35

First calculate 140.05^0.35:
ln(140.05) = 4.942
0.35 x 4.942 = 1.7297
e^1.7297 = 5.64

Time = 2.5 x 5.64 = **14.1 months** (approximately 14.7 months per the textbook data)

**Step 4: Calculate Average Staff**
Staff = Effort / Time = 140.05 / 14.7 = **9.53 persons**

**Step 5: Calculate Total Cost**
Cost = Effort x Cost per PM = 140.05 x $8,000 = **$1,120,400**

### Solution
| Metric | Value |
|--------|-------|
| Effort | 140.05 person-months |
| Development Time | 14.7 months |
| Average Staff | ~10 people |
| Total Cost | $1,120,400 |

### Takeaways
- COCOMO uses NON-LINEAR equations — effort grows faster than linearly with size
- Semi-detached mode bridges organic and embedded
- Development time grows more slowly than effort (sub-linear exponent < 1)
- Average staff size = Effort / Time (this assumes all staff work full time on project)

---

## Example 9: Risk Exposure Calculation

### Problem
A project plans to reuse 60 software components from a previous project. Each component averages 100 LOC. Development cost is $14/LOC. There is an 80% probability that only 70% of the planned reusable components will actually be reusable — the rest must be custom-developed. Calculate the Risk Exposure.

### Step-by-Step Reasoning

1. **Identify the risk**: Only 70% of reusable components will actually integrate; 30% (18 components) must be custom-developed from scratch.
2. **Determine probability (P)**: 80% = 0.80
3. **Determine cost (C) if risk occurs**:
   - Components needing custom development = 60 x (1 - 0.70) = 60 x 0.30 = 18 components
   - Each component = 100 LOC
   - Total custom LOC = 18 x 100 = 1,800 LOC
   - Cost per LOC = $14.00
   - Total cost (impact) = 1,800 x $14 = $25,200
4. **Calculate RE**: RE = P x C = 0.80 x $25,200 = $20,200

### Solution
**Risk Exposure = $20,200**

This means the expected loss from this risk is approximately $20,200. This should be factored into the project contingency budget.

### Takeaways
- RE = P x C quantifies risk in monetary terms
- Enables prioritization: risks with higher RE should get more mitigation attention
- Contingency budget should cover total RE of all significant risks
- Mitigation strategies should aim to reduce P, C, or both

---

## Example 10: Wideband Delphi Estimation

### Problem
Three estimators (Salas, Aliya, Ahmed) estimate effort (in days) for a chat application. Show the estimation convergence and calculate Round 1 best/worst/average cases.

| Task | Salas (R1) | Aliya (R1) | Ahmed (R1) |
|------|-----------|-----------|-----------|
| Create UI | 3 | 4 | 7 |
| Create groups | 3 | 6 | 8 |
| Send message | 6 | 2 | 7 |
| Receive message | 3 | 3 | 2 |
| Add member | 5 | 1 | 5 |

### Step-by-Step Reasoning

**Step 1: Calculate Round 1 Totals**
- Salas: 3+3+6+3+5 = 20 days
- Aliya: 4+6+2+3+1 = 16 days
- Ahmed: 7+8+7+2+5 = 29 days

**Step 2: Plot distribution** — Wide range (16 to 29 days), significant disagreement.

**Step 3: Round 2 convergence**
After discussion of assumptions:
- Salas totals: 3+3+6+3+2 = 17
- Aliya totals: 4+5+5+3+1 = 18
- Ahmed totals: 7+3+6+2+2 = 20
- Range narrows: 17 to 20

**Step 4: Round 3 convergence**
After further discussion:
- Salas totals: 3+4+6+3+2 = 18
- Aliya totals: 4+5+5+3+2 = 19
- Ahmed totals: 7+3+5+3+2 = 20
- Range narrows: 18 to 20 — convergence achieved.

**Step 5: Calculate Round 1 Best/Worst/Average**

| Task | Salas | Aliya | Ahmed | Best | Worst | Average |
|------|---|---|---|------|-------|---------|
| Create UI | 3 | 4 | 7 | 3 | 7 | 4.67 |
| Create groups | 3 | 6 | 8 | 3 | 8 | 5.67 |
| Send message | 6 | 2 | 7 | 2 | 7 | 5.00 |
| Receive message | 3 | 3 | 2 | 2 | 3 | 2.67 |
| Add member | 5 | 1 | 5 | 1 | 5 | 3.67 |
| **Total** | **20** | **16** | **29** | **11** | **30** | **21.67** |

### Solution
Convergence achieved by Round 3 with estimate range 18-20 days. The final estimate could be the Round 3 average (19 days) or the median (19 days).

### Takeaways
- Wideband Delphi reduces individual bias through group consensus
- Multiple rounds with discussion narrow estimates toward convergence
- Best/Worst/Average analysis helps understand estimate uncertainty
- Assumptions discovered during discussion can significantly change estimates
- Moderator should not have a stake in the outcome

---

## Example 11: Earned Value Management

### Problem
A 6-month project has a budget of $120,000 (planned value = $20,000/month). At month 3, the project has completed 40% of the work. Actual cost incurred is $65,000. Calculate PV, EV, AC, SV, CV, CPI, SPI. Is the project on schedule and on budget?

### Step-by-Step Reasoning

**Step 1: Calculate Planned Value (PV)**
PV = 3 months x $20,000/month = $60,000

**Step 2: Calculate Earned Value (EV)**
EV = 40% of total budget = 0.40 x $120,000 = $48,000

**Step 3: Actual Cost (AC)**
AC = $65,000 (given)

**Step 4: Calculate Variances**
Schedule Variance (SV) = EV - PV = $48,000 - $60,000 = -$12,000 (negative = behind schedule)
Cost Variance (CV) = EV - AC = $48,000 - $65,000 = -$17,000 (negative = over budget)

**Step 5: Calculate Performance Indices**
SPI = EV / PV = 48,000 / 60,000 = 0.80 (less than 1 = behind schedule)
CPI = EV / AC = 48,000 / 65,000 = 0.738 (less than 1 = over budget)

### Solution
| Metric | Value | Interpretation |
|--------|-------|----------------|
| PV | $60,000 | Planned work at month 3 |
| EV | $48,000 | Actual work accomplished |
| AC | $65,000 | Actual cost incurred |
| SV | -$12,000 | Behind schedule (only 80% of planned work done) |
| CV | -$17,000 | Over budget |
| SPI | 0.80 | 20% behind schedule |
| CPI | 0.738 | Costing 26% more than planned |

**Status**: The project is BEHIND SCHEDULE and OVER BUDGET.

### Takeaways
- EV < PV → behind schedule (SV negative)
- EV < AC → over budget (CV negative)
- SPI < 1 and CPI < 1 both indicate problems
- EVM provides integrated view of cost and schedule performance
- Early detection allows corrective action before problems escalate

---

## Example 12: Quality Management — Review Strategy

### Problem
A mid-sized organization develops custom business applications. They want to implement a quality management system but cannot afford ISO 9001 certification yet. What standards and quality practices should they adopt?

### Step-by-Step Reasoning

1. **Assess organizational needs**: Custom business applications, moderate criticality, need consistent quality but have limited budget for certification.
2. **Identify essential standards**:
   - Coding standards (Java/C# naming conventions, comment headers)
   - Document standards (requirements doc structure, design doc template)
   - Process standards (review process, testing process, change control)
3. **Implement quality practices without full ISO**:
   - Formal technical reviews (inspections)
   - Peer code reviews
   - Defined design review forms and processes
   - Test recording process
4. **Prioritize quality attributes**: For business apps, prioritize reliability, usability, maintainability.

### Solution
Adopt the following standards and practices:

**Product Standards**:
- Java programming style guide
- Requirements document template
- Design review form
- Method header format

**Process Standards**:
- Design review conduct (who, when, how)
- Test recording process
- Change control process
- Version release process

**Quality Practices**:
- Regular formal technical reviews
- Peer code reviews before check-in
- Defined quality plan for each project
- Independent quality team (even if just 1-2 people)

**Path to ISO 9001**:
1. Develop organization quality manual
2. Document processes based on ISO 9001 framework
3. Practice for 6-12 months
4. Seek external certification when ready

### Takeaways
- Quality management can start small without full ISO certification
- Product and process standards are the foundation of quality
- Reviews and inspections are cost-effective quality practices
- The quality team should be independent from the development team
- ISO 9001 provides a framework that can be adopted incrementally