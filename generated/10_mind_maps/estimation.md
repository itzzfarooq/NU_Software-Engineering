# Software Estimation - Mind Map

```
                                     +==================================================+
                                     |          SOFTWARE PROJECT ESTIMATION             |
                                     |  Predict effort, cost, and schedule accurately   |
                                     +==================================================+
                                                    |
              +-------------------------------------+-------------------------------------+
              |                                     |                                     |
              v                                     v                                     v
+-----------------------------+       +-----------------------------+       +-----------------------------+
|      WHY ESTIMATE?          |       |    WHAT IS ESTIMATED?       |       |   ESTIMATION TECHNIQUES     |
+-----------------------------+       +-----------------------------+       +-----------------------------+
|                             |       |                             |       |                             |
|  +-----------+              |       |  +---------+                |       |  +-----------+              |
|  |STAKEHOLDER|              |       |  | SCOPE   |                |       |  | DELPHI    |              |
|  |confidence |              |       |  +---------+                |       |  +-----------+              |
|  +-----------+              |       |    |                        |       |                             |
|  +-----------+              |       |    +-- LOC                  |       |  +-----------+              |
|  | VENDORS   |              |       |    +-- FP                   |       |  |WIDEBAND   |              |
|  | budget    |              |       |                             |       |  | DELPHI    |              |
|  +-----------+              |       |  +---------+                |       |  +-----------+              |
|  +-----------+              |       |  | TIME     |                |       |    |                       |
|  | TEAM knows|              |       |  +---------+                |       |    +-- Step 1: Choose Team  |
|  | what/when |              |       |    |                        |       |    +-- Step 2: Kickoff      |
|  +-----------+              |       |    +-- Activity Network     |       |    |    Meeting (WBS,       |
|  +-----------+              |       |    |   Diagram              |       |    |    Assumptions)        |
|  | PROJECT   |              |       |    |                        |       |    +-- Step 3: Individual  |
|  | MANAGER   |              |       |  +---------+                |       |    |    Prep (Est. each)   |
|  | less work |              |       |  | COST     |                |       |    +-- Step 4: Est.        |
|  +-----------+              |       |  +---------+                |       |    |    Session (rounds,   |
|                             |       |    |                        |       |    |    converge)           |
|                             |       |    +-- People               |       |    +-- Step 5: Assemble    |
|                             |       |    +-- Equipment            |       |    |    Tasks               |
|                             |       |    +-- License              |       |    +-- Step 6: Review      |
|                             |       |    +-- Admin                |       |         Results           |
|                             |       |    +-- Training             |       |                             |
+-----------------------------+       +-----------------------------+       +-----------------------------+
                                                                              |
                                                                              v
                                                                   +-----------------------+
                                                                   |  OTHER TECHNIQUES     |
                                                                   +-----------------------+
                                                                   |                       |
                                                                   |  +------------------+ |
                                                                   |  | Expert Judge     | |
                                                                   |  +------------------+ |
                                                                   |  +------------------+ |
                                                                   |  | Top-Down         | |
                                                                   |  +------------------+ |
                                                                   |  +------------------+ |
                                                                   |  | Bottom-Up        | |
                                                                   |  +------------------+ |
                                                                   |  +------------------+ |
                                                                   |  | Analogy          | |
                                                                   |  +------------------+ |
                                                                   |  +------------------+ |
                                                                   |  | Planning Poker   | |
                                                                   |  +------------------+ |
                                                                   +-----------------------+


+===============================================================================================================+
|                                          SIZE MEASUREMENT & COCOMO                                            |
+===============================================================================================================+

  +--------------------------------------------------------+
  |                  SIZE METRICS                          |
  +--------------------------------------------------------+
  |                                                        |
  |  3-Point Formula:  S = (Sopt + 4Sm + Spess) / 6       |
  |                                                        |
  |  +----------+              +----------+                 |
  |  |   LOC    |              |    FP    |                 |
  |  +----------+              +----------+                 |
  |                                                        |
  |  +--------------------------------------------------+  |
  |  |           FUNCTION POINT (FP) DETAIL               |  |
  |  +--------------------------------------------------+  |
  |  |  UFP = Sigma(count x weight) for EI/EO/EQ/ILF/EIF |  |
  |  |                                                    |  |
  |  |  +------+ +------+ +------+ +------+ +------+      |  |
  |  |  | EI   | | EO   | | EQ   | | ILF  | | EIF  |      |  |
  |  |  +------+ +------+ +------+ +------+ +------+      |  |
  |  |                                                    |  |
  |  |  CAF = 0.65 + (0.01 x Sigma Fi) [0.65 .. 1.35]    |  |
  |  |  FP = UFP x CAF                                    |  |
  |  |                                                    |  |
  |  |  14 Value Adjustment Factors F1-F14, each 0-5      |  |
  |  |  Sigma Fi ranges from 0 to 70                      |  |
  |  +--------------------------------------------------+  |
  |                                                        |
  |  FP -> Effort & Cost:                                   |
  |  Cost = (FP x (LOC/FP) / (LOC/PM)) x Cost/PM           |
  +--------------------------------------------------------+


  +====================================================================+
  |                       COCOMO MODELS                                |
  +====================================================================+
  |                                                                    |
  |                    ALGORITHMIC FORMULA                             |
  |         Effort = A x (Size)^B x M                                 |
  |         TDEV = C x (Effort)^D                                     |
  |         Staff = Effort / TDEV                                     |
  |         Cost = Effort x Cost_per_PM                               |
  |                                                                    |
  |  +-----------------------------------+                             |
  |  |       BASIC COCOMO                |                             |
  |  +-----------------------------------+                             |
  |  | Mode      | a   | b   | c   | d   |                             |
  |  | Organic   | 2.4 |1.05 | 2.5 |0.38 |                             |
  |  | Semi-Det  | 3.0 |1.12 | 2.5 |0.35 |                             |
  |  | Embedded  | 3.6 |1.20 | 2.5 |0.32 |                             |
  |  +-----------------------------------+                             |
  |                                                                    |
  |  +-----------------------------------+                             |
  |  |       COCOMO II (Modern)          |                             |
  |  +-----------------------------------+                             |
  |  | PM = 2.94 x (Size)^B x M          |                             |
  |  | B = 0.91 + 0.01 x Sigma(SF)      |                             |
  |  | TDEV = 3.67 x (PM)^F             |                             |
  |  | F = 0.28 + 0.2(B - 0.91)         |                             |
  |  +-----------------------------------+                             |
  |                                                                    |
  |  Applicable at 3 stages:                                           |
  |  - Application Composition (Object Points)                         |
  |  - Early Design (FP, 7 cost drivers)                               |
  |  - Post-Architecture (KLOC, 17 cost drivers)                       |
  |                                                                    |
  +====================================================================+


  +====================================================================+
  |             SCALE FACTORS (B exponent)       COST DRIVERS (EAF = M) |
  +====================================================================+
  |                                                                    |
  |  +-----+  +-----+  +-----+  +-----+  +-----+                      |
  |  | PREC|  |DFLEX|  |RESL |  |TEAM |  |PMAT |                      |
  |  +-----+  +-----+  +-----+  +-----+  +-----+                      |
  |  Each rated VL=1.24 ... VH=0.81/0.82                              |
  |  B = 0.91 + 0.01 x Sigma(ratings)                                 |
  |                                                                    |
  |  PRODUCT:       PLATFORM:         PERSONNEL:                       |
  |  RELY DATA      TIME STOR         ACAP PCAP                        |
  |  CPLX RUSE      PVOL              AEXP PEXP                        |
  |  DOCU                              LTEX                            |
  |                                                                    |
  |  PROJECT:                                                          |
  |  TOOL SITE                                                         |
  |  SCED                                                              |
  |                                                                    |
  +====================================================================+

  +====================================================================+
  |                       KEY FORMULAS (Summary)                       |
  +====================================================================+
  |                                                                    |
  |  LOC 3-POINT:    S = (Sopt + 4Sm + Spess) / 6                     |
  |  UFP:            UFP = Sigma(count x weight) for EI/EO/EQ/ILF/EIF  |
  |  CAF:            CAF = 0.65 + (0.01 x Sigma Fi), range [0.65,1.35]|
  |  FP:             FP = UFP x CAF                                    |
  |  BASIC COCOMO:   E = a(KLOC)^b, D = c(E)^d, S = E/D,             |
  |                  C = E x $/PM                                      |
  |  COCOMO II:      PM = 2.94 x (Size)^B x M                         |
  |                  B = 0.91 + 0.01 x Sigma(scale factors)           |
  |                  TDEV = 3.67 x (PM)^F, F = 0.28 + 0.2(B - 0.91)  |
  |  COST from FP:   Cost = (FP x (LOC/FP) / (LOC/PM)) x Cost/PM      |
  |  EAF (M):        M = Pi(all cost driver multipliers)               |
  |                                                                    |
  +====================================================================+

  +====================================================================+
  |                       COMMON TRAPS                                 |
  +====================================================================+
  |                                                                    |
  |  - Don't forget the 4x weight on 'most likely' in 3-point formula  |
  |  - CAF range is 0.65 to 1.35, NOT 0 to 1                          |
  |  - Personnel multipliers < 1.00 mean BETTER cap. = LESS effort     |
  |  - COCOMO uses KLOC, not raw LOC (32,000 LOC = 32 KLOC)           |
  |  - FP is language-independent; LOC is language-dependent            |
  |  - Moderator in Wideband Delphi must be NEUTRAL (not PM)           |
  |  - ILF = internal files; EIF = external interface files            |
  |  - EI = data in; EO = data out; EQ = inquiry (read-only)          |
  |                                                                    |
  +====================================================================+

  +====================================================================+
  |               FP INFO DOMAIN WEIGHT TABLE                          |
  +====================================================================+
  |                                                                    |
  |  Domain       Simple  Average  Complex                              |
  |  -----------------------------------------                          |
  |  EI             3       4        6                                  |
  |  EO             4       5        7                                  |
  |  EQ             3       4        6                                  |
  |  ILF            7      10       15                                  |
  |  EIF            5       7       10                                  |
  |                                                                    |
  +====================================================================+

  +====================================================================+
  |             COCOMO II 5 SCALE FACTORS                              |
  +====================================================================+
  |                                                                    |
  |  PREC  DFLEX  RESL  TEAM  PMAT                                     |
  |  Each rated VL=1.24 ... VH=0.81/0.82                               |
  |  B = 0.91 + 0.01 x Sigma(ratings)                                  |
  |                                                                    |
  +====================================================================+

  +====================================================================+
  |             14 VALUE ADJUSTMENT FACTORS (Fi)                        |
  +====================================================================+
  |                                                                    |
  |  F1  Data Communications                                           |
  |  F2  Distributed Data Processing                                   |
  |  F3  Performance                                                   |
  |  F4  Heavily Used Configuration                                    |
  |  F5  Transaction Rate                                              |
  |  F6  On-Line Data Entry                                            |
  |  F7  End-User Efficiency                                           |
  |  F8  On-Line Update                                                |
  |  F9  Complex Processing                                            |
  |  F10 Reusability                                                   |
  |  F11 Installation Ease                                             |
  |  F12 Operational Ease                                              |
  |  F13 Multiple Sites                                                |
  |  F14 Facilitate Change                                             |
  |                                                                    |
  |  Each rated 0 (none) to 5 (essential)                              |
  |  Sigma Fi ranges from 0 to 70                                      |
  |                                                                    |
  +====================================================================+

  +====================================================================+
  |       PRODUCTIVITY DATA (Capers Jones)                             |
  +====================================================================+
  |                                                                    |
  |  Application Type    LOC/PM     Cost/PM                             |
  |  Low-level           3,200      $9,000                             |
  |  Middle-level        2,300      $11,000                            |
  |  High-level          1,200      $14,000                            |
  |                                                                    |
  +====================================================================+
```