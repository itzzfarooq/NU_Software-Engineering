# Project Scheduling & WBS — Mind Map

```
                                          +===========================================+
                                          |         PROJECT SCHEDULING & WBS         |
                                          +===========================================+
                                            /          |                |          \
                                           /           |                |           \
                                          /            |                |            \
                         +==============+   +==============+   +==============+   +==============+
                         |   1. WBS     |   | 2. SCHEDULING |   | 3. CPM / CPA |   | 4. CONTROL  |
                         +==============+   +==============+   +==============+   +==============+
                         /    |     \       /    |      \        /    |     \       /     |      \
                        /     |      \     /     |       \      /     |      \     /      |       \
              +-------+ +-------+ +-------+ +-------+ +-------+ +-------+ +-------+ +-------+ +-------+
              |DEFINE | |FORMATS| |PITFALL| |TECHNQ| |RESOURC| |NETWRK| |FORWARD| |BACKWRD| |  EVM  |
              |  &    | |       | |       | |      | |LEVELNG| | RULES| | PASS  | | PASS  | |       |
              |GOALS  | |       | |       | |      | |       | |      | |       | |       | |       |
              +-------+ +-------+ +-------+ +-------+ +-------+ +-------+ +-------+ +-------+ +-------+
              /  |   \    /   \      |        |   |       |       |        |        |        |
             /   |    \  /     \     |        |   |       |       |        |        |        |
      +-----+ +--+--+ +--+--+ +--+--+ +------+ +--+---+  |  +----+---+ +----+---+ +----+---+
      |DELVR | |OUTLN| |TREE | |WRONG| |ACTIVTY| | ID  |  |  | ES, EF | | LS, LF | | PV, EV |
      |-ORINT| |(INDT)| |(CHAR| |DETAL| |NETWORK| |  &  |  |  |max(EF) | |min(LS) | | SV, CV |
      |      | |     | | T)  | |     | |DIAGRAM| | DEP |  |  | fwd    | | bwd    | |        |
      +------+ +-----+ +-----+ +-----+ |(DAG)  | +------+  |  | pass  | | pass  | +--------+
                                        +-------+            +--------+ +--------+
                                        /   |   \
                                       /    |    \
                              +--------+ +----+ +----+
                              |GANTT CH| |ACTV| |MILST|
                              |(BAR CH)| |NET | |ONE  |
                              +--------+ +----+ +----+
                                              |
                                          +---+---+
                                          |  CPM  |
                                          | PERT  |
                                          +-------+


  +======================================================================+
  |                         WBS — DETAILED TREE                          |
  +======================================================================+
  |
  |   [Project]
  |      |
  |      +-- Level 1: Total Program (Managerial / Client-facing)
  |      |     |
  |      |     +-- Level 2: Project (Budgets)
  |      |            |
  |      |            +-- Level 3: Task (Schedules, Reporting)
  |      |
  |      +-- Level 4: Subtask (Technical, PM-defined)
  |      |     |
  |      |     +-- Level 5: Work Package (~80 hrs, estimated/tracked)
  |      |     |
  |      |     +-- Level 6: Level of Effort (Support)
  |
  |   WBS Work Types:
  |      +-- Product (physical deliverables)
  |      +-- Integration (bringing pieces together)
  |      +-- Support (admin, PM, training, expenses)
  |
  +======================================================================+


  +======================================================================+
  |                  CPM — CALCULATION FLOWCHART                         |
  +======================================================================+
  |
  |   +----------+     +----------+     +----------+     +----------+
  |   | ACTIVITY |---->| FORWARD  |---->| BACKWARD |---->|  FLOAT   |
  |   | LIST w/  |     | PASS     |     | PASS     |     |  CALC    |
  |   | DURATION |     | (ES, EF) |     | (LS, LF) |     | TF, FF   |
  |   +----------+     +----------+     +----------+     +----------+
  |                                                           |
  |                                                           v
  |                                                  +------------------+
  |                                                  | IDENTIFY CRITICAL|
  |                                                  | PATH (TF = 0)    |
  |                                                  +------------------+
  |
  |   Formulas:
  |   +----------------------------------------------------------+
  |   | EF = ES + Duration          (Forward Pass)               |
  |   | ES(successor) = max(EF of predecessors)                  |
  |   | LS = LF - Duration          (Backward Pass)              |
  |   | LF(predecessor) = min(LS of successors)                  |
  |   | Total Float = LF - EF  OR  LS - ES                      |
  |   | Free Float = min(ES_successors) - ES_self - Duration     |
  |   +----------------------------------------------------------+
  |
  +======================================================================+

  +======================================================================+
  |                    SCHEDULING PROBLEMS TREE                           |
  +======================================================================+
  |
  |   [SCHEDULING PROBLEMS]
  |      |
  |      +-- Estimation Difficulty
  |      |     +-- Predicting cost/effort is hard
  |      |     +-- Productivity not proportional to team size
  |      |
  |      +-- Brooks' Law
  |      |     +-- "Adding people to a late project makes it later"
  |      |     +-- Communication overhead increases
  |      |
  |      +-- The Unexpected
  |            +-- Always allow contingency
  |            +-- Risk management needed
  |
  +======================================================================+

  +======================================================================+
  |                    RESOURCE LEVELING TREE                            |
  +======================================================================+
  |
  |   [RESOURCE LEVELING]
  |      |
  |      +-- Goal: Balance resource demand, resolve conflicts
  |      |
  |      +-- Methods:
  |      |     +-- Use float to shift non-critical tasks
  |      |     +-- Split tasks into phases
  |      |     +-- Add resources (if feasible)
  |      |
  |      +-- Trade-offs:
  |            +-- May extend project duration
  |            +-- May increase cost
  |            +-- Requires time-cost trade-off decisions
  |
  +======================================================================+

  +======================================================================+
  |                      WBS PITFALLS TREE                               |
  +======================================================================+
  |
  |   [WBS PITFALLS]
  |      |
  |      +-- Wrong Level of Detail (too coarse or too fine)
  |      +-- Deliverables vs Activities (WBS is NOT task list)
  |      +-- WBS is not a Plan/Schedule (no dates, no dependencies)
  |      +-- WBS Updates Require Change Control (scope management)
  |      +-- WBS is not an Organizational Hierarchy (don't mirror company)
  |
  +======================================================================+
```