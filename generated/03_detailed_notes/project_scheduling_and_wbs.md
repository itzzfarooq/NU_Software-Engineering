# Project Scheduling & Work Breakdown Structure (WBS) — Detailed Notes

---

## Topic Overview

This topic covers two fundamental pillars of software project management: **Work Breakdown Structure (WBS)** and **Project Scheduling**. WBS is the process of decomposing a project into manageable deliverables and work packages. Project scheduling builds on the WBS to assign time, resources, dependencies, and calendar dates to each task. Together, they form the backbone of project planning, estimation, tracking, and control.

Key techniques include Critical Path Method (CPM) for identifying the longest path through a network of dependent activities, resource leveling to smooth demand, and Earned Value Management (EVM) for tracking project health.

---

## Why This Topic Exists

- **Without decomposition**, large projects become unmanageable — tasks are forgotten, started late, or allocated to multiple people with no clear ownership.
- **Without scheduling**, there is no way to predict delivery dates, identify bottlenecks, or track progress against a baseline.
- **Ballpark estimates become targets** if not grounded in a structured WBS.
- **Two main causes of project failure**: forgetting something critical, and treating rough estimates as hard targets.
- Scheduling provides the mechanism to detect delays early, manage dependencies, and make trade-off decisions between time, cost, and scope.

---

## Core Concepts & Definitions

| Concept | Definition |
|---------|-----------|
| **Plan** | Identifies activities. No specific start/end dates. |
| **Estimate** | Predicting effort, time, and cost (size and duration of activities). |
| **Schedule** | Adds specific start/end dates, relationships, and resources. |
| **Work Package** | A group of related tasks defined at the same level within a WBS. |
| **Critical Path** | The longest path through an activity network; determines minimum project duration. |
| **Float (Slack)** | Amount of time an activity can be delayed without affecting the project (total float) or the next activity (free float). |
| **EVM** | Earned Value Management — compares planned vs actual performance using PV, EV, AC. |

---

## Work Breakdown Structure (WBS)

### Definition

A **Work Breakdown Structure** is a deliverable-oriented hierarchical decomposition of a project into smaller components. Each element may be a product, data, a service, or any combination. The WBS provides the framework for detailed cost estimating, schedule development, and control.

### WBS Levels

| Level | Name | Used By | Purpose |
|-------|------|---------|---------|
| 1 | Total Program | Customer/Exec | Authorizations |
| 2 | Project | Customer/Exec | Budgeting |
| 3 | Task | Customer/Exec | High-level tracking/reporting |
| 4 | Subtask | PM & Team | Detailed planning |
| 5 | Work Package | PM & Team | Lowest-level tracking, estimates |
| 6 | Level of Effort | PM & Team | Support activities |

- **Contract WBS (CWBS)**: First 2–3 levels, used for client discussions.
- **Project WBS (PWBS)**: Defined by PM and team, tied to deliverables, lowest-level tracking.

### WBS Formats

**1. Outline (Indented Format):**

```
0.0 Retail Web Site
  1.0 Project Management
  2.0 Requirements Gathering
  3.0 Analysis & Design
  4.0 Site Software Development
    4.1 HTML Design and Creation
    4.2 Backend Software
      4.2.1 Database Implementation
      4.2.2 Middleware Development
      4.2.3 Security Subsystems
      4.2.4 Catalog Engine
      4.2.5 Transaction Processing
    4.3 Graphics and Interface
    4.4 Content Creation
  5.0 Testing and Production
```

**2. Graphical Tree (Organizational Chart):**

```
             [0.0 Retail Web Site]
              /     |      |      \
             /      |      |       \
      [1.0 PM] [2.0 Req] [3.0 Design] [4.0 Dev] [5.0 Test]
                                        /    |     \
                                       /     |      \
                                  [4.1 HTML] [4.2 Backend] [4.3 Graphics]
                                              /    |    |    \      \
                                             /     |    |     \      \
                                    [4.2.1 DB] [4.2.2 MW] [4.2.3 Sec] [4.2.4 Cat] [4.2.5 Trans]
```

### WBS Guidelines

- Must be accurate and readable.
- Assign clear responsibilities to the project team.
- Indicate milestones and control points.
- Enable cost, time, and risk estimation.
- Include **three types of work**:
  - **Product** — physical deliverables.
  - **Integration** — bringing products together.
  - **Support** — administration, LOE, expenses.
- Break down until you can generate accurate time and cost estimates (work packages ~80 hours).
- Each element must correspond to a deliverable.
- What hurts most is what's **missing**.

### WBS Pitfalls

| Pitfall | Explanation |
|---------|-------------|
| **Wrong level of detail** | Too coarse (loses accuracy) or too fine (overwhelming overhead). |
| **Deliverables vs Activities** | WBS is deliverable-oriented, not activity-oriented. |
| **WBS is not a plan/schedule** | It shows *what*, not *when* or *who*. |
| **WBS updates need change control** | Scope changes must be formally managed. |
| **WBS is not org hierarchy** | Don't confuse it with a company org chart. |

### WBS Dictionary

A companion document describing each WBS element:
- Statement of work
- List of associated activities
- Milestones
- Responsible organization
- Start/end dates
- Resources required

---

## Project Scheduling

### Purpose

- Split project into tasks.
- Estimate time and resources for each task.
- Organize tasks concurrently for optimal workforce use.
- Minimize task dependencies to avoid delays.
- Create bar charts (Gantt charts) and activity networks.

### Scheduling Process

```
Identify Activities
       |
       v
Identify Possible Dependencies
       |
       v
Estimate Resources
       |
       v
Assign People
       |
       v
Create Activity Network and Bar Charts
```

### Scheduling Problems

| Problem | Description |
|---------|-------------|
| Estimating difficulty | Predicting cost and effort is inherently challenging. |
| Brooks' Law | Adding people to a late project makes it later (communication overhead). |
| The unexpected | Always allow contingency in planning. |

### Types of Schedules

| Type | Description |
|------|-------------|
| Milestone Schedule | Key events only |
| Gantt Chart | Bar chart showing tasks over time |
| Network Diagram | Shows dependencies between tasks |

### Bar Charts (Gantt Charts)

- Tasks listed on left, time on top.
- Horizontal bars represent duration.
- Overlapping bars show parallel work.
- Easy to visualize against calendar time.

### Activity Network Diagrams

Model project activities and their relationships as a network. Two best-known techniques:

1. **CPM (Critical Path Method)** / **CPA (Critical Path Analysis)**
2. **PERT (Program Evaluation Review Technique)**

Both use **Activity-on-Arrow** approach: activities drawn as arrows, nodes represent start/completion events.

### Rules for Activity Network Creation

1. Flow from left to right.
2. Activity cannot begin until all predecessors are done.
3. Arrows can cross (show flow).
4. Every activity must have an ID.
5. No looping.
6. Activity ID > preceding activity ID.

---

## Critical Path Method (CPM) — Detailed Worked Example

### Example Data

| Activity | Predecessor | Duration (days) |
|----------|-------------|-----------------|
| A | — | 3 |
| B | A | 4 |
| C | A | 2 |
| D | B | 5 |
| E | C | 1 |
| F | C | 2 |
| G | D, E | 4 |
| H | F, G | 3 |

### Step 1: Identify All Paths and Lengths

| Path | Activities | Duration |
|------|------------|----------|
| Path 1 | A → B → D → G → H | 3 + 4 + 5 + 4 + 3 = **19** |
| Path 2 | A → C → E → G → H | 3 + 2 + 1 + 4 + 3 = **13** |
| Path 3 | A → C → F → H | 3 + 2 + 2 + 3 = **10** |

**Critical Path = A → B → D → G → H (19 days)** — the longest path.

### Step 2: Forward Pass (ES & EF)

- **ES (Early Start)**: Earliest an activity can start.
- **EF (Early Finish)** = ES + Duration.

| Activity | Duration | ES | EF | Calculation |
|----------|----------|----|----|-------------|
| A | 3 | 0 | 3 | ES = 0, EF = 0+3 |
| B | 4 | 3 | 7 | ES = EF of A |
| C | 2 | 3 | 5 | ES = EF of A |
| D | 5 | 7 | 12 | ES = EF of B |
| E | 1 | 5 | 6 | ES = EF of C |
| F | 2 | 5 | 7 | ES = EF of C |
| G | 4 | 12 | 16 | ES = max(EF of D=12, EF of E=6) = 12 |
| H | 3 | 16 | 19 | ES = max(EF of F=7, EF of G=16) = 16 |

### Step 3: Backward Pass (LS & LF)

- **LF (Late Finish)**: Latest an activity can finish without delaying the project.
- **LS (Late Start)** = LF − Duration.
- Project finish = 19 (EF of last activity H).

| Activity | Duration | LF | LS | Calculation |
|----------|----------|----|----|-------------|
| H | 3 | 19 | 16 | LF = project finish, LS = 19−3 |
| G | 4 | 16 | 12 | LF = LS of H |
| F | 2 | 16 | 14 | LF = LS of H |
| D | 5 | 12 | 7 | LF = LS of G |
| E | 1 | 12 | 11 | LF = LS of G |
| B | 4 | 7 | 3 | LF = LS of D |
| C | 2 | 11 | 9 | LF = min(LS of E=11, LS of F=14) = 11 |
| A | 3 | 3 | 0 | LF = min(LS of B=3, LS of C=9) = 3 |

### Step 4: Calculate Float / Slack

- **Total Float (TF)** = LF − EF (or LS − ES)
- **Free Float (FF)** = min(ES of successors) − ES of activity − Duration

| Activity | ES | EF | LS | LF | TF | FF | Critical? |
|----------|----|----|----|----|----|----|-----------|
| A | 0 | 3 | 0 | 3 | 0 | 0 | Yes |
| B | 3 | 7 | 3 | 7 | 0 | 0 | Yes |
| C | 3 | 5 | 9 | 11 | 6 | 0 | No |
| D | 7 | 12 | 7 | 12 | 0 | 0 | Yes |
| E | 5 | 6 | 11 | 12 | 6 | 5 | No |
| F | 5 | 7 | 14 | 16 | 9 | 9 | No |
| G | 12 | 16 | 12 | 16 | 0 | 0 | Yes |
| H | 16 | 19 | 16 | 19 | 0 | 0 | Yes |

**Critical path activities**: A, B, D, G, H (TF = 0).

### Second CPM Example (Practice)

| Activity | Predecessor | Duration |
|----------|-------------|----------|
| A | — | 5 |
| B | A | 4 |
| C | A | 5 |
| D | B | 6 |
| E | C | 3 |
| F | D, E | 4 |

**Paths:**
- A → B → D → F = 5 + 4 + 6 + 4 = **19** (Critical)
- A → C → E → F = 5 + 5 + 3 + 4 = **17**

---

## Resource Leveling

- **Goal**: Resolve resource conflicts, balance usage, smooth demand.
- **Techniques**: Delay non-critical activities (use float), split tasks, add resources.
- **Trade-offs**: May extend project duration and increase cost.
- **Key insight**: If you have more tasks than people at any point, use the float on non-critical path activities to shift work.

---

## Earned Value Management (EVM) Basics

| Term | Meaning |
|------|---------|
| **PV (Planned Value)** | Budgeted cost of work scheduled (what you planned to have done by now). |
| **EV (Earned Value)** | Budgeted cost of work performed (what you actually completed, in budget terms). |
| **AC (Actual Cost)** | Actual cost incurred for work performed. |
| **SV (Schedule Variance)** | EV − PV (positive = ahead of schedule). |
| **CV (Cost Variance)** | EV − AC (positive = under budget). |

EVM enables objective tracking of whether a project is on schedule and on budget.

---

## Relationships Between Concepts

```
Project Scope Statement
         |
         v
    Work Breakdown Structure (What)
         |
         v
    Activity Definition & Sequencing
         |
         v
    Resource Estimation & Duration Estimation
         |
         v
    Schedule Development (When)
         |
         v
    CPM / Critical Path Analysis
         |
         v
    Resource Leveling (if needed)
         |
         v
    Baseline Schedule + EVM Tracking
```

- Without WBS, estimates are guesswork.
- Without CPM, you don't know which tasks drive the deadline.
- Without resource leveling, your schedule may be infeasible.
- Without EVM, you can't objectively tell if you're on track.

---

## Common Mistakes / Exam Traps

| Trap | Correction |
|------|------------|
| Confusing WBS with a schedule | WBS is deliverable hierarchy, not a timeline. |
| Forgetting support activities in WBS | Include PM, admin, training, etc. |
| Making work packages too large (>80 hrs) | Break down further for accurate estimates. |
| Using activities instead of deliverables in WBS | WBS nodes are deliverables, not actions. |
| Incorrect forward pass | ES of successor = max(EF of all predecessors). |
| Forgetting to check all predecessors on merge points | Activity G depends on BOTH D and E — use max EF. |
| Misidentifying critical path | Path with longest total duration, not most activities. |
| TF = 0 automatically means critical | Yes — but also check that the path is continuous. |
| Thinking all float is usable without risk | Free float is safer to use; using total float may affect successors. |
| Confusing ES/EF forward pass with LS/LF backward pass | Forward = earliest; backward = latest. |
| Not allowing contingency | "The unexpected always happens." |

---

## Active Recall Questions

1. What are the three types of work that must be included in a WBS?
2. What is the difference between Contract WBS and Project WBS?
3. What is the 80-hour rule for work packages?
4. Why can't a WBS be used as a schedule?
5. Calculate ES, EF, LS, LF for all activities in the second CPM example (A=5, B=4, C=5, D=6, E=3, F=4).
6. What is the difference between Total Float and Free Float?
7. What is Brooks' Law and how does it relate to scheduling?
8. Name three EVM metrics and what they measure.
9. What happens to the project duration after resource leveling?
10. List five rules for creating an activity network diagram.

**Answers:**
1. Product, Integration, Support.
2. CWBS = first 2–3 levels, used for client reporting; PWBS = defined by PM team, lowest-level tracking.
3. Work packages should be no larger than ~80 hours of effort for accurate estimation.
4. WBS shows deliverables, not time-dependent activities with dates and dependencies.
5. Critical path = A→B→D→F = 19. (A: ES=0, EF=5; B: ES=5, EF=9, D: ES=9, EF=15; F: ES=15, EF=19; C: ES=5, EF=10; E: ES=10, EF=13; C/E have float.)
6. Total Float = LF−EF (delay without affecting project end); Free Float = min(ES successor) − ES − Duration (delay without affecting next activity).
7. Adding people to a late project makes it later due to communication overhead.
8. PV (Planned Value), EV (Earned Value), AC (Actual Cost). SV = EV−PV, CV = EV−AC.
9. It typically extends the project duration.
10. Flow left to right, predecessors must finish, arrows can cross, each activity has an ID, no looping, IDs increase.

---

## Potential Exam Questions

1. **Draw** an activity network diagram for a given set of activities with predecessors and durations.
2. **Calculate** the critical path, ES, EF, LS, LF, Total Float, and Free Float for all activities.
3. **Explain** the difference between a WBS and a project schedule using examples.
4. **Describe** the three types of work in a WBS and why each is important.
5. **Discuss** how the Wideband Delphi technique improves estimation accuracy.
6. **Analyze** a scenario where resource leveling is needed and describe the trade-offs involved.
7. **Compare** CPM and PERT approaches to activity networks.
8. **Given EVM data** (PV, EV, AC), calculate SV and CV and interpret whether the project is ahead/behind schedule and under/over budget.
9. **Identify** and **correct** errors in a faulty WBS or activity network.
10. **Explain** why the WBS must be developed before scheduling can begin.

---

## Topic Summary

- **WBS** decomposes the project into deliverable-oriented hierarchical components, enabling accurate estimation, clear ownership, and scope control.
- **WBS formats**: Outline (indented) and Graphical Tree. Both should include product, integration, and support work.
- **WBS pitfalls**: Wrong detail level, using activities instead of deliverables, treating WBS as a schedule.
- **Project scheduling** converts the plan into a timeline with dependencies, resources, and dates using Gantt charts and activity networks.
- **CPM** identifies the critical path (longest duration path). Activities on this path have zero total float and cannot be delayed without extending the project.
- **Forward pass** computes ES and EF. **Backward pass** computes LS and LF. **Float** = LS−ES or LF−EF.
- **Resource leveling** resolves conflicts but may extend duration.
- **EVM** uses PV, EV, AC to compute Schedule Variance (SV) and Cost Variance (CV) for objective progress tracking.
- The WBS is the **foundation** — without it, scheduling, estimation, and control are unreliable.