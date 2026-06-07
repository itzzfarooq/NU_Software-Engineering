# Risk Management — Detailed Study Notes

---

## Topic Overview

Risk Management is a proactive discipline within software engineering that identifies, analyzes, and prepares for uncertainties that could negatively impact a project's schedule, budget, quality, or viability. It shifts the team from a reactive "fire-fighting" posture to a forward-looking stance where potential problems are anticipated and mitigated before they strike.

---

## Why This Topic Exists

Software projects are inherently uncertain. Requirements change, staff leave, technology fails, and deadlines shift. Without risk management, teams operate blindly, reacting to crises as they occur -- which is expensive, stressful, and often leads to project failure. Risk management exists to:

- Reduce the likelihood of unpleasant surprises
- Provide contingency plans so the team is never caught off-guard
- Allocate limited resources (time, money, people) to the most threatening issues
- Improve communication among stakeholders about what could go wrong
- Increase the probability of project success

---

## Core Concepts & Definitions

| Concept | Definition |
|---|---|
| **Risk** | An uncertain event or condition that, if it occurs, has a negative effect on project objectives |
| **Problem** | An event that has already occurred (different from risk) |
| **Constraint** | A certainty (NOT a risk) -- e.g., a fixed deadline |
| **Uncertainty** | The risk may or may not happen; there are no 100% risks |
| **Loss** | The unwanted consequence if the risk becomes real |
| **Risk Exposure (RE)** | RE = P x C where P = probability, C = cost of impact |
| **Risk Management** | The art of managing risks to achieve a WIN-WIN outcome between team and customer |
| **RMMM** | Risk Mitigation, Monitoring, and Management -- the plan for handling each risk |

### Two Characteristics of Risk

1. **Uncertainty** -- The risk may or may not happen (0% < P < 100%)
2. **Loss** -- If realized, there are negative consequences

### Risk Probability Scales

| Descriptor | Range |
|---|---|
| Very Low | < 10% |
| Low | 10% -- 25% |
| Moderate | 25% -- 50% |
| High | 50% -- 75% |
| Very High | > 75% |

### Sub-Types by Knowability

| Type | Description | Example |
|---|---|---|
| **Known risks** | Uncovered after careful evaluation of project plan, business/technical environment | Unrealistic delivery date |
| **Predictable risks** | Extrapolated from past project experience | Past staff turnover patterns |
| **Unpredictable risks** | Extremely difficult to identify in advance | A once-in-a-decade hardware failure |

---

## Reactive vs Proactive Strategies

| Dimension | Reactive | Proactive |
|---|---|---|
| **Philosophy** | "Don't worry, I'll think of something" | Formal risk analysis performed upfront |
| **Timing** | Nothing is done until something goes wrong | Risks identified, analyzed, and planned for in advance |
| **Approach** | Fix on failure; crisis management | Root cause correction; contingency plans |
| **Practices** | Resources found and applied when risk strikes | TQM concepts, statistical SQA, examining risk sources beyond software |
| **Outcome** | Chaotic, expensive, schedule slips | Controlled, predictable, lower stress |

### Reactive Approaches (from worst to less-bad)

1. **Crisis management** -- Failure does not respond to applied resources; project is in jeopardy
2. **Fix on failure** -- Resources are found and applied when the risk strikes
3. **Mitigation** -- Plan for additional resources in anticipation of fire fighting

### Proactive Steps

1. Identify possible risks (what can go wrong?)
2. Analyze each risk (probability + impact)
3. Rank risks by probability and impact (Negligible < Marginal < Critical < Catastrophic)
4. Develop contingency plans for high-probability, high-impact risks

---

## Seven Principles of Risk Management

| # | Principle | Meaning |
|---|---|---|
| 1 | **Maintain a global perspective** | View software risks within the context of the system and business problem |
| 2 | **Take a forward-looking view** | Think about future risks; establish contingency plans now |
| 3 | **Encourage open communication** | If someone states a risk, do not discount it |
| 4 | **Integrate** | Risk consideration must be woven into the software process itself |
| 5 | **Emphasize a continuous process** | Stay vigilant throughout; modify risks as more is known |
| 6 | **Develop a shared product vision** | All stakeholders sharing the same vision leads to better risk ID |
| 7 | **Encourage teamwork** | Pool the talents, skills, and knowledge of all stakeholders |

Memory aid: **G F I E C D T** (Global, Forward-looking, Integrate, Emphasize continuous, Communicate, Develop vision, Teamwork)

---

## Risk Management Paradigm (Cycle)

```
                    +-----------+
                    |  IDENTIFY |
                    +-----+-----+
                          |
                          v
                    +-----------+
                    |  ANALYZE  |
                    +-----+-----+
                          |
                          v
                    +-----------+
                    |   PLAN    |
                    +-----+-----+
                          |
                          v
                    +-----------+
                    |   TRACK   |
                    +-----+-----+
                          |
                          v
                    +-----------+
                    |  CONTROL  |
                    +-----+-----+
                          |
             (back to IDENTIFY)
```

The paradigm is a continuous cycle, not a one-time activity.

---

## Risk Identification

### Systematic Process

Risk identification is a **systematic attempt** to specify threats to the project plan. It identifies both:

- **Generic risks** -- threats to every software project
- **Product-specific risks** -- identified by those with clear understanding of the technology, people, and environment specific to the software to be built. Requires examination of the project plan and statement of scope.

### Seven Risk Categories

| Category | Description | Key Questions |
|---|---|---|
| **Product size** | Risks associated with the overall size of the software | Estimated LOC/FP? % deviation from past products? Number of users? |
| **Business impact** | Risks from management or marketplace constraints | Effect on company revenue? Senior management visibility? Cost of late delivery? |
| **Customer characteristics** | Risks from customer sophistication and communication | Worked with customer before? Solid idea of requirements? Willing to participate in reviews? |
| **Process definition** | Risks from how well the software process is defined/followed | Common process framework established? CASE tools used? Formal technical reviews? |
| **Development environment** | Risks from availability/quality of tools | Are tools integrated? Are document formats established? |
| **Technology to be built** | Risks from complexity and newness of technology | New to organization? New algorithms? Unproven hardware? Specialized UI? |
| **Staff size and experience** | Risks from team composition | Best people available? Right skills? Staff turnover low? Adequate training? |

### Risk Item Checklist

A risk item checklist can be organized as:

1. A list of characteristics relevant to each risk subcategory
2. A questionnaire that leads to an estimate on the impact of each risk
3. A list containing a set of risk components/drivers and their probability of occurrence

### Questionnaire for Assessing Overall Project Risk

The degree of project risk is directly proportional to the number of **negative responses**.

1. Have top software and customer managers formally committed to support the project?
2. Are end-users enthusiastically committed to the project?
3. Are requirements fully understood by the team and customers?
4. Have customers been involved fully in requirements definition?
5. Do end-users have realistic expectations?
6. Is project scope stable?
7. Does the team have the right mix of skills?
8. Are project requirements stable?
9. Does the team have experience with the technology?
10. Is the number of people adequate?
11. Do all constituencies agree on the importance and requirements?

---

## Risk Projection (Estimation)

### Risk Exposure Formula

```
RE = P x C
```

Where:
- **RE** = Risk Exposure
- **P** = Probability of occurrence (0.0 to 1.0)
- **C** = Cost to the project should the risk occur

### Worked Example

- **Risk identified**: Only 70% of planned reusable components will integrate; remaining must be custom-built.
- **Probability**: 80% (0.80)
- **Impact**: 18 components x 100 LOC each x $14/LOC = $25,200
- **RE** = 0.80 x $25,200 = **$20,200**

### Four Risk Projection Steps

1. Establish a scale reflecting the perceived likelihood of a risk
2. Delineate the consequences of the risk
3. Estimate the impact of the risk on the project and product
4. Note the overall accuracy of the projection to avoid misunderstandings

### Risk Components and Drivers

| Component | Definition |
|---|---|
| **Performance risk** | Uncertainty the product will meet requirements and be fit for use |
| **Cost risk** | Uncertainty the project budget will be maintained |
| **Support risk** | Uncertainty the software will be easy to correct, adapt, and enhance |
| **Schedule risk** | Uncertainty the schedule will be maintained and delivery on time |

### Impact Assessment Levels

| Level | Performance | Cost | Schedule | Support |
|---|---|---|---|---|
| **Catastrophic** | Mission failure | > $500K overrun | Unachievable | Nonresponsive software |
| **Critical** | Mission success questionable | $100K--$500K | Possible slippage | Minor modification delays |
| **Marginal** | Secondary mission degradation | $1K--$100K | Realistic, achievable | Responsive software support |
| **Negligible** | Inconvenience only | < $1K | Early achievable | Easily supportable |

### Risk Table Structure

| Risk Summary | Risk Category | Probability | Impact (1-5) | RMMM |
|---|---|---|---|---|
| Short description | One of 7 categories | % or scale value | 1 (low) to 5 (catastrophic) | Pointer to RMMM plan |

Process:
1. Estimate probability of occurrence
2. Estimate impact on a scale of 1 to 5 (1 = low, 5 = catastrophic)
3. Sort the table by probability and impact (descending)
4. Establish a threshold -- risks above the threshold go into the RMMM plan

### Post-Table Steps

a) All stakeholders review the table to verify no risk was overlooked
b) Risk is re-evaluated at the end of each project milestone
c) Overall risk exposure is recalculated

---

## Risk Mitigation, Monitoring, and Management (RMMM)

### Risk Mitigation (Avoidance)

- **Goal**: Reduce the probability and/or impact of a risk before it occurs
- High priority risks get detailed mitigation strategies
- Low priority risks get brief strategies
- Risk mitigation is **expensive** but cost-effective compared to crisis management
- Best mitigation is **advance planning**: talk to customers, communicate early, document clearly
- Mitigation is a continuous process, not a one-time event

### Risk Monitoring (Tracking)

- **Goal**: Track identified risks, monitor residual risks, identify new risks, evaluate process effectiveness
- Monitoring should be **ongoing** throughout the project lifecycle
- Responsibilities:
  - Who monitors each risk?
  - How often are risks reviewed?
  - What metrics track risk status?
  - How is status communicated to stakeholders?

### Risk Management (Contingency)

- **Goal**: Have contingency plans ready if risk becomes reality
- Regular RMMM meetings to track risks
- Document every risk in the RMMM Plan

### Recording Risk Information (Template)

| Field | Example |
|---|---|
| Project | Embedded software for XYZ system |
| Risk type | Schedule risk |
| Priority (1-5) | 4 |
| Risk factor | Project completion depends on tests requiring hardware component under development; delivery may be delayed |
| Probability | 60% |
| Impact | Project completion delayed for each day hardware is unavailable |
| Monitoring approach | Scheduled milestone reviews with hardware group |
| Contingency plan | Modify testing strategy to use software simulation |
| Estimated resources | 6 additional person-months beginning in July |

---

## Risk Refinement

- At the start of a project, broad risks and their causes can be identified
- As the project proceeds, some causes disappear and new ones appear
- Risk refinement identifies the **exact causes and severity** of a risk
- Example: "A new graphics library will not be delivered on schedule"
  - **Why?** What is the root cause?
  - **Effect?** What happens because of this cause?
  - This refinement helps move from vague concern to actionable mitigation

---

## Risk Retention

- Risks with **low probability, low exposure, or minimal loss** are retained
- If a risk falls **below the threshold**, retain and track it (do not ignore it)
- If a retained risk grows **beyond the threshold**, develop a mitigation plan

---

## Relationships Between Concepts

```
Risk Identification ──> Risk Projection (P x C) ──> Risk Table ──> RMMM Plan
        │                                                              │
        └── Refinement (refine causes)                                 │
                                                                       │
                                                            Risk Monitoring
                                                                   │
                                                            Risk Retention
                                                              (if low risk)
```

- **Risk ID** feeds into **Risk Projection** (estimation of P and C)
- **Projection** populates the **Risk Table** (sorted by severity)
- The **Risk Table** drives the **RMMM Plan** (mitigation strategies)
- **Risk Monitoring** tracks all risks throughout the lifecycle
- When risks are refined, their P and C may change, updating the table
- Low-priority risks are **retained** (tracked but not actively mitigated)

---

## Common Mistakes / Exam Traps

| Mistake | Correct Understanding |
|---|---|
| Confusing risk with a problem | A problem has already occurred; a risk is a future uncertainty |
| Confusing risk with a constraint | A constraint is 100% certain (e.g., a hard deadline); a risk has P < 100% |
| Thinking risk management is one-time | It is a continuous cycle (Identify -> Analyze -> Plan -> Track -> Control) |
| Ignoring low-probability risks entirely | Retain and track them; they may grow beyond the threshold |
| Confusing RE formula units | RE = P x C where C is in monetary cost, not impact scale (1-5) |
| Mixing up risk categories | Know the 7 categories: Product size, Business impact, Customer, Process, Environment, Technology, Staff |
| Thinking mitigation is a one-time event | Mitigation is continuous throughout the project |
| Equating "reactive" with "proactive" | Reactive = wait for failure; Proactive = plan ahead |
| Forgetting the risk table columns | Risk Summary, Category, Probability, Impact, RMMM |
| Treating all risks equally | Risks must be prioritized (sorted by probability x impact) |

---

## Active Recall Questions

1. What are the two essential characteristics of any risk?
2. What is the difference between a risk, a problem, and a constraint?
3. Write the risk exposure formula and explain each term.
4. List the five steps of the Risk Management Paradigm in order.
5. What are the seven principles of risk management?
6. Name the seven risk categories used in risk identification.
7. What is the difference between generic risks and product-specific risks?
8. List the four risk projection steps.
9. What are the four risk components? (Performance, Cost, Support, Schedule)
10. What is the difference between reactive and proactive risk management?
11. What is risk retention and when would you use it?
12. What does RMMM stand for and what does each part involve?
13. Describe the impact levels: Catastrophic, Critical, Marginal, Negligible.
14. What is risk refinement and why is it important?
15. How does the number of negative responses to the risk questionnaire relate to project risk?

---

## Potential Exam Questions

1. **Calculation**: A risk has a 65% probability of occurring. If it occurs, the cost will be $45,000. What is the risk exposure (RE)?

2. **Short answer**: Explain the difference between "Mitigation" and "Management" in the context of RMMM.

3. **Scenario**: Your team is building a mobile app using a new cross-platform framework that no one on the team has used before. Which risk categories are relevant? Describe at least three specific risks.

4. **Compare/Contrast**: Compare reactive and proactive risk management strategies. When might a reactive approach be acceptable?

5. **List/Describe**: List the seven principles of risk management and explain why "Encourage open communication" is critical.

6. **Application**: Given a risk table with five risks, show how you would sort it, identify which risks need an RMMM plan, and explain why.

7. **Diagram**: Draw the Risk Management Paradigm cycle and explain what happens at each step.

8. **Essay**: "Risk management is more expensive than crisis management." Argue for or against this statement.

9. **Classification**: For each of the following, classify as Known, Predictable, or Unpredictable risk: (a) unrealistic delivery date, (b) past staff turnover patterns, (c) a new government regulation passed last night.

10. **Analysis**: A risk with P = 90% and C = $1,000 has RE = $900. Another risk has P = 10% and C = $100,000 has RE = $10,000. Which should you prioritize? Explain.

---

## Topic Summary

- **Risk** = uncertainty + loss. Not a problem, not a constraint.
- **Reactive** = wait for failure; **Proactive** = plan ahead (far better).
- **Seven Principles**: Global perspective, forward-looking, open communication, integrate, continuous process, shared vision, teamwork.
- **Paradigm**: Identify -> Analyze -> Plan -> Track -> Control (continuous cycle).
- **Seven Categories** for risk identification: Product size, Business impact, Customer characteristics, Process definition, Development environment, Technology, Staff.
- **Projection**: RE = P x C. Four steps: scale, delineate consequences, estimate impact, note accuracy.
- **Risk Table**: Risk Summary | Category | Probability | Impact | RMMM. Sorted by severity.
- **RMMM**: Mitigation (avoid/reduce), Monitoring (track), Management (contingency).
- **Refinement**: Dig deeper into causes as the project evolves.
- **Retention**: Low-risk items are kept but tracked; if they cross threshold, act.

**Bottom line**: The goal of risk management is not to eliminate all risk -- that is impossible. The goal is to know what the risks are, understand their potential impact, and have a plan ready. This turns uncertainty from a threat into a managed variable.