# Agile Software Development — Mind Map

```
                                      +============================================+
                                      |          AGILE SOFTWARE DEVELOPMENT        |
                                      |  "Responding to change over following a   |
                                      |   plan" — Manifesto for Agile (2001)      |
                                      +============================================+
                                                     |
      +----------------------------------------------+----------------------------------------------+
      |                                              |                                              |
      v                                              v                                              v
+====================+  +====================+  +====================+  +====================+  +====================+
| 1. WHY AGILE      |  | 2. AGILE MANIFESTO |  | 3. 12 PRINCIPLES   |  | 4. 5 AGILE         |  | 5. EXTREME         |
| EXISTS             |  | (2001)             |  |                    |  | PRINCIPLES         |  | PROGRAMMING (XP)   |
+====================+  +====================+  +====================+  +====================+  +====================+
| Fast-changing      |  | Individuals &      |  | 1.  Welcome change  |  | Customer           |  | (See nested box    |
| business needs     |  | interactions >     |  | 2.  Deliver freq.   |  | involvement        |  |  tree below)       |
| Plan-driven too    |  |   processes/tools  |  | 3.  Business + devs |  | Incremental        |  |                    |
| slow/rigid         |  | Working software > |  |     work daily      |  | delivery           |  |                    |
| Need rapid         |  |   comprehensive    |  | 4.  Motivated indiv.|  | People not process |  |                    |
| delivery/evolution |  |   docs             |  | 5.  Face-to-face    |  | Embrace change     |  |                    |
| Late 1990s         |  | Customer collab. > |  | 6.  Working sw =    |  | Maintain simplicity|  |                    |
| reaction to        |  |   contract negot.  |  |     progress        |  +====================+  |                    |
| heavyweight methods|  | Respond to change >|  | 7.  Sustainable     |                         |                    |
+====================+  |   following plan   |  |     pace            |                         |                    |
                        +====================+  | 8.  Technical       |                         |                    |
                                                |     excellence      |                         |                    |
                                                | 9.  Simplicity      |                         |                    |
                                                | 10. Self-organizing  |                         |                    |
                                                | 11. Reflect/adjust  |                         |                    |
                                                | 12. Customer        |                         |                    |
                                                |     involvement     |                         |                    |
                                                |     throughout      |                         |                    |
                                                +====================+                         |                    |
                                                                                                |                    |
      +----------------------------------------------+------------------------------------------+                    |
      |                                              |                                                                 |
      v                                              v                                                                 |
+====================+  +====================+  +====================+  +====================+                           |
| 6. SCRUM          |  | 7. SCRUM vs XP    |  | 8. AGILE vs        |  | 9. APPLICABILITY   |                           |
+====================+  +====================+  | TRADITIONAL        |  +====================+                           |
| (See nested box   |  | Scrum = Management |  +====================+  | GOOD FOR           |                           |
|  tree below)      |  | XP = Technical     |  | (See comparison    |  | Small/medium       |                           |
|                    |  | COMPLEMENTARY      |  |  table below)      |  | product dev.       |                           |
|                    |  | (not alternatives) |  | 17 differences     |  | Custom systems     |                           |
|                    |  +====================+  +====================+  | (committed client)  |                           |
|                    |                                               | Non-critical sys.   |                           |
|                    |  +====================+                       +====================+                           |
|                    +--+ 10. SCALING AGILE |                       | NOT SUITABLE       |                           |
|                       +====================+                       | Large systems      |                           |
|                       | PROBLEMS           |                       | (hard to scale)    |                           |
|                       | - Large teams: can't|                      | Safety-critical    |                           |
|                       |   maintain XP      |                       | (need docs)        |                           |
|                       | - Communication    |                       | Outsourced dev.    |                           |
|                       |   overhead         |                       | (contract issues)  |                           |
|                       | - Legacy/plan-dr.  |                       | Complex non-func.   |                           |
|                       |   components       |                       | requirements        |                           |
|                       | - Separate teams   |                       | Rigid process       |                           |
|                       |   conflict w/      |                       | standards           |                           |
|                       |   collective owner |                       +====================+                           |
|                       +--------------------+                                                                        |
|                       | STRATEGIES         |                                                                        |
|                       | Scale UP:          |                                                                        |
|                       |   Adapt agile for  |                                                                        |
|                       |   whole system     |                                                                        |
|                       |   (more arch, docs,|                                                                        |
|                       |   formal coord.)   |                                                                        |
|                       | Scale OUT:         |                                                                        |
|                       |   Agile for comp.  |                                                                        |
|                       |   Plan-driven for  |                                                                        |
|                       |   system integ.    |                                                                        |
|                       +====================+


--- EXTREME PROGRAMMING (XP) — Nested Detail ---

                                      +============================================+
                                      |       EXTREME PROGRAMMING (XP) DETAIL      |
                                      +============================================+
                                                   |
              +------------------------------------+------------------------------------+
              |                                    |                                    |
              v                                    v                                    v
+==============================+  +======================================+  +==============================+
| XP RELEASE CYCLE             |  | 10 XP PRACTICES                      |  | KEY TECHNIQUES                |
+------------------------------+  +--------------------------------------+  +------------------------------+
| Select user stories          |  | 1.  Incremental planning             |  | User stories                 |
| Break stories into tasks     |  | 2.  Small releases                  |  | (As a... I want... so that)  |
| Plan release                 |  | 3.  Simple design                   |  | Planning game                |
| Develop / Integrate / Test   |  | 4.  Test-first development (TDD)    |  | (team estimation)            |
| Release software             |  | 5.  Refactoring                     |  | Automated testing            |
| Evaluate → loop back         |  | 6.  Pair programming                |  | (xUnit, JUnit)               |
+------------------------------+  | 7.  Collective ownership            |  | UI prototyping               |
                                  | 8.  Continuous integration          |  +==============================+
                                  | 9.  Sustainable pace               |
                                  | 10. On-site customer                |
                                  +======================================+


--- SCRUM — Nested Detail ---

                                      +============================================+
                                      |              SCRUM DETAIL                  |
                                      +============================================+
                                                   |
              +------------------------------------+------------------------------------+
              |                                    |                                    |
              v                                    v                                    v
+==============================+  +======================================+  +==============================+
| SCRUM PRINCIPLES             |  | 3 ROLES                             |  | 5 EVENTS                     |
+------------------------------+  +--------------------------------------+  +------------------------------+
| Controlled chaos             |  | Scrum Master                        |  | Sprint (2-4 weeks)           |
| Commitment                   |  |   (facilitator, protector)          |  | Sprint Planning              |
| Information radiator         |  | Product Owner                       |  | Daily Stand-up               |
| Time-boxing                  |  |   (customer voice, backlog)         |  |   (15 min, 3 questions)      |
| Emergent requirements        |  | Team                                |  | Sprint Review                |
| People not process           |  |   (self-organizing, 5-7 people)     |  | Sprint Retrospective         |
+------------------------------+  +--------------------------------------+  +------------------------------+

+======================================+  +=============================================+
| 3 ARTIFACTS                          |  | BENEFITS & PROBLEMS                         |
+--------------------------------------+  +---------------------------------------------+
| Product Backlog                      |  | BENEFITS:                                    |
| Sprint Backlog                       |  |   Empowerment, morale, transparency,         |
| Burndown Chart                       |  |   prioritization                             |
+--------------------------------------+  | PROBLEMS:                                    |
                                          |   Role conflict, imposition w/o training,    |
                                          |   lack of authority                          |
                                          +=============================================+

```

## Comparison Tables

### AGILE vs TRADITIONAL — 17 Differences

```
+==========================================================================================================+
| DIMENSION           | AGILE                                           | TRADITIONAL                        |
+==========================================================================================================+
| Team                | Whole team                                      | Hierarchy                          |
| Requirements        | User stories                                    | Analyst-written specs              |
| Iteration           | 1-4 weeks                                       | 2-3 months                         |
| Acceptance tests    | During iteration                                | At end                             |
| Programming         | Pair programming                                | Solo + QA                          |
| Testing             | TDD                                             | After coding                       |
| Ownership           | Collective                                      | Manager                            |
| Integration         | Continuous                                      | End of module                      |
| Pace                | Sustainable (marathon)                          | 80/20 sprint                       |
| Workspace           | Open room                                       | Cubicles                           |
| Design              | Simple, just-in-time                            | Big upfront                        |
| Refactoring         | Continuous                                      | End of project                     |
| Documentation       | Light                                           | Intensive                          |
| Task allocation     | Team self-selects                               | PM assigns                         |
| Progress            | Burndown chart                                  | Task count                         |
| Status              | Daily stand-up                                  | Weekly PM meeting                  |
| Project status      | Status board                                    | Completed tasks                    |
+==========================================================================================================+
```

### SCRUM vs XP

```
+==============================================================+
| SCRUM                    vs          XP                      |
+==============================================================+
| Management framework     vs   Technical practices            |
| COMPLEMENTARY — not alternatives!                            |
+==============================================================+
```

## Legend

```
+============================+  = Title Node (Major topic)
|                            |
+============================+

+----------------------------+  = Sub-node (Properties, details)
|                            |
+----------------------------+

TEXT = Description / Detail

│     = Vertical connector
├──   = Branch (has siblings below)
└──   = Final branch (no siblings below)
v     = Hierarchical connection (parent → child)
```

*End of Agile Software Development Mind Map*
