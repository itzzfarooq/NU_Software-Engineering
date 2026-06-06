# Software Process Models — Detailed Exam Notes

## What Is a Software Process?

A **software process** is a structured set of activities required to develop a software system. Every software process — regardless of methodology — involves four fundamental activities:

| Activity | Purpose |
|---|---|
| **Specification** | Defining what the system should do |
| **Design and Implementation** | Organizing and building the system |
| **Validation** | Checking that it meets the customer's real needs |
| **Evolution** | Changing the system in response to evolving requirements |

A **software process model** is an *abstract representation* of a process from a particular perspective. There is no single "right" process; in practice, most large systems incorporate elements from multiple models.

---

## Process Descriptions

When describing processes, we talk about activities and their ordering. Process descriptions may also include:

| Element | Definition |
|---|---|
| **Products** | The outcomes (artifacts) of a process activity |
| **Roles** | Reflect the responsibilities of the people involved |
| **Pre-conditions** | Statements that must be true *before* an activity begins |
| **Post-conditions** | Statements that are true *after* an activity completes or a product is produced |

> **Exam Tip:** Know that process descriptions go beyond just listing activities — they include products, roles, and pre/post-conditions.

---

## The Waterfall Model

### Overview

The Waterfall model is a **plan-driven** process with separate and distinct phases flowing sequentially downward, like a waterfall. Each phase must be completed before the next begins.

### Phases (in order)

```
┌─────────────────────────────────────┐
│  1. Requirements Definition         │
└──────────────┬──────────────────────┘
               ▼
┌─────────────────────────────────────┐
│  2. System and Software Design      │
└──────────────┬──────────────────────┘
               ▼
┌─────────────────────────────────────┐
│  3. Implementation & Unit Testing   │
└──────────────┬──────────────────────┘
               ▼
┌─────────────────────────────────────┐
│  4. Integration & System Testing    │
└──────────────┬──────────────────────┘
               ▼
┌─────────────────────────────────────┐
│  5. Operation and Maintenance       │
└─────────────────────────────────────┘
```

### Problems of the Waterfall Model

| Problem | Explanation |
|---|---|
| **Inflexible partitioning** | Difficult to respond to changing customer requirements once a phase is underway |
| **Stable requirements assumed** | Only appropriate when requirements are well-understood and changes will be limited |
| **Few business systems have stable requirements** | Most real-world systems face evolving needs |
| **Late delivery** | No working software is produced until late in the lifecycle |

### When to Use the Waterfall Model

- **Large systems engineering projects** developed at several sites
- The **plan-driven nature** helps coordinate work across distributed teams
- When requirements are **stable, well-understood**, and unlikely to change
- When **regulatory/compliance** documentation is mandatory

> **Instructor Emphasis:** The Waterfall model is mostly used for large system engineering projects where coordination across sites is critical.

---

## Incremental Development

### Overview

In incremental development, **specification, development, and validation are interleaved** — not sequential as in Waterfall. The system is developed as a series of versions (increments), each adding functionality.

```
┌─────────────────────┐
│  Outline Description │
└──────────┬──────────┘
           ▼
┌──────────────────────────────────────────────────────────────────┐
│                   Concurrent Activities                          │
│                                                                  │
│   Specification ◀────▶ Initial Version                          │
│        │                                                          │
│        ▼                                                          │
│   Development ◀────▶ Intermediate Versions                      │
│        │                                                          │
│        ▼                                                          │
│   Validation ◀────▶ Final Version                                │
└──────────────────────────────────────────────────────────────────┘
```

### Benefits

| Benefit | Explanation |
|---|---|
| **Reduced cost of change** | Less analysis and documentation needs to be redone compared to Waterfall |
| **Easier customer feedback** | Customers see demonstrations of working software and comment on progress |
| **Rapid delivery** | Useful software can be deployed to customers earlier than with Waterfall |

### Problems

| Problem | Explanation |
|---|---|
| **Process not visible** | Managers need regular deliverables; rapid development makes it costly to document every version |
| **System structure degrades** | Without refactoring, regular change corrupts the software structure, making further changes increasingly difficult and costly |

> **Instructor Emphasis:** System structure degradation is the key problem — refactoring is essential to maintain quality in incremental development.

---

## Reuse-Oriented / Integration and Configuration

### Overview

This model is based on **software reuse** where systems are assembled from existing components or COTS (Commercial Off-The-Shelf) systems. Reused elements may be configured to adapt behavior and functionality to user requirements.

### Types of Reusable Software

| Type | Description |
|---|---|
| **Stand-alone applications (COTS)** | Configured for use in a particular environment |
| **Component collections** | Packages designed for integration with frameworks like .NET or J2EE |
| **Web services** | Developed to service standards, available for remote invocation |

### Stages of the Reuse-Oriented Process

```
┌──────────────────────┐
│ Requirements          │
│ Specification         │──────────────┐
└──────────────────────┘              │
                                      ▼
                           ┌──────────────────────┐
                           │ Software Discovery    │
                           │ & Evaluation          │
                           └──────────┬───────────┘
                                      │
                                      ▼
                           ┌──────────────────────┐
                           │ Requirements          │
                           │ Refinement            │
                           └──────────┬───────────┘
                                      │
                      ┌───────────────┼───────────────┐
                      ▼               ▼               ▼
           ┌─────────────┐ ┌──────────────┐ ┌──────────────────┐
           │ Application  │ │  Components  │ │  Develop New     │
           │ System Avail │ │  Available   │ │  Components      │
           └──────┬──────┘ └──────┬───────┘ └────────┬─────────┘
                  ▼               ▼                   │
      ┌──────────────────┐ ┌──────────────┐          │
      │ Configure App    │ │   Adapt      │          │
      │ System           │ │  Components  │          │
      └────────┬─────────┘ └──────┬───────┘          │
               │                  │                   │
               ▼                  ▼                   ▼
           ┌────────────────────────────────────────────┐
           │          Integrate System                   │
           └────────────────────────────────────────────┘
```

**Key stages:**

1. **Requirements specification** — Define what the system should do
2. **Software discovery and evaluation** — Find existing components/COTS
3. **Requirements refinement** — Adjust requirements to match available software
4. **Configuration / Adaptation / Development** — Configure, adapt, or build new components
5. **Integration** — Assemble everything into the final system

### Advantages and Disadvantages

| Advantages | Disadvantages |
|---|---|
| Reduced costs and risks — less software developed from scratch | **Requirements compromises are inevitable** — system may not meet real user needs |
| Faster delivery and deployment | **Loss of control** over evolution of reused system elements |

> **Instructor Emphasis:** Requirements compromises and loss of control are the two critical disadvantages to remember for exams.

---

## Plan-Driven vs. Agile: The Spectrum

| Aspect | Plan-Driven | Agile |
|---|---|---|
| **Planning** | All activities planned in advance; progress measured against plan | Planning is incremental; easier to change the process |
| **Requirements** | Captured upfront, documented thoroughly | Evolve continuously through customer collaboration |
| **Change** | Difficult to accommodate once process is underway | Expected and embraced |
| **Documentation** | Comprehensive | Minimal — focus on working code |
| **Delivery** | Late delivery of working software | Frequent delivery of increments |
| **Customer involvement** | At milestones (requirements, reviews) | Full-time engagement throughout |

> **Key Insight:** In practice, most practical processes include elements of **both** plan-driven and agile approaches. There are no absolute right or wrong processes.

---

## Quick Reference: Three Models at a Glance

| Model | Nature | When to Use | Key Risk |
|---|---|---|---|
| **Waterfall** | Plan-driven, sequential phases | Stable requirements, large distributed projects | Cannot accommodate change easily |
| **Incremental** | Interleaved spec/dev/validation | Evolving requirements, need for rapid delivery | Structure degradation without refactoring |
| **Reuse-oriented** | Assemble from existing components | Business systems, COTS-based development | Requirements compromises, loss of control |

---

## Exam Checklist

- [ ] Know the 4 basic process activities (specification, design/implementation, validation, evolution)
- [ ] Understand what products, roles, and pre/post-conditions mean in process descriptions
- [ ] Waterfall: 5 phases, problems, when to use
- [ ] Incremental: benefits and problems (especially structure degradation)
- [ ] Reuse-oriented: 5 stages, 3 types of reusable software, advantages/disadvantages
- [ ] Plan-driven vs. agile: key differences
- [ ] Most large systems use elements from all three models
