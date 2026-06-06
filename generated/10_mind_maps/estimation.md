```
╔══════════════════════════════════════════════════════════════════════════════╗
║                              ESTIMATION                                    ║
╠══════════════════════════════════════════════════════════════════════════════╣
║  Techniques, models, and metrics for predicting software project effort     ║
╚══════════════════════════════════════════════════════════════════════════════╝

  │
  ├── Lines of Code (LOC) ────────────────────────────────────────────────────
  │   ├── Definition — Count of source lines (physical or logical)
  │   ├── Types — Delivered, Adapted, Equivalent source instructions
  │   ├── Pros — Easy to understand, directly measurable, historical data
  │   ├── Cons — Language dependent, ignores complexity, no quality measure
  │   ├── Productivity Metrics — LOC per person-month or staff-hour
  │   └── Cost Models — COCOMO (Basic, Intermediate, Detailed), SLIM
  │
  ├── Function Points (FP) ────────────────────────────────────────────────────
  │   ├── Five Components — EI, EO, EQ, ILF, EIF
  │   ├── Calculation — UFP x VAF (14 GSCs each rated 0-5)
  │   ├── Pros — Technology independent, available early, based on functionality
  │   └── Cons — Subjective assessment, training required, complex calculation
  │
  ├── Wideband Delphi ────────────────────────────────────────────────────────
  │   ├── Process — Experts estimate independently; discuss; re-estimate
  │   ├── Steps — Select team, distribute, estimate, share, discuss, repeat
  │   ├── Advantages — Reduces bias, leverages group knowledge, builds consensus
  │   └── Disadvantages — Time consuming, needs skilled facilitator
  │
  ├── Estimation Formulas ────────────────────────────────────────────────────
  │   ├── COCOMO II — Effort = a x Size^b x EAF
  │   ├── Basic COCOMO — Effort = a x KLOC^b (constants vary by project type)
  │   ├── FP Estimation — Productivity, Cost, Effort per FP
  │   └── Analogy-Based — Compare to similar projects; adjust for differences
  │
  ├── Estimation Techniques ──────────────────────────────────────────────────
  │   ├── Top-Down — Overall size; decompose; quick but less accurate
  │   ├── Bottom-Up — Individual tasks; sum; accurate but time consuming
  │   ├── Three-Point — O + 4M + P / 6 (PERT method)
  │   └── Planning Poker — Story points, Fibonacci sequence, team consensus
  │
  └── Estimation Challenges ──────────────────────────────────────────────────
      ├── Common Problems — Optimism bias, underestimation, uncertainty
      └── Best Practices — Multiple techniques, historical data, contingency
```

# Estimation - Mind Map

```
Estimation
├── Lines of Code LOC
│   ├── Definition
│   │   ├── Count of source lines
│   │   ├── Physical or logical lines
│   │   └── Excludes comments and blanks
│   ├── Types
│   │   ├── Delivered source instructions
│   │   ├── Adapted source instructions
│   │   └── Equivalent source instructions
│   ├── Pros
│   │   ├── Easy to understand
│   │   ├── Directly measurable
│   │   └── Historical data available
│   ├── Cons
│   │   ├── Language dependent
│   │   ├── Doesn't account for complexity
│   │   ├── No quality measure
│   │   └── Late in development
│   ├── Productivity Metrics
│   │   ├── LOC per person-month
│   │   └── LOC per staff-hour
│   └── Cost Estimation Models
│       ├── COCOMO
│       │   ├── Basic
│       │   ├── Intermediate
│       │   └── Detailed
│       └── SLIM
├── Function Points FP
│   ├── Definition
│   │   ├── Measure of functionality
│   │   ├── Independent of technology
│   │   └── Based on user requirements
│   ├── Five Component Types
│   │   ├── External inputs EI
│   │   ├── External outputs EO
│   │   ├── External inquiries EQ
│   │   ├── Internal logical files ILF
│   │   └── External interface files EIF
│   ├── Calculation
│   │   ├── Unadjusted Function Points UFP
│   │   ├── Value Adjustment Factor VAF
│   │   └── FP = UFP x VAF
│   ├── VAF Components
│   │   ├── 14 General System Characteristics
│   │   ├── Scale 0-5 for each
│   │   ├── Total influence 0-70
│   │   └── VAF = 0.65 + 0.01 x sum
│   ├── Pros
│   │   ├── Technology independent
│   │   ├── Available early
│   │   ├── Based on functionality
│   │   └── Good for estimation
│   └── Cons
│       ├── Subjective assessment
│       ├── Training required
│       ├── Complex calculation
│       └── Less accurate for small projects
├── Wideband Delphi
│   ├── Definition
│   │   ├── Expert judgment technique
│   │   ├── Group consensus approach
│   │   └── Anonymous estimation
│   ├── Process
│   │   ├── Coordinator organizes
│   │   ├── Experts estimate independently
│   │   ├── Group discussion of estimates
│   │   ├── Re-estimation
│   │   └── Final consensus
│   ├── Steps
│   │   ├── 1. Select experts 3-7 people
│   │   ├── 2. Coordinator distributes materials
│   │   ├── 3. Each expert makes estimate
│   │   ├── 4. Estimates shared anonymously
│   │   ├── 5. Group discusses differences
│   │   ├── 6. Re-estimate
│   │   └── 7. Repeat until consensus
│   ├── Advantages
│   │   ├── Reduces bias
│   │   ├── Leverages group knowledge
│   │   ├── Builds team consensus
│   │   └── Identifies assumptions
│   └── Disadvantages
│       ├── Time consuming
│       ├── Requires skilled facilitator
│       ├── Dominant personalities
│       └── Groupthink potential
├── Estimation Formulas
│   ├── COCOMO II
│   │   ├── Effort = a x Size^b x EAF
│   │   ├── Duration = c x Effort^d
│   │   └── Size in KLOC or FP
│   ├── Basic COCOMO
│   │   ├── Effort = a x KLOC^b
│   │   ├── Time = c x Effort^d
│   │   └── Model constants by project type
│   │       ├── Organic: a=2.4 b=1.05
│   │       ├── Semi-detached: a=3.0 b=1.12
│   │       └── Embedded: a=3.6 b=1.20
│   ├── Function Point Estimation
│   │   ├── Productivity = FP / Person-months
│   │   ├── Cost = FP x Cost per FP
│   │   └── Effort = FP x Effort per FP
│   └── Analogy-Based Estimation
│       ├── Compare to similar projects
│       ├── Adjust for differences
│       └── Expert judgment
├── Estimation Techniques
│   ├── Top-Down Estimation
│   │   ├── Start with overall size
│   │   ├── Decompose to components
│   │   ├── Sum components
│   │   └── Quick but less accurate
│   ├── Bottom-Up Estimation
│   │   ├── Estimate individual tasks
│   │   ├── Sum all tasks
│   │   └── More accurate but time consuming
│   ├── Three-Point Estimation
│   │   ├── Optimistic O
│   │   ├── Most likely M
│   │   ├── Pessimistic P
│   │   ├── Expected = O + 4M + P / 6
│   │   └── Standard deviation = P - O / 6
│   └── Planning Poker
│       ├── Agile estimation technique
│       ├── Uses story points
│       ├── Fibonacci sequence
│       └── Team consensus
└── Estimation Challenges
    ├── Common Problems
    │   ├── Optimism bias
    │   ├── Underestimation
    │   ├── Unknown requirements
    │   ├── Technical uncertainty
    │   └── Team inexperience
    └── Best Practices
        ├── Use multiple techniques
        ├── Calibrate with historical data
        ├── Include contingency
        ├── Update estimates regularly
        ├── Document assumptions
        └── Consider risk factors
```
