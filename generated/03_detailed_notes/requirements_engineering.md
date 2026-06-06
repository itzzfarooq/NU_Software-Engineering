# Requirements Engineering — Detailed Exam Notes

## Why Requirements Engineering Matters

Every software project begins with a fundamental question: *what should the system do?* Requirements engineering is the process of answering that question rigorously. Getting requirements right is critical — errors at this stage propagate through design, implementation, and testing, becoming exponentially more expensive to fix.

> **Instructor Emphasis:** The requirements engineering process is **iterative** — it is NOT linear. You cycle through phases, refining understanding with each pass.

---

## The Requirements Engineering Process

The requirements engineering process consists of three main sub-processes, connected in an iterative cycle:

```
┌──────────────────────────────────┐
│  Requirements Elicitation        │
│  and Analysis                    │◀──────────────────┐
└───────────────┬──────────────────┘                   │
                │                                       │
                ▼                                       │
┌──────────────────────────────────┐                   │
│  Requirements Specification      │───────┐           │
└───────────────┬──────────────────┘       │           │
                │                          │           │
                ▼                          ▼           │
┌──────────────────────────────────┐  ┌────────────────────────┐
│  System Descriptions             │  │  Requirements          │
│  (User & System Requirements)    │──│  Validation            │──┘
└───────────────┬──────────────────┘  └────────────────────────┘
                │
                ▼
┌──────────────────────────────────┐
│  Requirements Document           │
└──────────────────────────────────┘
```

**Key outputs at each stage:**

| Stage | Produces |
|---|---|
| Elicitation & Analysis | System descriptions (understanding of needs) |
| Specification | User and system requirements |
| Validation | Confirmed/validated requirements |
| Overall | **Requirements document** |

---

## Stage 1: Requirements Elicitation and Analysis

### What Happens Here?

This is the process of **discovering requirements** by working with stakeholders. The fundamental question is:

> *What do the system stakeholders require or expect from the system?*

### Stakeholder Involvement

Stakeholders are anyone who has a vested interest in the system:

| Stakeholder Type | Role in Elicitation |
|---|---|
| **End users** | Provide operational requirements — what they need to do their job |
| **Customers** | Define business requirements and priorities |
| **System managers** | Specify maintenance, monitoring, and operational constraints |
| **External regulators** | Define compliance and regulatory requirements |

### Techniques for Elicitation

| Technique | Description |
|---|---|
| **Interviews** | Direct conversations with stakeholders to understand needs |
| **Workshops** | Group sessions to resolve conflicts and build shared understanding |
| **Observation** | Watching users in their actual work environment |
| **Prototyping** | Building preliminary versions to elicit feedback |
| **Use cases / scenarios** | Describing how users interact with the system |

### Common Challenges

- **Stakeholders don't know what they want** until they see something
- **Conflicting requirements** from different stakeholder groups
- **Communication gaps** between technical and non-technical stakeholders
- **Implicit requirements** — things users assume but never articulate

> **Exam Tip:** Elicitation is about *listening and discovering*, not telling stakeholders what they need.

---

## Stage 2: Requirements Specification

### What Happens Here?

This is the process of **defining the requirements in detail** — turning what was learned during elicitation into precise, documented requirements.

### User Requirements vs. System Requirements

| Level | Description | Audience |
|---|---|---|
| **User requirements** | High-level statements of what the system should do, written in natural language | Customers, end users |
| **System requirements** | Detailed functional and non-functional specifications | Developers, testers |

### Functional vs. Non-Functional Requirements

| Type | Definition | Example |
|---|---|---|
| **Functional** | What the system *does* — specific behaviors, features, operations | "The system shall allow users to search for products by name" |
| **Non-functional** | How the system *performs* — constraints on operation and development | "The system shall respond to queries within 2 seconds" |

### Specification Formats

| Format | When Used |
|---|---|
| **Natural language** | Most common; accessible to all stakeholders |
| **Structured templates** | Standardized forms for consistency |
| **Formal specifications** | Mathematical notation for critical/safety systems |
| **Use cases** | Describing user-system interactions |

---

## Stage 3: Requirements Validation

### What Happens Here?

This is the process of **checking the validity of the requirements** — making sure they are correct, complete, consistent, and achievable.

> **Key Insight:** Validation checks requirements against reality. It answers: "Did we get the requirements right?"

### Validation Techniques

| Technique | How It Works |
|---|---|
| **Requirements reviews** | Systematic manual examination of requirements for errors |
| **Prototyping** | Building a model to validate user understanding |
| **Test-case generation** | Writing test cases from requirements to check completeness |
| **Automated analysis** | Using tools to check for inconsistencies |

### What Validation Checks For

| Criterion | Question |
|---|---|
| **Validity** | Does the system provide the functions users really need? |
| **Consistency** | Are there contradictory requirements? |
| **Completeness** | Are all required functions and constraints documented? |
| **Realism** | Can the requirements actually be implemented given constraints? |
| **Verifiability** | Can each requirement be tested? |

---

## The Iterative Nature

The most critical concept to understand is that requirements engineering is **iterative**, not sequential:

1. You begin with **rough elicitation** → producing initial understanding
2. You **specify** what you understand → producing a draft specification
3. You **validate** the specification → discovering gaps, conflicts, ambiguities
4. You go **back to elicitation** → filling gaps, resolving conflicts
5. Each cycle **refines** the requirements → building confidence

This cycle continues until the requirements are stable, validated, and agreed upon.

> **Instructor Emphasis:** Requirements engineering is an iterative, cyclical process — NOT a one-shot linear activity.

---

## The Requirements Document

The requirements document (also called the Software Requirements Specification — SRS) is the **final output** of the requirements engineering process.

### Purpose of the Requirements Document

| Purpose | Explanation |
|---|---|
| **Contractual basis** | Serves as the agreement between customer and developer |
| **System specification input** | Provides input to the design and implementation phases |
| **Validation basis** | Used to check that the system meets its requirements |
| **System evolution** | Reference for future maintenance and enhancement |

### Typical Structure of an Requirements Document

| Section | Content |
|---|---|
| **Introduction** | System purpose, scope, definitions |
| **User requirements** | High-level functional and non-functional requirements |
| **System requirements** | Detailed specifications |
| **System models** | Use case diagrams, data flow diagrams |
| **System interface** | User interfaces, hardware interfaces, software interfaces |
| **Glossary** | Definitions of terms |
| **Appendices** | Additional detail, prototypes, analysis data |

---

## Stakeholder Involvement Across the Process

| Process Stage | Primary Stakeholders | Their Role |
|---|---|---|
| **Elicitation** | End users, customers, domain experts | Provide information about needs and constraints |
| **Specification** | Analysts, developers | Translate needs into formal/informal requirements |
| **Validation** | All stakeholders | Review and confirm requirements are correct |
| **Document approval** | Project manager, customer | Sign off on final requirements |

> **Exam Tip:** Stakeholder involvement is not limited to elicitation — they participate throughout the entire requirements engineering process.

---

## Common Requirements Engineering Pitfalls

| Pitfall | Consequence |
|---|---|
| Assuming requirements are stable | Requirements change; plans become obsolete |
| Insufficient stakeholder involvement | Missing critical requirements |
| Conflicting requirements not resolved | Design compromises, user dissatisfaction |
| Requirements too vague | Cannot be implemented or tested |
| Ignoring non-functional requirements | System works but is too slow, insecure, or unusable |

---

## Exam Checklist

- [ ] Know the 3 stages of requirements engineering (elicitation & analysis, specification, validation)
- [ ] Understand the iterative nature — it is a cycle, not a sequence
- [ ] Know what the requirements document contains and its purpose
- [ ] Understand user requirements vs. system requirements
- [ ] Know the difference between functional and non-functional requirements
- [ ] Understand stakeholder involvement at each stage
- [ ] Know validation techniques (reviews, prototyping, test-case generation, automated analysis)
- [ ] Understand what validation checks for (validity, consistency, completeness, realism, verifiability)
