# Estimation — Detailed Notes

## The Story of Estimation

Every software project begins with a question that stakeholders desperately want answered: **"How much will it cost, and how long will it take?"** Estimation is the discipline of answering that question — not with certainty, but with educated, data-driven projections. A good estimate is not a guess; it's a **calculated prediction** based on historical data, analytical techniques, and professional judgment. The consequences of bad estimation are severe: budgets explode, deadlines slip, trust erodes, and projects get cancelled. This chapter explores the fundamental techniques for estimating software projects.

---

## Why Estimation Matters — The Three Pillars

Project estimation revolves around three fundamental parameters:

```
         SCOPE
        /      \
       /        \
      /          \
   TIME ──────── COST
```

| Parameter | Description | Estimation Question |
|-----------|-------------|-------------------|
| **Scope** | What work needs to be done? | What features, components, and tasks are required? |
| **Time** | How long will it take? | What is the project schedule? |
| **Cost** | How much will it cost? | What is the budget required? |

These three parameters are **interconnected**:
- More scope → more time → more cost
- Less time → may need more resources → more cost
- Less cost → fewer resources → more time

### Benefits of Estimation for Stakeholders

| Stakeholder | Benefit |
|-------------|---------|
| **Customers** | Know what they'll pay and when they'll receive the product |
| **Project Managers** | Can plan resources, set milestones, and manage expectations |
| **Developers** | Have realistic deadlines and workload expectations |
| **Management** | Can make informed go/no-go decisions on project investment |

---

## The Importance of Cost Estimation

Cost estimation is particularly critical because:
1. It determines **whether the project is financially viable**
2. It sets the **budget** that constrains all other decisions
3. It affects **resource allocation** — how many people, what skills, what tools
4. It influences **contract negotiations** — fixed-price vs. time-and-materials
5. It is often the **most scrutinized** number by management and customers

---

## What Makes a Good Estimate?

A good estimation must have these qualities:

| Quality | Description |
|---------|-------------|
| **Accuracy** | The estimate should be close to the actual outcome |
| **Precision** | The estimate should be specific, not vague ranges |
| **Justifiable** | The estimate must be backed by data and reasoning |
| **Consistent** | Similar projects should produce similar estimates |
| **Documented** | Assumptions and basis of estimate must be recorded |
| **Regularly updated** | Estimates should be revised as new information emerges |

> **Key Insight:** No estimate is perfect. The goal is to minimize the gap between estimated and actual values while being transparent about uncertainty.

---

## Wideband Delphi Technique — The Expert Judgment Method

The **Wideband Delphi** technique is a structured estimation method that leverages **collective expert judgment**. It's called "Wideband" because it involves wider communication and more structured interaction than the original Delphi method.

### Why Wideband Delphi?

- Individual estimates are often **biased** by personal experience, optimism, or pessimism
- Group discussion exposes **hidden assumptions** and blind spots
- The structured process produces **more reliable estimates**
- It captures **organizational knowledge** from experienced team members

### The 6-Step Wideband Delphi Process

#### Step 1: Planning
- The **moderator** organizes the estimation session
- Select a group of **5-7 estimators** (experienced team members)
- Define the **scope** of what needs to be estimated
- Provide all available project documentation and historical data
- Ensure everyone understands the rules and objectives

#### Step 2: Individual Estimation
- Each estimator **independently** creates their estimate
- No discussion or collaboration at this stage
- Each person records their estimate along with assumptions and reasoning
- This prevents groupthink and anchoring bias

#### Step 3: Group Discussion (Round 1)
- Each estimator **presents their estimate** and reasoning to the group
- Discussion focuses on **differences** — why did person A estimate 6 months while person B estimated 3 months?
- Common assumptions are identified; disagreements are explored
- No voting or averaging yet — just understanding

#### Step 4: Individual Re-estimation
- After hearing all perspectives, each estimator **revises** their estimate
- They incorporate insights from the discussion
- New estimates are recorded independently (again, no discussion)

#### Step 5: Group Discussion (Round 2)
- Revised estimates are presented
- If estimates have **converged** (are now close), the process may end
- If significant disagreement remains, further discussion occurs

#### Step 6: Final Estimation
- If estimates converge → use the **average or median** as the final estimate
- If estimates don't converge → additional rounds or fallback to the moderator's judgment
- Document all assumptions, rationale, and the final estimate

### Convergence Diagram

```
Round 1 Estimates:
  Person A: ████████████████████ (20 days)
  Person B: ████████ (8 days)
  Person C: ████████████████ (15 days)
  Person D: ██████████████ (13 days)
  Person E: ██████████████████ (18 days)
  
  Spread: 8-20 days (HUGE disagreement)

         [Group Discussion — Understanding Differences]

Round 2 Estimates:
  Person A: ████████████████ (15 days)
  Person B: ████████████ (12 days)
  Person C: █████████████ (13 days)
  Person D: ██████████████ (14 days)
  Person E: ████████████████ (15 days)

  Spread: 12-15 days (Much closer!)

         [Final Discussion]

Final Estimate: ~14 days (median/average)
```

> **Exam Tip:** Know the 6 steps and understand WHY convergence happens — it's because shared information reduces individual bias.

---

## Chat Application Case Study

Consider estimating the effort for building a **Chat Application**:

| Component | Estimated Effort (person-days) |
|-----------|-------------------------------|
| User authentication system | 8 |
| Real-time messaging engine | 20 |
| Chat history/database | 12 |
| User interface (web) | 15 |
| File sharing feature | 10 |
| Notification system | 7 |
| Testing and QA | 14 |
| **Total** | **86 person-days** |

Using Wideband Delphi, a team of 5 developers might individually estimate between 70-110 person-days. After discussion, they converge on approximately **86 person-days** as the consensus estimate.

---

## Line of Code (LOC) Estimation

LOC estimation is one of the oldest and most straightforward techniques. It estimates project size by counting the number of **source lines of code** that will be produced.

### The Three-Point Formula

LOC estimation uses three estimates to account for uncertainty:

```
Estimated LOC = (Optimistic + 4 × Most Likely + Pessimistic) / 6
```

This is a **weighted average** that emphasizes the most likely estimate while accounting for best-case and worst-case scenarios.

### Example 1: Simple Calculation

| Estimate | Lines of Code |
|----------|---------------|
| Optimistic (O) | 4,000 |
| Most Likely (M) | 6,000 |
| Pessimistic (P) | 9,000 |

```
LOC = (4,000 + 4×6,000 + 9,000) / 6
LOC = (4,000 + 24,000 + 9,000) / 6
LOC = 37,000 / 6
LOC = 6,167 lines
```

### Example 2: Larger Project

| Estimate | Lines of Code |
|----------|---------------|
| Optimistic (O) | 15,000 |
| Most Likely (M) | 22,000 |
| Pessimistic (P) | 35,000 |

```
LOC = (15,000 + 4×22,000 + 35,000) / 6
LOC = (15,000 + 88,000 + 35,000) / 6
LOC = 138,000 / 6
LOC = 23,000 lines
```

### Example 3: Small Module

| Estimate | Lines of Code |
|----------|---------------|
| Optimistic (O) | 200 |
| Most Likely (M) | 350 |
| Pessimistic (P) | 600 |

```
LOC = (200 + 4×350 + 600) / 6
LOC = (200 + 1,400 + 600) / 6
LOC = 2,200 / 6
LOC = 367 lines
```

### Limitations of LOC Estimation

| Limitation | Description |
|-----------|-------------|
| Language dependent | 1000 lines of Python ≠ 1000 lines of Assembly |
| Quality ignored | More code doesn't mean better code |
| Programmer skill varies | Different programmers write different amounts of code for the same feature |
| Late in development | You can only count LOC after code is written — too late for early estimation |

---

## Function Point (FP) Estimation

Function Point estimation overcomes LOC limitations by measuring software size based on **what the software does** (its functionality), not how it's implemented (its code).

### The 5 Information Domain Types

Function points are calculated based on five information domain characteristics:

| # | Domain Type | Description | Examples |
|---|------------|-------------|----------|
| 1 | **External Inputs (EI)** | Data entering the system from outside | User input forms, data imports, API calls received |
| 2 | **External Outputs (EO)** | Data leaving the system to outside | Reports, messages sent, data exports |
| 3 | **External Inquiries (EQ)** | Input/output pairs — query and response | Search queries with results, lookup operations |
| 4 | **Internal Logical Files (ILF)** | Data stores maintained within the system | Database tables, internal data structures |
| 5 | **External Interface Files (EIF)** | Data stores referenced but maintained by external systems | Shared databases, third-party data feeds |

### Weighting Factors Table

Each domain type is assigned a weight based on complexity:

| Domain Type | Simple | Average | Complex |
|------------|--------|---------|---------|
| External Inputs (EI) | 3 | 4 | 6 |
| External Outputs (EO) | 4 | 5 | 7 |
| External Inquiries (EQ) | 3 | 4 | 6 |
| Internal Logical Files (ILF) | 7 | 10 | 15 |
| External Interface Files (EIF) | 5 | 7 | 10 |

### The 14 General System Characteristics (GSCs)

These 14 factors adjust the raw function point count based on **system-wide quality attributes**:

| # | General System Characteristic |
|---|------------------------------|
| 1 | Data communications |
| 2 | Distributed data processing |
| 3 | Performance |
| 4 | Heavily used configuration |
| 5 | Transaction rate |
| 6 | Online data entry |
| 7 | End-user efficiency |
| 8 | Online update |
| 9 | Complex processing |
| 10 | Reusability |
| 11 | Installation ease |
| 12 | Operational ease |
| 13 | Multiple sites |
| 14 | Facilitate change |

Each GSC is rated on a scale of **0 (not present) to 5 (strong influence)**.

### Value Adjustment Factor (VAF)

```
VAF = 0.65 + (0.01 × Σ GSC ratings)
```

Where Σ GSC ratings is the sum of all 14 GSC scores (each 0-5).

- **Minimum VAF** = 0.65 (when all GSCs = 0)
- **Maximum VAF** = 1.35 (when all GSCs = 5)

### Function Point Formula

```
FP = (Σ counts × weights) × VAF
```

### Counting Example

Consider a system with the following counts:

| Domain Type | Simple | Average | Complex |
|------------|--------|---------|---------|
| EI | 2×3=6 | 3×4=12 | 1×6=6 |
| EO | 1×4=4 | 2×5=10 | 0×7=0 |
| EQ | 3×3=9 | 1×4=4 | 0×6=0 |
| ILF | 1×7=7 | 2×10=20 | 0×15=0 |
| EIF | 2×5=10 | 0×7=0 | 1×10=10 |

**Raw FP** = (6+12+6) + (4+10+0) + (9+4+0) + (7+20+0) + (10+0+10)
**Raw FP** = 24 + 14 + 13 + 27 + 20 = **98**

If Σ GSC ratings = 42:
```
VAF = 0.65 + (0.01 × 42) = 0.65 + 0.42 = 1.07
```

**Adjusted FP** = 98 × 1.07 = **104.86 FP**

### FP to LOC Conversion

To convert function points to lines of code, use a language-specific conversion factor:

| Language | LOC per FP |
|----------|-----------|
| Assembly | 320 |
| C | 128 |
| C++ | 53 |
| Java | 46 |
| Python | 35 |
| SQL | 12 |

**Example:** A project with 105 FP in Java:
```
LOC = 105 × 46 = 4,830 lines of Java code
```

### LOC to Effort Conversion

Once you have LOC, estimate effort using **productivity rates**:

| Language | LOC per Person-Month |
|----------|---------------------|
| Assembly | 200 |
| C | 500 |
| C++ | 600 |
| Java | 700 |
| Python | 800 |

**Example:** 4,830 LOC in Java:
```
Effort = 4,830 / 700 = 6.9 person-months
```

### Effort to Cost Conversion

Finally, convert effort to cost:

```
Cost = Effort × Cost per Person-Month
```

**Example:** 6.9 person-months at $8,000/person-month:
```
Cost = 6.9 × $8,000 = $55,200
```

### Complete Chain Example

```
FP (105) → LOC (4,830 Java) → Effort (6.9 PM) → Cost ($55,200)
```

---

## E-Commerce FP Example

Let's estimate a complete **e-commerce system** using function points:

| Domain Type | Simple | Average | Complex |
|------------|--------|---------|---------|
| EI | 4×3=12 | 6×4=24 | 3×6=18 |
| EO | 3×4=12 | 5×5=25 | 2×7=14 |
| EQ | 5×3=15 | 4×4=16 | 2×6=12 |
| ILF | 3×7=21 | 4×10=40 | 2×15=30 |
| EIF | 2×5=10 | 3×7=21 | 1×10=10 |

**Raw FP** = (12+24+18) + (12+25+14) + (15+16+12) + (21+40+30) + (10+21+10)
**Raw FP** = 54 + 51 + 43 + 91 + 41 = **280**

If Σ GSC ratings = 56:
```
VAF = 0.65 + (0.01 × 56) = 1.21
```

**Adjusted FP** = 280 × 1.21 = **338.8 FP**

Converting to Java:
```
LOC = 338.8 × 46 = 15,585 lines
Effort = 15,585 / 700 = 22.3 person-months
Cost = 22.3 × $8,000 = $178,400
```

---

## Summary: Estimation Techniques Comparison

| Technique | Basis | When to Use | Accuracy |
|-----------|-------|-------------|----------|
| **Wideband Delphi** | Expert judgment | Early planning, no historical data | Medium-High |
| **LOC Estimation** | Lines of code | When language and design are known | Low-Medium |
| **Function Points** | Functionality delivered | Early stages, language-independent | Medium-High |

---

## Quick Reference: Key Formulas

| Formula | Description |
|---------|-------------|
| `LOC = (O + 4M + P) / 6` | Three-point LOC estimation |
| `FP = (Σ counts × weights) × VAF` | Function point calculation |
| `VAF = 0.65 + (0.01 × Σ GSC)` | Value adjustment factor |
| `LOC = FP × LOC/FP factor` | FP to LOC conversion |
| `Effort = LOC / (LOC per person-month)` | LOC to effort conversion |
| `Cost = Effort × Cost per person-month` | Effort to cost conversion |

---

## Exam Preparation Checklist

- [ ] Can you explain the 3 pillars of estimation (scope, time, cost)?
- [ ] Can you describe all 6 steps of the Wideband Delphi technique?
- [ ] Can you draw and explain the convergence diagram?
- [ ] Can you calculate LOC using the three-point formula?
- [ ] Can you identify the 5 information domain types for FP?
- [ ] Can you apply weighting factors from the complexity table?
- [ ] Can you list and explain the 14 GSCs?
- [ ] Can you calculate VAF and FP?
- [ ] Can you convert FP → LOC → Effort → Cost?
- [ ] Can you solve the e-commerce FP example?
