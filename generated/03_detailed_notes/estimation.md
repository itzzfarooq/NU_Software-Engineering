# Software Estimation - Detailed Study Notes

---

## Topic Overview

Software project estimation is the process of predicting the effort, time, and cost required to build a software system. It is a critical project management activity performed during the planning phase, typically before development begins. Estimation uses historical data, structured techniques, and mathematical models to produce defensible forecasts that guide budgeting, scheduling, and resource allocation.

---

## Why This Topic Exists

- **Projects fail without accurate estimates** -- wrong estimation leads to wrong schedules, which leads to project failure, which shatters stakeholder trust
- **Stakeholders** need confidence about feasibility and design
- **Vendors** need to manage budgets based on expected effort
- **Team members** need to know what to do and when
- **Project managers** need everyone on the same page to reduce management burden
- **Bidding and contracts** require defensible cost figures
- **Resource planning** (people, equipment, licensing, training, admin) depends on estimates

---

## Core Concepts & Definitions

| Term | Definition |
|------|-----------|
| **Estimation** | The process of predicting the effort, cost, and time required to complete a software project |
| **LOC** | Lines of Code -- a size metric counting source lines (excluding blanks and comments) |
| **FP** | Function Points -- a size metric based on delivered functionality, independent of language |
| **Person-Month (PM)** | The amount of work one person can complete in one month |
| **KLOC** | Thousands of Lines of Code (1 KLOC = 1000 LOC) |
| **UFP** | Unadjusted Function Points -- raw count before complexity adjustment |
| **CAF / VAF** | Complexity Adjustment Factor / Value Adjustment Factor -- a multiplier (0.65 to 1.35) |
| **EAF** | Effort Adjustment Factor -- product of all cost driver multipliers in COCOMO |
| **WBS** | Work Breakdown Structure -- hierarchical decomposition of project tasks |
| **Productivity** | Rate of output per unit of effort (e.g., LOC/pm or FP/pm) |

### Assumptions Make Estimates More Accurate

- Team members make assumptions to deal with incomplete information
- Assumptions must be **written down** so that if they prove incorrect, the estimate can be backtracked and corrected

---

## LOC Estimation (3-Point Formula)

### The Three-Point (Expected Value) Formula

```
S = (S_opt + 4 * S_ml + S_pess) / 6
```

Where:
- **S_opt** = Optimistic estimate (best-case scenario)
- **S_ml** = Most likely estimate
- **S_pess** = Pessimistic estimate (worst-case scenario)

### Worked Example: 3D Geometric Analysis

| Parameter | Value |
|-----------|-------|
| Optimistic (S_opt) | 4,600 LOC |
| Most Likely (S_ml) | 6,900 LOC |
| Pessimistic (S_pess) | 8,600 LOC |

```
S = (4600 + 4 * 6900 + 8600) / 6
S = (4600 + 27600 + 8600) / 6
S = 40800 / 6
S = 6,800 LOC
```

### Full CAD System Example

| Function | Estimated LOC |
|----------|--------------|
| User Interface and Control Facilities (UICF) | 2,300 |
| 2D Geometric Analysis (2DGA) | 5,300 |
| 3D Geometric Analysis (3DGA) | 6,800 |
| Database Management (DBM) | 3,350 |
| Computer Graphics Display Facilities (CGDF) | 4,950 |
| Peripheral Control Function (PCF) | 2,100 |
| Design Analysis Modules (DAM) | 8,400 |
| **Total Estimated LOC** | **33,200** |

**Given:** Organizational average productivity = 620 LOC/pm, burdened labor rate = $8,000/month

**Calculations:**
```
Effort = Total LOC / Productivity = 33,200 / 620 = 54 person-months
Cost per LOC = $8,000 / 620 = $12.90 ≈ $13/LOC
Total Cost = 33,200 × $13 = $431,600
```

### LOC Example 2: Login & Booking System

| Module | LOC |
|--------|-----|
| Login and Registration | 1,000 |
| Search and Booking | 3,000 |
| Payment and Checkout | 2,000 |
| User Profile | 1,500 |
| Feedback and Rating | 500 |
| **Total** | **8,000** |

Given: 600 LOC/pm, $8,000/month

```
Cost per LOC = $8,000 / 600 = $13.33
Effort = 8,000 / 600 = 13.3 person-months
Total Cost = 8,000 × $13.33 = $106,400
```

### LOC Example 3: 50,000 LOC Project

Given: 50,000 LOC, 5 developers, $50/hour, 12 months, 160 hours/month, 600 LOC/developer/month

```
1. Total effort = 50,000 / 600 = 83.3 person-months
2. Cost per developer per month = 160 × $50 = $8,000
3. Total cost = 83.3 × $8,000 = $666,400
```

---

## Function Point Analysis

### Overview

Function Points measure software size based on **functionality delivered to the user**, independent of programming language. Steps:

1. Count information domain values
2. Compute Unadjusted Function Points (UFP)
3. Compute Total Degree of Influence (TDI) from 14 factors
4. Compute Value Adjustment Factor (VAF / CAF)
5. Compute FP = UFP × CAF

### Five Information Domain Types

| Domain | Code | Description | Simple | Average | Complex |
|--------|------|-------------|--------|---------|---------|
| External Inputs | EI | Data entering the system (forms, controls) | 3 | 4 | 6 |
| External Outputs | EO | Data exiting the system (reports, displays) | 4 | 5 | 7 |
| External Inquiries | EQ | Queries that retrieve data without changing it | 3 | 4 | 6 |
| Internal Logical Files | ILF | Logical data groups maintained within the system | 7 | 10 | 15 |
| External Interface Files | EIF | Logical data groups from other applications | 5 | 7 | 10 |

### 14 Value Adjustment Factors (Fi)

Each rated 0 (no influence) to 5 (essential):

| # | Factor | Description |
|---|--------|-------------|
| F1 | Data Communications | Communication facilities used to transfer data |
| F2 | Distributed Data Processing | How processing components are distributed |
| F3 | Performance | Response time or throughput requirements |
| F4 | Heavily Used Configuration | How heavily the hardware platform is used |
| F5 | Transaction Rate | Frequency of transaction execution |
| F6 | On-Line Data Entry | Percentage of information entered online |
| F7 | End-User Efficiency | Design for user efficiency |
| F8 | On-Line Update | How many ILFs are updated online |
| F9 | Complex Processing | Complex logic, algorithms, or processing |
| F10 | Reusability | Designed for reuse |
| F11 | Installation Ease | Conversion and installation considerations |
| F12 | Operational Ease | Start-up, backup, recovery difficulty |
| F13 | Multiple Sites | Designed for use at multiple sites |
| F14 | Facilitate Change | Designed to facilitate changes |

### CAF (Complexity Adjustment Factor) Formula

```
CAF = 0.65 + (0.01 × ΣFi)
```

- Minimum ΣFi = 0 → CAF = 0.65
- Maximum ΣFi = 70 → CAF = 1.35
- Range: **0.65 to 1.35**

### Worked Example 1: Full FP Calculation

**Step 1: Compute UFP**

| Domain | Count | Weight | Total |
|--------|-------|--------|-------|
| EI | 20 | 4 (avg) | 80 |
| EO | 30 | 5 (avg) | 150 |
| EQ | 10 | 4 (avg) | 40 |
| ILF | 5 | 10 (avg) | 50 |
| EIF | 4 | 7 (avg) | 28 |
| **UFP** | **69** | | **348** |

**Step 2: Compute CAF with ΣFi = 70 (maximum)**

```
CAF = 0.65 + (0.01 × 70) = 1.35
FP = 348 × 1.35 = 469.8 FP
```

**Step 3: Compute CAF with ΣFi = 48**

```
CAF = 0.65 + (0.01 × 48) = 1.13
FP = 348 × 1.13 = 393.24 FP
```

**Conversion to Effort and Cost:**

Given: 10 hours per FP, 8 hours/day, $100/hour

```
Effort = 393 × 10 = 3,930 hours
Duration = 3,930 / 8 = 491.25 days ≈ 98.25 weeks ≈ 24.6 months
Cost = 3,930 × $100 = $393,000
```

### Worked Example 2: LOC-to-FP Conversion

Given: 80,000 LOC, average 100 LOC/FP, ΣFi = 48

```
FPs = 80,000 / 100 = 800 FP
```

| Domain | Count | Weight | Total |
|--------|-------|--------|-------|
| EI | 40 | 4 | 160 |
| EO | 50 | 5 | 250 |
| EQ | 30 | 4 | 120 |
| ILF | 20 | 10 | 200 |
| EIF | 12 | 7 | 84 |
| **UFP** | **152** | | **814** |

```
CAF = 0.65 + (0.01 × 48) = 1.13
FP = 814 × 1.13 = 919.82 FP
```

### Worked Example 3: The "Move" Logistics System

| Domain | Count | Average Weight | Total |
|--------|-------|---------------|-------|
| EI | 25 | 4 | 100 |
| EO | 50 | 5 | 250 |
| EQ | 40 | 4 | 160 |
| ILF | 12 | 10 | 120 |
| EIF | 3 | 7 | 21 |
| **UFP** | **130** | | **651** |

ΣFi = 36

```
CAF = 0.65 + (0.01 × 36) = 1.01
FP = 651 × 1.01 = 657.51 FP
```

**Effort & Cost:**

Given: 10 FP/person-month, 10-month duration, $5,000/month/developer

```
Effort = 657.51 / 10 = 65.75 person-months
Team Size = 65.75 / 10 = 6.575 ≈ 7 developers
Total Cost = 65.75 × $5,000 = $328,750
```

### Worked Example 4: Real-Time Control System

| Domain | Count | Weight | Total |
|--------|-------|--------|-------|
| EI | 15 | 4 | 60 |
| EO | 25 | 5 | 125 |
| EQ | 10 | 4 | 40 |
| ILF | 8 | 10 | 80 |
| EIF | 5 | 7 | 35 |
| **UFP** | **63** | | **340** |

ΣFi = 42

```
CAF = 0.65 + (0.01 × 42) = 1.07
FP = 340 × 1.07 = 363.8 FP
```

Given: 8 FP/person-month (typical for real-time)

```
Effort = 363.8 / 8 = 45.47 person-months
Duration = 8 months
Team Size = 45.47 / 8 = 5.68 ≈ 6 developers
Total Cost = 45.47 × $6,000 = $272,820
```

### Worked Example 5: E-Commerce with Mixed Complexity

| Domain | Simple | Average | Complex |
|--------|--------|---------|---------|
| EI | 10 × 3 = 30 | 5 × 4 = 20 | 2 × 6 = 12 |
| EO | 8 × 4 = 32 | 12 × 5 = 60 | 5 × 7 = 35 |
| EQ | 15 × 3 = 45 | 10 × 4 = 40 | 3 × 6 = 18 |
| ILF | - | 6 × 10 = 60 | 4 × 15 = 60 |
| EIF | 3 × 5 = 15 | 2 × 7 = 14 | 1 × 10 = 10 |
| **UFP** | | | **391** |

ΣFi = 45

```
CAF = 0.65 + (0.01 × 45) = 1.10
FP = 391 × 1.10 = 430.1 FP
```

Given: 12 FP/person-month, 6-month duration, $5,500/month

```
Effort = 430.1 / 12 = 35.84 person-months
Team Size = 35.84 / 6 = 5.97 ≈ 6 developers
Total Cost = 35.84 × $5,500 = $197,120
```

### Worked Example 6: Mixed Complexity with SFi Table

| Domain | Count | Complexity | Weight | Total |
|--------|-------|-----------|--------|-------|
| EI | 4 | Simple | 3 | 12 |
| EI | 4 | Average | 4 | 16 |
| EI | 2 | Complex | 6 | 12 |
| EO | 3 | Simple | 4 | 12 |
| EO | 5 | Average | 5 | 25 |
| EO | 1 | Complex | 7 | 7 |
| EQ | 4 | Simple | 3 | 12 |
| EQ | 5 | Average | 4 | 20 |
| EQ | 3 | Complex | 6 | 18 |
| ILF | 2 | Average | 10 | 20 |
| ILF | 2 | Complex | 15 | 30 |
| EIF | 2 | Simple | 5 | 10 |
| EIF | 3 | Average | 7 | 21 |
| **UFP** | | | | **212** |

ΣFi = 33

```
CAF = 0.65 + (0.01 × 33) = 0.98
FP = 212 × 0.98 = 207.76 FP
```

**Cost Estimation from FP:**

```
Cost = (FP × (LOC/FP) / (LOC/PM)) × Cost/PM
For middle-level software:
= (208 × ((250/200 + 200/200 + 300/200 + 167/200) / 4) / 2300) × 11000
= (208 × 1.235 / 2300) × 11000
= (256.88 / 2300) × 11000
= $1,228.70
```

### LOC vs FP Comparison

| Feature | LOC | FP |
|---------|-----|----|
| Language dependency | Depends on language | Independent of language |
| Scope | Sizing software modules | Sizing whole applications |
| Ease of computation | Easier to compute | More difficult to compute |
| Frequency of use | More often used | Less often used |
| Estimation accuracy | Good for estimation | Better for estimation |

---

## COCOMO Models

### Basic COCOMO (Constructive Cost Model)

Three project modes:

| Mode | Description | a | b | c | d |
|------|-------------|---|---|---|---|
| **Organic** | Small team, familiar with project, similar past work | 2.4 | 1.05 | 2.5 | 0.38 |
| **Semi-Detached** | Mix of organic and embedded characteristics | 3.0 | 1.12 | 2.5 | 0.35 |
| **Embedded** | Highly complex, unfamiliar team, tight constraints | 3.6 | 1.20 | 2.5 | 0.32 |

### Basic COCOMO Formulas

```
Effort (E) = a × (KLOC)^b     [person-months]
Dev Time (D) = c × (E)^d       [months]
Avg Staff (S) = E / D           [persons]
Total Cost (C) = E × Cost_per_PM
```

### Worked Example: Semi-Detached (32 KLOC)

```
KLOC = 32, a = 3.0, b = 1.12, c = 2.5, d = 0.35

Effort = 3.0 × (32)^1.12
       = 3.0 × 46.68
       = 140.05 person-months

Dev Time = 2.5 × (140.05)^0.35
         = 2.5 × 5.88
         = 14.7 months

Avg Staff = 140.05 / 14.7 = 9.52 persons

Cost (at $8,000/PM) = 140.05 × $8,000 = $1,120,400
```

### Experience Level Cost Table

| Experience Level | Cost per Person-Month |
|-----------------|----------------------|
| Low | $6,000 |
| Average | $8,000 |
| High | $10,000 |

Average cost = ($6,000 + $8,000 + $10,000) / 3 = **$8,000**

---

## COCOMO II (Detailed Model)

### General Formula

```
Effort = A × (Size)^B × M
```

Where:
- **A** = 2.94 (calibrated constant)
- **Size** = KLOC or FP
- **B** = 0.91 + 0.01 × (sum of 5 scale factors)
- **M** = Product of all cost driver multipliers (EAF)

### Three COCOMO II Sub-Models

| Model | Phase | Sizing Method |
|-------|-------|---------------|
| **Application Composition** | Early stages, prototyping | Object Points |
| **Early Design** | Requirements understood, basic architecture | Function Points |
| **Post-Architecture** | Established architecture, detailed design | KLOC or FP |

### Application Composition Model

```
Effort = (Object Points × Productivity) / 3000
```

Object points = screens + reports + 3GL modules (weighted by complexity: simple/medium/difficult)

### Early Design Model

```
PM = 2.94 × (FP)^B × M
TDEV = 3.67 × (PM)^F
```

Where:
- **B** = 0.91 + 0.01 × (sum of 5 scale factors)
- **F** = 0.28 + 0.2 × (B - 0.91)
- **M** = Product of 7 cost driver multipliers

### Post-Architecture Model

```
PM = 2.94 × (Size)^B × M
```

Where **Size** is in KLOC or FP, and **M** is the product of **17 cost drivers**.

### Five Scale Factors (for B exponent)

| Scale Factor | Very Low | Low | Nominal | High | Very High | Extra High |
|-------------|----------|-----|---------|------|-----------|------------|
| Precedentedness (PREC) | 1.24 | 1.10 | 1.00 | 0.89 | 0.81 | - |
| Development Flexibility (DFLEX) | 1.24 | 1.10 | 1.00 | 0.91 | 0.82 | - |
| Architecture/Risk Resolution (RESL) | 1.24 | 1.10 | 1.00 | 0.91 | 0.83 | - |
| Team Cohesion (TEAM) | 1.24 | 1.10 | 1.00 | 0.91 | 0.82 | - |
| Process Maturity (PMAT) | 1.24 | 1.10 | 1.00 | 0.91 | 0.82 | - |

```
B = 0.91 + 0.01 × (sum of 5 scale factor ratings)
```

---

## Cost Drivers (Effort Adjustment Factor - EAF Table)

### COCOMO II Post-Architecture Cost Drivers (17 Factors)

#### Product Factors

| Driver | Code | VL | L | N | H | VH | EH |
|--------|------|----|----|----|----|----|----|
| Required Software Reliability | RELY | 0.82 | 0.92 | 1.00 | 1.10 | 1.26 | - |
| Database Size | DATA | - | 0.90 | 1.00 | 1.14 | 1.28 | - |
| Product Complexity | CPLX | 0.73 | 0.87 | 1.00 | 1.17 | 1.34 | 1.74 |
| Developed for Reusability | RUSE | - | 0.91 | 1.00 | 1.10 | 1.22 | 1.31 |
| Documentation Match | DOCU | - | 0.91 | 1.00 | 1.11 | 1.23 | - |

#### Platform Factors

| Driver | Code | VL | L | N | H | VH | EH |
|--------|------|----|----|----|----|----|----|
| Time Constraint | TIME | - | - | 1.00 | 1.11 | 1.29 | 1.63 |
| Storage Constraint | STOR | - | - | 1.00 | 1.05 | 1.12 | 1.21 |
| Platform Volatility | PVOL | - | 0.87 | 1.00 | 1.15 | 1.30 | - |

#### Personnel Factors

| Driver | Code | VL | L | N | H | VH | EH |
|--------|------|----|----|----|----|----|----|
| Analyst Capability | ACAP | 1.50 | 1.22 | 1.00 | 0.83 | 0.69 | - |
| Programmer Capability | PCAP | 1.29 | 1.13 | 1.00 | 0.91 | 0.84 | - |
| Applications Experience | AEXP | 1.40 | 1.18 | 1.00 | 0.89 | 0.81 | - |
| Platform Experience | PEXP | 1.34 | 1.15 | 1.00 | 0.91 | 0.85 | - |
| Language & Toolset Experience | LTEX | 1.29 | 1.12 | 1.00 | 0.91 | 0.84 | - |

#### Project Factors

| Driver | Code | VL | L | N | H | VH | EH |
|--------|------|----|----|----|----|----|----|
| Use of Software Tools | TOOL | 1.29 | 1.12 | 1.00 | 0.90 | 0.83 | - |
| Multi-Site Development | SITE | 1.22 | 1.09 | 1.00 | 0.93 | 0.86 | 0.80 |
| Schedule Constraint | SCED | 1.23 | 1.08 | 1.00 | 1.04 | 1.10 | - |

### How EAF Works

```
M = RELY × DATA × CPLX × RUSE × DOCU × TIME × STOR × PVOL × ACAP × PCAP × AEXP × PEXP × LTEX × TOOL × SITE × SCED
```

- Values > 1.00 increase effort (harder conditions)
- Values < 1.00 decrease effort (favorable conditions)
- Baseline nominal = 1.00 for all drivers

---

## Estimation Techniques

### 1. Delphi Technique

A structured communication technique that gathers input from multiple experts.

**Process:**
1. Facilitator/coordinator selected
2. Create list of experts
3. Create 3-5 questions (e.g., "Azure or AWS for this project?")
4. Collect all results
5. Analyze and iterate until consensus

### 2. Wideband Delphi

A repeatable, team-based estimation process with more interaction than traditional Delphi.

**Six-Step Process:**

| Step | Activity | Details |
|------|----------|---------|
| 1 | Choose the Team | PM selects 3-7 team members + moderator. Moderator should be neutral (not the PM). |
| 2 | Kickoff Meeting | Ensure everyone understands the process, reviews scope docs, brainstorms assumptions, generates WBS, agrees on units of estimation. |
| 3 | Individual Preparation | Each member independently estimates each task and documents assumptions. |
| 4 | Estimation Session | Multi-round process: fill forms → moderator plots results → discuss disagreements (not individual numbers) → revise → converge |
| 5 | Assemble Tasks | PM collects final estimates and compiles task list, estimates, and assumptions. |
| 6 | Review Results | PM reviews final task list with estimation team. |

**Convergence Goal:** Estimates cluster together across rounds (tighter spread = consensus).

### 3. Estimation by Analogy

Compare the proposed project with completed similar projects. Use historical data from analogous projects to derive estimates.

### 4. Other Strategies

| Strategy | Description |
|----------|-------------|
| Algorithmic Cost Modeling | Mathematical models (COCOMO, SLIM) |
| Expert Judgment | Relies on individual or group expertise |
| Parkinson's Law | Work expands to fill available time |
| Price-to-Win | Estimate set to win the contract |
| Top-Down | Overall estimate decomposed to components |
| Bottom-Up | Individual components estimated and summed |

---

## Algorithmic Cost Modeling General Form

```
Effort = A × (Size)^B × M
```

- **A** = constant from historical data
- **B** = accounts for non-linear size-effort relationship
- **Size** = LOC or FP
- **M** = multiplier (cost driver collection)

### Productivity Data by Application Type

| Application Type | LOC/PM | Cost per PM |
|-----------------|--------|-------------|
| Low-level software | 3,200 | $9,000 |
| Middle-level software | 2,300 | $11,000 |
| High-level software | 1,200 | $14,000 |

---

## Relationships Between Concepts

```
Requirements
     |
     v
WBS (Work Breakdown Structure)
     |
     v
Estimate Scope (LOC or FP)
     |
     +--- Using 3-Point Formula for LOC
     |         OR
     +--- Using UFP × CAF for Function Points
     |
     v
Apply Productivity Data (LOC/pm or FP/pm)
     |
     v
Compute Effort (person-months)
     |
     +--- Basic COCOMO: E = a × (KLOC)^b
     |    COCOMO II:   E = A × (Size)^B × M
     |
     v
Compute Development Time: D = c × E^d
     |
     v
Compute Staff: S = E / D
     |
     v
Compute Cost: C = E × Cost_per_PM
     |
     v
Validation: Wideband Delphi / Expert Review
```

---

## Common Mistakes / Exam Traps

1. **Forgetting the 4 multiplier in the 3-point formula**: The most likely value is weighted 4x, not equally with optimistic and pessimistic.
2. **Confusing UFP and FP**: UFP is the unadjusted count; FP = UFP × CAF. Many problems give UFP but ask for FP.
3. **CAF range confusion**: CAF ranges from 0.65 (minimum) to 1.35 (maximum). It is NOT 0 to 1.
4. **Skipping the 0.65 base in CAF**: CAF = 0.65 + (0.01 × ΣFi). Do not forget the 0.65 constant.
5. **Inverse cost driver logic**: Personnel factors like ACAP: higher capability = LOWER multiplier (< 1.00). Counterintuitive.
6. **LOC vs FP units**: LOC counts every source line (not blank/comment). FP counts functional units.
7. **KLOC vs LOC in COCOMO**: COCOMO formulas use KLOC, not raw LOC. 50,000 LOC = 50 KLOC.
8. **Project mode selection**: Organic (small, familiar) vs Semi-detached (mixed) vs Embedded (large, unfamiliar).
9. **Wideband Delphi moderator role**: The moderator must be neutral, not the project manager.
10. **FP language independence**: FP is language-independent; LOC is language-dependent.
11. **Forgetting to divide FP by productivity**: Effort = FP / (FP/pm), not FP × productivity.
12. **Confusing EI/EO/EQ**: EI = data IN, EO = data OUT, EQ = query/retrieval (does not change system state).

---

## Active Recall Questions

1. What is the 3-point estimation formula for LOC? Write it out.
2. What are the five information domain values used in Function Point Analysis?
3. What is the CAF formula and what is its valid range?
4. What are the three COCOMO project modes and their a/b constants?
5. List the 14 value adjustment factors (Fi) used in FP analysis.
6. What is the difference between Delphi and Wideband Delphi?
7. How do you convert between LOC and FP using historical data?
8. What does EAF stand for and how is it calculated in COCOMO II?
9. What are the five scale factors in COCOMO II?
10. How many cost drivers are in the Post-Architecture model? Name the categories.
11. What is the nominal value for each cost driver multiplier?
12. How do you calculate development time from effort in Basic COCOMO?
13. What is the difference between UFP and FP?
14. Why are assumptions important in estimation?
15. What does a cost driver value < 1.00 mean?

---

## Potential Exam Questions

1. **Calculate the expected LOC** for a component with optimistic = 3,200, most likely = 5,000, and pessimistic = 7,400. Show your work.

2. **A project has 15 EIs, 25 EOs, 10 EQs, 5 ILFs, and 3 EIFs** with average complexity. ΣFi = 40. Calculate UFP, CAF, and FP. If productivity is 15 FP/pm and cost is $7,000/PM, find effort and cost.

3. **A semi-detached project has 45 KLOC.** Calculate effort, development time, and average staff using Basic COCOMO. If average cost is $8,000/PM, find total cost.

4. **Explain the Wideband Delphi process** in six steps. Why is it better than individual expert judgment?

5. **Compare LOC and FP** as estimation metrics. When would you use each?

6. **Given the following COCOMO II cost drivers**: RELY = H (1.10), CPLX = VH (1.34), ACAP = H (0.83), TOOL = L (1.12). Calculate EAF if all other drivers are nominal (1.00).

7. **A real-time system** has ΣFi = 55, UFP = 280, productivity = 8 FP/pm, cost = $6,000/PM. Find FP, effort, duration (8 months), team size, and cost.

8. **Explain how the 5 scale factors affect the B exponent** in COCOMO II. What does a higher B value indicate?

9. **Create an effort estimation sheet** (best, worst, average) for Round 1 of a Wideband Delphi session with 3 estimators and 4 tasks.

10. **A project has 208 FP with the following LOC/FP ratios**: 250, 200, 300, 167. Average productivity is 2,300 LOC/PM and cost is $11,000/PM. Calculate the estimated cost.

---

## Topic Summary

- **Estimation** predicts effort, time, and cost for software projects
- **LOC Estimation** uses the 3-point weighted average formula: S = (Sopt + 4Sm + Spess) / 6
- **Function Point Analysis** measures size via 5 information domains (EI, EO, EQ, ILF, EIF) adjusted by 14 complexity factors: FP = UFP × [0.65 + (0.01 × ΣFi)]
- **COCOMO Basic** uses 3 modes (Organic / Semi-Detached / Embedded) with formulas E = a(KLOC)^b and D = cE^d
- **COCOMO II** has 3 sub-models (Application Composition, Early Design, Post-Architecture) with 17 cost drivers and 5 scale factors
- **EAF** is the product of all cost driver multipliers (nominal = 1.00); values < 1 decrease effort, values > 1 increase effort
- **Estimation Techniques** include Delphi, Wideband Delphi (6-step team process), Analogy, Expert Judgment, Top-Down, and Bottom-Up
- **Key relationships**: Size → Effort → Time → Staff → Cost
- **Assumptions must be documented** to allow backtracking and correction
