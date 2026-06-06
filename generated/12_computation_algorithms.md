# Software Engineering — Computation Algorithms for Exam Preparation

---

## 1. LOC Estimation — Three-Point Formula

### Problem Type
Estimating the expected size (LOC) of a software component using historical data with uncertainty.

### Recognition Pattern
- You are given **three values** for a task: optimistic (Sopt), most likely (Sm), and pessimistic (Spess)
- Asked to find the **expected size** or **weighted average**

### Step-by-Step Algorithm
```
Step 1: Identify the three estimates
   Sopt = Optimistic estimate (best case, smallest)
   Sm   = Most likely estimate (realistic)
   Spess = Pessimistic estimate (worst case, largest)

Step 2: Apply the PERT weighted average formula
   S = (Sopt + 4×Sm + Spess) / 6

Step 3: Report the result in LOC
```

### Shortcut Heuristics
- The most likely value is weighted **4× more** than the other two
- Result is always between Sopt and Spess, closer to Sm
- Quick sanity check: answer should be roughly (Sopt + Sm + Spess) / 3 but pulled toward Sm

### Common Mistakes
- Using (Sopt + Sm + Spess) / 3 instead of the weighted formula
- Forgetting to multiply Sm by 4 before adding
- Confusing optimistic (small) with pessimistic (large)

### Example Walkthrough
```
Given: Sopt = 4600, Sm = 6900, Spess = 8600

S = (4600 + 4×6900 + 8600) / 6
S = (4600 + 27600 + 8600) / 6
S = 40800 / 6
S = 6800 LOC
```

---

## 2. Function Point Calculation — 5-Step Process

### Problem Type
Calculating Function Points (FP) for a software system based on information domain characteristics.

### Recognition Pattern
- You are given counts of: External Inputs (EI), External Outputs (EO), External Inquiries (EQ), Internal Logical Files (ILF), External Interface Files (EIF)
- You may also be given ratings for 14 General System Characteristics (GSCs)

### Step-by-Step Algorithm
```
Step 1: Calculate UFC (Unadjusted Function Count)
   UFC = Σ(Count of each element × its weight)

   Weighting Table:
   +---------------------+----------+-----------+-----------+
   | Component           | Simple   | Average   | Complex   |
   +---------------------+----------+-----------+-----------+
   | External Inputs     |    3     |     4     |     6     |
   | External Outputs    |    4     |     5     |     7     |
   | External Inquiries  |    3     |     4     |     6     |
   | Internal Logical    |    7     |    10     |    15     |
   |   Files             |          |           |           |
   | External Interface  |    5     |     7     |    10     |
   |   Files             |          |           |           |
   +---------------------+----------+-----------+-----------+

Step 2: Rate 14 General System Characteristics (0-5 each)
   Each Fi rated: 0=no influence ... 5=essential influence
   Calculate ΣFi = sum of all 14 ratings

Step 3: Calculate VAF (Value Adjustment Factor)
   VAF = 0.65 + (0.01 × ΣFi)
   Range: 0.65 (min) to 1.35 (max)

Step 4: Calculate FP
   FP = UFC × VAF

Step 5: (Optional) Convert to LOC
   LOC = FP × Language-specific factor
```

### Shortcut Heuristics
- If complexity not specified, assume **Average** weights
- VAF range is always 0.65 to 1.35 (memorize these bounds)
- Quick check: UFC = 0 means no functionality; higher UFC = more functionality
- ΣFi = 0 → VAF = 0.65 (no adjustment); ΣFi = 70 → VAF = 1.35 (max adjustment)

### Common Mistakes
- Using wrong weights (e.g., swapping Simple/Average/Complex)
- Forgetting the 0.65 base in VAF formula
- Not multiplying ΣFi by 0.01
- Confusing UFC with FP (FP = UFC × VAF, not UFC alone)

### Example Walkthrough
```
Given: EI=5(Avg), EO=8(Avg), EQ=4(Simple), ILF=3(Complex), EIF=2(Avg)
       ΣFi = 42

Step 1: UFC = (5×4) + (8×5) + (4×3) + (3×15) + (2×7)
       UFC = 20 + 40 + 12 + 45 + 14 = 131

Step 2: ΣFi = 42

Step 3: VAF = 0.65 + (0.01 × 42) = 0.65 + 0.42 = 1.07

Step 4: FP = 131 × 1.07 = 140.17 ≈ 140 FP
```

---

## 3. FP-LOC Conversion

### Problem Type
Converting Function Points to Lines of Code using language-specific factors.

### Recognition Pattern
- Given FP value and programming language
- Asked to estimate LOC

### Step-by-Step Algorithm
```
Step 1: Identify the language conversion factor

   +----------------+-------------------+
   | Language       | LOC per FP        |
   +----------------+-------------------+
   | Assembly       |      320          |
   | C              |      105          |
   | C++            |       54          |
   | Java           |       46          |
   | Python         |       35          |
   | Visual Basic   |       29          |
   | SQL            |       12          |
   +----------------+-------------------+

Step 2: Apply the formula
   LOC = FP × Language Factor

Step 3: Report the result
```

### Shortcut Heuristics
- Higher-level language = fewer LOC per FP (more expressive)
- Assembly is ~7× more verbose than Python
- Quick mental model: Java ≈ 50 LOC/FP, Python ≈ 35 LOC/FP
- If language not in table, interpolate based on abstraction level

### Common Mistakes
- Using wrong language factor (check the table!)
- Multiplying FP × LOC instead of FP × Factor
- Not rounding to whole LOC (LOC must be integer)

### Example Walkthrough
```
Given: FP = 140, Language = Java (46 LOC/FP)

LOC = 140 × 46 = 6,440 lines of code
```

---

## 4. LOC-Effort Conversion

### Problem Type
Estimating effort (person-months) from lines of code using historical productivity data.

### Recognition Pattern
- Given total LOC and productivity rate (LOC per person-month)
- Asked to find effort in person-months

### Step-by-Step Algorithm
```
Step 1: Get total LOC (sum of all components if multiple)
   Total LOC = Σ(LOC of each module/function)

Step 2: Get productivity rate from historical data
   Productivity Rate = LOC per person-month (LOC/pm)

Step 3: Apply the formula
   Effort (person-months) = Total LOC / Productivity Rate

Step 4: Report the result
```

### Shortcut Heuristics
- Higher productivity rate = less effort needed
- If productivity = 600 LOC/pm, then 6000 LOC ≈ 10 person-months
- Quick estimate: divide LOC by hundreds (e.g., 6000/600 = 10)

### Common Mistakes
- Confusing productivity rate (LOC/pm) with cost rate ($/pm)
- Not summing LOC from all components before dividing
- Reporting effort in person-hours instead of person-months

### Example Walkthrough
```
Given: Total LOC = 33,200, Productivity Rate = 620 LOC/pm

Effort = 33,200 / 620 = 53.55 ≈ 54 person-months
```

---

## 5. Effort-Cost Conversion

### Problem Type
Calculating total project cost from effort and per-person-month cost.

### Recognition Pattern
- Given effort in person-months and cost per person-month
- Asked to find total project cost

### Step-by-Step Algorithm
```
Step 1: Get effort in person-months
   (from previous calculation or given directly)

Step 2: Get cost per person-month
   Cost/pm = Monthly salary + overheads

Step 3: Apply the formula
   Total Cost = Effort (person-months) × Cost per person-month

Step 4: Report the result in currency units
```

### Shortcut Heuristics
- Cost/pm typically includes salary + overhead (30-50% overhead is common)
- Quick check: if effort = 12 pm and cost/pm = $8000, cost ≈ $96,000
- Can also compute: Cost/LOC = Cost/pm ÷ Productivity rate

### Common Mistakes
- Forgetting to include overheads in cost/pm
- Using effort in hours instead of person-months
- Confusing cost/pm with total cost

### Example Walkthrough
```
Given: Effort = 12.88 person-months, Cost/pm = $8,000

Total Cost = 12.88 × $8,000 = $103,040
```

---

## 6. Risk Exposure (RE)

### Problem Type
Calculating the risk exposure (expected loss) for a identified risk.

### Recognition Pattern
- Given probability (P) of risk occurrence and cost/consequence (C) if it occurs
- Asked to find risk exposure or expected loss

### Step-by-Step Algorithm
```
Step 1: Determine probability (P)
   P is expressed as a decimal (0 to 1)
   Or convert percentage: 25% = 0.25

Step 2: Determine cost/consequence (C)
   C is the monetary impact if the risk occurs
   Must be in consistent units (e.g., dollars)

Step 3: Apply the formula
   RE = P × C

Step 4: Rank risks by RE for prioritization
```

### Shortcut Heuristics
- P ranges: Very Low (<10%), Low (10-25%), Moderate (25-50%), High (50-75%), Very High (>75%)
- RE is in the same units as C (e.g., dollars)
- Higher RE = higher priority for mitigation
- Quick mental math: P=0.5, C=$100K → RE=$50K

### Common Mistakes
- Using percentage instead of decimal for P (e.g., 25 instead of 0.25)
- Confusing probability with impact
- Not converting all costs to same units
- Ignoring RE when ranking risks (should rank by RE descending)

### Example Walkthrough
```
Given: P = 0.40 (40% probability), C = $200,000

RE = 0.40 × $200,000 = $80,000

This risk has an expected loss of $80,000.
```

---

## 7. Critical Path Analysis — Forward and Backward Pass

### Problem Type
Finding the critical path, ES, EF, LS, LF, and float for each activity in a project network.

### Recognition Pattern
- Given activities with predecessors and durations
- Asked to find: Early Start (ES), Early Finish (EF), Late Start (LS), Late Finish (LF), Critical Path, Float

### Step-by-Step Algorithm
```
=== FORWARD PASS (ES and EF) ===
Step 1: Start with first activity (no predecessors)
   ES = 0
   EF = ES + Duration

Step 2: For each subsequent activity:
   ES = MAX(EF of all predecessors)
   EF = ES + Duration

Step 3: Continue until last activity
   Project Duration = EF of last activity

=== BACKWARD PASS (LS and LF) ===
Step 4: Start with last activity
   LF = Project Duration
   LS = LF - Duration

Step 5: For each preceding activity:
   LF = MIN(LS of all successors)
   LS = LF - Duration

Step 6: Continue until first activity
   LS of first activity should be 0

=== CALCULATE FLOAT ===
Step 7: Total Float for each activity
   TF = LF - EF  OR  TF = LS - ES

Step 8: Identify Critical Path
   Critical Path = activities where TF = 0
```

### Shortcut Heuristics
- Forward pass: always take MAX when merging paths
- Backward pass: always take MIN when splitting paths
- Critical path is the LONGEST path through the network
- All activities on critical path have TF = 0
- Quick check: first activity ES=0, last activity LF = project duration

### Common Mistakes
- Using MIN instead of MAX in forward pass (should be MAX)
- Using MAX instead of MIN in backward pass (should be MIN)
- Forgetting that EF = ES + Duration (not ES + Duration - 1)
- Not verifying that first activity LS = 0 and last activity EF = LF

### Example Walkthrough
```
Activities: A(3), B(4), C(2), D(5), E(1), F(2), G(4), H(3)
Dependencies: A→B, A→C, B→D, C→E, C→F, D→G, E→G, F→H, G→H

Forward Pass:
  A: ES=0, EF=3
  B: ES=3, EF=7
  C: ES=3, EF=5
  D: ES=7, EF=12
  E: ES=5, EF=6
  F: ES=5, EF=7
  G: ES=12, EF=16 (MAX of D=12, E=6)
  H: ES=16, EF=19 (MAX of F=7, G=16)

Backward Pass:
  H: LF=19, LS=16
  G: LF=16, LS=12
  F: LF=16, LS=14
  D: LF=12, LS=7
  E: LF=12, LS=11
  B: LF=7, LS=3
  C: LF=11, LS=9
  A: LF=3, LS=0

Float: A=0, B=0, C=6, D=0, E=6, F=9, G=0, H=0
Critical Path: A → B → D → G → H (19 days)
```

---

## 8. Free Float

### Problem Type
Calculating the free float of an activity (flexibility without affecting successors).

### Recognition Pattern
- Given ES values of activity and its successors
- Asked to find Free Float (FF)

### Step-by-Step Algorithm
```
Step 1: Identify ES of the activity
   ES_activity

Step 2: Identify ES of ALL successor activities
   ES_successor1, ES_successor2, ...

Step 3: Find MINIMUM ES among all successors
   MIN(ES_successors)

Step 4: Get Duration of the activity
   Duration_activity

Step 5: Apply the formula
   FF = MIN(ES_successor) - ES_activity - Duration_activity
```

### Shortcut Heuristics
- FF ≤ TF always (free float is never greater than total float)
- FF = 0 for critical path activities
- If activity has only one successor, FF = ES_successor - EF_activity
- Quick check: FF is the "extra" time before next activity must start

### Common Mistakes
- Using LF instead of ES_successor
- Forgetting to subtract Duration_activity
- Using MAX instead of MIN for multiple successors
- Confusing FF with TF

### Example Walkthrough
```
Given: Activity C: ES=3, Duration=2
       Successor E: ES=5
       Successor F: ES=5

FF = MIN(5, 5) - 3 - 2 = 5 - 3 - 2 = 0

Activity C has zero free float (any delay affects successors immediately).
```

---

## 9. Wideband Delphi — Convergence Process

### Problem Type
Using team consensus estimation to converge on effort estimates through multiple rounds.

### Recognition Pattern
- Multiple estimators providing estimates for tasks
- Asked to show convergence across rounds
- Asked to calculate best/worst/average cases

### Step-by-Step Algorithm
```
Step 1: CHOOSE TEAM
   Select 3-7 team members and a moderator

Step 2: KICKOFF MEETING
   - Understand project scope and WBS
   - Brainstorm assumptions
   - Agree on unit of estimation

Step 3: INDIVIDUAL PREPARATION
   - Each member independently estimates each task
   - Document assumptions

Step 4: ESTIMATION SESSION (multiple rounds)
   Round 1:
   - Each member submits estimates
   - Moderator plots estimates on a line
   - Team discusses disagreements (not individual numbers)
   - Members revise estimates

   Repeat until convergence (estimates cluster together)

Step 5: ASSEMBLE TASKS
   - Collect final estimates
   - Compile task list, estimates, assumptions

Step 6: REVIEW RESULTS
   - Review with estimation team
```

### Convergence Calculation
```
For each round:
   Sum of estimates = Σ(all estimators' total estimates)

Convergence metric:
   Range = Max estimate - Min estimate
   As rounds progress, Range should decrease

Final estimate:
   Best case = Minimum estimate across all members for each task
   Worst case = Maximum estimate across all members for each task
   Average = (Sum of all members' estimates) / Number of members
```

### Shortcut Heuristics
- Typically converges in 3-4 rounds
- If estimates don't converge, add more assumptions
- Individual estimate times are NOT discussed (only the task issues)
- Final estimate is often the average of last round
- Best case = min; Worst case = max; Average = mean

### Common Mistakes
- Discussing individual estimates instead of task issues
- Stopping before convergence
- Not documenting assumptions
- Forcing consensus instead of allowing natural convergence

### Example Walkthrough
```
3 estimators (Salas, Aliya, Ahmed), 5 tasks, 3 rounds:

Round 1 cumulative totals:
   Salas: 20, Aliya: 16, Ahmed: 29
   Range: 29 - 16 = 13

Round 2 cumulative totals:
   Salas: 17, Aliya: 18, Ahmed: 23
   Range: 23 - 17 = 6

Round 3 cumulative totals:
   Salas: 18, Aliya: 19, Ahmed: 20
   Range: 20 - 18 = 2 (converged!)

Best case per task (Round 1): min of each row
Worst case per task (Round 1): max of each row
Average per task (Round 1): mean of each row
```

---

## Complete Estimation Chain — Putting It All Together

### The Full Pipeline
```
┌─────────────────────────────────────────────────────────────────┐
│  Step 1: Size Estimation                                        │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │ Option A: LOC Estimation                                │    │
│  │   S = (Sopt + 4×Sm + Spess) / 6                        │    │
│  │                                                         │    │
│  │ Option B: Function Point Estimation                     │    │
│  │   UFC = Σ(count × weight)                               │    │
│  │   VAF = 0.65 + (0.01 × ΣFi)                            │    │
│  │   FP = UFC × VAF                                        │    │
│  │   LOC = FP × Language Factor                            │    │
│  └─────────────────────────────────────────────────────────┘    │
│                          ↓                                      │
│  Step 2: Effort Estimation                                      │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │ Effort (pm) = Total LOC / Productivity Rate             │    │
│  └─────────────────────────────────────────────────────────┘    │
│                          ↓                                      │
│  Step 3: Cost Estimation                                        │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │ Cost = Effort (pm) × Cost per person-month              │    │
│  └─────────────────────────────────────────────────────────┘    │
│                          ↓                                      │
│  Step 4: Risk Assessment                                        │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │ RE = P × C                                              │    │
│  └─────────────────────────────────────────────────────────┘    │
│                          ↓                                      │
│  Step 5: Scheduling                                             │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │ Forward Pass → Backward Pass → Float → Critical Path    │    │
│  └─────────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────────┘
```

### Key Formulas Summary Card

| Formula | Variables | Units |
|---------|-----------|-------|
| S = (Sopt + 4Sm + Spess) / 6 | Sopt, Sm, Spess = size estimates | LOC |
| UFC = Σ(count × weight) | count = element count; weight = from table | UFC |
| VAF = 0.65 + (0.01 × ΣFi) | Fi = rating 0-5 for each of 14 GSCs | VAF (0.65-1.35) |
| FP = UFC × VAF | UFC = unadjusted count; VAF = adjustment | FP |
| LOC = FP × Lang_Factor | Lang_Factor = from conversion table | LOC |
| Effort = LOC / Productivity_Rate | Productivity = LOC/pm from history | person-months |
| Cost = Effort × Cost_per_pm | Cost/pm = salary + overhead | currency |
| RE = P × C | P = probability (0-1); C = cost impact | currency |
| TF = LF - EF = LS - ES | LF, EF, LS, ES = from network analysis | time units |
| FF = MIN(ES_succ) - ES_act - Dur | ES_succ = successor early starts | time units |
