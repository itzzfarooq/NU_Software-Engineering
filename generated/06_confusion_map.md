# Software Engineering - Confusion Map

Commonly confused concepts, misunderstandings, and exam traps organized by topic.

---

## 1. Software Process Models

### Verification vs Validation
| Confusion | Clarification |
|-----------|---------------|
| Thinking they mean the same thing | **Verification**: "Are we building the product right?" (conforms to spec). **Validation**: "Are we building the right product?" (meets user needs) |
| Assuming V&V only happens at the end | V&V activities occur throughout the entire development lifecycle |
| Confusing static vs dynamic V&V | Static = reviews/walkthroughs (no execution). Dynamic = testing (execution required) |

**Exam Trap**: A question asks "Did we build the right product?" — the answer is **Validation**, not Verification.

### Waterfall vs Incremental
| Confusion | Clarification |
|-----------|---------------|
| Thinking waterfall is always bad | Waterfall works well when requirements are stable, well-understood, and unlikely to change |
| Assuming incremental = Agile | Incremental is a delivery strategy. Agile is a philosophy with values/practices. Incremental can exist outside Agile |
| Thinking you can go back in waterfall | True waterfall is sequential and non-iterative (though in practice some backtracking occurs) |
| Confusing incremental with iterative | **Incremental**: deliver pieces progressively. **Iterative**: refine/improve the whole through repeated cycles |

### Spiral Model
| Confusion | Clarification |
|-----------|---------------|
| Thinking spiral is just another waterfall | Spiral is risk-driven and iterative; each cycle involves risk analysis |
| Assuming all projects should use spiral | Spiral is expensive — best for large, high-risk projects, not small ones |
| Confusing risk analysis with testing | Risk analysis in spiral identifies what *could* go wrong; testing verifies what *has been built* |

### V-Model
| Confusion | Clarification |
|-----------|---------------|
| Thinking V-model = Waterfall with testing added | V-model explicitly maps each development phase to a corresponding test level (requirements → acceptance, design → integration, etc.) |
| Assuming testing only happens at the right side | Test planning/Design starts during the corresponding left-side phase |

---

## 2. Requirements Engineering

### Functional vs Non-Functional Requirements
| Confusion | Clarification |
|-----------|---------------|
| Thinking non-functional = quality attributes only | Non-functional includes constraints, standards compliance, performance, security, usability, etc. |
| Assuming functional requirements cover everything | Functional = *what* the system does. Non-functional = *how well* or *under what conditions* |
| Confusing a specific non-functional requirement with a quality attribute | "Response time < 2s" is a non-functional requirement; "Performance" is the quality attribute |

### Requirements Elicitation Techniques
| Confusion | Clarification |
|-----------|---------------|
| Confusing interviews with observation | Interviews = ask questions. Observation = watch users work (ethnography) |
| Thinking prototyping is a requirements *document* | Prototyping is an elicitation technique; the output is a prototype, not a specification |
| Assuming all techniques work equally well | Different techniques suit different stakeholders and project contexts |

### Requirements Validation
| Confusion | Clarification |
|-----------|---------------|
| Confusing validation with verification | Requirements Validation = "Did we capture the right requirements?" Requirements Verification = "Are the requirements consistent and complete?" |
| Thinking requirements validation = testing | Validation happens *before* implementation (reviews, prototyping, test-case generation) |

---

## 3. Design Principles

### Coupling vs Cohesion
| Confusion | Clarification |
|-----------|---------------|
| Thinking high coupling is good | High coupling = bad (modules depend heavily on each other). Low coupling = good (modules are independent) |
| Thinking low cohesion is good | Low cohesion = bad (module does many unrelated things). High cohesion = good (module has a focused purpose) |
| Reversing the "good/bad" directions | **Coupling**: want LOW. **Cohesion**: want HIGH. This is the #1 exam mistake |
| Confusing data coupling with content coupling | Data coupling = modules share data via parameters (best). Content coupling = one module modifies another's internal data (worst) |

**Exam Trap**: "Which is desirable?" — Coupling should be **low**, Cohesion should be **high**.

### Information Hiding
| Confusion | Clarification |
|-----------|---------------|
| Confusing with abstraction | Abstraction = hiding complexity by showing only essential features. Information hiding = hiding implementation details within modules |
| Thinking it only applies to OOP | Information hiding applies to all module-based designs |

### MVC (Model-View-Controller)
| Confusion | Clarification |
|-----------|---------------|
| Confusing Model with View | Model = data and business logic. View = user interface/presentation |
| Thinking MVC is a process model | MVC is an architectural pattern, not a development process |

---

## 4. Software Architecture

### Architecture vs Design
| Confusion | Clarification |
|-----------|---------------|
| Thinking they are the same | Architecture = high-level structure, component relationships, constraints. Design = detailed decisions within architectural constraints |
| Assuming architecture decisions are easily reversible | Architectural decisions are expensive to change later |

### Pattern Types
| Confusion | Clarification |
|-----------|---------------|
| Confusing architectural patterns with design patterns | Architectural patterns = system-wide structure (MVC, layered, client-server). Design patterns =局部 solutions (Observer, Factory, Singleton) |
| Thinking all patterns apply at the same level | Some patterns are architectural (large-scale), some are design (class-level), some are implementation (code-level) |

---

## 5. Testing

### White-box vs Black-box vs Gray-box
| Confusion | Clarification |
|-----------|---------------|
| Thinking white-box = testing by developers only | White-box = test based on internal structure/code. Black-box = test based on specifications only |
| Assuming gray-box is the most common | Gray-box (knowledge of internals but testing from outside) is practical but often unmentioned in exams |
| Confusing structural testing with functional testing | White-box = structural (code coverage). Black-box = functional (spec coverage) |

### Testing Levels
| Confusion | Clarification |
|-----------|---------------|
| Confusing unit vs integration testing | Unit = individual components. Integration = combined components working together |
| Thinking system testing = acceptance testing | System testing = verify the complete system against requirements. Acceptance testing = customer validates it meets their needs |
| Assuming regression testing is a level | Regression testing is an activity performed *at any level* to ensure changes haven't broken existing functionality |
| Confusing alpha vs beta testing | Alpha = internal (in-house). Beta = external (real users in real environment) |

### Testing Strategies
| Confusion | Clarification |
|-----------|---------------|
| Confusing top-down with bottom-up | Top-down = test from main module downward (uses stubs). Bottom-up = test from lowest modules upward (uses drivers) |
| Thinking smoke testing is thorough | Smoke testing = quick check that core functionality works (sanity check) |

---

## 6. Metrics & Effort Estimation

### LOC vs FP
| Confusion | Clarification |
|-----------|---------------|
| Thinking LOC is language-independent | LOC is language-**dependent**. FP is language-**independent** |
| Assuming FP eliminates all bias | FP still requires subjective judgment in counting function types |
| Confusing LOC as a productivity metric | More LOC ≠ better. LOC measures size, not quality or productivity directly |

### COCOMO
| Confusion | Clarification |
|-----------|---------------|
| Confusing effort with duration | Effort = person-months. Duration = calendar time. They are related but different |
| Thinking COCOMO replaces estimation | COCOMO provides estimates; human judgment and calibration are still needed |
| Confusing the three COCOMO levels | Basic = simple formula. Intermediate = cost drivers. Detailed = phase-level adjustments |

### Risk Exposure
| Confusion | Clarification |
|-----------|---------------|
| Confusing risk exposure with probability | Risk Exposure = Probability × Impact (both must be considered) |
| Thinking only high-probability risks matter | High-impact, low-probability risks can also be critical (black swan events) |

---

## 7. Configuration Management & Change Control

### CM vs Change Control
| Confusion | Clarification |
|-----------|---------------|
| Thinking they are the same | CM = managing versions, baselines, configurations. Change Control = process for proposing, evaluating, approving changes |
| Confusing version control with configuration management | Version control is *part of* CM, but CM also includes build management, release management, etc. |

### Baselines
| Confusion | Clarification |
|-----------|---------------|
| Thinking baselines are just "checkpoints" | Baselines are formally reviewed and approved artifacts that can only change through formal change control |
| Assuming any version can be a baseline | Baselines are established at specific milestones (e.g., after requirements review) |

---

## 8. Quality Assurance & Reliability

### QA vs QC vs Testing
| Confusion | Clarification |
|-----------|---------------|
| Thinking QA = Testing | QA = process-oriented (prevention). QC = product-oriented (detection). Testing is a QC activity |
| Assuming QA catches all defects | QA focuses on preventing defects; QC and testing catch existing defects |

### Reliability Metrics
| Confusion | Clarification |
|-----------|---------------|
| Confusing MTTF with MTBF | MTTF = Mean Time To Failure (for non-repairable). MTBF = Mean Time Between Failures (for repairable) |
| Confusing reliability with availability | Reliability = probability of failure-free operation. Availability = proportion of time system is operational |
| Thinking reliability can be "proven" | Reliability can be estimated, not proven, for complex systems |

---

## 9. Project Management

### Planning vs Scheduling
| Confusion | Clarification |
|-----------|---------------|
| Thinking they are the same | Planning = defining WHAT to do and HOW. Scheduling = assigning WHEN and WHO |
| Assuming scheduling is just creating a timeline | Scheduling involves resource allocation, dependencies, and critical path analysis |

### Staffing vs Effort
| Confusion | Clarification |
|-----------|---------------|
| Thinking more people = less time (Brooks's Law) | Adding people to a late project makes it later (communication overhead increases) |
| Confusing effort with staffing level | Effort = total person-months. Staffing = number of people assigned at any time |

---

## 10. General Exam Traps

| Trap | Why It's Wrong |
|------|----------------|
| "High coupling is good" | High coupling = bad. Want low coupling. |
| "Low cohesion is good" | Low cohesion = bad. Want high cohesion. |
| "Verification = building the right product" | Verification = building the product *right*. Validation = building the right product. |
| "LOC is language-independent" | LOC is language-dependent. FP is language-independent. |
| "More people always speeds up projects" | Brooks's Law: adding people to late projects makes them later. |
| "Waterfall is always inferior" | Waterfall suits stable, well-understood requirements. |
| "Agile has no documentation" | Agile values working software *over* comprehensive documentation, not *no* documentation. |
| "Testing proves software is correct" | Testing can show presence of bugs, never their absence (Dijkstra). |
| "Risk exposure = probability + impact" | Risk exposure = probability × impact (multiplication, not addition). |
| "System testing = acceptance testing" | System testing verifies against requirements. Acceptance testing verifies customer needs. |
| "Integration testing happens after unit testing" | Integration testing combines already-tested units. Sequence matters. |
| "Prototyping is a design technique" | Prototyping is a requirements elicitation technique. |
| "Information hiding = abstraction" | Information hiding hides implementation details. Abstraction hides complexity. |
| "V-model skips test planning" | V-model maps each dev phase to a test level, including early test planning. |
