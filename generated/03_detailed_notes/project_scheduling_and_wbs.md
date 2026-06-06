# Project Scheduling and Work Breakdown Structure — Detailed Notes

## The Story of Scheduling

A software project without a schedule is like a road trip without a map — you might eventually arrive somewhere, but it won't be where you intended, and it will cost far more than planned. Project scheduling transforms estimates into a **concrete timeline** with specific activities, dependencies, and milestones. At its heart lies the **Work Breakdown Structure (WBS)** — the tool that decomposes a complex project into manageable, trackable pieces. This chapter tells the story of how we go from "we need to build this" to "here's exactly what happens, when, and by whom."

---

## Planning vs. Estimating vs. Scheduling — Understanding the Differences

These three terms are often confused, but they serve distinct purposes:

| Activity | Purpose | Question Answered | When |
|----------|---------|-------------------|------|
| **Planning** | Define WHAT will be done and HOW | "What activities are needed? What's the approach?" | Early in project |
| **Estimating** | Determine HOW MUCH (effort, cost, size) | "How many person-days? How much money?" | During planning |
| **Scheduling** | Determine WHEN and WHO | "When will each activity happen? Who will do it?" | After estimating |

```
Planning → Estimating → Scheduling
   (What)     (How much)    (When/Who)
```

> **Key Insight:** You can't schedule before you estimate, and you can't estimate before you plan. They form a **sequential dependency chain**.

---

## The Work Breakdown Structure (WBS)

### Definition

The **Work Breakdown Structure (WBS)** is a hierarchical decomposition of the total scope of work to be carried out by the project team. It breaks down the project into smaller, more manageable components called **work packages**.

### Purpose of WBS

The WBS serves multiple critical purposes:

| Purpose | Description |
|---------|-------------|
| **Scope definition** | Clearly defines all work that must be done (and nothing that doesn't) |
| **Organization** | Provides a structured framework for organizing project activities |
| **Estimation** | Enables accurate effort and cost estimation at the work package level |
| **Assignment** | Makes it possible to assign responsibility for specific pieces of work |
| **Tracking** | Allows progress to be monitored at a granular level |
| **Communication** | Provides a common language for discussing project scope |

### WBS Concepts, Goals, and Benefits

#### Concepts
- **Decomposition**: Breaking larger elements into smaller pieces
- **Hierarchy**: Each level represents a more detailed description of the work
- **100% Rule**: The WBS must include 100% of the work defined by the project scope
- **Mutual Exclusivity**: Each element appears in only one place in the WBS

#### Goals
- Ensure all project work is identified and accounted for
- Provide a framework for scheduling and budgeting
- Enable assignment of responsibility
- Facilitate progress tracking and reporting

#### Benefits
- Reduces the chance of missing important work
- Makes large projects manageable
- Improves estimation accuracy
- Enhances team understanding of project scope
- Provides clear assignment of responsibility

### When to Develop the WBS

The WBS should be developed:
- **During early planning** — as soon as project scope is reasonably well understood
- **Before estimating** — because estimates are created for work packages
- **Before scheduling** — because the WBS defines what activities need scheduling
- **Iteratively** — it may be refined as more is learned about the project

---

## Steps to Build a WBS — The 9-Step Process

| # | Step | Description |
|---|------|-------------|
| 1 | **Identify major deliverables** | List the primary outputs or components of the project |
| 2 | **Define work packages** | Break each deliverable into smaller, manageable pieces |
| 3 | **Identify activities** | Determine the specific tasks needed to complete each work package |
| 4 | **Verify the decomposition** | Ensure each piece is appropriately sized and well-defined |
| 5 | **Assign identifiers** | Give each element a unique ID/code for tracking |
| 6 | **Define milestones** | Identify key checkpoints and decision points |
| 7 | **Verify scope completeness** | Apply the 100% rule — does the WBS cover all scope? |
| 8 | **Review with stakeholders** | Get agreement from the team and customers |
| 9 | **Document assumptions** | Record any assumptions made during decomposition |

> **Key Rule — The 100% Rule:** The child elements at each level must account for 100% of the work represented by the parent element. Nothing can be missing, and nothing can be extra.

---

## WBS Formats

There are two primary formats for representing a WBS:

### 1. Outline Format (Hierarchical List)

```
1.0 Chat Application
    1.1 Requirements
        1.1.1 User requirements
        1.1.2 System requirements
        1.1.3 Requirements review
    1.2 Design
        1.2.1 Architecture design
        1.2.2 Database design
        1.2.3 UI design
    1.3 Implementation
        1.3.1 Frontend development
        1.3.2 Backend development
        1.3.3 Database implementation
    1.4 Testing
        1.4.1 Unit testing
        1.4.2 Integration testing
        1.4.3 System testing
    1.5 Deployment
        1.5.1 Installation
        1.5.2 User training
        1.5.3 Documentation
```

### 2. Graphical Tree Format

```
                    Chat Application (1.0)
                    /        |        \        \
              Requirements  Design  Implementation  Testing  Deployment
              (1.1)       (1.2)      (1.3)         (1.4)     (1.5)
              / | \       / | \      / | \         / | \      / | \
           User Sys  Arch DB  UI  FE  BE  DB    Unit Int Sys Inst Train Doc
          Req  Req   Des  Des Des Dev Dev Impl  Test Test Test
```

> **Exam Tip:** Be comfortable converting between outline and tree formats.

---

## WBS Example: Retail Web Site

Here's a complete WBS example for developing a **Retail Web Site**:

```
1.0 Retail Web Site
├── 1.1 Planning
│   ├── 1.1.1 Project charter
│   ├── 1.1.2 Stakeholder analysis
│   ├── 1.1.3 Project plan
│   └── 1.1.4 Requirements gathering
├── 1.2 Design
│   ├── 1.2.1 Site architecture
│   ├── 1.2.2 Database design
│   ├── 1.2.3 UI/UX design
│   ├── 1.2.4 Security design
│   └── 1.2.5 Design review
├── 1.3 Development
│   ├── 1.3.1 Product catalog module
│   ├── 1.3.2 Shopping cart module
│   ├── 1.3.3 Payment processing module
│   ├── 1.3.4 User account module
│   ├── 1.3.5 Admin panel
│   └── 1.3.6 API integration
├── 1.4 Testing
│   ├── 1.4.1 Unit testing
│   ├── 1.4.2 Integration testing
│   ├── 1.4.3 Performance testing
│   ├── 1.4.4 Security testing
│   └── 1.4.5 User acceptance testing
├── 1.5 Deployment
│   ├── 1.5.1 Server setup
│   ├── 1.5.2 Production deployment
│   ├── 1.5.3 DNS configuration
│   └── 1.5.4 SSL certificate installation
└── 1.6 Documentation & Training
    ├── 1.6.1 Technical documentation
    ├── 1.6.2 User manual
    ├── 1.6.3 Admin guide
    └── 1.6.4 Training sessions
```

---

## WBS Levels: CWBS vs. PWBS

| Level | Name | Description | Typical Depth |
|-------|------|-------------|---------------|
| **CWBS** (Contract WBS) | Contract-level | Defines the work to be delivered under a contract; used for external agreements | 3-4 levels |
| **PWBS** (Project WBS) | Project-level | Defines the internal project organization; used for managing work within the organization | 4-6 levels |

### Key Differences

| Aspect | CWBS | PWBS |
|--------|------|------|
| **Audience** | External stakeholders (customers, contractors) | Internal team members |
| **Detail Level** | Higher-level (what will be delivered) | Lower-level (how it will be done) |
| **Focus** | Deliverables and milestones | Activities and tasks |
| **Ownership** | Contract manager | Project manager |

---

## WBS Dictionary

The WBS dictionary provides **detailed descriptions** of each WBS element. Without it, the WBS codes are just labels — the dictionary gives them meaning.

### WBS Dictionary Entry Example

```
┌─────────────────────────────────────────────────────┐
│ WBS CODE: 1.3.2                                     │
│ TITLE: Shopping Cart Module                         │
│─────────────────────────────────────────────────────│
│ Description:                                        │
│ Development of the shopping cart functionality      │
│ including add/remove items, quantity updates,       │
│ price calculations, and session persistence.        │
│─────────────────────────────────────────────────────│
│ Responsible: Senior Developer                       │
│ Estimated Effort: 120 person-hours                  │
│ Estimated Cost: $9,600                              │
│ Dependencies: 1.3.1 (Product Catalog), 1.2.2 (DB) │
│ Milestone: Cart module complete by Week 6           │
│ Deliverables: Source code, unit tests, documentation│
│ Acceptance Criteria: All cart operations functional │
│─────────────────────────────────────────────────────│
│ Assumptions: Payment module available as external   │
│ API. Session management framework in place.         │
└─────────────────────────────────────────────────────┘
```

---

## Common WBS Pitfalls

| Pitfall | Description | Consequence |
|---------|-------------|-------------|
| **Too much detail** | Decomposing to the task level (hours of work) | Overwhelming complexity, micromanagement |
| **Too little detail** | Not decomposing enough | Work packages too large to estimate or track |
| **Missing work** | Not capturing all scope items | Scope creep, untracked work |
| **Duplicate entries** | Same work appearing in multiple places | Confusion about responsibility, double-counting |
| **Output-focused decomposition** | Breaking down by outputs rather than work | Difficulty assigning and tracking |
| **Action-oriented decomposition** | Breaking down by actions/work needed | Better for estimation and assignment |

> **Best Practice:** Decompose until work packages are **small enough to estimate reliably** (typically 8-80 hours of effort) but **large enough to be manageable**.

---

## The Scheduling Process

Scheduling transforms the WBS into a **time-ordered plan**. It answers: "When will each piece of work happen?"

### The 5-Step Scheduling Process

```
Step 1: IDENTIFY ACTIVITIES
   (What work needs to be done? - from WBS)
        ↓
Step 2: DETERMINE DEPENDENCIES
   (Which activities depend on which?)
        ↓
Step 3: ESTIMATE RESOURCES
   (Who/what is needed for each activity?)
        ↓
Step 4: ASSIGN RESOURCES & DURATION
   (How long will each activity take? Who will do it?)
        ↓
Step 5: CREATE SCHEDULING CHARTS
   (Bar charts, network diagrams, Gantt charts)
```

### Scheduling Problems: Brooks's Law

**Brooks's Law** states:

> "Adding manpower to a late software project makes it later."

This counter-intuitive law exists because:
1. **New people need training** — existing team members must stop working to train them
2. **Communication overhead** increases exponentially with team size
3. **Task decomposition limits** — not all tasks can be divided among more people
4. **Ramp-up time** — new people become productive only after understanding the codebase

| Team Size | Communication Channels (n(n-1)/2) |
|-----------|----------------------------------|
| 3 | 3 |
| 5 | 10 |
| 10 | 45 |
| 15 | 105 |
| 20 | 190 |

> **Key Insight:** Communication overhead grows **quadratically** with team size, while productivity grows only **linearly** (at best). This is why throwing more people at a late project often makes it worse.

---

## Bar Charts (Gantt Charts)

Bar charts (Gantt charts) are the most common scheduling visualization. They show:
- **Tasks** on the vertical axis
- **Time** on the horizontal axis
- **Bars** representing the duration of each task
- **Dependencies** shown as arrows between bars
- **Milestones** shown as diamonds or special markers

### Example Gantt Chart

```
Week:       1    2    3    4    5    6    7    8
            |    |    |    |    |    |    |    |
Requirements ████
Design            ██████
Backend Dev              ████████████
Frontend Dev               ████████████
Testing                              ████████
Deployment                                   ████
            |    |    |    |    |    |    |    |
Milestones: ◆         ◆              ◆         ◆
           Start   Design        Code       Release
                   Complete     Complete
```

---

## Activity Network Diagrams — CPM and PERT

Activity network diagrams show the **sequence and dependencies** of activities. The two main techniques are:

### CPM (Critical Path Method)
- Uses **deterministic** time estimates (one estimate per activity)
- Focuses on finding the **critical path** — the longest path through the network
- Activities on the critical path **cannot be delayed** without delaying the project

### PERT (Program Evaluation and Review Technique)
- Uses **probabilistic** time estimates (three estimates: optimistic, most likely, pessimistic)
- Better for projects with **high uncertainty**
- Provides probability of completing by a specific date

### Rules for Network Creation

When building a network diagram:
1. Each activity is represented by a **node** (box or circle)
2. **Arrows** represent dependencies (direction shows sequence)
3. **No loops** — the network must be a directed acyclic graph (DAG)
4. **Start and end nodes** must be clearly identified
5. Each activity has **one predecessor** (except start) and **one successor** (except end)
6. Dependencies must be **logical**, not arbitrary

---

## Activity Network Example — Complete Worked Problem

### Activity Data Table

| Activity | Description | Duration (days) | Predecessors |
|----------|-------------|-----------------|--------------|
| A | Requirements gathering | 5 | — |
| B | System design | 4 | A |
| C | Database design | 3 | A |
| D | Frontend development | 6 | B |
| E | Backend development | 7 | B, C |
| F | Integration | 4 | D, E |
| G | Testing | 5 | F |
| H | Deployment | 2 | G |

### Network Diagram

```
        ┌─────── B(4) ──────── D(6) ───────┐
        │                    ↓              │
A(5) ───┤                    ↓              ├──→ F(4) ──→ G(5) ──→ H(2)
        │                    ↓              │
        └─────── C(3) ──── E(7) ───────────┘
```

### Forward Pass — Calculating ES and EF

**Forward Pass** determines the **Earliest Start (ES)** and **Earliest Finish (EF)** for each activity.

```
ES = max(EF of all predecessors)
EF = ES + Duration
```

| Activity | ES | EF |
|----------|----|----|
| A | 0 | 5 |
| B | 5 | 9 |
| C | 5 | 8 |
| D | 9 | 15 |
| E | max(9,8) = 9 | 16 |
| F | max(15,16) = 16 | 20 |
| G | 20 | 25 |
| H | 25 | 27 |

**Project Duration = 27 days**

### Backward Pass — Calculating LS and LF

**Backward Pass** determines the **Latest Start (LS)** and **Latest Finish (LF)** for each activity.

```
LF = min(LS of all successors)
LS = LF - Duration
```

Starting from the end (LF of H = 27):

| Activity | LF | LS |
|----------|----|----|
| H | 27 | 25 |
| G | 25 | 20 |
| F | 20 | 16 |
| E | 16 | 9 |
| D | 16 | 10 |
| C | 9 | 6 |
| B | min(10,9) = 9 | 5 |
| A | min(5,6) = 5 | 0 |

### Critical Path Identification

The **critical path** is the longest path through the network where **Total Float = 0**.

```
Total Float = LS - ES = LF - EF
```

| Activity | ES | EF | LS | LF | Total Float | Critical? |
|----------|----|----|----|----|-------------|-----------|
| A | 0 | 5 | 0 | 5 | 0 | **YES** |
| B | 5 | 9 | 5 | 9 | 0 | **YES** |
| C | 5 | 8 | 6 | 9 | 1 | No |
| D | 9 | 15 | 10 | 16 | 1 | No |
| E | 9 | 16 | 9 | 16 | 0 | **YES** |
| F | 16 | 20 | 16 | 20 | 0 | **YES** |
| G | 20 | 25 | 20 | 25 | 0 | **YES** |
| H | 25 | 27 | 25 | 27 | 0 | **YES** |

**Critical Path: A → B → E → F → G → H (27 days)**

### Float Analysis

```
Total Float = LS - ES    (or LF - EF)
Free Float = ES(successor) - EF(current)
```

**Total Float**: How much an activity can be delayed without delaying the **project**.

**Free Float**: How much an activity can be delayed without delaying the **next activity**.

#### Free Float Calculations

| Activity | ES of Successor | EF | Free Float |
|----------|----------------|----|-----------|
| A | 5 | 5 | 0 |
| B | min(9,9)=9 | 9 | 0 |
| C | 9 | 8 | 1 |
| D | 16 | 15 | 1 |
| E | 16 | 16 | 0 |
| F | 20 | 20 | 0 |
| G | 25 | 25 | 0 |
| H | — | 27 | 0 |

> **Key Insight:** Activities on the critical path have **zero total float AND zero free float**. Non-critical activities have float — this is "slack time" that can absorb delays.

---

## Second Example Problem

### Activity Data Table

| Activity | Duration (days) | Predecessors |
|----------|-----------------|--------------|
| A | 3 | — |
| B | 4 | A |
| C | 6 | A |
| D | 5 | B |
| E | 8 | B, C |
| F | 3 | D, E |
| G | 4 | F |
| H | 2 | G |

### Forward Pass

| Activity | ES | EF |
|----------|----|----|
| A | 0 | 3 |
| B | 3 | 7 |
| C | 3 | 9 |
| D | 7 | 12 |
| E | max(7,9)=9 | 17 |
| F | max(12,17)=17 | 20 |
| G | 20 | 24 |
| H | 24 | 26 |

**Project Duration = 26 days**

### Backward Pass

| Activity | LF | LS |
|----------|----|----|
| H | 26 | 24 |
| G | 24 | 20 |
| F | 20 | 17 |
| E | 17 | 9 |
| D | 17 | 12 |
| C | 9 | 3 |
| B | min(12,9)=9 | 5 |
| A | min(5,3)=3 | 0 |

### Complete Analysis

| Activity | ES | EF | LS | LF | Total Float | Critical? |
|----------|----|----|----|----|-------------|-----------|
| A | 0 | 3 | 0 | 3 | 0 | **YES** |
| B | 3 | 7 | 5 | 9 | 2 | No |
| C | 3 | 9 | 3 | 9 | 0 | **YES** |
| D | 7 | 12 | 12 | 17 | 5 | No |
| E | 9 | 17 | 9 | 17 | 0 | **YES** |
| F | 17 | 20 | 17 | 20 | 0 | **YES** |
| G | 20 | 24 | 20 | 24 | 0 | **YES** |
| H | 24 | 26 | 24 | 26 | 0 | **YES** |

**Critical Path: A → C → E → F → G → H (26 days)**

> **Note:** In this example, Activity B has a total float of 2 days, meaning it can be delayed by up to 2 days without affecting the project end date. Activity D has 5 days of float.

---

## Summary: From WBS to Schedule

```
WBS (What needs to be done?)
    ↓
Activity List (Specific tasks)
    ↓
Dependencies (What depends on what?)
    ↓
Duration Estimates (How long each takes?)
    ↓
Network Diagram (Visual sequence)
    ↓
Critical Path Analysis (ES/EF/LS/LF/Float)
    ↓
Schedule (Gantt chart with milestones)
```

---

## Quick Reference: Key Formulas

| Formula | Description |
|---------|-------------|
| `EF = ES + Duration` | Earliest Finish |
| `ES = max(EF of predecessors)` | Earliest Start |
| `LS = LF - Duration` | Latest Start |
| `LF = min(LS of successors)` | Latest Finish |
| `Total Float = LS - ES` | How much an activity can be delayed |
| `Free Float = ES(successor) - EF(current)` | Delay without affecting next activity |
| `Communication Channels = n(n-1)/2` | Brooks's Law context |

---

## Common Mistakes

| Mistake | Correction |
|---------|------------|
| Confusing total float with free float | Total float = delay without delaying project; Free float = delay without delaying next activity |
| Forgetting that critical path has zero float | Activities on the critical path ALWAYS have zero float |
| Assuming adding people always speeds up a project | Brooks's Law: adding people to a late project makes it later |
| Confusing CWBS with PWBS | CWBS = contract-level (external); PWBS = project-level (internal) |

## Exam Traps

| Trap | Why It's Tricky | Correct Answer |
|------|----------------|----------------|
| "Critical path is the shortest path" | It's the LONGEST path — determines minimum project duration | Longest path = shortest possible project duration |
| "Float = 0 means the activity is late" | Float = 0 means the activity has NO slack — it's on the critical path | It's not late, it's critical |

## Active Recall Questions

1. What is the difference between planning, estimating, and scheduling?
2. What is the 100% rule for WBS?
3. State Brooks's Law.
4. What is the formula for total float?
5. What are the 3 types of WBS levels?
6. How do you calculate free float?
7. What are the rules for creating network diagrams?
8. What is the difference between CWBS and PWBS?

## Exam Preparation Checklist

- [ ] Can you explain the difference between planning, estimating, and scheduling?
- [ ] Can you define WBS and its purpose?
- [ ] Can you list the 9 steps to build a WBS?
- [ ] Can you draw a WBS in both outline and tree format?
- [ ] Can you explain the 100% rule for WBS?
- [ ] Can you identify common WBS pitfalls?
- [ ] Can you describe Brooks's Law and why it's true?
- [ ] Can you create a Gantt chart from a schedule?
- [ ] Can you draw an activity network diagram?
- [ ] Can you perform forward and backward passes?
- [ ] Can you calculate Total Float and Free Float?
- [ ] Can you identify the critical path?
- [ ] Can you solve both example problems completely?

## Potential Exam Questions

1. Explain the difference between planning, estimating, and scheduling with examples.
2. What is a WBS and why is it important? Describe the 100% rule.
3. Compare CWBS and PWBS.
4. Describe Brooks's Law and explain why it is true.
5. Perform a forward and backward pass on a given network diagram and identify the critical path.
6. Calculate total float and free float for given activities.
7. What are common WBS pitfalls and how can they be avoided?
8. Draw a Gantt chart from a given activity list and dependencies.

## Topic Summary

Project scheduling transforms estimates into a concrete timeline. The Work Breakdown Structure (WBS) decomposes project scope into manageable work packages using the 100% rule. WBS comes in outline and graphical tree formats, with CWBS (contract-level) and PWBS (project-level) variants. The 9-step WBS building process ensures completeness. Scheduling follows 5 steps: identify activities, determine dependencies, estimate resources, assign resources and duration, create charts. Brooks's Law states adding people to a late project makes it later due to communication overhead growing quadratically. Gantt charts show tasks over time. CPM uses deterministic estimates; PERT uses probabilistic estimates. Forward pass calculates ES and EF; backward pass calculates LS and LF. Total Float = LS - ES; Free Float = ES(successor) - EF. Critical path has zero float and determines minimum project duration.
