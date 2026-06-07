# Software Testing — Detailed Study Notes

---

## 1. Topic Overview

Software testing is the dynamic execution of a program using artificial data to discover defects and demonstrate that the system meets its requirements. It is a core activity within the broader Verification and Validation (V&V) process. Testing spans the entire development lifecycle, from individual unit checks to large-scale user acceptance trials. A fundamental truth of testing is that it **can reveal the presence of errors, but never their absence** — passing all tests does not mean the software is correct, only that no defects were found under the tested conditions.

---

## 2. Why This Topic Exists

Software is written by humans, and humans inevitably introduce defects. Without testing:

- **Defects would reach users**, causing financial loss, safety incidents, or reputational damage.
- **Requirements would go unchecked** — there would be no way to confirm that the system does what it was specified to do.
- **Change would be dangerous** — without regression testing, every fix or enhancement risks breaking existing functionality.
- **Contracts could not be closed** — acceptance testing is the formal mechanism by which customers sign off on delivered software.

Testing exists to:
- **Validate** that the software meets user needs and contractual requirements.
- **Find defects** before deployment, reducing cost (the earlier a bug is caught, the cheaper it is to fix).
- **Build confidence** in the system's reliability, safety, security, and performance.
- **Provide a safety net** for ongoing maintenance via regression testing.
- **Fulfil regulatory obligations** (e.g., safety-critical systems in aviation, medical devices).

---

## 3. Core Concepts & Definitions

### 3.1 Fundamental Terminology

| Concept | Definition |
|---------|-----------|
| **Verification** | "Are we building the product right?" — checks that the software conforms to its specification |
| **Validation** | "Are we building the right product?" — checks that the software meets the user's real needs |
| **Defect (Fault)** | A static error in the source code (e.g., a wrong condition, a missing null check) |
| **Failure** | An observable incorrect behaviour at runtime, caused by the execution of a defect |
| **Error** | A human mistake made during development that introduces a defect |
| **Test Case** | A set of inputs, preconditions, and expected outputs designed to exercise a specific behaviour |
| **Test Suite** | A collection of related test cases (e.g., all unit tests for a class) |
| **Assertion** | A boolean check comparing the actual result of a test against the expected result |
| **Regression Testing** | Re-executing existing tests after code changes to ensure nothing broke |
| **Operational Profile** | A model describing how the system is actually used (frequency of features, input distributions) |
| **Cyclomatic Complexity** | A metric equal to the number of independent paths in a program; used in path testing |
| **Static Testing** | Analysis without execution (inspections, walkthroughs, code reviews, tool-based analysis) |
| **Dynamic Testing** | Executing the program with test data and observing its behaviour |

### 3.2 Verification vs Validation — Detailed Comparison

| Dimension | Verification | Validation |
|-----------|-------------|------------|
| Core Question | "Did we build it right?" | "Did we build the right thing?" |
| Focus | Conformance to the specification | Satisfying the user's actual needs |
| When Applied | Throughout development (reviews, unit tests) | Late in the lifecycle (user testing, acceptance) |
| Can Catch Wrong Requirements? | No — if the spec is wrong, verification still passes | Yes — validation checks against user needs, not spec |
| Typical Techniques | Inspections, white-box testing, static analysis | Black-box testing, alpha/beta testing, acceptance testing |
| Success Criterion | No deviation from specification | User accepts and uses the system |

### 3.3 Defect Testing vs Validation Testing

| Dimension | Validation Testing | Defect Testing |
|-----------|-------------------|----------------|
| Primary Goal | Demonstrate requirements are met | Discover faults and incorrect behaviour |
| Test Case Design | Reflects normal, expected usage | Deliberately uses unusual or extreme inputs |
| Successful Test | System operates correctly (no failures) | System fails, exposing a defect |
| When Used | Release testing, user testing | Unit testing, component testing, penetration testing |

---

## 4. Testing Levels

Testing is organised into levels, each with a distinct scope, purpose, and audience.

### 4.1 Overview Diagram

```
                        SOFTWARE TESTING LEVELS
                            │
            ┌───────────────┼───────────────────────┐
            │               │                       │
    Development Testing  Release Testing      User Testing
            │               │                       │
    ┌───────┼───────┐   Separate Team     ┌───────┼───────┐
    │       │       │   Black-box          │       │       │
  Unit  Component  System  Scenario-based  Alpha  Beta  Acceptance
```

### 4.2 Comparison Table

| Level | Who Executes | Primary Goal | Scope | Typical Techniques |
|-------|-------------|--------------|-------|-------------------|
| **Unit Testing** | Developer | Find defects in isolation | Single function, method, or class | White-box, path testing, automated (JUnit) |
| **Component Testing** | Developer | Verify interfaces between units | Several integrated units | Interface testing, stub/driver development |
| **System Testing** | Developer | Validate overall behaviour & interactions | Entire integrated system | Black-box scenario testing, performance testing |
| **Release Testing** | Separate test team | Validate against requirements | Complete release candidate | Black-box, scenario-based, specification-derived |
| **Alpha Testing** | Potential users (at developer site) | Real-world feedback, controlled | Near-complete system | Exploratory usage, guided scenarios |
| **Beta Testing** | Real users (at their own site) | Discover unanticipated issues | Pre-release version | Real-world usage, heterogeneous environments |
| **Acceptance Testing** | Customer | Formal sign-off and handover | Delivered system | Contract-based tests, acceptance scenarios |

### 4.3 Detailed Descriptions

**Unit Testing:**
- Tests the smallest testable part of the software in isolation.
- A "unit" may be a single function, a method within a class, or an entire class.
- Object class testing requires testing all operations, all attributes, and all possible states — inheritance makes this harder because behaviour may be spread across a hierarchy.
- Best automated using frameworks like JUnit, NUnit, pytest.
- Automated test structure: **setup** (initialize inputs/expected outputs) → **call** (invoke the method) → **assert** (compare actual to expected).

**Component Testing:**
- Combines several units that work together as a composite component.
- Focuses on **interfaces** — data passed between units, parameter types, return values, exception handling.
- Errors often surface at boundaries between components (e.g., one module expects a non-null value, another passes null).

**System Testing:**
- The entire system is integrated and tested as a whole.
- Focuses on **component interactions** — how modules behave together under realistic loads and scenarios.
- Covers functional and non-functional requirements (performance, security, usability).

**Release Testing:**
- Conducted by a separate team, not the developers.
- Primarily a **validation** activity (demonstrates requirements are met), not a defect-finding mission.
- Uses **scenario-based testing** — realistic usage scenarios derived from the requirements document.
- Typically **black-box** — the test team has no access to source code.

**User Testing (Alpha / Beta / Acceptance):**
- **Alpha:** Users test at the developer's location in a controlled environment. Catches obvious issues before wider release.
- **Beta:** Users test at their own sites. Catches environment-specific issues, unanticipated usage patterns, and platform incompatibilities. Critical for building credibility.
- **Acceptance:** Formal process where the customer signs off. For custom software, acceptance tests are agreed contractually in advance. For COTS software, acceptance involves checking functionality, performance, and compatibility.

---

## 5. Testing Techniques

### 5.1 Comparison Table

| Technique | Type | Source of Tests | Strengths | Weaknesses | Best For |
|-----------|------|----------------|-----------|------------|----------|
| **Black-Box Testing** | Dynamic | Specification / requirements | Tester-independent; catches spec gaps | May miss internal logic errors | Release testing, acceptance testing |
| **White-Box Testing** | Dynamic | Source code structure | Thorough internal coverage | Expensive; only as good as the code | Unit testing, path testing |
| **Path Testing (Basis Path)** | White-box | Control flow graph | Systematic independent path coverage | Exponential for large programs | Critical functions with moderate complexity |
| **Error Guessing** | Dynamic | Experience / domain knowledge | Finds real-world corner cases | Unsystematic; depends on tester skill | All levels as a supplement |
| **Penetration Testing** | Dynamic | Security threat models | Finds real vulnerabilities | Cannot prove security; expensive | Security-critical systems |
| **Inspections** | Static | Any representation | Catches defects early, no execution needed | Cannot test non-functional behaviour | Requirements, design, code reviews |

### 5.2 Black-Box Testing

The tester has **no access to source code**. Tests are derived entirely from the specification or requirements.

Key sub-techniques:
- **Equivalence Partitioning:** Divide the input domain into classes where the program should behave equivalently. Test one representative from each class.
  - Example: A function accepts integers 1–100. Equivalence classes: {valid: 1–100}, {below: <1}, {above: >100}.
- **Boundary Value Analysis:** Test at the edges of equivalence classes (where defects cluster).
  - Example: For valid range 1–100, test 0, 1, 2, 99, 100, 101.
- **Scenario-Based Testing:** Design tests around realistic usage scenarios from the requirements document.
  - Example: "User logs in, searches for a product, adds to cart, and checks out."

### 5.3 White-Box Testing (Structural Testing)

The tester has **full access to source code**. Tests are designed based on the internal logic.

Key coverage criteria:
- **Statement Coverage:** Every statement executed at least once (weakest criterion).
- **Branch Coverage:** Every true/false branch taken at least once.
- **Path Coverage:** Every possible path through the code executed (strongest but often infeasible).

### 5.4 Path Testing (Basis Path Testing)

Path testing is a white-box technique that ensures a **basis set** of independent paths through a program is executed. It provides strong coverage without requiring every possible path (which can be exponential).

**Steps:**
1. Draw the **control flow graph** — nodes represent statements or decisions; edges represent flow of control.
2. Compute **cyclomatic complexity** `M = E - N + 2` (edges minus nodes plus 2), or `M = number of predicate nodes + 1`.
3. Identify a **basis set** of `M` independent paths.
4. Design test cases to exercise each path.

**Binary Search Example — Method Signature:**

```java
public static void search(int key, int[] elemArray, Result r) {
1:  int bottom = 0;
2:  int top = elemArray.length - 1;
3:  int mid;
4:  r.found = false;
5:  r.index = -1;
6:  while (bottom <= top) {
7:      mid = (top + bottom) / 2;
8:      if (elemArray[mid] == key) {
9:          r.index = mid;
10:         r.found = true;
11:         return;
12:     } else {
13:         if (elemArray[mid] < key)
14:             bottom = mid + 1;
15:         else
16:             top = mid - 1;
17:     }
18:  }
19: }
```

**Flow Graph Nodes (simplified):**

```
         Node 1-5: initialization (entry)
              │
         Node 6: while (bottom <= top)
            / \
          Yes   No
           │     │
         Node 7: compute mid
           │
         Node 8: if (elemArray[mid] == key)
          / \
        Yes   No
         │     │
   Node 9-11:  Node 13: if (elemArray[mid] < key)
   set found,     / \
   return      Yes   No
                │     │
          Node 14:   Node 16:
          bottom=    top=
          mid+1      mid-1
                \     /
                 \   /
               (back to Node 6)

         Node 19: exit (after loop or return)
```

**Independent Paths (basis set):**

| Path ID | Node Sequence | Scenario |
|---------|---------------|----------|
| P1 | 1-2-3-4-5-6-7-8-9-10-11-19 | Key found at first check (immediate return) |
| P2 | 1-2-3-4-5-6-19 | Empty array or key < smallest element (loop body skipped) |
| P3 | 1-2-3-4-5-6-7-8-13-14-6-... | Key > mid value (go right — bottom adjusted) |
| P4 | 1-2-3-4-5-6-7-8-13-16-6-... | Key < mid value (go left — top adjusted) |

Cyclomatic complexity: `M = 4` (4 predicate nodes: the while condition, the `==` check, and the `<` check... actually let me count more carefully. The while is a predicate, the `==` is a predicate, the `<` is a predicate. That's 3 predicates, so `M = 3 + 1 = 4`). This matches the 4 independent paths above.

A **dynamic program analyzer** can be used during testing to verify which paths were actually exercised.

### 5.5 Error Guessing

- Not a formal technique — relies on the tester's **experience** and **domain knowledge**.
- Testers guess where defects are most likely to occur and design test cases accordingly.
- Common weak spots:
  - Zero or null values
  - Very large numbers (overflow)
  - Alphabetic characters in numeric fields
  - Empty arrays or collections
  - Boundary conditions
  - Divide-by-zero scenarios

### 5.6 Penetration Testing (Security)

- Deliberately attempts to **exploit vulnerabilities** to gain unauthorised access.
- Examines software, hardware, and organisational weaknesses.
- Extremely difficult because proving a system is secure is impossible — you can only show that specific known attacks fail.

---

## 6. Test-Driven Development (TDD)

### 6.1 The TDD Cycle (Red-Green-Refactor)

```
         ┌─────────────────────────────────────┐
         │           SELECT TASK               │
         └────────────────┬────────────────────┘
                          │
                          ▼
         ┌─────────────────────────────────────┐
         │         WRITE A TEST                 │
         │   (test fails initially — RED)      │
         └────────────────┬────────────────────┘
                          │
                          ▼
         ┌─────────────────────────────────────┐
         │     IMPLEMENT MINIMAL CODE          │
         │   to make the test pass — GREEN     │
         └────────────────┬────────────────────┘
                          │
                          ▼
         ┌─────────────────────────────────────┐
         │         RUN ALL TESTS               │
         │   ┌───── All pass? ─────┐           │
         │   Yes                  No           │
         │    │                    │           │
         │    ▼                    ▼           │
         │  REFACTOR           FIX CODE       │
         │  (improve design,    & re-run       │
         │   remove duplication)               │
         │    │                               │
         └────┴────────────────────────────────┘
                          │
                          ▼
               NEXT TASK (repeat)
```

### 6.2 Benefits

| Benefit | Explanation |
|---------|-------------|
| **Code Coverage** | Every line of code is written because a test required it — no dead code |
| **Regression Testing** | The growing test suite is re-run after every change, catching regressions instantly |
| **Simplified Debugging** | When a test fails, the bug is in the code most recently written or modified |
| **Living Documentation** | Tests describe what the code does — they are always up to date and executable |
| **Better Design** | Writing tests first forces the developer to think about interfaces and contracts before implementation |

### 6.3 Refactoring

- The third step in TDD (after Red and Green).
- **Refactoring** is restructuring existing code without changing its external behaviour.
- Goals: improve readability, reduce complexity, remove duplication ("code smells").
- Essential because "writing code that works is not enough — the code has to be clean."

---

## 7. Testing Process and Automation

### 7.1 The General Testing Process

```
    ┌──────────────┐
    │ Design Test  │──────▶ Test Cases
    │   Cases      │
    └──────┬───────┘
           ▼
    ┌──────────────┐
    │ Prepare Test │──────▶ Test Data
    │    Data      │
    └──────┬───────┘
           ▼
    ┌──────────────┐
    │ Run Program  │──────▶ Test Results
    │ with Data    │
    └──────┬───────┘
           ▼
    ┌──────────────┐
    │ Compare to   │──────▶ Test Reports
    │ Expectations │
    └──────────────┘
```

### 7.2 Automated Testing Components

Every automated test (e.g., using JUnit) has three essential parts:

| Part | Description | Example (JUnit) |
|------|-------------|-----------------|
| **Setup** | Initialize the system: create objects, set inputs, define expected outputs | `@Before` method, constructor |
| **Call** | Invoke the method or component under test | `int result = calculator.add(2, 3);` |
| **Assertion** | Compare actual output to expected; test passes if assertion is true, fails if false | `assertEquals(5, result);` |

### 7.3 Testing Documentation

- **Test Plan:** Describes what is to be tested, the testing schedule, required resources, and test processes.
- **Test Case Specification:** Detailed specification of inputs, expected outputs, and test data for each test case.

---

## 8. Detailed Explanations

### 8.1 Why "Testing Cannot Prove Absence of Errors"

This is the single most important concept in software testing. The input space of even a trivial program is effectively infinite. Running a million test cases that all pass does not guarantee the million-and-first would not fail. Testing builds **confidence**, not certainty. Formal verification (mathematical proof) can prove correctness, but it is extremely expensive and only feasible for small, critical components.

### 8.2 Inspections vs Testing — Complementary, Not Opposing

| Aspect | Inspections (Static) | Testing (Dynamic) |
|--------|---------------------|-------------------|
| Execution required? | No | Yes |
| When applicable | Any time (even before code exists) | Only after code exists |
| Catches | Errors, style issues, spec gaps | Runtime failures, performance issues |
| Interactions between errors | Not a problem (static analysis) | One error can mask another |
| Non-functional checks | Limited | Performance, usability, security |
| Incomplete systems | Can inspect partial work | Need stubs/drivers for incomplete code |

### 8.3 Why GUI Testing Is Hard

- User interfaces are **presentation-oriented** — subjective assessment is needed.
- The interface is **non-deterministic** — same inputs may produce different user actions.
- Test coverage is measured by **number of user actions exercised**, which is hard to quantify.
- Partial automation is possible (scripted scenarios) but determining whether output is acceptable requires **human intervention**.

### 8.4 Reliability Testing

- Measures **how dependable** the system is over time.
- Requires an **operational profile** — a model of how the system is actually used (frequency of features, types of interactions, expected loads).
- Key metrics:
  - **MTTF (Mean Time To Failure):** Average time between failures.
  - **POFOD (Probability of Failure On Demand):** Likelihood of failure on a single operation.
  - **Failure Intensity:** Failures per unit time.
- Measurements are **meaningless** without a representative operational profile.

---

## 9. Relationships to Other Topics

| Topic | Relationship to Testing |
|-------|------------------------|
| **Requirements Engineering** | Requirements are the basis for validation testing and acceptance criteria |
| **Software Design** | Design documents guide system and component testing |
| **Implementation / Coding** | Code is the object of all dynamic testing; TDD ties coding and testing together |
| **Software Process Models** | Testing phase is defined differently in Waterfall (late phase) vs Agile (continuous) |
| **Quality Management** | Testing is a key quality assurance activity; inspections complement testing |
| **Configuration Management** | Test cases and results are configuration items that must be version-controlled |
| **Project Management** | Testing consumes significant time and resources; must be planned and scheduled |
| **Risk Management** | Testing effort is often prioritised based on risk (high-risk components tested more) |
| **Maintenance** | Regression testing is critical during maintenance to prevent regressions |
| **Safety Engineering** | Safety-critical systems require extensive testing evidence for certification |

---

## 10. Examples

### 10.1 Example: TDD for a `findMax` Function

**Task:** Implement a function that returns the maximum element from an integer array.

```
Iteration 1:
  Test:   assertEquals(5, findMax(new int[]{1, 3, 5, 2, 4}));
  Result: FAIL (function does not exist)
  Code:   public int findMax(int[] arr) { return 5; }
  Result: PASS (but clearly incomplete — we wrote just enough to pass)

Iteration 2:
  Test:   assertEquals(10, findMax(new int[]{10, 1, 2}));
  Result: FAIL (returns 5 instead of 10)
  Code:   public int findMax(int[] arr) {
            int max = arr[0];
            for (int i = 1; i < arr.length; i++)
              if (arr[i] > max) max = arr[i];
            return max;
          }
  Result: PASS

Refactor: No duplication; code is clean.
```

### 10.2 Example: Binary Search — Test Cases for Path Coverage

**Method:** `search(int key, int[] elemArray, Result r)`

| Test Case | Input | Expected Output | Path Exercised | Notes |
|-----------|-------|----------------|----------------|-------|
| TC1 | `key=5, elemArray=[5]` | `r.found=true, r.index=0` | P1: 1-2-3-4-5-6-7-8-9-10-11-19 | Immediate match |
| TC2 | `key=5, elemArray=[]` | `r.found=false, r.index=-1` | P2: 1-2-3-4-5-6-19 | Empty array, loop skipped |
| TC3 | `key=9, elemArray=[5,7,9]` | `r.found=true, r.index=2` | P3: 1-2-3-4-5-6-7-8-13-14-6-...->19 | Key > mid; search right half |
| TC4 | `key=1, elemArray=[5,7,9]` | `r.found=false, r.index=-1` | P4: 1-2-3-4-5-6-7-8-13-16-6-...->19 | Key < mid; search left half, exhaust |

### 10.3 Example: Equivalence Partitioning

**Requirement:** A system accepts a password of length 6–20 characters.

Equivalence classes:
- **Valid:** 6–20 characters (test with "abc123", "abcdefghijklmnopqrst")
- **Invalid — too short:** 0–5 characters (test with "", "a", "abcde")
- **Invalid — too long:** 21+ characters (test with 21 'a's)

Boundary value analysis (testing edges):
- Test 5 chars (just below minimum)
- Test 6 chars (minimum valid)
- Test 20 chars (maximum valid)
- Test 21 chars (just above maximum)

### 10.4 Example: Error Guessing

**Scenario:** A function that divides two integers.

An experienced tester immediately suspects:
- Division by zero (test with denominator = 0)
- Negative numbers (test with `-10 / 2`, `10 / -2`, `-10 / -2`)
- Very large numerator (integer overflow)
- Numerator smaller than denominator (returns 0 if integer division)
- Floating-point precision if casting

---

## 11. Common Mistakes / Exam Traps

| # | Mistake | Why It Is Wrong | Correct Understanding |
|---|---------|-----------------|----------------------|
| 1 | "Testing proves the software is correct." | The input space is infinite; passing all tests does not guarantee no defects exist. | Testing can only reveal the presence of errors, not their absence. |
| 2 | "Verification and validation are the same thing." | They answer different questions and catch different types of issues. | Verification = spec conformance; Validation = user needs. |
| 3 | "TDD just means writing tests first." | TDD is a full development methodology with three steps, not just the order of writing. | TDD: Red (write failing test) → Green (implement to pass) → Refactor (improve code). |
| 4 | "Path testing requires testing every possible execution path." | For any non-trivial program, paths are exponential. Basis path testing tests only linearly independent paths. | Basis path testing uses cyclomatic complexity to find a minimal set of independent paths. |
| 5 | "Beta testing is just a marketing gimmick with no engineering value." | Beta testing exposes the system to real-world environments and usage patterns that lab testing cannot replicate. | Beta testing is a critical validation activity that catches environment-specific and unanticipated-usage bugs. |
| 6 | "All testing should be automated." | GUI testing, usability testing, and exploratory testing require human judgment and cannot be fully automated. | Automate regression and unit tests; reserve human judgment for scenarios, UI, and usability. |
| 7 | "Black-box testing does not require the requirements document." | Black-box tests are derived entirely from the specification — without it, there is no basis for expected behaviour. | Black-box testing requires a complete, unambiguous specification. |
| 8 | "A system that passes all tests is defect-free." | Tests only cover the scenarios that were designed and executed. | The absence of detected defects does not mean no defects exist. |
| 9 | "Unit testing is sufficient — integration and system testing are unnecessary." | Components may work perfectly in isolation but fail when interacting due to interface mismatches. | Integration and system testing catch interface and interaction bugs that unit tests miss. |
| 10 | "Error guessing is unscientific and should be avoided." | Error guessing is a legitimate technique based on heuristics and domain expertise. | Error guessing complements formal techniques by finding real-world corner cases. |
| 11 | "The goal of release testing is to find as many defects as possible." | Release testing is primarily a validation activity (confirming requirements are met), not a defect-finding mission. | Release testing demonstrates conformance to specification; defect testing is the focus of development testing. |
| 12 | "Acceptance testing is the same as beta testing." | Acceptance testing is a formal, contract-based handover; beta testing is informal real-world validation. | Acceptance = contractual sign-off; Beta = real-world exposure before release. |
| 13 | "Cyclomatic complexity tells you how many bugs are in the code." | Cyclomatic complexity measures the number of independent paths, not the number of defects. | Cyclomatic complexity guides test case design (minimum number of paths to test). |
| 14 | "Static analysis is not real testing." | Static analysis (inspections, reviews) is a legitimate and highly effective V&V technique. | Static and dynamic testing are complementary; both should be used. |

---

## 12. Active Recall Questions

1. What is the difference between verification and validation? Give one example of each.
2. Why is it impossible to prove that software is correct through testing alone?
3. List the three levels of development testing and describe what each level focuses on.
4. What are the three mandatory parts of every automated test? Explain each.
5. Describe the Red-Green-Refactor cycle in TDD. What happens at each step?
6. What is the difference between alpha testing and beta testing?
7. List the four steps of basis path testing, in order.
8. What is cyclomatic complexity, and how is it computed? What does it tell you?
9. Give two examples of test cases you would design using equivalence partitioning, and two using boundary value analysis.
10. When would you choose white-box testing over black-box testing, and vice versa?
11. What is an operational profile, and why is it critical for reliability testing?
12. Why is GUI testing difficult to automate fully?
13. What is the key difference between release testing and development system testing?
14. Why are inspections and testing considered complementary rather than opposing techniques?
15. What three factors influence the level of confidence needed from V&V activities?
16. What is a "basis set" of paths in path testing? How many paths does it contain?
17. Why is refactoring an essential part of TDD, not an optional extra?
18. Name three common error guessing scenarios that an experienced tester would check.
19. What is the difference between a defect, an error, and a failure?
20. For the binary search example, what happens to the flow graph and independent paths if the array is empty?

---

## 13. Potential Exam Questions

1. **Explain** the difference between verification and validation. Provide one concrete example of each from the weather station case study (reportWeather, shutdown, etc.).
2. **Describe** the three levels of development testing (unit, component, system). For each level, state what is being tested, what type of defects it targets, and give an example.
3. **Walk through** the complete TDD process for implementing a function `isPalindrome(String s)` that returns true if the string reads the same forwards and backwards. Show the test, the minimal implementation, the refactoring step, and how you would incrementally add more test cases.
4. **Compare and contrast** black-box testing with white-box testing. Give one scenario where each is the better choice and explain why.
5. **Given the binary search program** shown in the notes, draw the control flow graph, compute cyclomatic complexity, identify all independent paths in the basis set, and design a set of test cases that covers every path.
6. **Explain** the statement "Testing can show the presence of errors, but not their absence." Why is this a fundamental limitation, and how do software engineers compensate for it in practice?
7. **Describe** the user testing process: distinguish between alpha, beta, and acceptance testing. Explain the purpose of each stage, who runs it, and what artefacts are produced.
8. **What is regression testing**, and why is it especially important in TDD and in maintenance? How does incremental test development in TDD support regression testing?
9. **A critical e-commerce system passed all release testing (validation) but failed during beta testing. Explain why this can happen.** Consider differences in environment, usage patterns, user behaviour, and unanticipated system interactions.
10. **When would you choose error guessing** over formal test design techniques like equivalence partitioning? Give three scenarios where error guessing is more effective.
11. **Explain how the testing strategy differs for critical systems (e.g., aircraft flight control) versus information systems (e.g., a university library system).** Consider validation versus defect focus, the role of operational profiles, and the types of testing required.
12. **A developer argues that "if our unit tests pass, we don't need integration testing." Why is this dangerously wrong?** Use an example of an interface defect that would not be caught by unit tests.

---

## 14. Topic Summary

- **Testing is dynamic verification** — it executes the program with test data. **Inspections are static verification** — they analyse representations without execution.
- **Verification** asks "are we building the product right?" (spec conformance). **Validation** asks "are we building the right product?" (user needs).
- **Validation testing** demonstrates that requirements are met (success = correct behaviour). **Defect testing** aims to expose faults (success = incorrect behaviour).
- **Testing levels** are organised hierarchically: unit → component → system (development), then release, then user (alpha → beta → acceptance).
- **TDD** (Red-Green-Refactor) interleaves testing and development: write a failing test, implement to pass, refactor, repeat.
- **Black-box testing** derives tests from the specification (no code access). **White-box testing** derives tests from internal logic (full code access).
- **Path testing** uses a control flow graph and cyclomatic complexity to identify a minimal basis set of independent paths for coverage.
- **Error guessing** relies on tester experience. **Penetration testing** attempts to exploit security vulnerabilities.
- **Reliability testing** requires an operational profile and measures MTTF, POFOD, and failure intensity.
- **Testing strategy** depends on system type: critical systems need extensive defect testing, information systems focus on validation, and embedded systems rely on integration testing.
- **The fundamental limitation:** no amount of testing can prove the absence of defects — testing only builds confidence.