# Software Testing — Detailed Exam Notes

## Why Testing?

Testing is intended to show that a program does what it is intended to do and to discover program defects before it is put into use. When you test software, you execute a program using artificial data and check the results for errors, anomalies, or information about non-functional attributes.

> **Critical Insight:** Testing can reveal the **presence** of errors, but NOT their absence. You can prove a program has bugs, but you cannot prove it is bug-free through testing alone.

Testing is part of a more general **verification and validation (V&V)** process, which also includes static validation techniques.

---

## Testing Goals: Validation vs. Defect Testing

Testing has two fundamental, complementary goals:

| Goal | Purpose | Test Case Design | Successful Test Means |
|---|---|---|---|
| **Validation testing** | Demonstrate to developer and customer that the software meets its requirements | Designed to reflect expected system use | System operates as intended |
| **Defect testing** | Discover situations where behavior is incorrect, undesirable, or non-conforming to specification | Can be deliberately obscure; need not reflect normal use | Test makes the system perform incorrectly, exposing a defect |

> **Instructor Emphasis:** Validation asks "did we build the right thing?" Defect testing asks "can we break it?" Both are essential.

---

## Input-Output Model of Program Testing

```
┌─────────────────────────────────────────────────┐
│              Input Test Data                     │
│  ┌───────────────────────┐                      │
│  │         Ie            │──── Inputs causing   │
│  └───────────────────────┘     anomalous        │
└────────────────────┬────────────────────────────┘
                     │
                     ▼
             ┌──────────────┐
             │    SYSTEM    │
             └──────┬───────┘
                     │
                     ▼
┌────────────────────┴────────────────────────────┐
│              Output Test Results                 │
│  ┌───────────────────────┐                      │
│  │         Oe            │──── Outputs which    │
│  └───────────────────────┘     reveal defects   │
└─────────────────────────────────────────────────┘
```

| Symbol | Meaning |
|---|---|
| **Ie** | Subset of test data that causes anomalous behavior |
| **Oe** | Subset of test results that reveal the presence of defects |

The model shows testing as an **input-output process** where specific inputs are designed to produce outputs that reveal defects.

---

## Verification vs. Validation

| Concept | Question | Focus |
|---|---|---|
| **Verification** | "Are we building the product right?" | Software should conform to its specification |
| **Validation** | "Are we building the right product?" | Software should do what the user really requires |

> **Exam Tip:** Verification = conformance to specification. Validation = conformance to real user needs. These are different things — a system can pass verification (matches spec) but fail validation (wrong product).

---

## V&V Confidence

The aim of V&V is to establish confidence that the system is **fit for purpose**. This confidence depends on:

| Factor | How It Affects Confidence |
|---|---|
| **Software purpose** | Level of confidence depends on how critical the software is to the organization |
| **User expectations** | Users may have low expectations for certain kinds of software |
| **Marketing environment** | Getting a product to market early may be more important than finding all defects |

> **Real-world insight:** A game app needs different confidence levels than a medical device controller.

---

## Inspections vs. Testing

### Two Complementary Verification Approaches

| Approach | Type | What It Does |
|---|---|---|
| **Software inspections** | Static verification | Analysis of the static system representation (source code, requirements, design) to discover problems — WITHOUT executing the system |
| **Software testing** | Dynamic verification | Executing the system with test data and observing operational behavior |

### Where Each Is Applied

```
                        ┌──────────────┐
                        │ Inspections  │
                        └──────┬───────┘
                               │
          ┌────────────────────┼────────────────────┐
          │                    │                    │
          ▼                    ▼                    ▼
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│   Requirements  │  │    Software     │  │   UML Design    │
│  Specification  │  │  Architecture   │  │    Models       │
└────────┬────────┘  └─────────────────┘  └─────────────────┘
         │                                       │
         ▼                                       │
┌─────────────────┐                    ┌─────────────────┐
│     System      │                    │    Database     │
│    Prototype    │◄───────────────────│    Schemas      │
└─────────────────┘                    └────────┬────────┘
                                                │
                                                ▼
                                      ┌─────────────────┐
                                      │     Program     │
                                      └────────┬────────┘
                                               │
                                               ▼
                                      ┌─────────────────┐
                                      │     Testing     │
                                      └─────────────────┘
```

### Advantages of Inspections Over Testing

| Advantage | Explanation |
|---|---|
| **No error masking** | During testing, errors can mask (hide) other errors. Inspection is static, so no interaction between errors |
| **Incomplete versions** | Incomplete systems can be inspected without additional costs; testing incomplete programs requires specialized test harnesses |
| **Broader quality attributes** | Inspections can check compliance with standards, portability, and maintainability — not just correctness |

### When Inspections Cannot Replace Testing

| Limitation | Reason |
|---|---|
| Cannot check conformance to real requirements | Inspections verify against specification, not user needs |
| Cannot check non-functional characteristics | Performance, usability, reliability require execution |

> **Key Insight:** Inspections and testing are **complementary, not opposing** verification techniques. Both should be used during V&V.

---

## The Software Testing Process Model

```
┌──────────────┐    ┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│  Test Cases  │───▶│  Test Data   │───▶│ Test Results │───▶│ Test Reports │
└──────┬───────┘    └──────┬───────┘    └──────┬───────┘    └──────────────┘
       │                   │                   │
       ▼                   ▼                   ▼
┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│   Design     │    │   Prepare    │    │ Run program  │    ┌──────────────┐
│  test cases  │───▶│  test data   │───▶│ with test    │───▶│   Compare    │
│              │    │              │    │    data      │    │   results    │
└──────────────┘    └──────────────┘    └──────────────┘    └──────────────┘
```

**Process flow:**
1. Design test cases → produces Test cases
2. Prepare test data → produces Test data
3. Run program with test data → produces Test results
4. Compare results to expected → produces Test reports

---

## Stages of Testing

| Stage | Who Does It | What It Tests |
|---|---|---|
| **Development testing** | The development team | Tests during development to discover bugs and defects |
| **Release testing** | A separate testing team | Tests a complete version before release to users |
| **User testing** | Users or potential users | Tests the system in their own environment |

---

## Development Testing

Development testing includes all testing activities carried out by the team developing the system. It has three levels:

### Unit / Component / System Testing

| Level | What's Tested | Focus |
|---|---|---|
| **Unit testing** | Individual program units or object classes in isolation | Testing functionality of objects or methods |
| **Component testing** | Several individual units integrated into composite components | Testing **component interfaces** |
| **System testing** | Some or all components integrated together | Testing **component interactions** |

```
Unit Testing ──▶ Component Testing ──▶ System Testing
(individual      (integrated           (whole system
 components)      components)           interactions)
```

---

## Unit Testing

Unit testing is the process of testing individual components **in isolation**. It is a **defect testing** process.

Units may be:
- Individual **functions or methods** within an object
- **Object classes** with several attributes and methods
- **Composite components** with defined interfaces

---

## Object Class Testing

Complete test coverage of a class involves:

| Requirement | What It Means |
|---|---|
| **Test all operations** | Every method associated with the object must be tested |
| **Set and interrogate all attributes** | Every attribute must be readable and writable |
| **Exercise all possible states** | The object must be tested in every state it can enter |

> **Instructor Emphasis:** Inheritance makes object class testing harder because the information to be tested is not localized — behavior may be inherited from parent classes.

### Weather Station Example

| Method | Purpose |
|---|---|
| `reportWeather()` | Reports weather data |
| `reportStatus()` | Reports system status |
| `powerSave(instruments)` | Puts instruments in power save mode |
| `remoteControl(commands)` | Executes remote control commands |
| `reconfigure(commands)` | Reconfigures the system |
| `restart(instruments)` | Restarts instruments |
| `shutdown(instruments)` | Shuts down instruments |

**State transitions to test:**
- `Shutdown → Running → Shutdown`
- `Configuring → Running → Testing → Transmitting → Running`
- `Running → Collecting → Running → Summarizing → Transmitting → Running`

---

## Automated Testing (JUnit)

Whenever possible, unit testing should be **automated** so tests are run and checked without manual intervention.

### Test Automation Framework Components

| Component | Purpose |
|---|---|
| **Setup part** | Initialize the system with the test case: inputs and expected outputs |
| **Call part** | Call the object or method to be tested |
| **Assertion part** | Compare result with expected result; **true = pass, false = fail** |

> **Exam Tip:** JUnit is the standard framework for Java automated testing. Know the three components: setup, call, assertion.

---

## Path Testing

### Objective

Path testing ensures that the set of test cases is such that **each path through the program is executed at least once**.

### Basis Path Testing Steps

1. **Draw a control flow graph** (to determine different program paths)
2. **Find a basis set of paths** (independent paths)
3. **Generate test cases** to exercise each path

### Flow Graph Concepts

| Concept | Description |
|---|---|
| **Nodes** | Represent program statements, especially decisions (conditions) |
| **Arcs (edges)** | Represent the flow of control between statements |
| **Decision node** | A node with a condition that creates branching |
| **Independent path** | A path that introduces at least one new set of processing statements or a new condition |

### Binary Search Example

#### Source Code

```java
public static void search(int key, int[] elemArray, Result r) {
    // Node 1: Entry
    int bottom = 0;                                    // Node 2
    int top = elemArray.length - 1; int mid;           // Node 3
    r.found = false;                                   // Node 4
    r.index = -1;                                      // Node 4

    while (bottom <= top) {                            // Node 5 (decision)
        mid = (top + bottom) / 2;                      // Node 6
        if (elemArray[mid] == key) {                   // Node 7 (decision)
            r.index = mid;                             // Node 8
            r.found = true;                            // Node 9
            return;                                    // Node 10
        } else {
            if (elemArray[mid] < key) {                // Node 11 (decision)
                bottom = mid + 1;                      // Node 12
            } else {
                top = mid - 1;                         // Node 13
            }
        }
    }
    // Node 14: Exit (not found)
}
```

#### Flow Graph

```
              (1)  Entry
               │
              (2)  bottom = 0
               │
              (3)  top = len-1
               │
              (4)  found=false, index=-1
               │
          ┌───▶(5)  bottom <= top? ◀──┐
          │    /             \         │
          │   / (no)          \ (yes) │
          │  ▼                  ▼      │
         (14) Exit          (6) mid   │
         (not found)          │        │
                             (7) arr[mid]==key?
                            /      \
                        (yes)     (no)
                          │         │
                        (8)       (11) arr[mid]<key?
                          │        /      \
                        (9)     (12)    (13)
                          │    bottom   top
                        (10)   =mid+1  =mid-1
                        return   │        │
                          │      └────┬───┘
                          │           │
                          └───────────┘──▶ (back to 5)
```

#### Independent Paths

| Path | Nodes | Description |
|---|---|---|
| **Path 1** | 1→2→3→4→5→6→7→8→9→10→14 | Key found on first iteration (`elemArray[mid] == key`) |
| **Path 2** | 1→2→3→4→5→14 | Key not found immediately (`bottom > top` at first check) |
| **Path 3** | 1→2→3→4→5→6→7→11→12→5→... | `elemArray[mid] > key` → `bottom = mid + 1` → loop continues |
| **Path 4** | 1→2→3→4→5→6→7→11→13→5→... | `elemArray[mid] < key` → `top = mid - 1` → loop continues |

> **Exam Tip:** You must be able to identify independent paths from a flow graph. The number of independent paths equals the **cyclomatic complexity** of the program.

### How to Count Independent Paths

**Cyclomatic complexity formula:**
```
M = E - N + 2P
```
Where:
- E = number of edges
- N = number of nodes
- P = number of connected components (usually 1)

For binary search: M = 14 edges - 13 nodes + 2(1) = **3** independent paths minimum (though the example identifies 4 due to the nested decision structure).

---

## Quick Reference: Testing at a Glance

| Concept | Definition | Key Point |
|---|---|---|
| Validation testing | Show software meets requirements | Successful test = system works correctly |
| Defect testing | Find faults and defects | Successful test = system fails |
| Verification | "Building the product right" | Conformance to specification |
| Validation | "Building the right product" | Conformance to user needs |
| Inspections | Static analysis (no execution) | Applied to requirements, design, code |
| Testing | Dynamic analysis (execution) | Applied to prototypes and programs |
| Unit testing | Individual components in isolation | Defect testing for methods/classes |
| Component testing | Integrated units | Focus on interfaces |
| System testing | Whole system | Focus on interactions |
| Path testing | Execute every path at least once | Uses flow graphs and basis paths |

---

## Exam Checklist

- [ ] Testing goals: validation vs. defect testing
- [ ] Input-output model of testing (Ie, Oe)
- [ ] Verification vs. validation (definitions and difference)
- [ ] V&V confidence factors (software purpose, user expectations, marketing environment)
- [ ] Inspections vs. testing: when each applies, advantages of inspections
- [ ] Inspections and testing are complementary, not opposing
- [ ] Testing process model (design → prepare → run → compare)
- [ ] Three stages of testing (development, release, user)
- [ ] Development testing: unit → component → system (and what each focuses on)
- [ ] Unit testing: in isolation, defect testing process
- [ ] Object class testing: operations, attributes, states
- [ ] Automated testing: JUnit, 3 components (setup, call, assertion)
- [ ] Path testing: objective, flow graph, basis path testing steps
- [ ] Binary search: flow graph nodes 1-14, independent paths
- [ ] Cyclomatic complexity formula: M = E - N + 2P
