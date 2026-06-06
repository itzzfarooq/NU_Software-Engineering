# Agile Software Development — Detailed Exam Notes

## Why Agile?

Rapid development and delivery is now often the most important requirement for software systems. Businesses operate in fast-changing environments where it is practically impossible to produce a set of stable software requirements. Software has to evolve quickly to reflect changing business needs. Plan-driven development is essential for some types of systems but does not meet these business needs.

Agile development methods emerged in the late 1990s, aiming to **radically reduce delivery time** for working software systems.

---

## The Agile Manifesto

The Agile Manifesto, authored by 17 practitioners (including Kent Beck, Martin Fowler, Robert C. Martin, and others), establishes four core values:

> "We are uncovering better ways of developing software by doing it and helping others do it. Through this work we have come to value:"

| Value | Over | Implication |
|---|---|---|
| **Individuals and interactions** | Processes and tools | People and communication matter more than rigid processes |
| **Working software** | Comprehensive documentation | Deliver functioning software, not thick manuals |
| **Customer collaboration** | Contract negotiation | Work with customers continuously, not just at contract signing |
| **Responding to change** | Following a plan | Adapt to new information rather than blindly following a plan |

> "That is, while there is value in the items on the right, we value the items on the left more."

**Critical exam point:** The manifesto does NOT say the right-side items are worthless — it says the left-side items are valued *more*.

---

## The 5 Principles of Agile Methods

| # | Principle | Description |
|---|---|---|
| 1 | **Customer involvement** | Customers should be closely involved throughout development. Their role: provide and prioritize new system requirements and evaluate iterations. |
| 2 | **Incremental delivery** | Software is developed in increments. The customer specifies requirements for each increment. |
| 3 | **People not process** | Team members' skills should be recognized and exploited. They should develop their own ways of working without prescriptive processes. |
| 4 | **Embrace change** | Expect requirements to change. Design the system to accommodate these changes. |
| 5 | **Maintain simplicity** | Focus on simplicity in both the software and the development process. Actively eliminate complexity wherever possible. |

> **Instructor Emphasis:** These 5 principles are the foundation — every XP practice maps back to one or more of these principles.

---

## Plan-Driven vs. Agile Development

### The Key Difference

```
PLAN-DRIVEN:
┌──────────────┐    ┌──────────────────┐    ┌──────────────────┐
│ Requirements │───▶│    Specification  │───▶│ Design &         │
│ Engineering  │    │                  │    │ Implementation   │
└──────────────┘    └──────────────────┘    └──────────────────┘
       ▲                                            │
       │         Requirements change requests       │
       └────────────────────────────────────────────┘

AGILE:
┌──────────────┐    ◀──▶    ┌──────────────────┐
│ Requirements │◀──────────▶│ Design &         │
│ Engineering  │            │ Implementation   │
└──────────────┘            └──────────────────┘
      (continuous cycle)
```

### Detailed Comparison

| Aspect | Plan-Driven | Agile |
|---|---|---|
| **Approach** | Separate development stages, outputs planned in advance | Specification, design, implementation, testing are interleaved |
| **Iteration** | Occurs within activities | Across the entire process |
| **Requirements** | Captured upfront, contractually defined | Evolve continuously through customer collaboration |
| **Change** | Difficult to accommodate once process is underway | Expected and embraced |
| **Delivery** | Late delivery of working software | Frequent delivery of working increments |
| **Documentation** | Comprehensive | Minimal — focus on working code |
| **Not necessarily Waterfall** | Plan-driven + incremental development is possible | Inherently incremental |

> **Key Insight:** Plan-driven does NOT automatically mean Waterfall. You can have plan-driven incremental development.

---

## Extreme Programming (XP)

XP is the most influential agile method, developed in the late 1990s. It takes an "extreme" approach to iterative development:

- New versions may be built **several times per day**
- Increments are delivered to customers **every 2 weeks**
- **All tests must pass** for every build; build is only accepted if tests run successfully

### The XP Release Cycle

```
┌─────────────────────────┐     ┌─────────────────────────┐
│ Select user stories     │────▶│ Break down stories      │
│ for this release        │     │ to tasks                │
└────────────▲────────────┘     └────────────┬────────────┘
             │                               │
             │                               ▼
             │                    ┌─────────────────────────┐
             │                    │ Plan release            │
             │                    └────────────┬────────────┘
             │                               │
             │                               ▼
             │                    ┌─────────────────────────┐
             │                    │ Develop / integrate /   │
             │                    │ test software           │
             │                    └────────────┬────────────┘
             │                               │
             ▼                               ▼
┌─────────────────────────┐     ┌─────────────────────────┐
│ Evaluate system         │◀────│ Release software        │
└─────────────────────────┘     └─────────────────────────┘
```

**Cycle:** Select stories → Break to tasks → Plan release → Develop/integrate/test → Release → Evaluate → Repeat

---

## XP Practices (10 Key Practices)

### Table 1: Core Development Practices

| # | Practice | Description | Maps to Principle |
|---|---|---|---|
| 1 | **Incremental planning** | Requirements recorded on story cards; stories for release determined by time available and priority; developers break stories into development tasks | Incremental delivery |
| 2 | **Small releases** | Minimal useful set of functionality developed first; releases are frequent, incrementally adding functionality | Incremental delivery |
| 3 | **Simple design** | Enough design carried out to meet current requirements — no more | Maintain simplicity |
| 4 | **Test-first development** | Automated unit test framework used to write tests for new functionality *before* the functionality is implemented | Embrace change |
| 5 | **Refactoring** | Developers continuously refactor code as soon as improvements are found; keeps code simple and maintainable | Maintain simplicity |

### Table 2: Team and Process Practices

| # | Practice | Description | Maps to Principle |
|---|---|---|---|
| 6 | **Pair programming** | Developers work in pairs, checking each other's work and providing support | People not process |
| 7 | **Collective ownership** | Pairs work on all areas of system; no islands of expertise; anyone can change anything | People not process |
| 8 | **Continuous integration** | As soon as work on a task is complete, it's integrated into the whole system; all unit tests must pass after integration | Embrace change |
| 9 | **Sustainable pace** | Large amounts of overtime are not acceptable; net effect is often reduced code quality and productivity | People not process |
| 10 | **On-site customer** | End-user representative available full-time; customer is a member of the development team, responsible for bringing requirements for implementation | Customer involvement |

> **Exam Tip:** You must know all 10 XP practices. Know which agile principle each maps to.

---

## User Stories and Task Cards

### User Stories

In XP, user requirements are expressed as **user stories** or scenarios. They are:

- Written on **cards** by the customer
- Broken down into **implementation tasks** by the development team
- Tasks form the basis of **schedule and cost estimates**
- Customer chooses stories for each release based on **priority and estimates**

**User story format:**
```
┌──────────────────────────────────────────────────┐
│ Prescribing medication                           │
│                                                  │
│ The record of the patient must be open for       │
│ input. Click on the medication field and select  │
│ either 'current medication', 'new medication'    │
│ or 'formulary'.                                  │
│                                                  │
│ If 'current medication' → check dose, change     │
│ dose if needed, confirm prescription.            │
│                                                  │
│ If 'new medication' → type first few letters,    │
│ choose from list, check, enter dose, confirm.    │
│                                                  │
│ If 'formulary' → search approved formulary,      │
│ select drug, check, enter dose, confirm.         │
│                                                  │
│ System checks dose within approved range.        │
│ After confirmation, prescription is displayed    │
│ for checking. Click 'OK' to record on audit DB.  │
└──────────────────────────────────────────────────┘
```

### Task Cards

Task cards are derived from user stories. Example for "Prescribing medication":

| Task | Description |
|---|---|
| **Task 1: Change dose** | Modify the dose of a prescribed drug |
| **Task 2: Formulary selection** | Search and select from approved formulary |
| **Task 3: Dose checking** | Safety precaution: lookup formulary for generic drug name, retrieve min/max dose, check prescribed dose against range, issue error if outside range |

> **Exam Tip:** User stories are customer-facing; task cards are developer-facing. Stories get decomposed into tasks.

---

## Refactoring

### Concept

Conventional wisdom says "design for change" — anticipate changes to reduce later costs. **XP rejects this approach**, arguing that changes cannot be reliably anticipated. Instead, XP proposes **constant code improvement (refactoring)** to make changes easier when they must be implemented.

### What Refactoring Involves

- Programming teams look for possible software improvements
- Make improvements **even when there is no immediate need**
- Improves **understandability** — reduces need for documentation
- Makes changes **easier** because code is well-structured and clear
- Some changes require **architecture refactoring** — this is much more expensive

### Examples of Refactoring

| Example | What Changes |
|---|---|
| **Re-organize class hierarchy** | Remove duplicate code across related classes |
| **Rename attributes and methods** | Make names clearer and more intuitive |
| **Replace inline code with library methods** | Extract repeated code into reusable functions |

### Benefits of Refactoring

| Benefit | Explanation |
|---|---|
| **Code simplicity** | Code stays clean and readable |
| **Reduced documentation need** | Well-structured code is self-documenting |
| **Easier maintenance** | Future changes are cheaper and faster |
| **Continuous quality** | Prevents technical debt from accumulating |

> **Instructor Emphasis:** Refactoring is done continuously — every hour or half hour. Each transformation is trivial alone, but together they produce significant improvements.

---

## Test-Driven Development (TDD) Cycle

TDD reverses the traditional test-after approach. The TDD cycle is:

```
    ┌──────────────────────┐
    │  1. Write a test     │
    │     that FAILS       │
    │  (functionality      │
    │   doesn't exist yet) │
    └──────────┬───────────┘
               │
               ▼
    ┌──────────────────────┐
    │  2. Write code to    │
    │     make the test    │
    │     PASS             │
    └──────────┬───────────┘
               │
               ▼
    ┌──────────────────────┐
    │  3. REFACTOR         │
    │     (clean up the    │
    │      code)           │
    └──────────┬───────────┘
               │
               └──────────▶ Repeat
```

**TDD Mantra:** *Red → Green → Refactor*
- **Red:** Test fails (code doesn't exist)
- **Green:** Test passes (code written)
- **Refactor:** Clean up without changing behavior

### Components of an Automated Test (e.g., JUnit)

| Component | Purpose |
|---|---|
| **Setup** | Initialize system with test case inputs and expected outputs |
| **Call** | Execute the object or method being tested |
| **Assertion** | Compare result with expected result; true = pass, false = fail |

---

## 17 Differences Between Agile and Traditional Development

These represent 180-degree shifts in thinking:

| # | Aspect | Traditional | Agile |
|---|---|---|---|
| 1 | **Team** | Hierarchical: analyst, designer, coder, tester, architect, team lead, QA manager, PM | **Whole team** — customer is part of the team; self-organizing with servant leader |
| 2 | **Requirements** | Captured and written by analyst and PM, verified with customer | **User stories** written by customers on index cards |
| 3 | **Development iteration** | 2-3 month iterations; first iteration is detailed design/plan | **Short cycles** (1-4 weeks); each produces working software; demonstrated to stakeholders |
| 4 | **Acceptance tests** | Written at initial level, used as acceptance at end | Written during iteration; language easy for all to read; once passing, never fail again |
| 5 | **Programming style** | Each coder assigned task by lead; QA checks errors | **Pair programming** — two programmers at one workstation, intensely interacting |
| 6 | **Testing** | Test cases at prototype approval; QA tests code | **TDD** — write failing test first, then code to make it pass |
| 7 | **Ownership** | Manager is solely responsible | **Collective ownership** — everyone works on everything; no one has more authority |
| 8 | **Integration** | Done at end of module/project by QA team | **Continuous integration** — check in and integrate several times per day |
| 9 | **Development pace** | 80/20 principle: high speed initial 20%, moderate 60%, speed up last 20% | **Sustainable pace** — marathon not sprint; no overtime allowed |
| 10 | **Workspace** | Separate rooms/cubicles for each team member | **Open workspace** — team works together; walls covered with charts/diagrams |
| 11 | **Design & architecture** | Designed/architected for whole project at beginning | **Simple design** — focus only on current iteration stories; design evolves |
| 12 | **Refactoring** | Done at end of project, initiated by QA | **Continuous refactoring** — every hour/half hour; each change trivial alone |
| 13 | **Documentation** | Intensive diagrams and specifications | **Light documentation** — produce no document unless need is immediate and significant |
| 14 | **Task allocation** | PM/team lead assigns tasks | **Self-selection** — team decides how much work to commit to |
| 15 | **Progress monitoring** | Monitor by counting completed tasks | **Burndown chart** — shows remaining work hours each day |
| 16 | **Status meetings** | Weekly meetings; everyone reports to PM | **Daily stand-up** — 3 things: what done, what aiming for, what blocks |
| 17 | **Project status** | Shown by number of completed tasks | **Status board** — "What's Working Well" and "What's Not Working" |

> **Exam Tip:** These 17 differences are frequently tested. Know at least the top 7-8 (team, requirements, iterations, testing, ownership, integration, pace, design).

---

## Agile Applicability

| Good Fit | Poor Fit |
|---|---|
| Product development (small/medium products for sale) | Large safety-critical systems |
| Custom development with committed customer involvement | Systems with strict regulatory requirements |
| Projects with few external rules/regulations | Projects requiring extensive upfront documentation |
| Fast-changing requirements | Stable, well-understood requirements |

---

## Exam Checklist

- [ ] Agile Manifesto: 4 values (and that right side has value too)
- [ ] 5 principles of agile methods (customer involvement, incremental delivery, people not process, embrace change, maintain simplicity)
- [ ] Plan-driven vs. agile: diagram and key differences
- [ ] All 10 XP practices (2 tables) and which principles they map to
- [ ] XP release cycle (6 steps in order)
- [ ] User stories: format, purpose, who writes them
- [ ] Task cards: derived from user stories, developer-facing
- [ ] Refactoring: concept, examples, benefits
- [ ] TDD cycle: Red → Green → Refactor
- [ ] 17 differences between Agile and Traditional (at least top 8)
