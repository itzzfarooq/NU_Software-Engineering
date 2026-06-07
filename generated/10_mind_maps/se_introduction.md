# Mind Map: Introduction to Software Engineering

```
                                   +================================+
                                   |    SOFTWARE ENGINEERING        |
                                   |  (Ch.1 - Introduction)         |
                                   +================================+
                                              |
            +----------+----------+-----------+-----------+----------+----------+
            |          |          |           |           |          |          |
            v          v          v           v           v          v          v
     +----------+ +----------+ +--------+ +--------+ +--------+ +--------+ +--------+
     |   WHAT   | |   WHY    | |COSTS & | |  GOOD  | |PROCESS | |  APP   | |DIVERSITY|
     |    IS    | |IMPORTANT | |FAILURE | |SOFTWARE| |ACTIVS  | | TYPES  | & CHALL.|
     |    SE?   | |          | |        | |ATTRS   | |        | |        |         |
     +----------+ +----------+ +--------+ +--------+ +--------+ +--------+ +--------+
          |             |          |           |           |           |          |
          v             v          v           v           v           v          v
   +----------+   +-----------+ +------+ +--------+ +-----------+ +----------+ +------+
   |Engineering|   |Economies  | |COST | |MAINTAI-| |1.SPECIFI- | |Standalone| |Hetero-|
   |discipline |   |depend on  | |FACTS| |NABILITY| |  CATION   | |Interactive|geneity|
   |all aspects|   |software   | |     | |        | |           | |Embedded  |      |
   |of software|   |           | |60%  | |Evolve  | |2.DEVELOP- | |Batch     |Security|
   |production |   |Society    | |devel| |to meet | |  MENT     | |Entertain | & Trust|
   |           |   |relies on  | |40%  | |changing| |           | |Simulation|      |
   |Theory +   |   |trustworthy| |test | |needs   | |3.VALIDA-  | |Data Coll | Scale |
   |methods +  |   |systems    | |     | |        | |  TION     | |Sys-of-Sys|      |
   |constraints|   |           | |MAINT| |DEPENDA-| |           | |          | Speed |
   |           |   |Cheaper in | |COSTS| |BILITY &| |4.EVOLU-   | +----------+ of    |
   |NOT just   |   |long run to| |>    | |SECURITY | |  TION     |      |     Change |
   |coding     |   |use SE     | |devel| |        | +-----------+      |            |
   |           |   |methods    | |     | |Reliable |      |             v            |
   |SE != CS   |   |           | |     | |+Safe +  |      v       +-----------+     |
   |SE != SysE |   +-----------+ |     | |Secure   |  +---------+ | WEB-BASED|     |
   +----------+                  |     | |         |  |ITERATIVE| | SOFTWARE |     |
                                 |     | |EFFICIEN-|  |  CYCLE  | |  ENGINE- |     |
                                 |     | |  CY     |  |         | |   ERING  |     |
                                 |     | |         |  |Spec->Dev| +----------+     |
                                 |     | |Response,|  |>Valid-> |      |           |
                                 |     | |Memory,  |  |>Evolve  |      v           |
                                 |     | |CPU use  |  +---------+  +-----------+   |
                                 |     | |         |                |REUSE is   |   |
                                 |     | |ACCEPTA- |                |dominant   |   |
                                 |     | | BILITY  |                |approach   |   |
                                 |     | |         |                |           |   |
                                 |     | |Usable,  |                |Incremental|   |
                                 |     | |Underst- |                | & agile   |   |
                                 |     | |andable, |                |developmt  |   |
                                 |     | |Compatibl|                +-----------+   |
                                 |     | +--------+                                   |
                                 |     |                                               |
                                 |     v                                               |
                                 | +------+                                            |
                                 | |PROJCT|                                            |
                                 | |FAILUR|                                            |
                                 | |FACTOR|                                            |
                                 | +------+                                            |
                                 |    |                                                |
                                 |    +-- Incr. complexity                             |
                                 |    +-- No SE methods used                           |
                                 |    +-- Changing requirements                        |
                                 |    +-- Poor specification                           |
                                 |    +-- Inadequate testing                           |
                                 |                                                     |
                                 |       +===================================+         |
                                 |       |       ACM/IEEE CODE OF ETHICS    |         |
                                 |       +===================================+         |
                                 |           |       |        |        |              |
                                 |           v       v        v        v              |
                                 |    +--------+ +------+ +------+ +------+           |
                                 |    |Best    | |Trust-| |Respt | |Safe  |           |
                                 |    |interest| |worthy| |IP    | |&Rel. |           |
                                 |    |of      | |& de- | |rights| |approv|           |
                                 |    |client  | |pendab| |      | |only  |           |
                                 |    +--------+ +------+ +------+ +------+           |
                                 |                                                       
                                 |       +============================================+
                                 +----->|            CASE STUDIES                     |
                                        +============================================+
                                            |               |                  |
                                            v               v                  v
                                   +---------------+ +-------------+ +------------------+
                                   |INSULIN PUMP  | |  MENTCARE   | |WILDWEATHERS      |
                                   |              | |             | |                  |
                                   |Embedded      | |Medical Info | |Data Collection   |
                                   |Control System| |System       | |+ Web-Based       |
                                   |              | |             | |                  |
                                   |Safety-critical| |Confidential | |Remote stations   |
                                   |Real-time     | |records      | |24/7 availability |
                                   |Dependability | |Multi-context| |Large data volumes|
                                   |Failure=death | |Availability | |Internet delivery |
                                   +---------------+ +-------------+ +------------------+



                    +==============================================+
                    |      GENERIC vs. CUSTOMIZED PRODUCTS         |
                    +==============================================+
                           |                              |
                           v                              v
                  +------------------+          +------------------+
                  |   GENERIC        |          |  CUSTOMIZED      |
                  |   (off-the-shelf)|          |  (bespoke)       |
                  +------------------+          +------------------+
                  | Spec owned by    |          | Spec owned by    |
                  | developer        |          | customer         |
                  | Change decisions |          | Change decisions |
                  | by developer     |          | by customer      |
                  | PC software, CAD |          | Embedded control,|
                  | dental apps     |          | ATC, traffic     |
                  +------------------+          +------------------+



        +=============================================================+
        |          FUNDAMENTAL PRINCIPLES (apply to ALL systems)       |
        +=============================================================+
            |           |               |               |
            v           v               v               v
     +----------+ +-----------+ +---------------+ +-----------------+
     |Managed & | |Dependabil| |Understanding  | |Reuse existing   |
     |understood| |ity & perf| |& managing reqs| |software where   |
     |process   | |important | |(what software | |appropriate      |
     |          | |for all   | |should do)     | |                 |
     +----------+ +----------+ +---------------+ +-----------------+



    +====================================================================+
    |                   SOFTWARE ENGINEERING vs.                          |
    |              COMPUTER SCIENCE vs. SYSTEM ENGINEERING                |
    +====================================================================+

    +--------------------------+   +------------------------------+
    |   COMPUTER SCIENCE       |   |   SOFTWARE ENGINEERING       |
    |   Theory & fundamentals  |   |   Practicalities of deliv-   |
    |   Algorithms, proofs,    |   |   ering useful software      |
    |   data structures        |   |   Specification through      |
    |                          |   |   maintenance + management   |
    +--------------------------+   +------------------------------+
                     \                          /
                      \                        /
                       v                      v
              +------------------------------------------+
              |       SYSTEM ENGINEERING                  |
              |  All aspects of computer-based systems:   |
              |  Hardware + Software + Process Eng.       |
              |  (SE is a SUBSET of SysE)                 |
              +------------------------------------------+
```

