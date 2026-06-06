# Software Engineering Introduction — Detailed Exam Notes

## What Is Software Engineering, Really?

Every economy depends on software. Your phone, your bank, your university's enrollment system, the traffic lights on your way to class — all software-controlled. Software engineering is the discipline that makes building these systems possible, predictable, and economically viable. Without it, we'd still be writing personal programs that work on one machine and break on another. With it, we build systems that millions rely on every day.

The key insight: **software costs more to maintain than to develop**. For systems with a long lifespan, maintenance costs can be several times the original development cost. This single fact drives almost every software engineering practice — if building software is cheap but changing it is expensive, then every decision we make during development must account for future change.

---

## Why Does Software Engineering Exist?

Software projects fail. Not occasionally — frequently. The two main reasons:

1. **Increasing complexity** — systems are larger, more distributed, and more interconnected than ever. New techniques help us build bigger systems, but the demands grow faster than our ability.

2. **Failure to use engineering methods** — it's easy to write programs without software engineering. Many companies drifted into software development without formal methods. Their software is more expensive and less reliable than it should be.

> **Key Insight:** Software engineering exists because personal programming techniques don't scale to professional, team-based, long-lived systems.

---

## What Is Software?

Software has two components:

| Component | Description |
|-----------|-------------|
| **Computer programs** | The executable code that runs on hardware |
| **Associated documentation** | Requirements docs, design docs, user manuals, API references |

Software products come in two flavors:

| Type | Description | Example | Specification Owner |
|------|-------------|---------|-------------------|
| **Generic products** | Stand-alone systems marketed and sold to any buyer | MS Word, Photoshop, CAD software | Developer owns spec; developer decides changes |
| **Customized (bespoke) products** | Commissioned by a specific customer for their specific needs | Air traffic control, embedded systems, hospital management | Customer owns spec; customer decides changes |

> **Exam Tip:** Know who owns the specification for generic vs. customized products. This is a classic MCQ question.

---

## Attributes of Good Software

Five essential attributes define whether software is "good":

| Attribute | What It Means | Why It Matters |
|-----------|---------------|----------------|
| **Maintainability** | Software can evolve to meet changing needs | Change is inevitable; if software can't change, it becomes obsolete |
| **Dependability** | Includes reliability, security, safety — software shouldn't cause physical/economic damage or be vulnerable to malicious users | Users must trust the software with their data and safety |
| **Efficiency** | Doesn't wastefully use memory, processor cycles, or resources | Performance, responsiveness, memory utilization |
| **Usability** | Easy to learn, use, and understand | If users can't use it, the software fails regardless of technical quality |
| **Acceptability** | Must be understandable, usable, and compatible with other systems the user has | Software that doesn't fit the user's ecosystem gets rejected |

> **Instructor Emphasis:** Maintainability is arguably the most important because maintenance is the most expensive phase. A system that can't be maintained is a system with an expiration date.

---

## Software Engineering — The Formal Definition

> "Software engineering is an engineering discipline that is concerned with all aspects of software production from the early stages of system specification through to maintaining the system after it has gone into use."

Breaking this down:

- **Engineering discipline** — uses appropriate theories and methods to solve problems, while respecting organizational and financial constraints
- **All aspects of software production** — not just coding. Includes project management, tool development, methods, and support processes
- **From specification to maintenance** — covers the entire lifecycle, not just the development phase

### How SE Differs from Related Fields

| Field | Focus | SE's Relationship |
|-------|-------|-------------------|
| **Computer Science** | Theory and fundamentals | SE applies CS theory to practical software development |
| **System Engineering** | All aspects of computer-based systems (hardware, software, process) | SE is part of the broader system engineering process |

---

## The Four Fundamental Activities

Every software process — regardless of methodology — involves four activities:

| Activity | What Happens | Who's Involved |
|----------|-------------|----------------|
| **Specification** | Define what the system should do and the constraints on its operation | Customers and engineers together |
| **Development** | Design and program the system | Development team |
| **Validation** | Check that the software meets what the customer requires | Testing team, QA, customers |
| **Evolution** | Modify the software in response to changing requirements | Maintenance team, with customer input |

```
Specification ──▶ Development ──▶ Validation ──▶ Evolution
                                                    │
                                                    └──▶ (Back to Specification — the cycle continues)
```

> **Key Insight:** These activities are not strictly sequential. In practice, they overlap and iterate. But understanding them as distinct activities helps organize the work.

---

## Application Types — The Software Spectrum

Software systems come in many forms. Each type has different engineering challenges:

| # | Application Type | Description | Example |
|---|-----------------|-------------|---------|
| 1 | **Stand-alone applications** | Run on a local computer, no network needed | MS Word, Photoshop |
| 2 | **Interactive transaction-based** | Execute on remote server, accessed from user's device | E-commerce, banking apps |
| 3 | **Embedded control systems** | Control and manage hardware devices | Car engine control, microwave |
| 4 | **Batch processing systems** | Process data in large batches, input → output | Payroll, billing systems |
| 5 | **Entertainment systems** | Primarily for personal entertainment | Games, streaming apps |
| 6 | **Systems for modeling & simulation** | Model physical processes with interacting objects | Weather simulation, engineering models |
| 7 | **Data collection systems** | Collect data from environment using sensors | IoT sensors, monitoring systems |
| 8 | **Systems of systems** | Composed of multiple other software systems | Smart city infrastructure |

> **Exam Tip:** Know at least 5-6 application types with examples. MCQ questions often ask "which type of system is X?"

---

## General Issues Affecting Software

Four challenges shape modern software engineering:

| Challenge | Description | Impact on SE |
|-----------|-------------|-------------|
| **Heterogeneity** | Systems must operate across diverse networks with different computer and mobile device types | Requires portable, interoperable designs |
| **Business & social change** | Emerging economies and new technologies force rapid software adaptation | Need for agile, responsive development |
| **Security & trust** | Software is intertwined with all aspects of life; users must trust it | Security-by-design, encryption, access control |
| **Scale** | Software ranges from tiny embedded devices to Internet-scale cloud systems | Different engineering approaches for different scales |

---

## Software Engineering Fundamentals

Four principles apply to **all** types of software systems:

1. **Managed development process** — systems should be developed using a controlled, understood process (different processes for different types, but always a process)
2. **Dependability and performance** — critical for all systems, regardless of type
3. **Requirements management** — understanding and controlling what the software should do
4. **Software reuse** — when appropriate, reuse existing software rather than writing new code from scratch

> **Instructor Emphasis:** These fundamentals are universal. Whether you're building a game or a medical device, these four principles always apply.

---

## Web-Based Software Engineering

The web changed everything about how we build software:

| Aspect | Traditional | Web-Based |
|--------|-------------|-----------|
| **Platform** | Local machine | Distributed, cloud-based |
| **Distribution** | Physical media or local network | Internet |
| **Reuse** | Component libraries | Web services, APIs, microservices |
| **Development approach** | Often plan-driven | Almost always incremental/agile |
| **Delivery** | Periodic releases | Continuous deployment |

Key web SE concepts:
- **Software reuse** is the dominant approach — assemble from pre-existing components
- **Incremental and agile development** — impractical to specify everything upfront for web systems

---

## Ethical and Professional Responsibilities

Software engineers have responsibilities to:

| Responsibility | To Whom |
|----------------|---------|
| **Public** | Act consistently with the public interest |
| **Client & Employer** | Act in their best interest, consistent with public interest |
| **Product** | Ensure products meet the highest professional standards |
| **Judgment** | Maintain integrity and independence |
| **Management** | Promote ethical approaches to development |
| **Profession** | Advance the integrity and reputation of the profession |
| **Colleagues** | Be fair and supportive |
| **Self** | Participate in lifelong learning |

### ACM/IEEE Code of Ethics — 8 Principles

| # | Principle | One-Line Summary |
|---|-----------|-----------------|
| 1 | **PUBLIC** | Act in the public interest |
| 2 | **CLIENT AND EMPLOYER** | Serve client/employer, but not at public's expense |
| 3 | **PRODUCT** | Ensure products meet professional standards |
| 4 | **JUDGMENT** | Maintain professional judgment integrity |
| 5 | **MANAGEMENT** | Lead ethically |
| 6 | **PROFESSION** | Advance the profession |
| 7 | **COLLEAGUES** | Be fair and supportive to peers |
| 8 | **SELF** | Continuous learning |

> **Exam Tip:** You don't need to memorize all 8 word-for-word, but know the key ones: PUBLIC, CLIENT/EMPLOYER, PRODUCT, JUDGMENT. These appear in MCQ and short-answer questions.

---

## Relationships to Other Topics

This introductory topic connects to everything else in the course:

- **Software Processes** (Topic 2) — the four activities (specification, development, validation, evolution) are implemented through specific process models
- **Agile** (Topic 3) — agile methods are one approach to carrying out the four activities
- **Testing** (Topic 4) — validation is one of the four activities; testing is how we perform it
- **Quality Management** (Topic 11) — the attributes of good software (maintainability, dependability, etc.) are the quality goals we design for
- **Estimation** (Topic 7) — understanding that maintenance costs exceed development costs drives estimation practices
- **Ethics** — the ACM/IEEE code appears in multiple contexts throughout the course

---

## Common Mistakes

| Mistake | Correction |
|---------|------------|
| Thinking SE is just programming | SE covers the entire lifecycle — specification, design, testing, maintenance, project management |
| Confusing generic and custom software specification ownership | Generic = developer owns; Custom = customer owns |
| Thinking the four activities are strictly sequential | They overlap and iterate in practice |
| Assuming all software has the same engineering needs | Different application types require different approaches |

---

## Exam Traps

| Trap | Why It's Tricky | Correct Answer |
|------|----------------|----------------|
| "Software engineering is the same as computer science" | CS focuses on theory; SE focuses on practical delivery | SE is an engineering discipline applied to software production |
| "Generic products have customer-owned specs" | Students confuse who initiates the product | Developer owns the spec for generic products |
| "Maintenance is the cheapest phase" | Feels intuitive since it's "just fixing bugs" | Maintenance is the most expensive phase, often 2-3x development cost |
| "All software requires the same development approach" | One-size-fits-all thinking | Different types need different methods (games vs. safety-critical systems) |

---

## Active Recall Questions

1. Define software engineering in one sentence.
2. What are the two components of "software"?
3. List the five essential attributes of good software.
4. What is the difference between generic and customized software products?
5. Who owns the specification for generic products? For customized products?
6. Name the four fundamental software engineering activities.
7. Why is software maintenance more expensive than development?
8. List eight application types of software systems.
9. What are the four general issues affecting software?
10. Name the four software engineering fundamentals.
11. What is the difference between software engineering and computer science?
12. List four principles from the ACM/IEEE Code of Ethics.

---

## Potential Exam Questions

1. **Short answer:** Explain why software maintenance is typically more expensive than initial development.
2. **Comparison:** Differentiate between generic and customized software products, including who owns the specification in each case.
3. **List:** Name and briefly describe the four fundamental activities of a software process.
4. **Essay:** Why is software engineering necessary? Discuss with reference to project failure and increasing complexity.
5. **Application:** A hospital wants to build a patient management system. What type of application is this, and what special considerations apply?
6. **Ethics:** A client asks you to hide a security vulnerability in their software. Which ACM/IEEE principles apply?

---

## Topic Summary

Software engineering is the engineering discipline concerned with all aspects of software production — from specification through maintenance. It exists because personal programming techniques don't scale to professional, team-based systems. Good software is maintainable, dependable, efficient, usable, and acceptable. Every software process involves four activities: specification, development, validation, and evolution. Software comes in many application types, each with different engineering challenges. The field is shaped by four general issues: heterogeneity, business change, security, and scale. Four fundamentals apply universally: managed processes, dependability/performance, requirements management, and software reuse. The ACM/IEEE Code of Ethics provides eight principles for professional conduct. Understanding this foundation is essential because every other topic in this course builds on these concepts.
