# Software Estimation - Mind Map

```
                                  SOFTWARE PROJECT ESTIMATION
                                        │
            ┌───────────────────────────┼───────────────────────────┐
            │                           │                           │
       WHY ESTIMATE?           WHAT IS ESTIMATED?          ESTIMATION TECHNIQUES
            │                           │                           │
  ┌─────────┼─────────┐     ┌───────────┼───────────┐     ┌─────────┼─────────┐
  │         │         │     │           │           │     │         │         │
STAKEHOLDERS VENDORS  │  SCOPE      TIME       COST     DELPHI  WIDEBAND  ANALOGY
confidence  budget   │     │           │           │     │      DELPHI      │
  │         │         │     │           │           │     │         │         │
  TEAM      PROJECT   │  ┌──┴──┐   ┌───┴───┐   ┌──┴──┐  │  ┌───────┼───────┐
  knows     MANAGER   │  │LOC  │   │Activity│   │People│  │  │       │       │
  what/when less work │  │ FP  │   │Network │   │Equip │  │STEP 1  STEP 2  STEP 3
                      │  │     │   │Diagram │   │License│  │Choose  Kickoff  Indiv.
                      │  │     │   │        │   │Admin  │  │Team    Meeting  Prep.
                      │  │     │   │        │   │Train  │  │(3-7)   (WBS,   (Est.
                      │  │     │   │        │   │       │  │        Assump.) each)
                      │  │     │   │        │   │       │  │  │       │       │
                      │  │     │   │        │   │       │  │STEP 4  STEP 5  STEP 6
                      │  │     │   │        │   │       │  │Estimate Assemble Review
                      │  │     │   │        │   │       │  │Session  Tasks   Results
                      │  │     │   │        │   │       │  │(rounds,
                      │  │     │   │        │   │       │  │converge)
                      │  │     │   │        │   │       │
                      │  │     │   │        │   │       │
            ┌─────────┴──┴──┐  │        │   │       OTHER TECHNIQUES
            │               │  │        │   │       │
      SIZE MEASUREMENT      │  │        │   │  ┌─────┼─────┬─────┐
            │               │  │        │   │  │     │     │     │
   ┌────────┴────────┐      │  │        │   │Expert Top-  Bottom Parkin.
   │                 │      │  │        │   │Judge Down   Up    Law
   │                 │      │  │        │   │
 ┌─┴──┐          ┌──┴───┐  │  │        │   │
 │ LOC │          │  FP  │  │  │        │   │
 └──┬──┘          └──┬───┘  │  │        │   │
    │                │      │  │        │   │
    │ 3-Point Formula│      │  │        │   │
    │ Sopt+4Sm+Spess │      │  │        │   │
    │ ─────────────  │      │  │        │   │
    │       6        │      │  │        │   │
    │                │      │  │        │   │
    ├────────────────┼──────┼──┼────────┼───┤
    │                │      │  │        │   │
    │          ┌─────┴──┐   │  │        │   │
    │          │  UFP   │   │  │        │   │
    │          │ ┌──┼──┐│   │  │        │   │
    │          │ │  │  ││   │  │        │   │
    │          │EI EO EQ│   │  │        │   │
    │          │ILF EIF │   │  │        │   │
    │          └──┬──┬──┘   │  │        │   │
    │             │  │      │  │        │   │
    │     ┌───────┘  └──┐   │  │        │   │
    │     │              │   │  │        │   │
    │  ┌──┴──┐      ┌────┴──┐│  │        │   │
    │  │CAF  │      │ 14 Fi ││  │        │   │
    │  │0.65 │      │(0-5)  ││  │        │   │
    │  │+0.01│      │F1-F14 ││  │        │   │
    │  │×ΣFi │      └───┬───┘│  │        │   │
    │  └──┬──┘          │    │  │        │   │
    │     └──────┬──────┘    │  │        │   │
    │            │           │  │        │   │
    │       ┌────┴────┐      │  │        │   │
    │       │FP = UFP │      │  │        │   │
    │       │  × CAF  │      │  │        │   │
    │       └────┬────┘      │  │        │   │
    │            │           │  │        │   │
    │            └─────┬─────┘  │        │   │
    │                  │        │        │   │
    │          ┌───────┴──────┐ │        │   │
    │          │ Effort & Cost │ │        │   │
    │          │ from FP      │ │        │   │
    │          └──────────────┘ │        │   │
    │                           │        │   │
    │                           │        │   │
    │                    ┌──────┴─────────┴─┐
    │                    │  COCOMO MODELS   │
    │                    └────────┬─────────┘
    │                             │
    │          ┌──────────────────┼──────────────────┐
    │          │                  │                  │
    │    ┌─────┴─────┐    ┌──────┴──────┐    ┌──────┴──────┐
    │    │   BASIC   │    │  COCOMO II  │    │            │
    │    │  COCOMO   │    │   (Modern)  │    │            │
    │    └─────┬─────┘    └──────┬──────┘    │            │
    │          │                 │            │            │
    │    ┌─────┼─────┐    ┌─────┼─────┐      │            │
    │    │     │     │    │     │     │      │            │
    │  ORG   SEMI  EMB  APPL  EARLY POST    │            │
    │  2.4   3.0   3.6 COMP. DESIGN ARCH    │            │
    │  1.05  1.12  1.20 (Obj. (FP,  (KLOC   │            │
    │                Points) 7 CD)  17 CD)   │            │
    │                │         │         │   │            │
    │                │         │         │   │            │
    │   ┌────────────┴─────────┴─────────┴───┴──────┐    │
    │   │         ALGORITHMIC FORMULA              │    │
    │   │    Effort = A × (Size)^B × M             │    │
    │   │    TDEV = C × (Effort)^D                 │    │
    │   │    Staff = Effort / TDEV                 │    │
    │   │    Cost = Effort × Cost_per_PM           │    │
    │   └──────────────────────────────────────────┘    │
    │                         │                         │
    │                         │                         │
    │          ┌──────────────┴──────────────┐          │
    │          │                             │          │
    │    ┌─────┴──────┐              ┌───────┴──────┐   │
    │    │SCALE FACTORS│              │ COST DRIVERS │   │
    │    │(B exponent) │              │  (EAF = M)   │   │
    │    └─────┬───────┘              └───────┬──────┘   │
    │          │                             │          │
    │    ┌─────┼──────┐            ┌─────────┼─────────┐│
    │    │     │      │            │         │         ││
    │  PREC  RESL  TEAM           │         │         ││
    │  DFLEX       PMAT        PRODUCT   PLATFORM  PERSONNEL
    │                            │         │         │
    │                        RELY DATA   TIME STOR  ACAP PCAP
    │                        CPLX RUSE   PVOL       AEXP PEXP
    │                        DOCU                    LTEX
    │                                                 │
    │                                            PROJECT
    │                                             │
    │                                          TOOL SITE
    │                                          SCED
    │
    │
    │                    KEY FORMULAS (Summary)
    │
    ├───────────────────────────────────────────────────────
    │
    │  LOC 3-POINT:    S = (Sopt + 4Sm + Spess) / 6
    │
    │  UFP:            UFP = Σ(count × weight) for EI/EO/EQ/ILF/EIF
    │
    │  CAF:            CAF = 0.65 + (0.01 × ΣFi), range [0.65, 1.35]
    │
    │  FP:             FP = UFP × CAF
    │
    │  BASIC COCOMO:   E = a(KLOC)^b, D = c(E)^d, S = E/D, C = E × $/PM
    │
    │  COCOMO II:      PM = 2.94 × (Size)^B × M
    │                  B = 0.91 + 0.01 × Σ(scale factors)
    │                  TDEV = 3.67 × (PM)^F, F = 0.28 + 0.2(B - 0.91)
    │
    │  COST from FP:   Cost = (FP × (LOC/FP) / (LOC/PM)) × Cost/PM
    │
    │  EAF (M):        M = Π(all cost driver multipliers)
    │
    │
    │                    COMMON TRAPS
    │
    ├───────────────────────────────────────────────────────
    │
    │  - Don't forget the 4x weight on 'most likely' in the 3-point formula
    │  - CAF range is 0.65 to 1.35, NOT 0 to 1
    │  - Personnel multipliers < 1.00 mean BETTER capability = LESS effort
    │  - COCOMO uses KLOC, not raw LOC (32,000 LOC = 32 KLOC)
    │  - FP is language-independent; LOC is language-dependent
    │  - Moderator in Wideband Delphi must be NEUTRAL (not PM)
    │  - ILF = internal files; EIF = external interface files (don't confuse)
    │  - EI = data in; EO = data out; EQ = inquiry (read-only)
    │
    │
    │               FP INFO DOMAIN WEIGHT TABLE
    │
    ├───────────────────────────────────────────────────────
    │
    │  Domain       Simple  Average  Complex
    │  ─────────────────────────────────────
    │  EI             3       4        6
    │  EO             4       5        7
    │  EQ             3       4        6
    │  ILF            7      10       15
    │  EIF            5       7       10
    │
    │
    │             BASIC COCOMO PARAMETER TABLE
    │
    ├───────────────────────────────────────────────────────
    │
    │  Mode          a     b     c     d
    │  ────────────────────────────────────────
    │  Organic      2.4  1.05  2.5  0.38
    │  Semi-Det     3.0  1.12  2.5  0.35
    │  Embedded     3.6  1.20  2.5  0.32
    │
    │
    │             COCOMO II 5 SCALE FACTORS
    │
    ├───────────────────────────────────────────────────────
    │
    │  PREC  DFLEX  RESL  TEAM  PMAT
    │  Each rated VL=1.24 ... VH=0.81/0.82
    │  B = 0.91 + 0.01 × Σ(ratings)
    │
    │
    │             14 VALUE ADJUSTMENT FACTORS (Fi)
    │
    ├───────────────────────────────────────────────────────
    │
    │  F1  Data Communications
    │  F2  Distributed Data Processing
    │  F3  Performance
    │  F4  Heavily Used Configuration
    │  F5  Transaction Rate
    │  F6  On-Line Data Entry
    │  F7  End-User Efficiency
    │  F8  On-Line Update
    │  F9  Complex Processing
    │  F10 Reusability
    │  F11 Installation Ease
    │  F12 Operational Ease
    │  F13 Multiple Sites
    │  F14 Facilitate Change
    │
    │  Each rated 0 (none) to 5 (essential)
    │  ΣFi ranges from 0 to 70
    │
    │
    │       PRODUCTIVITY DATA (Capers Jones)
    │
    ├───────────────────────────────────────────────────────
    │
    │  Application Type    LOC/PM     Cost/PM
    │  Low-level           3,200      $9,000
    │  Middle-level        2,300      $11,000
    │  High-level          1,200      $14,000
```
