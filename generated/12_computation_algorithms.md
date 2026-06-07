# Computation Algorithms for Software Engineering

---

## Algorithm 1: LOC Estimation (Three-Point Formula)

### Problem Type
Estimating the size of a software component in Lines of Code when historical data is available.

### Recognition Pattern
- You have optimistic (best-case), most-likely, and pessimistic (worst-case) estimates
- You need a weighted expected value that accounts for uncertainty
- Formula: `S = (S_opt + 4 x S_most + S_pess) / 6`

### Step-by-Step Algorithm

**Step 1: Decompose the project into functions/components**
- Break the system into identifiable functions (e.g., UI, database, analysis modules)

**Step 2: For each function, collect three estimates**
- `S_opt` (optimistic): Best-case scenario — everything goes right
- `S_most` (most likely): Realistic scenario — normal challenges
- `S_pess` (pessimistic): Worst-case scenario — many things go wrong

**Step 3: Apply the weighted average formula**
```
Expected LOC = (S_opt + 4 x S_most + S_pess) / 6
```

**Step 4: Sum all function estimates**
```
Total Expected LOC = Sum of all function expected values
```

**Step 5: Calculate effort and cost**
```
Effort (person-months) = Total LOC / Productivity (LOC/pm)
Cost = Effort x Cost per person-month
Cost per LOC = Cost per person-month / Productivity
```

### Shortcuts
- If you only have one estimate, use it as `S_most` and estimate `S_opt ≈ 0.6 x S_most`, `S_pess ≈ 1.4 x S_most`
- The formula gives more weight (4x) to the most likely estimate — it dominates
- Memorize: `S = (a + 4b + c) / 6` is the standard PERT-derived formula

### Common Mistakes
- **Counting blank lines and comments**: DO NOT count blank lines or comments — only source code with declarations, logic, and computations
- **Forgetting to sum components**: Calculate expected value PER FUNCTION, then sum — do NOT sum optimistics separately
- **Using wrong units**: Ensure LOC estimates are consistent units (not mixing KLOC and LOC)
- **Ignoring historical productivity**: Without baseline productivity data, LOC estimates are meaningless for effort/cost

### Example

**Given**: 3D geometric analysis function:
- Optimistic = 4,600 LOC
- Most likely = 6,900 LOC
- Pessimistic = 8,600 LOC

**Calculation**:
Expected = (4600 + 4 x 6900 + 8600) / 6
         = (4600 + 27600 + 8600) / 6
         = 40800 / 6
         = **6,800 LOC**

**CAD System Example** (all functions):

| Function | Expected LOC |
|----------|-------------|
| 2D geometric analysis | 5,300 |
| 3D geometric analysis | 6,800 |
| UI and control facilities | 2,300 |
| Database management | 3,350 |
| Design analysis modules | 8,400 |
| Computer graphics display | 4,950 |
| Peripheral control | 2,100 |
| **Total** | **33,200** |

Given productivity = 620 LOC/pm, cost = $8,000/month:
- Effort = 33,200 / 620 = 53.5 ≈ **54 person-months**
- Cost per LOC = 8000/620 ≈ **$13/LOC**
- Total Cost = 33,200 x 13 = **$431,600**

---

## Algorithm 2: Function Point Analysis (UFP + CAF)

### Problem Type
Estimating software size based on functional requirements independent of programming language.

### Recognition Pattern
- You have counts of system inputs, outputs, queries, files, and interfaces
- You need to convert functional requirements into a size metric
- Language independence is important (estimation before technology choice)

### Step-by-Step Algorithm

**Step 1: Count the five information domain values**

| Domain | Symbol | Description |
|--------|--------|-------------|
| External Inputs | EI | User inputs providing data or control (update ILFs) |
| External Outputs | EO | Derived data provided to user |
| External Inquiries | EQ | Online input generating immediate response (retrieves data) |
| Internal Logical Files | ILF | Logical data groupings within the application |
| External Interface Files | EIF | Logical data from external applications |

**Step 2: Assign complexity weights**

| Domain | Simple | Average | Complex |
|--------|--------|---------|---------|
| EI | 3 | 4 | 6 |
| EO | 4 | 5 | 7 |
| EQ | 3 | 4 | 6 |
| ILF | 7 | 10 | 15 |
| EIF | 5 | 7 | 10 |

**Step 3: Calculate Unadjusted Function Points (UFP)**
```
UFP = Sum over all domains of (Count x Weight)
```

**Step 4: Rate the 14 General System Characteristics (Fi)**

Rate each Fi from 0 (no influence) to 5 (essential):

| # | Factor |
|---|--------|
| F1 | Data communications |
| F2 | Distributed data processing |
| F3 | Performance |
| F4 | Heavily used configuration |
| F5 | Transaction rate |
| F6 | On-line data entry |
| F7 | End-user efficiency |
| F8 | On-line update |
| F9 | Complex processing |
| F10 | Reusability |
| F11 | Installation ease |
| F12 | Operational ease |
| F13 | Multiple sites |
| F14 | Facilitate change |

**Step 5: Calculate Complexity Adjustment Factor (CAF)**
```
CAF = 0.65 + (0.01 x Sum Fi)
```
Range: 0.65 (minimum) to 1.35 (maximum, when Sum Fi = 70)

**Step 6: Calculate Final Function Points**
```
FP = UFP x CAF
```

**Step 7: Estimate effort and cost**
```
Effort = FP / Productivity (FP/person-month)
Cost = Effort x Cost per person-month
```

### Shortcuts
- When complexity is unknown, assume "Average" weights for all domains
- CAF ≈ 1.0 when Sum Fi ≈ 35 (moderate complexity)
- If all Fi = 0 (no complexity factors present), CAF = 0.65
- If all Fi = 5 (maximum complexity), CAF = 1.35
- FP-to-LOC conversion varies by language (e.g., 1 FP ≈ 60 LOC for Java, 100 LOC for C)

### Common Mistakes
- **Counting log files as ILFs**: Log files are NOT counted as ILFs — only logical files that maintain business data
- **Confusing EI and EQ**: If input generates immediate retrieval output without updating data, it is an EQ, not EI
- **Forgetting to multiply by CAF**: UFP alone is NOT the final FP count
- **Using wrong weights**: Use Simple/Average/Complex columns correctly — don't mix them
- **Double counting**: An input that also produces output should be counted as ONE EI, not EI + EO

### Example

**Move System — Logistics Application**

Counts: EI=25, EO=50, EQ=40, ILF=12, EIF=3 (all average complexity)

**UFP Calculation**:
| Domain | Count | x Weight | = Total |
|--------|-------|---------|--------|
| EI | 25 | x 4 | 100 |
| EO | 50 | x 5 | 250 |
| EQ | 40 | x 4 | 160 |
| ILF | 12 | x 10 | 120 |
| EIF | 3 | x 7 | 21 |
| **UFP** | | | **651** |

**CAF Calculation** (Sum Fi = 36):
```
CAF = 0.65 + (0.01 x 36) = 0.65 + 0.36 = 1.01
```

**FP Calculation**:
```
FP = 651 x 1.01 = 657.51 FP
```

**Effort & Cost** (Productivity = 10 FP/person-month, $5,000/person-month):
```
Effort = 657.51 / 10 = 65.75 person-months
Team Size (10 months) = 65.75 / 10 ≈ 7 developers
Total Cost = 65.75 x $5,000 = $328,750
```

---

## Algorithm 3: COCOMO (Basic and Intermediate)

### Problem Type
Estimating effort, development time, staff size, and cost for software projects based on size (KLOC).

### Recognition Pattern
- You know the estimated size in KLOC (thousands of lines of code)
- You can classify the project as Organic, Semi-detached, or Embedded
- You need person-months, calendar time, and cost estimates

### Step-by-Step Algorithm — Basic COCOMO

**Step 1: Determine project mode**

| Mode | Description |
|------|-------------|
| Organic | Small team, familiar with project, similar past projects |
| Semi-detached | Mixed — between organic and embedded |
| Embedded | Highly complex, unfamiliar team, tight constraints |

**Step 2: Identify constants (a, b, c, d)**

| Mode | a (Effort coefficient) | b (Effort exponent) | c (Time coefficient) | d (Time exponent) |
|------|----------------------|---------------------|---------------------|-------------------|
| Organic | 2.4 | 1.05 | 2.5 | 0.38 |
| Semi-detached | 3.0 | 1.12 | 2.5 | 0.35 |
| Embedded | 3.6 | 1.20 | 2.5 | 0.32 |

**Step 3: Calculate Effort (person-months)**
```
E = a x (KLOC)^b
```

**Step 4: Calculate Development Time (months)**
```
D = c x (E)^d
```

**Step 5: Calculate Average Staff Size**
```
S = E / D
```

**Step 6: Calculate Total Cost**
```
Average cost/person-month = (Low + Average + High) / 3
Cost = E x Average cost/person-month
```

### Step-by-Step Algorithm — Intermediate COCOMO

Intermediate COCOMO adds **cost drivers** (15 multipliers) to adjust the effort:

```
E = a x (KLOC)^b x (Product of cost driver multipliers)
```

**Cost Driver Categories**:
- **Product**: RELY (reliability), DATA (database size), CPLX (complexity)
- **Platform**: TIME (execution time), STOR (storage), PVOL (platform volatility)
- **Personnel**: ACAP (analyst capability), PCAP (programmer capability), AEXP (applications experience), PEXP (platform experience), LTEX (language/tool experience)
- **Project**: TOOL (software tools), SITE (multisite), SCED (schedule constraint)

Each cost driver is rated from Very Low to Extra High, with corresponding multipliers (e.g., ACAP Very Low = 1.50, ACAP Very High = 0.69).

### Shortcuts
- For quick estimates: only use Basic COCOMO (3 constants, no multipliers)
- Semi-detached is the default mode for most business applications
- KLOC = LOC / 1000 (always convert from LOC to KLOC)
- Development time is sub-linear (d < 1), so doubling effort doesn't double time
- For organic mode: E ≈ 2.4 x KLOC (since 1.05 ≈ 1.0 for small projects)

### Common Mistakes
- **Using LOC instead of KLOC**: The formulas require KLOC — divide LOC by 1000 first
- **Confusing exponent bases**: Effort uses (KLOC)^b, Time uses (Effort)^d — different exponents for different equations
- **Forgetting the constants**: The a and c constants (2.4, 3.0, 3.6 and 2.5) are not optional
- **Assuming linearity**: COCOMO is NON-LINEAR — 2x the KLOC does NOT produce 2x the effort
- **Misclassifying the mode**: Be honest about team familiarity and project complexity
- **Using average cost incorrectly**: Average cost = (low + avg + high) / 3, not a single value

### Example — Semi-detached Mode

**Given**: 32,000 LOC (32 KLOC), semi-detached mode

**Effort**:
```
E = 3.0 x (32)^1.12
32^1.12 = e^(1.12 x ln(32)) = e^(1.12 x 3.4657) = e^(3.8816) ≈ 48.47
E = 3.0 x 48.47 = 145.4 PM
```
(Textbook value: 140.05 PM — rounding variations)

**Development Time**:
```
D = 2.5 x (140.05)^0.35
140.05^0.35 = e^(0.35 x ln(140.05)) = e^(0.35 x 4.942) = e^(1.7297) ≈ 5.64
D = 2.5 x 5.64 = 14.1 months
```
(Textbook value: 14.7 months)

**Average Staff**:
```
S = 140.05 / 14.7 ≈ 10 persons
```

**Cost** (cost/person-month = average of $6K, $8K, $10K = $8K):
```
Cost = 140.05 x $8,000 = $1,120,400
```

---

## Algorithm 4: CPM — Critical Path Method (Forward/Backward Pass, Float)

### Problem Type
Scheduling project activities, identifying the critical path, and calculating slack/float.

### Recognition Pattern
- You have a list of activities with durations and predecessor relationships
- You need to find the shortest possible project duration
- You need to identify which activities cannot be delayed (critical path)

### Step-by-Step Algorithm

**Step 1: Draw the Activity Network**
- Represent activities as nodes (or arrows, depending on notation)
- Connect with arrows showing dependencies (predecessor → successor)
- Flow from left to right
- No loops allowed

**Step 2: Forward Pass — Calculate Early Start (ES) and Early Finish (EF)**

Rules:
- ES of first activity(ies) = 0
- EF = ES + Duration
- ES of any activity = MAX(EF of ALL predecessors)
- If no predecessor, ES = 0

```
For each activity in order from start:
  ES = 0 if no predecessor, else MAX(EF of all predecessors)
  EF = ES + Duration
```

**Step 3: Backward Pass — Calculate Late Finish (LF) and Late Start (LS)**

Rules:
- LF of last activity(ies) = project duration (EF of last activity)
- LS = LF - Duration
- LF of any activity = MIN(LS of ALL successors)
- If no successor, LF = project duration

```
For each activity in reverse order:
  LF = Project Duration if no successor, else MIN(LS of all successors)
  LS = LF - Duration
```

**Step 4: Identify All Paths and Find the Critical Path**

List all paths from start to end, sum durations. The longest path is the Critical Path.

```
Critical Path = Path with maximum total duration
Critical activities = All activities on this path (TF = 0)
```

**Step 5: Calculate Total Float (TF)**
```
TF = LF - EF = LS - ES
```
- TF = 0 for critical activities
- TF > 0 means the activity can be delayed by up to TF days without affecting project completion

**Step 6: Calculate Free Float (FF)**
```
FF = MIN(ES of all successors) - ES - Duration
```
- FF = amount an activity can be delayed without affecting the early start of any successor
- FF <= TF always

### Shortcuts
- The critical path is always the path with the longest duration
- Any activity with TF = 0 is on the critical path
- If multiple paths have the same maximum duration, ALL are critical paths
- Free float can never exceed total float
- Total float can be shared among activities on the same path; free float is per-activity

### Common Mistakes
- **Starting ES at 1 instead of 0**: Convention is ES = 0 for the first activity
- **Taking MIN instead of MAX for forward pass**: ES = MAX(EF of predecessors), not MIN
- **Taking MAX instead of MIN for backward pass**: LF = MIN(LS of successors), not MAX
- **Forgetting to identify all paths**: A path you miss might be the critical path
- **Using wrong predecessor relationships**: If an activity has multiple predecessors, ALL must complete before it starts
- **Confusing total float and free float**: TF affects project completion; FF only affects successor's early start

### Example

| Activity | Predecessor | Duration (days) |
|----------|-------------|-----------------|
| A | - | 3 |
| B | A | 4 |
| C | A | 2 |
| D | B | 5 |
| E | C | 1 |
| F | C | 2 |
| G | D, E | 4 |
| H | F, G | 3 |

**Forward Pass**:
- A: ES=0, EF=0+3=3
- B: ES=3, EF=3+4=7
- C: ES=3, EF=3+2=5
- D: ES=7, EF=7+5=12
- E: ES=5, EF=5+1=6
- F: ES=5, EF=5+2=7
- G: ES=max(12,6)=12, EF=12+4=16
- H: ES=max(7,16)=16, EF=16+3=19

**Paths**:
- A-B-D-G-H = 3+4+5+4+3 = **19 days** ← CRITICAL
- A-C-E-G-H = 3+2+1+4+3 = 13 days
- A-C-F-H = 3+2+2+3 = 10 days

**Backward Pass**:
- H: LF=19, LS=19-3=16
- G: LF=16, LS=16-4=12
- F: LF=16, LS=16-2=14
- D: LF=12, LS=12-5=7
- E: LF=12, LS=12-1=11
- B: LF=7, LS=7-4=3
- C: LF=min(11,14)=11, LS=11-2=9
- A: LF=min(3,9)=3, LS=3-3=0

**Total Float**:
- A: 3-3=0, B: 7-7=0, D: 12-12=0, G: 16-16=0, H: 19-19=0 (CRITICAL)
- C: 11-5=6, E: 11-6=5, F: 16-7=9

**Free Float**:
- C: min(5,5)-3-2=0
- E: 12-5-1=6
- F: 16-5-2=9

**Result**: Project duration = 19 days. Critical path = A-B-D-G-H.

---

## Algorithm 5: Risk Exposure (RE = P x C)

### Problem Type
Quantifying the financial impact of a risk to prioritize mitigation efforts.

### Recognition Pattern
- A risk event has been identified with a probability of occurrence
- The impact/consequence can be expressed in monetary terms
- Need to compare risks to decide where to allocate mitigation resources

### Step-by-Step Algorithm

**Step 1: Identify and describe the risk**
- What can go wrong?
- Under what conditions?
- What is the triggering event?

**Step 2: Estimate the Probability (P)**
- Range: 0.0 (impossible) to 1.0 (certain)
- Use historical data, expert judgment, or analogy
- Common scales: Very Low (<10%), Low (10-25%), Moderate (25-50%), High (50-75%), Very High (>75%)

**Step 3: Estimate the Cost Impact (C)**
- What is the cost to the project if the risk occurs?
- Include: additional development, delayed delivery penalties, lost revenue, rework costs
- Express in monetary units ($)

**Step 4: Calculate Risk Exposure**
```
RE = P x C
```

**Step 5: Interpret and prioritize**
- Higher RE = higher priority for mitigation
- Compare RE across all identified risks
- Set a threshold: risks above threshold need RMMM plans; risks below are retained and tracked

**Step 6: Develop RMMM Strategy**
- **Mitigation**: Actions to reduce P or C (or both)
- **Monitoring**: Factors/tracking to detect if risk is becoming more/less likely
- **Management**: Contingency plan if risk becomes reality

### Shortcuts
- If C is hard to estimate, use impact categories (1=negligible to 5=catastrophic) with rough monetary equivalents
- For comparing risks qualitatively: Risk Priority = Probability x Impact (1-5 scale)
- When exact costs are unknown, use order-of-magnitude estimates ($1K, $10K, $100K, $500K+)
- A risk with P > 75% needs immediate mitigation regardless of RE value

### Common Mistakes
- **Using probabilities as percentages (80 instead of 0.80)**: Always use decimal form (0.0 to 1.0). RE = 0.80 x $25,200 = $20,200 (correct); RE = 80 x $25,200 = $2,016,000 (wrong!)
- **Confusing impact with RE**: Impact (C) is the cost IF the risk occurs. RE = P x C is the expected value.
- **Forgetting to convert units**: Ensure P and C are in compatible units (both as decimals and dollars)
- **Double-counting**: Don't multiply impact by probability twice — RE = P x C, not P x (P x C)
- **Overlooking secondary risks**: Mitigation actions can create new risks — identify and assess those too

### Example

**Risk**: Only 70% of planned reusable components will actually integrate; remaining 30% must be custom-developed.

**Probability**: P = 0.80 (80% likely)

**Impact Calculation**:
- Planned reusable components = 60
- Components needing custom dev = 60 x (1 - 0.70) = 18
- Average component size = 100 LOC
- Custom LOC needed = 18 x 100 = 1,800 LOC
- Cost per LOC = $14.00
- Impact (C) = 1,800 x $14 = $25,200

**Risk Exposure**:
```
RE = 0.80 x $25,200 = $20,200
```

**Interpretation**: The expected monetary loss from this risk is $20,200. The project should budget this amount as contingency and prioritize mitigation strategies (e.g., evaluate reuse candidates earlier, have backup components identified).

### Risk Table Template

| Risk | Category | Probability | Impact (1-5) | C ($) | RE ($) | RMMM |
|------|----------|-------------|--------------|-------|--------|------|
| Reusable components insufficient | Technology | 80% | 4 (critical) | $25,200 | $20,200 | RMMM-1 |
| Key developer leaving | People | 40% | 5 (catastrophic) | $50,000 | $20,000 | RMMM-2 |
| Requirements changes | Requirements | 60% | 3 (marginal) | $15,000 | $9,000 | RMMM-3 |
| Hardware delay | Project | 30% | 4 (critical) | $30,000 | $9,000 | RMMM-4 |

---

## Summary: When to Use Each Algorithm

| Algorithm | When to Use | Input Needed | Output |
|-----------|-------------|--------------|--------|
| LOC 3-Point | Early estimation, language-dependent | Opt/Most/Pess LOC per function | Expected LOC, effort, cost |
| Function Point | Language-independent estimation | EI, EO, EQ, ILF, EIF counts + 14 Fi factors | FP count, effort, cost |
| COCOMO Basic | High-level effort/time estimation | KLOC, project mode (Organic/Semi/Embedded) | Person-months, months, staff, cost |
| CPM Scheduling | Project scheduling after estimation | Activities, durations, dependencies | ES/EF/LS/LF, critical path, float |
| Risk Exposure | Risk prioritization | Probability (P), Cost impact (C) | RE = P x C, risk priority ranking |

## Key Formulas Reference Card

| Formula | Equation | Notes |
|---------|----------|-------|
| Expected LOC | (S_opt + 4S_most + S_pess)/6 | PERT weighted average |
| Function Point | FP = UFP x [0.65 + 0.01 x Sum(Fi)] | CAF range: 0.65 to 1.35 |
| UFP | Sum(Count x Weight) per domain | 5 domains, 3 complexity levels |
| COCOMO Effort | E = a x (KLOC)^b | a=2.4/3.0/3.6, b=1.05/1.12/1.20 |
| COCOMO Time | D = c x (E)^d | c=2.5 for all, d=0.38/0.35/0.32 |
| COCOMO Staff | S = E / D | Average staff size |
| Early Start | ES = max(EF of predecessors) | Forward pass |
| Early Finish | EF = ES + Duration | Forward pass |
| Late Finish | LF = min(LS of successors) | Backward pass |
| Late Start | LS = LF - Duration | Backward pass |
| Total Float | TF = LF - EF = LS - ES | Delay without delaying project |
| Free Float | FF = min(ES_successors) - ES - Dur | Delay without affecting next activity |
| Risk Exposure | RE = P x C | P in decimal (0-1), C in $ |