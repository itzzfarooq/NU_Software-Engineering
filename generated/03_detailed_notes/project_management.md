# Chapter 22 - Project Management — Detailed Notes

---

## Topic Overview

Software project management is the discipline of planning, organizing, and controlling software projects so that they are delivered **on time**, **within budget**, and **meet customer expectations**. Unlike construction or manufacturing, software is intangible — you cannot "see" progress by looking at a physical artifact. This makes software project management uniquely challenging.

The chapter covers three universal management activities: **project planning**, **risk management**, and **people management**, with special emphasis on risk classification, the risk management process, teamwork, and group communication.

---

## Why This Topic Exists

Software development always operates under **budget and schedule constraints** set by the organization. Without active management, projects routinely exceed budgets, miss deadlines, and fail to satisfy customers. Project management provides the structure needed to:

- Coordinate people and tasks
- Anticipate and mitigate problems before they derail the project
- Keep stakeholders informed
- Ensure the team remains productive and motivated

---

## Core Concepts & Definitions

| Concept | Definition |
|---|---|
| **Software Project Management** | Activities ensuring software is delivered on time, on schedule, and according to requirements. |
| **Success Criteria** | (1) Deliver at agreed time, (2) Keep costs within budget, (3) Meet customer expectations, (4) Maintain a well-functioning team. |
| **Intangible Product** | Software cannot be seen/touched; progress cannot be measured by inspecting a physical artifact. |
| **One-off Projects** | Large software projects are usually different from previous ones, making past experience an unreliable guide. |
| **Variable Processes** | Software processes are organization-specific; we cannot reliably predict when a process will cause problems. |

### Factors Influencing Project Management

| Factor | Impact |
|---|---|
| Company size | Small vs. large companies manage differently |
| Software customers | Internal vs. external customers change dynamics |
| Software size | Larger systems need more formal management |
| Software type | Safety-critical, web, embedded — each demands different approaches |
| Organizational culture | Hierarchical vs. flat organizations influence style |
| Software development processes | Agile vs. plan-driven require different management |

---

## Key Management Activities

### 1. Project Planning
Managers are responsible for planning, estimating, scheduling development, and assigning people to tasks. This includes writing **proposals** to win contracts and defining project objectives. (Covered in depth in Chapter 23.)

### 2. Reporting
Project managers report progress to customers and to the organization's senior management. Regular reporting keeps stakeholders aligned and enables early intervention when problems arise.

### 3. Risk Management
The practice of identifying potential risks and drawing up plans to minimize their effect on the project. Because software development is full of uncertainties (vague requirements, changing needs, estimation difficulties, varying skill levels), risk management is critical.

### 4. People Management
Selecting the right people for the team and establishing ways of working that lead to effective team performance. Good people management is *more important* than managing technology — motivated, experienced staff can solve any problem.

#### Teamwork Essentials
- Teams achieve more than individuals working alone
- Groups are more reliable at repetitive tasks
- BUT groups are expensive due to coordination and communication overhead
- Effective teamwork requires: understanding the work, organizing work properly, shared understanding, mutual trust, and conflict resolution skills
- Successful teams share a **common vision**; the team leader shapes culture by example, promoting openness and transparency

#### Group Communication
- **Formal**: Document-based (email), regular meetings, milestone reviews
- **Informal**: Ad-hoc conversations, shared repositories, instant messaging
- Communication depends on: team size, organizational structure, physical location (distributed teams face more challenges), and nature of the work
- **Virtual teams**: Geographically dispersed teams that may never meet physically — advantages (access to global specialists, reduced travel) vs. disadvantages (communication problems, cultural differences, reduced cohesion)

| System Type | Team Size | Team Structure |
|---|---|---|
| Personal systems | 1-3 people | Informal communications |
| Small system | Up to 10 people | Regular formal meetings; close coordination |
| Application system | Up to 30 people | Informal communications |
| Large system | Up to 100+ people | Sub-teams and task groups; formal communications |

---

## Risk Classification

Risks are classified along two dimensions: **type of risk** (technical, organizational, people, etc.) and **what is affected**.

| Risk Category | What It Affects | Examples |
|---|---|---|
| **Project risks** | Schedule or resources | Staff turnover, management change, hardware unavailability, size underestimate |
| **Product risks** | Quality or performance of the software | CASE tool underperformance, defective reusable components |
| **Business risks** | The organization developing or procuring the software | Technology change, product competition |

### Combined Effects
Some risks affect **both** project and product:
- Requirements change
- Specification delays
- Size underestimate

---

## Risk Management Process (4-Step Cycle)

```
Risk Identification → Risk Analysis → Risk Planning → Risk Monitoring
       ↓                    ↓                 ↓                  ↓
List of potential    Prioritized risk    Risk avoidance &    Risk assessment
risks                list                contingency plans   (ongoing)
```

### Step 1: Risk Identification
Identify project, product, and business risks. Can be a team activity or individual. Use a **checklist** of common risk types:

| Risk Type | Examples |
|---|---|
| **Estimation** | Time underestimated, defect repair rate underestimated, size underestimated |
| **Organizational** | Restructuring, financial problems forcing budget cuts |
| **People** | Cannot recruit required staff, key staff ill, training unavailable |
| **Requirements** | Major rework from changes, customers misunderstanding impact |
| **Technology** | Database performance inadequate, defective reusable components |
| **Tools** | Code generation inefficient, tools cannot integrate |

### Step 2: Risk Analysis
Assess the **probability** (very low / low / moderate / high / very high) and **seriousness** (catastrophic / serious / tolerable / insignificant) of each risk.

| Risk | Probability | Effects |
|---|---|---|
| Organizational financial problems (budget cuts) | Low | Catastrophic |
| Cannot recruit required staff | High | Catastrophic |
| Key staff ill at critical times | Moderate | Serious |
| Defective reusable components | Moderate | Serious |
| Requirements changes requiring major rework | Moderate | Serious |
| Organizational restructuring | High | Serious |
| Database performance inadequate | Moderate | Serious |
| Underestimated development time | High | Serious |
| Tools cannot integrate | High | Tolerable |
| Customers misunderstand impact of changes | Moderate | Tolerable |
| Training unavailable | Moderate | Tolerable |
| Defect repair rate underestimated | Moderate | Tolerable |
| Size underestimated | High | Tolerable |
| Inefficient code generation | Moderate | Insignificant |

### Step 3: Risk Planning
Develop a strategy for each risk. Three types of strategies:

| Strategy | Goal | Example |
|---|---|---|
| **Avoidance** | Reduce *probability* of the risk arising | Reorganize team so work overlaps (reduces illness impact) |
| **Minimization** | Reduce the *impact* if the risk occurs | Replace defective components with known reliable ones |
| **Contingency** | Plan to *deal with* the risk if it happens | Pre-buy higher-performance database as backup |

#### Example Strategies by Risk

| Risk | Strategy |
|---|---|
| Organizational financial problems | Prepare briefing document showing project's business importance |
| Recruitment problems | Alert customer; investigate buying-in components |
| Staff illness | Reorganize team for work overlap so people understand each other's roles |
| Defective components | Replace with bought-in components of known reliability |
| Requirements changes | Derive traceability info; maximize information hiding in design |
| Organizational restructuring | Brief senior management on project's strategic value |
| Database performance | Investigate buying a higher-performance database |
| Underestimated development time | Investigate buying-in components or using a program generator |

### Step 4: Risk Monitoring
Regularly re-assess each identified risk to determine whether its **probability** or **effects** have changed. Each key risk should be discussed at management progress meetings.

#### "What If?" Questions (Scenario Thinking)
- What if several engineers are ill at the same time?
- What if an economic downturn leads to 20% budget cuts?
- What if the only expert on critical OSS leaves and the software's performance is inadequate?
- What if the component supplier goes out of business?
- What if the customer fails to deliver revised requirements on time?

---

## Relationships

```
                      ┌─────────────────────┐
                      │  Project Management │
                      └──────┬──────┬───────┘
                             │      │
              ┌──────────────┘      └──────────────┐
              ↓                                     ↓
      ┌───────────────┐                   ┌─────────────────┐
      │ Risk Mgmt     │                   │  People Mgmt    │
      │ (4-step cycle)│                   │ (motivation,    │
      │               │                   │  teamwork,      │
      │ • Identification                 │  communication) │
      │ • Analysis     │                   │                 │
      │ • Planning     │                   └─────────────────┘
      │ • Monitoring   │
      └───────────────┘
```

- **Risk Analysis feeds Risk Planning**: Only once you know probability and severity can you choose avoidance, minimization, or contingency.
- **Risk Monitoring feeds back into Identification**: New risks can emerge mid-project; monitoring may reveal previously missed risks.
- **Good People Management reduces People risks**: Motivated, well-trained, overlapping teams are less susceptible to staff illness, turnover, and low productivity.
- **Team size determines Communication approach**: Small teams can use informal methods; large or distributed teams need formal communication and shared repositories.

---

## Examples

**Example 1: Staff Illness (Moderate probability, Serious effect)**
- *Avoidance strategy*: Cross-train team members so work overlaps.
- *Contingency*: Have a backup plan for critical deliverables.

**Example 2: Requirements Changes (Moderate probability, Serious effect)**
- *Minimization strategy*: Maximize information hiding in design so changes are isolated.
- *Contingency*: Use traceability matrices to assess impact of each change quickly.

**Example 3: Underestimated Development Time (High probability, Serious effect)**
- *Minimization*: Investigate buying components instead of building from scratch.
- *Contingency*: Use a program generator to accelerate coding.

**Example 4: Distributed Virtual Team**
- *Formal communication*: Regular milestone reviews, email, video conferencing.
- *Informal*: Instant messaging, shared repositories (Git, shared docs).
- *Key challenge*: Cultural differences, coordination overhead, reduced cohesion.

---

## Common Mistakes / Exam Traps

1. **Confusing project, product, and business risks** — Remember: *Project* = schedule/resources, *Product* = quality/performance, *Business* = organization impact.
2. **Mixing up avoidance vs. minimization vs. contingency** — Avoidance *reduces probability*; minimization *reduces impact*; contingency *handles it after it occurs*.
3. **Forgetting that software is intangible** — You cannot measure progress by "looking at the product" like a building.
4. **Assuming one-off means "never done before"** — It means each large project has enough unique aspects that past experience only partially transfers.
5. **Treating risk management as a one-time activity** — It is a continuous cycle: identify → analyze → plan → monitor → re-identify.
6. **Believing large teams are always better** — Large teams require formal communication, incur overhead, and need sub-teams.
7. **Thinking technology management is more important than people management** — The text explicitly states people management is *more important*.
8. **Ignoring "what-if" scenario planning** — Exams love asking you to generate risk strategies from scenario questions.

---

## Active Recall Questions

1. What are the four success criteria for a software project?
2. List the three universal management activities described in this chapter.
3. What are the three categories of risk, and what does each affect?
4. Name the four steps of the risk management process in order.
5. What is the difference between an avoidance strategy and a contingency plan?
6. Give an example of a risk with high probability and catastrophic effects.
7. What factors influence group communication effectiveness?
8. What are the advantages and disadvantages of virtual teams?
9. Why is managing people considered more important than managing technology?
10. What team size triggers the need for formal communication?

---

## Potential Exam Questions

1. **Explain** the three distinctions that make software project management different from management in other engineering disciplines.

2. **Compare and contrast** project risks, product risks, and business risks. Provide two examples of each.

3. **Describe** the four-stage risk management process. For each stage, state what output is produced.

4. **A project depends on a single expert for a critical open-source component. The expert may leave, and the OSS performance may be inadequate.** Identify the risk category, assess its probability and effects, and propose one avoidance, one minimization, and one contingency strategy.

5. **Discuss** the relationship between team size and communication approach. Use the system type / team size table in your answer.

6. **Evaluate** the statement: "Technology management is the most critical success factor in software projects." Use material from this chapter to support or refute it.

7. **A large system requires a team of 100+ developers spread across three countries.** What communication challenges will arise? What tools and practices should the project manager adopt?

---

## Topic Summary

- **Project management** ensures on-time, on-budget delivery that meets customer expectations. Software's intangibility, one-off nature, and process variability make it uniquely challenging.
- **Risk management** follows a 4-step cycle: identification → analysis → planning → monitoring. Risks are classified as project, product, or business risks. Strategies are avoidance (reduce probability), minimization (reduce impact), and contingency (deal with it if it happens).
- **People management** is the most important factor. Good managers motivate staff, organize effective teams, and foster a culture of trust and openness.
- **Teamwork** requires shared vision, proper communication (formal/informal depending on size and distribution), and effective conflict resolution.
- **Group communication** depends on team size, location, organizational structure, and work nature. Virtual teams offer flexibility but face coordination and cultural challenges.