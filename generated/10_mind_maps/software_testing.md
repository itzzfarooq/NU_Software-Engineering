╔══════════════════════════════════════════════════════════════════════════════════╗
║                         SOFTWARE TESTING — MIND MAP                           ║
╚══════════════════════════════════════════════════════════════════════════════════╝

                                 SOFTWARE TESTING
                                      │
        ┌─────────────────────────────┼──────────────────────────────────────────┐
        │                             │                                          │
    [GOALS]                    [V & V FOUNDATION]                         [PROCESS]
        │                             │                                          │
    ┌───┴───┐                   ┌─────┴─────┐                             ┌─────┴──────┐
    │       │                   │           │                             │            │
  VALID.  DEFECT           VERIFICATION  VALIDATION                 TEST PLAN    TEST CASE
    │       │                   │           │                             │         SPEC.
    │       │             "Built right?"  "Right                         │            │
  Demonstrate           ┌─────┤       product?"                    What/When/    Inputs/
  requirements     Conforms to   │                              Who/Resources  Expected
  are met          specification │                              │            outputs
    │                      │     Meets user     TEST PLAN      │            │
  Successful           Inspections  needs      Schedule    RUN PROGRAM  COMPARE TO
  test = no            │               │       Resources        │      EXPECTATIONS
  failure          Static analysis  User test.  │               │            │
    │                            Acceptance    Process      TEST RESULTS  TEST REPORTS
  DEFECT TESTING                testing
    │
  Discover faults              │
    │                    INSPECTIONS
  Successful test                 │
  = finds defect       Static (no execution)
                          │
  ┌───────────────────────┤
  │        │              │
  Can catch  Catches      Broader quality
  spec gaps  interactions  (portability,
             between       maintainability)
             errors

        │
        │
        ├──────────────────────────────────────────────────────────────────────────┐
        │                                                                          │
    [TESTING LEVELS]                                                       [TECHNIQUES]
        │                                                                          │
    ┌───┴───────────────────────────────┐                              ┌───────────┴─────────────────┐
    │                                   │                              │                             │
  DEVELOPMENT TESTING            USER TESTING                    BLACK-BOX                  WHITE-BOX
    │                                   │                              │                             │
  ┌──┴───┬────────┬──────┐        ┌─────┴──────┐                No code access           Full code access
  │      │        │      │        │            │                       │                         │
 UNIT COMPONENT SYSTEM  │     ALPHA  BETA  ACCEPTANCE          Derived from spec        Derived from logic
  │      │        │     │        │      │      │                       │                         │
Single Integrate  Whole  │   At dev.  At user Formal             Equivalence             Statement
unit   units     system │   site     site    sign-off           partitioning             coverage
  │      │        │     │        │      │      │                       │                         │
Defect Interface Interact│  Controll. Real   Contract           Boundary value          Branch coverage
focus  focus     focus   │  environ.  world  based               analysis                      │
                          │                                                                    │
                          │                                                            Path coverage
                          │                                                                    │
                      RELEASE TESTING                                                  PATH TESTING (Basis)
                          │                                                                    │
                    ┌─────┴──────┐                                                   ┌─────────┴──────────┐
                Separate team    │                                             Control flow       Cyclomatic
                Black-box     Scenario-                                       graph (nodes/edges)  complexity
                Validation    based                                         Independent paths    M = E - N + 2
                focus         │                                             Dynamic program      M = predicate
                              │                                             analyzer checks     nodes + 1
                         [RELEASE CANDIDATE]                                path execution
                              │
                    ┌─────────┼──────────┐
                    │         │          │
                Test      Test       Test
              function-  reliabil-  perfor-
              ality      ity        mance
                              │
                         [CUSTOMER USAGE]

                          │
                          │                 ┌───────────────────────────────┐
                          │                 │                               │
                                          ERROR GUESSING          PENETRATION TESTING
                                               │                         │
                                        Experience-based          Security-focused
                                               │                         │
                                          Common weak spots:     Exploit vulnerabilities
                                           - Zero inputs          - Software weaknesses
                                           - Large numbers        - Hardware weaknesses
                                           - Alpha in numeric     - Organisational
                                           - Empty arrays           weaknesses
                                               │                         │
                                          Complements formal     Cannot prove security
                                          techniques

                          │
                          │
                      [TDD — TEST-DRIVEN DEVELOPMENT]
                          │
                    ┌─────┴──────────────────────────┐
                    │                                │
              RED-GREEN-REFACTOR                   BENEFITS
                    │                                │
            ┌───────┼───────┐              ┌─────────┼─────────┐
            │       │       │              │         │         │
          Write   Implement  Refactor    Code     Regression  Simplif.  Living
          test (= run test,    code     coverage  test suite  debug.   doc.
          fails)   pass                         (grows with  (bug in
                                            code base)   recent code)

                          │
                      [RELATED TOPICS]
                          │
        ┌─────────────────┼─────────────────┬──────────────────┐
        │                 │                 │                  │
  Requirements      Software Design    Quality Mgmt       Risk Mgmt
  (source of        (guides system      (QA activity,      (risk-based
  validation tests)  & component tests)  inspections)       test priority)

    ┌───────────────────┬───────────────────┬────────────────────┐
    │                   │                   │                    │
  SAFETY TESTING    RELIABILITY       INFORMATION         EMBEDDED
    │               TESTING           SYSTEMS TESTING    SYSTEMS TESTING
    │                   │                   │                    │
  Safety case        Operational        Database-          Platform reuse
  must demonstrate   profile (usage     centered           strategy
  no unrecoverable   model)             (no data loss)     Integration
  errors              │                                       testing
                    MTTF, POFOD,       User interaction     Limited
                    Failure intensity  intensive (GUI       debugging
                                       testing hard)

                          │
                      [KEY PRINCIPLES]
                          │
    ┌─────────────────────┼─────────────────────────┐
    │                     │                         │
Testing reveals      Absence of evidence        Inspections and
presence of         is not evidence of          testing are
errors, NOT         absence (passing            complementary
their absence       tests ≠ no bugs)            (static + dynamic)