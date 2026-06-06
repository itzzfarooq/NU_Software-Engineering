```
╔══════════════════════════════════════════════════════════════════╗
║                         SOFTWARE TESTING                         ║
╠══════════════════════════════════════════════════════════════════╣
║  Evaluating and verifying software quality and correctness      ║
╚══════════════════════════════════════════════════════════════════╝

  │
  ├── Testing Goals ───────────────────────────────────────────────
  │   ├── Verification (are we building the product right?)
  │   ├── Validation (are we building the right product?)
  │   └── Objectives (find defects, gain confidence, compliance)
  │
  ├── V&V (Verification & Validation) ─────────────────────────────
  │   ├── Static V&V (reviews, inspections, static analysis)
  │   ├── Dynamic V&V (unit, integration, system, acceptance)
  │   └── V-Model (maps each development phase to a test phase)
  │
  ├── Inspections and Reviews ─────────────────────────────────────
  │   ├── Types (informal, technical, walkthrough, formal)
  │   ├── Process (planning, overview, preparation, meeting, rework)
  │   ├── Roles (author, moderator, inspector, reader, scribe)
  │   └── Benefits (early defect detection, reduced rework)
  │
  ├── Testing Stages ──────────────────────────────────────────────
  │   ├── Unit Testing (individual components, white-box)
  │   ├── Integration Testing (interactions, top-down/bottom-up)
  │   ├── System Testing (complete system, functional + non-functional)
  │   └── Acceptance Testing (UAT, alpha, beta, contract)
  │
  ├── Path Testing ────────────────────────────────────────────────
  │   ├── White-Box Testing (internal structure, code-based)
  │   ├── Basis Path Testing (cyclomatic complexity, independent paths)
  │   ├── Control Flow Testing (statement, branch, condition coverage)
  │   └── Test Case Design (identify paths, design, execute)
  │
  ├── Test Types ──────────────────────────────────────────────────
  │   ├── Functional Testing (unit, integration, system, acceptance)
  │   ├── Non-Functional (performance, security, usability)
  │   ├── Regression Testing (retest after changes)
  │   └── Defect Testing (find failures, identify causes)
  │
  └── Test Automation ─────────────────────────────────────────────
      ├── Benefits (repeatability, speed, consistency)
      ├── Tools (frameworks, management, performance, GUI)
      └── Challenges (investment, maintenance, skill requirements)
```
 
# Software Testing - Mind Map

```
Software Testing
├── Testing Goals
│   ├── Verification
│   │   ├── Are we building the product right
│   │   ├── Conformance to specifications
│   │   └── Static testing
│   ├── Validation
│   │   ├── Are we building the right product
│   │   ├── Meets user needs
│   │   └── Dynamic testing
│   └── Objectives
│       ├── Find defects
│       ├── Prevent defects
│       ├── Gain confidence
│       ├── Provide information
│       ├── Conform to requirements
│       └── Compliance with standards
├── V&V Verification and Validation
│   ├── Static V&V
│   │   ├── Requirements reviews
│   │   ├── Design reviews
│   │   ├── Code inspections
│   │   └── Static analysis
│   ├── Dynamic V&V
│   │   ├── Unit testing
│   │   ├── Integration testing
│   │   ├── System testing
│   │   └── Acceptance testing
│   └── V-Model
│       ├── Requirements ↔ Acceptance testing
│       ├── Architecture ↔ System testing
│       ├── Design ↔ Integration testing
│       └── Code ↔ Unit testing
├── Inspections and Reviews
│   ├── Types of Reviews
│   │   ├── Informal review
│   │   ├── Technical review
│   │   ├── Walkthrough
│   │   └── Inspection formal
│   ├── Inspection Process
│   │   ├── Planning
│   │   ├── Overview meeting
│   │   ├── Preparation
│   │   ├── Inspection meeting
│   │   ├── Rework
│   │   └── Follow-up
│   ├── Roles
│   │   ├── Author
│   │   ├── Moderator
│   │   ├── Inspector
│   │   ├── Reader
│   │   └── Scribe
│   ├── Checklists
│   │   ├── Requirements checklist
│   │   ├── Design checklist
│   │   └── Code checklist
│   └── Benefits
│       ├── Early defect detection
│       ├── Reduced rework
│       ├── Knowledge sharing
│       └── Process improvement
├── Testing Stages
│   ├── Unit Testing
│   │   ├── Test individual components
│   │   ├── Developer testing
│   │   ├── White-box testing
│   │   └── Test coverage
│   ├── Integration Testing
│   │   ├── Test component interactions
│   │   ├── Top-down integration
│   │   ├── Bottom-up integration
│   │   ├── Big-bang integration
│   │   └── Sandwich approach
│   ├── System Testing
│   │   ├── Test complete system
│   │   ├── Functional testing
│   │   ├── Non-functional testing
│   │   └── Regression testing
│   └── Acceptance Testing
│       ├── User acceptance testing UAT
│       ├── Alpha testing
│       ├── Beta testing
│       ├── Contract acceptance testing
│       └── Regulatory acceptance testing
├── Path Testing
│   ├── White-Box Testing
│   │   ├── Test internal structure
│   │   ├── Code-based testing
│   │   └── Requires code access
│   ├── Basis Path Testing
│   │   ├── McCabe's cyclomatic complexity
│   │   ├── V G = E - N + 2P
│   │   ├── Independent paths
│   │   └── Graph theory
│   ├── Control Flow Testing
│   │   ├── Statement coverage
│   │   ├── Branch coverage
│   │   ├── Condition coverage
│   │   └── Path coverage
│   └── Test Case Design
│       ├── Identify independent paths
│       ├── Design test cases for each path
│       └── Execute and verify results
├── Test Types
│   ├── Functional Testing
│   │   ├── Unit testing
│   │   ├── Integration testing
│   │   ├── System testing
│   │   └── Acceptance testing
│   ├── Non-Functional Testing
│   │   ├── Performance testing
│   │   ├── Load testing
│   │   ├── Stress testing
│   │   ├── Security testing
│   │   ├── Usability testing
│   │   └── Compatibility testing
│   ├── Regression Testing
│   │   ├── Retest after changes
│   │   ├── Automated testing
│   │   └── Test suite maintenance
│   └── Defect Testing
│       ├── Find failures
│       ├── Identify causes
│       └── Debugging
└── Test Automation
    ├── Benefits
    │   ├── Repeatability
    │   ├── Speed
    │   ├── Consistency
    │   └── Early detection
    ├── Tools
    │   ├── Unit test frameworks
    │   ├── Test management tools
    │   ├── Performance testing tools
    │   └── GUI testing tools
    └── Challenges
        ├── Initial investment
        ├── Maintenance
        ├── False positives
        └── Skill requirements
```
