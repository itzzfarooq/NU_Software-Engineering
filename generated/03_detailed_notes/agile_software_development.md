# Agile Software Development — Detailed Exam Notes

---

## Topic Overview

Agile software development emerged in the late 1990s as a response to the slow, rigid, plan-driven methodologies that dominated the 1980s and 1990s. It prioritizes rapid delivery, customer collaboration, and the ability to embrace changing requirements. Agile is not a single method but a family of approaches (XP, Scrum, etc.) that share a common philosophy rooted in the Agile Manifesto (2001). This topic covers the motivation for agile, its core values and principles, key practices (especially Extreme Programming and Scrum), and how agile compares to traditional plan-driven development across 17 dimensions.

---

## Why This Topic Exists

Businesses today operate in fast-changing environments. It is practically impossible to produce a stable set of software requirements upfront. Software must evolve quickly to reflect shifting business needs. Traditional plan-driven development (e.g., Waterfall) assumes requirements are stable and can be fully defined early, which leads to late delivery, high rework costs, and misalignment with customer needs. Agile exists to:

- Radically reduce delivery time for working software.
- Accommodate changing requirements without excessive rework.
- Involve customers continuously so the product always reflects real needs.
- Minimize overhead (documentation, process bureaucracy) and focus on working code.

---

## Core Concepts & Definitions

| Term | Definition |
|------|------------|
| **Agile Development** | An iterative approach where specification, design, implementation, and testing are interleaved. The system is developed as a series of increments with stakeholder involvement. |
| **Increment** | A small, working version of the system delivered for evaluation (typically every 1–4 weeks). |
| **Iteration** | A short development cycle (time-boxed) that produces a potentially shippable product increment. |
| **Plan-Driven Development** | Stages (requirements, design, implementation) are planned in advance. Iteration may occur within activities but not across them. |
| **User Story** | A short, simple description of a feature told from the user's perspective. Format: "As a [role], I want [goal] so that [reason]." |
| **Refactoring** | Restructuring code to improve its structure without changing its behavior. Done continuously in agile. |
| **Test-First Development** | Writing an automated test before writing the production code that makes it pass. |
| **Pair Programming** | Two developers work together at one workstation: one types (driver), the other reviews (navigator). |
| **Continuous Integration** | Code is integrated into the main system several times per day; all tests must pass after each integration. |
| **Sprint** | In Scrum, a time-boxed period (2–4 weeks) during which a potentially shippable product increment is created. |
| **Product Backlog** | An ordered list of everything needed in the product, managed by the Product Owner. |
| **Sprint Backlog** | The set of product backlog items selected for a sprint, plus a plan for delivering them. |
| **Burndown Chart** | A visual chart showing remaining work (hours/days) over time in a sprint. |
| **Scrum Master** | Facilitator who protects the team, removes impediments, and ensures Scrum is followed. |
| **Product Owner** | Represents the customer; manages backlog, sets priorities, defines acceptance criteria. |

---

## Agile Manifesto & Principles

### The Agile Manifesto (2001)

> We are uncovering better ways of developing software by doing it and helping others do it. Through this work we have come to value:

| We value (LEFT) | Over (RIGHT) |
|----------------|--------------|
| **Individuals and interactions** | Processes and tools |
| **Working software** | Comprehensive documentation |
| **Customer collaboration** | Contract negotiation |
| **Responding to change** | Following a plan |

> That is, while there is value in the items on the right, we value the items on the left more.

### The 12 Principles of Agile Software

1. **Welcome changing requirements**, even late in development. Agile processes harness change for the customer's competitive advantage.
2. **Deliver working software frequently**, from a couple of weeks to a couple of months, with a preference for the shorter timescale.
3. **Business people and developers work together daily** throughout the project.
4. **Build projects around motivated individuals**. Give them the environment and support they need, and trust them to get the job done.
5. **Face-to-face conversation** is the most efficient and effective method of conveying information.
6. **Working software is the primary measure of progress**.
7. **Sustainable development**: sponsors, developers, and users should be able to maintain a constant pace indefinitely.
8. **Continuous attention to technical excellence and good design** enhances agility.
9. **Simplicity** — the art of maximizing the amount of work not done — is essential.
10. **The best architectures, requirements, and designs emerge from self-organizing teams**.
11. **At regular intervals, the team reflects on how to become more effective**, then tunes and adjusts its behavior.
12. **Customer involvement**: customers should be closely involved throughout development.

### Five Key Principles of Agile Methods

| Principle | Description |
|-----------|-------------|
| Customer involvement | Customers provide and prioritize requirements and evaluate iterations. |
| Incremental delivery | Software is developed in increments; customer decides what goes in each increment. |
| People not process | Team skills are recognized; members choose their own ways of working. |
| Embrace change | System is designed to accommodate changing requirements. |
| Maintain simplicity | Actively eliminate complexity from both software and process. |

---

## Extreme Programming (XP)

XP is the most well-known agile method, developed in the late 1990s by Kent Beck and others. It takes an "extreme" approach to iterative development:

- New versions may be built several times per day.
- Increments are delivered to customers every 2 weeks.
- All tests must run for every build; builds are accepted only if tests pass.

### XP Release Cycle

```
Select user stories for this release
    → Break down stories into tasks
        → Plan release
            → Develop/integrate/test software
                → Release software
                    → Evaluate system
                        → (loops back to story selection)
```

### XP Practices

| Practice | Description |
|----------|-------------|
| **Incremental planning** | Requirements on story cards; release content determined by time available and priority. |
| **Small releases** | Minimal useful functionality first; frequent incremental releases. |
| **Simple design** | Enough design for current requirements only; no gold-plating. |
| **Test-first development** | Automated unit tests written before code (xUnit frameworks like JUnit). |
| **Refactoring** | Continuous code improvement; keep code simple and maintainable. |
| **Pair programming** | Two developers at one workstation; continuous code review. |
| **Collective ownership** | Anyone can change any code; no islands of expertise. |
| **Continuous integration** | Integrate as soon as task is complete; all unit tests must pass. |
| **Sustainable pace** | No overtime; quality and productivity are harmed by long hours. |
| **On-site customer** | A customer representative is full-time team member. |

### Influential XP Practices (Most Widely Adopted)

1. **User stories** for specification
2. **Refactoring**
3. **Test-first development**
4. **Pair programming**

---

## Scrum

Scrum is an agile method focused on **managing the development process** (in contrast to XP's technical focus). Developed by Ken Schwaber and Jeff Sutherland.

### Scrum Principles

| Principle | Description |
|-----------|-------------|
| Controlled chaos | Team decides what to work on and how. |
| Commitment | Team agrees on what can be achieved in a time-box. |
| Information radiator | Visible chart/board showing development state. |
| Time-boxing | All activities have fixed deadlines. |
| Emergent requirements | Requirements emerge during development; focus on delivering a useful system. |
| People not process | Self-organizing team decides its own process. |

### Scrum Roles

| Role | Responsibility |
|------|---------------|
| **Scrum Master** | Facilitates team process, protects from interference, ensures Scrum is followed, resolves problems. |
| **Product Owner** | Represents customer/business, manages backlog, sets priorities, defines acceptance criteria. |
| **Scrum Team** | Self-organizing, cross-functional (5–7 people); delivers potentially shippable increment each sprint. |

### Scrum Events

| Event | Description |
|-------|-------------|
| **Sprint** | Time-boxed period (2–4 weeks) producing a potentially shippable increment. |
| **Sprint Planning** | At start of sprint; team selects stories from product backlog and breaks them into tasks. |
| **Daily Stand-up** | 15-minute daily meeting; each member reports: (1) what was done, (2) what will be done, (3) blockers. |
| **Sprint Review** | Demonstrate completed work to stakeholders. |
| **Sprint Retrospective** | At end of sprint; team reflects on what went well and what could be improved. |

### Scrum Artifacts

| Artifact | Description |
|----------|-------------|
| **Product Backlog** | Ordered list of everything needed in the product; managed by Product Owner. |
| **Sprint Backlog** | Tasks selected for the current sprint; owned and updated daily by the team. |
| **Burndown Chart** | Shows work remaining over time; if it does not trend downward, the team is behind schedule. |

### Scrum Benefits

- Team is empowered to make decisions.
- Team morale improves.
- Customers are involved.
- Daily stand-ups improve communication.
- Sprint backlog makes progress visible.
- Scrum Master protects the team.
- Most important work is done first (prioritized backlog).
- Process is transparent to all stakeholders.

### Scrum Problems

- Scrum Master and Product Owner roles should NOT be combined (creates conflict of interest).
- Imposing Scrum without training/support leads to failure.
- Teams may lack skills/experience for self-organization.
- Teams may lack authority to make decisions.

### Scrum vs XP

| Aspect | Scrum | XP |
|--------|-------|----|
| Focus | **Management** of development process | **Technical practices** of development |
| Primary concern | Project management, team coordination | Code quality, testing, design |
| Key artifacts | Product backlog, sprint backlog, burndown chart | Story cards, test cases, refactored code |
| Roles | Scrum Master, Product Owner, Team | Customer, Developer, Tester (less formal) |
| Complementarity | Provides the framework | Provides the engineering practices |

> **Key exam point**: Scrum and XP are **complementary**, not alternatives. They can (and often are) used together.

---

## Agile vs Traditional — 17 Differences (Detailed Table)

| # | Dimension | Traditional (Plan-Driven) | Agile |
|---|-----------|---------------------------|-------|
| 1 | **Team** | Hierarchical: analyst, designer, coder, tester, architect, team lead, QA manager, PM | Whole team: cross-functional, self-organizing; customer is a team member |
| 2 | **Requirements** | Captured and written by analyst/PM; verified from customer | User stories written BY the customer; a few words on an index card |
| 3 | **Development iteration** | 2–3 month iterations; first iteration is detailed design/plan | 1–4 week short cycles; working software delivered every iteration |
| 4 | **Acceptance tests** | Requirements contracted upfront used as acceptance tests at the end | Written by BA/QA/testers during iteration; once passed, never allowed to fail again |
| 5 | **Programming style** | Assigned by team lead; QA checks errors later | Pair programming: two developers at one workstation, continuous review |
| 6 | **Testing** | Test cases developed after prototype approval; QA team tests | Test-Driven Development (TDD): write failing test first, then code to pass it |
| 7 | **Ownership** | Manager is solely responsible for whole project | Collective ownership: everyone works on all parts; no single owner per module |
| 8 | **Integration** | Done at end of module/project by QA team | Continuous integration: check in and integrate several times per day |
| 9 | **Development pace** | 80/20 principle: fast start, moderate middle, fast finish | Sustainable pace: marathon, not sprint; no overtime allowed |
| 10 | **Workspace** | Separate rooms/cubicles; tasks assigned via PM or software | Open workspace: team works together in one room; walls covered with charts |
| 11 | **Design & architecture** | Entire project designed/architected at the beginning | Simple design: only current iteration's stories considered; design evolves |
| 12 | **Refactoring** | Done at end of project; initiated by QA team | Continuous refactoring: done every hour/half-hour to keep code clean |
| 13 | **Documentation** | Intensive documentation: diagrams, specifications | Light documentation: produce no document unless immediate and significant |
| 14 | **Task allocation** | PM/team lead assigns tasks to individuals | Task selection: team decides/selects how much work to commit to |
| 15 | **Progress monitoring** | By number of tasks completed | Burndown chart: shows remaining work (hours/days) each day |
| 16 | **Status meeting** | Weekly meetings; everyone reports to PM | Daily stand-up (15 min): what was done, what will be done, blockers |
| 17 | **Project status** | Shown by number of tasks completed | Status board: "What's Working Well" / "What's Not Working" poster |

---

## Detailed Explanations

### Why Agile Works

Agile works because it embraces the reality that requirements change. Instead of fighting this (by freezing requirements and planning everything upfront), agile builds change into the process. Short iterations mean feedback is received early and often. Customers see working software every 1–4 weeks, so misunderstandings are caught quickly. The focus on working software over documentation ensures effort goes into what delivers value.

### User Stories in Practice

A user story follows the template:

> **As a** [role], **I want** [goal] **so that** [reason].

Example:
> As a doctor, I want to prescribe medication electronically so that the pharmacy receives the order immediately.

Stories are written on index cards — intentionally brief. They serve as reminders for discussion, not complete specifications. The customer prioritizes stories. The development team estimates effort. Stories essential to the system are "Must Have"; low-priority stories can be postponed.

### The Planning Game

A team-based estimation process:
1. Split stories into tasks.
2. Each team member makes independent estimates.
3. Compare estimates and discuss differences.
4. Work is divided between pairs of developers.
5. Pairs make their own task allocation.
6. Stories not implemented remain in the stack for next iteration.

### Test-First Development (TDD) Lifecycle

```
1. Write a failing unit test → 2. Write code to make it pass → 3. Refactor → (repeat)
```

Benefits:
- Forces thinking about requirements before coding.
- Tests document the code (reducing need for separate documentation).
- Incremental testing: test and code developed together.
- Debugging is easier: when a test fails, the developer knows the cause.

### Refactoring vs Traditional Design

Traditional SE wisdom: Design for change upfront (anticipate and spend effort now to save later).
XP view: Changes cannot be reliably anticipated, so don't bother. Instead, refactor continuously. When a change is needed, the code is already clean and easy to modify.

**Examples of refactoring:**
- Reorganizing a class hierarchy to remove duplicate code.
- Renaming methods/attributes for clarity.
- Replacing inline code with calls to library methods.

**Limitation:** Some changes require architecture refactoring, which is much more expensive.

---

## Relationships to Other Topics

| Related Topic | Relationship |
|---------------|--------------|
| **Requirements Engineering** | Agile uses user stories instead of formal SRS documents. Requirements emerge iteratively. |
| **Software Design** | XP says "simple design" and refactor; traditional says "design upfront." |
| **Software Testing** | Testing is integrated (TDD, continuous integration) rather than a separate phase. |
| **Project Management** | Scrum provides the management framework; traditional PM uses Gantt charts and milestones. |
| **Software Quality** | Quality is built in via pair programming, TDD, and continuous refactoring. |
| **DevOps** | Continuous integration leads naturally to continuous delivery and DevOps practices. |
| **Plan-Driven Methods (Waterfall)** | Agile is the direct alternative; 17 differences above show the contrasts. |
| **System Architecture** | Scaling agile requires more upfront architecture; pure agile deemphasizes it. |

---

## Examples

### Example 1: User Story to Implementation

**Story:** "As a librarian, I want to search for books by ISBN so that I can quickly find a specific title."

**Breakdown into tasks:**
- Task 1: Create search input field (1 day)
- Task 2: Implement ISBN lookup in database (2 days)
- Task 3: Display search results (1 day)
- Task 4: Write unit tests for search (1 day)

**Pair allocation:** Developers A&B take Tasks 1&4; Developers C&D take Tasks 2&3.

### Example 2: TDD Cycle

1. Write test: `testSearchByISBN()` — expects a book object when valid ISBN is passed. Test fails (no code yet).
2. Write minimal code: `searchByISBN(isbn)` — queries database and returns result. Test passes.
3. Refactor: rename variables, extract helper methods, remove duplication.

### Example 3: Scrum Sprint

A 2-week sprint with team of 6:
- **Sprint Planning (Day 1 morning):** Team selects 5 stories from product backlog (priority set by Product Owner). Stories broken into 12 tasks. Team commits.
- **Daily Stand-up (every morning, 15 min):** Each member reports (1) yesterday's work, (2) today's plan, (3) blockers.
- **Sprint Review (Day 14 afternoon):** Team demonstrates working software to stakeholders.
- **Sprint Retrospective (Day 14 late afternoon):** Team discusses what went well, what to improve.

---

## Common Mistakes / Exam Traps

| Trap | Correction |
|------|------------|
| "Agile means no documentation" | Agile means **minimal** documentation — produce documents only when immediate and significant need exists. Some documentation may be legally/contractually required. |
| "Agile has no planning" | Agile plans continuously (release planning, iteration planning, daily stand-ups). Planning is adaptive, not absent. |
| "Scrum and XP are the same thing" | Scrum manages the **process**; XP provides **technical practices**. They are complementary. |
| "Agile works for all projects" | Agile is difficult for large systems, outsourced projects, safety-critical systems requiring extensive documentation, and systems with complex non-functional requirements. |
| "Pair programming is just two people doing one person's job" | Pair programming produces higher quality code, fewer bugs, and better knowledge sharing. It is not a 2x cost — it often saves time on debugging and rework. |
| "Refactoring means rewriting code" | Refactoring is **tiny transformations** that preserve behavior. It is not a rewrite. |
| "In agile, anyone can do anything anytime" | Collective ownership means anyone can change any code, but changes must pass all tests. There is structure. |
| "The Scrum Master manages the team" | The Scrum Master is a **servant-leader/facilitator**, not a traditional manager. The team is self-organizing. |
| "Agile methods emerged in the 2000s" | Agile methods emerged in the **late 1990s**; the Agile Manifesto was published in **2001**. |
| "Customer involvement only at the start and end" | Agile requires **continuous** customer involvement throughout the process. |

---

## Active Recall Questions

1. What are the four values of the Agile Manifesto? (Answer: Individuals & interactions over processes & tools; Working software over comprehensive documentation; Customer collaboration over contract negotiation; Responding to change over following a plan.)

2. What is the TDD lifecycle? (Answer: Write failing test → write code to pass → refactor → repeat.)

3. What is the difference between a Product Backlog and a Sprint Backlog? (Answer: Product Backlog is the full ordered list of everything needed; Sprint Backlog is the subset selected for the current sprint, broken into tasks.)

4. What are the five principles of agile methods? (Answer: Customer involvement, incremental delivery, people not process, embrace change, maintain simplicity.)

5. Name three XP practices and briefly describe each. (Answer: Pair programming — two developers at one workstation; Test-first development — tests before code; Continuous integration — integrate several times daily with all tests passing.)

6. Why should the Scrum Master and Product Owner roles NOT be combined? (Answer: Conflict of interest — Scrum Master represents the team; Product Owner represents the customer/business.)

7. What is the main difference in how requirements are handled in agile vs traditional? (Answer: Traditional: requirements captured upfront by analyst, verified from customer, contracted. Agile: user stories written by customer, can change at any time, prioritized continuously.)

8. What is the purpose of a burndown chart? (Answer: To show the amount of work remaining over time in a sprint. If it doesn't trend downward, the team is behind schedule.)

9. How does agile view refactoring compared to traditional design? (Answer: Traditional designs for change upfront (anticipate). Agile rejects this as unreliable and instead refactors continuously.)

10. What are the three questions in a daily stand-up meeting? (Answer: (1) What did I accomplish since the last meeting? (2) What will I do by the next meeting? (3) What blockers/obstacles are in my way?)

---

## Potential Exam Questions

1. **Compare and contrast** plan-driven and agile development. Include at least four specific differences.

2. **Explain** the Agile Manifesto and its four values. Why was it created?

3. **Describe** the XP release cycle. How does it differ from a traditional Waterfall release?

4. **What is** Test-Driven Development? Explain the lifecycle and its benefits.

5. **Explain** the Scrum framework: roles, events, and artifacts. How do Scrum and XP complement each other?

6. **Discuss** three situations where agile methods are NOT suitable. Justify your answer.

7. **Explain** the concept of refactoring in XP. How does it differ from the traditional approach to design for change?

8. **What are** user stories? Give an example and explain how they are used in release and iteration planning.

9. **Describe** the 17 differences between agile and traditional development for at least 10 dimensions (team, requirements, iteration, testing, ownership, integration, pace, workspace, documentation, task allocation).

10. **Evaluate** the statement: "Agile methods have no documentation and no planning." Why is this statement incorrect?

11. **Explain** scaling agile. What are the two strategies (scale up vs scale out) and when would you use each?

12. **Compare** the role of a Scrum Master with a traditional Project Manager.

---

## Topic Summary

| Key Takeaway | Details |
|-------------|---------|
| **Origin** | Agile emerged in the late 1990s as a reaction to slow, plan-driven methods. |
| **Core philosophy** | Individuals & interactions, working software, customer collaboration, responding to change. |
| **Manifesto** | 4 values + 12 principles; published 2001 by 17 software developers. |
| **Key methods** | XP (technical practices) and Scrum (management framework) — complementary, not alternatives. |
| **XP practices** | User stories, TDD, pair programming, refactoring, continuous integration, small releases, simple design, collective ownership, sustainable pace, on-site customer. |
| **Scrum roles** | Scrum Master (facilitator), Product Owner (customer voice), Team (self-organizing, 5-7 people). |
| **Scrum events** | Sprint (2-4 weeks), Sprint Planning, Daily Stand-up, Sprint Review, Sprint Retrospective. |
| **Scrum artifacts** | Product Backlog, Sprint Backlog, Burndown Chart. |
| **Agile vs Traditional** | 17 differences across team structure, requirements, iterations, testing, ownership, integration, pace, workspace, design, refactoring, documentation, task allocation, meetings, and status reporting. |
| **Suitability** | Best for small/medium products, custom systems with committed customer, non-critical systems. |
| **Limitations** | Difficult to scale to large systems; hard with complex non-functional requirements; incompatible with traditional outsourcing contracts; may conflict with organizational standards requiring documentation. |
| **Scaling strategies** | Scale up (adapt agile for whole system) vs Scale out (agile for components, plan-driven for integration). |