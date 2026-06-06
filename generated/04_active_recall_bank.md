# Active Recall Question Bank — Software Engineering

---

## 1. SOFTWARE ENGINEERING INTRODUCTION

### Definitions

1. **What is software engineering?** An engineering discipline concerned with all aspects of software production from early specification through to maintaining the system after it has gone into use.

2. **What is a generic software product?** A stand-alone system marketed and sold to any customer who wishes to buy it (e.g., PC software, CAD tools).

3. **What is a custom/bespoke software product?** Software commissioned by a specific customer to meet their own unique needs (e.g., embedded control systems, air traffic control).

4. **Who owns the specification for a generic product?** The software developer; decisions on changes are made by the developer.

5. **Who owns the specification for a custom product?** The customer; they make decisions on software changes.

6. **List the four essential attributes of good software.** Maintainability, dependability/security, efficiency, and acceptability.

7. **What is software maintainability?** Software should be written so it can evolve to meet changing customer needs. Change is inevitable in a changing business environment.

8. **What is software dependability?** Includes reliability, security, and safety. Dependable software should not cause physical or economic damage in the event of failure.

9. **What are the four fundamental software engineering activities?** Specification, development, validation, and evolution.

10. **What is the difference between software engineering and computer science?** Computer science focuses on theory and fundamentals; software engineering is concerned with the practicalities of developing and delivering useful software.

11. **What is the difference between software engineering and system engineering?** System engineering covers all aspects of computer-based systems including hardware, software, and process engineering. Software engineering is part of this broader discipline.

12. **Name eight application types of software systems.** Stand-alone, interactive transaction-based, embedded control, batch processing, entertainment, modeling/simulation, data collection, and systems of systems.

13. **What are the general issues affecting modern software?** Heterogeneity, business/social change, security/trust, and scale.

14. **What percentage of software costs are development vs. testing?** Roughly 60% development, 40% testing.

15. **What is the ACM/IEEE Code of Ethics?** A set of eight ethical principles (PUBLIC, CLIENT AND EMPLOYER, PRODUCT, JUDGMENT, MANAGEMENT, PROFESSION, COLLEAGUES, SELF) guiding professional software engineering behavior.

### Comparisons

16. **Generic vs. Custom products: Who controls the spec and who decides changes?**
    - Generic: Developer owns spec, developer decides changes
    - Custom: Customer owns spec, customer decides changes

17. **Software engineering vs. Programming:** SE involves all aspects of production (specification, design, validation, evolution, management); programming is only the coding activity.

### Applications

18. **A company wants to build an ERP system tailored to its workflows. Is this generic or custom? What are the implications?** Custom. The customer owns the specification and decides on changes. The development process must accommodate evolving requirements from the specific customer.

19. **Why are software costs dominated by maintenance rather than development?** Because software has a long life and must be changed to reflect changing business requirements. For systems with a long life, maintenance costs may be several times development costs.

---

## 2. SOFTWARE PROCESSES

### Definitions

20. **What is a software process?** A structured set of activities required to develop a software system, involving specification, design and implementation, validation, and evolution.

21. **What is a software process model?** An abstract representation of a process from a particular perspective.

22. **What is a plan-driven process?** A process where all activities are planned in advance and progress is measured against this plan.

23. **What is an agile process?** A process where planning is incremental and it is easier to change the process to reflect changing customer requirements.

24. **What are the five phases of the waterfall model?** Requirements definition, system/software design, implementation/unit testing, integration/system testing, and operation/maintenance.

25. **What is incremental development?** A process where specification, development, and validation are interleaved rather than sequential.

26. **What is integration and configuration?** A reuse-oriented approach where the system is assembled from existing configurable components (COTS systems).

27. **What are the three types of reusable software?** Stand-alone application systems (COTS), collections of objects for component frameworks (.NET, J2EE), and web services.

28. **What are the five key process stages of reuse-oriented SE?** Requirements specification, software discovery/evaluation, requirements refinement, application system configuration, and component adaptation/integration.

### Comparisons

29. **Waterfall vs. Incremental Development:**
    - Waterfall: Sequential phases, plan-driven, documentation-heavy, inflexible to change
    - Incremental: Interleaved activities, rapid delivery, customer feedback, less documentation

30. **Plan-driven vs. Agile:**
    - Plan-driven: Stages planned in advance, iteration within activities, outputs decided upfront
    - Agile: Specification/design/implementation/testing interleaved, outputs decided through negotiation

31. **When is the waterfall model appropriate?** When requirements are well-understood and changes will be fairly limited. Mostly used for large multi-site systems engineering projects.

32. **What are the main problems with incremental development?** Process is not visible to managers; system structure tends to degrade as new increments are added without refactoring.

### Applications

33. **You are developing a safety-critical air traffic control system. Which process model and why?** Waterfall, because requirements must be fully understood upfront, a complete analyzable specification is needed, and changes during development are unacceptable in safety-critical domains.

34. **A startup is building a mobile app with rapidly changing requirements. Which process model?** Incremental development (or agile), because rapid delivery, customer feedback, and flexibility to change are critical.

35. **A company needs to build a business system using existing CRM and ERP components. Which process model?** Integration and configuration (reuse-oriented), because the system can be assembled from existing COTS components with configuration.

---

## 3. AGILE SOFTWARE DEVELOPMENT

### Definitions

36. **State the four values of the Agile Manifesto.** (1) Individuals and interactions over processes and tools; (2) Working software over comprehensive documentation; (3) Customer collaboration over contract negotiation; (4) Responding to change over following a plan.

37. **What is Extreme Programming (XP)?** An influential agile method where new versions may be built several times per day, increments are delivered every 2 weeks, and all tests must pass for every build.

38. **What is a user story?** A requirements expression written on cards that the development team breaks down into implementation tasks. Used for incremental planning and scheduling.

39. **What is refactoring?** Continuously improving code structure without changing behavior, making changes easier when they need to be implemented.

40. **What is Test-Driven Development (TDD)?** Writing automated unit tests for new functionality before the functionality itself is implemented (red-green-refactor cycle).

41. **What is pair programming?** Developers work in pairs, checking each other's work and providing support to always do a good job.

42. **What is collective ownership?** All developers work on all areas of the system; no islands of expertise develop; anyone can change anything.

43. **What is continuous integration?** As soon as work on a task is complete, it is integrated into the whole system. All unit tests must pass after integration.

44. **What is sustainable pace?** Large amounts of overtime are not acceptable because they reduce code quality and medium-term productivity.

45. **What is an on-site customer?** A representative of the end-user available full-time to the XP team, responsible for bringing requirements for implementation.

### Comparisons

46. **Plan-driven vs. Agile development — five key differences:**
    - Planning: Upfront vs. incremental
    - Documentation: Comprehensive vs. minimal (working code focus)
    - Requirements: Stable, fixed vs. Changing, negotiated
    - Delivery: Single delivery vs. frequent incremental delivery
    - Customer role: At start/end vs. throughout development

47. **XP vs. traditional development:**
    - XP: Small releases, test-first, pair programming, collective ownership, refactoring
    - Traditional: Design upfront, individual coding, separate testing phase, documentation-heavy

### Applications

48. **An organization has strict regulatory requirements demanding complete documentation. Can they use pure agile? Why or why not?** No. Plan-driven approaches are needed for regulatory compliance. A hybrid approach combining plan-driven documentation with agile iterations may work.

49. **How do user stories differ from traditional requirements specifications?** User stories are brief, customer-written narratives on cards; they are broken into tasks by developers and serve as basis for estimates. Traditional specs are detailed, formal documents created upfront.

---

## 4. SOFTWARE TESTING

### Definitions

50. **What is software testing?** Executing a program with artificial data and checking results for errors, anomalies, or information about non-functional attributes. Can reveal the presence of errors but NOT their absence.

51. **What is verification?** "Are we building the product right?" — the software should conform to its specification.

52. **What is validation?** "Are we building the right product?" — the software should do what the user really requires.

53. **What is the difference between validation testing and defect testing?**
    - Validation testing: Expects system to perform correctly using test cases reflecting expected use
    - Defect testing: Test cases designed to expose defects; can be deliberately obscure

54. **What is a software inspection?** Static analysis where people examine the source representation to discover anomalies without executing the system.

55. **What are the three stages of testing?** Development testing, release testing, and user testing (alpha/beta).

56. **What is unit testing?** Testing individual components in isolation. It is a defect testing process.

57. **What is component testing?** Testing several individual units integrated into composite components, focusing on component interfaces.

58. **What is system testing?** Testing some or all components integrated together as a whole, focusing on component interactions.

59. **What are the three parts of an automated unit test?** Setup (initialize with test case inputs/expected outputs), call (invoke the method to be tested), and assertion (compare result with expected result).

60. **What is basis path testing?** A white-box testing technique where you draw a control flow graph, find a basis set of independent paths, and generate test cases to exercise each path.

61. **What is McCabe's cyclomatic complexity?** A metric for the number of independent paths through a program, calculated as V(G) = number of predicate nodes + 1 (or E - N + 2).

### Comparisons

62. **Inspections vs. Testing:**
    - Inspections: Static, no execution needed, can be applied to any representation, catch errors that mask other errors
    - Testing: Dynamic, requires execution, cannot check non-functional characteristics like performance

63. **Validation vs. Defect Testing:**
    - Validation: Shows system works as expected (successful = correct operation)
    - Defect: Finds faults (successful = system performs incorrectly, exposing a defect)

64. **Unit Testing vs. System Testing:**
    - Unit: Individual modules, isolation, tests functionality of methods
    - System: All components integrated, tests interactions between components

### Applications

65. **Why can't testing prove the absence of defects?** Testing can only show the presence of errors, not their absence. Even after many successful tests, untested scenarios may still contain defects.

66. **How do you design test cases for an object class?** Test all operations, set and interrogate all object attributes, and exercise the object in all possible states. Inheritance makes this harder because information is not localized.

67. **Draw the flow graph for a program with a while loop containing an if-else inside. Calculate the cyclomatic complexity.** The while is one predicate node, the if-else is another. V(G) = 2 + 1 = 3 independent paths.

---

## 5. PROJECT MANAGEMENT

### Definitions

68. **What are the four success criteria for software projects?** Deliver on time, keep costs within budget, deliver software meeting customer expectations, and maintain a coherent development team.

69. **What makes software project management unique?** The product is intangible, many projects are "one-off," and software processes are variable and organization-specific.

70. **What are the three universal management activities?** Project planning, risk management, and people management.

71. **What is a Work Breakdown Structure (WBS)?** A hierarchical decomposition of the project scope into manageable tasks.

### Applications

72. **Why can't you simply add more people to a late software project to make it on time?** Adding people increases communication overhead. Productivity is not proportional to the number of people. Brooks' Law: adding people to a late project makes it later.

73. **Why is the intangibility of software a challenge for project managers?** Managers cannot see progress by looking at the artifact being constructed, making it difficult to measure progress objectively.

---

## 6. RISK MANAGEMENT

### Definitions

74. **What is a risk?** A potential problem — an uncertain event that, if it occurs, has a negative impact on the project.

75. **What are the two characteristics of risk?** Uncertainty (may or may not happen) and Loss (unwanted consequences if it occurs).

76. **What are the three categories of risk?** Project risks (threaten schedule/resources), product risks (threaten quality/performance), business risks (threaten viability of the organization).

77. **What is risk exposure?** RE = P × C, where P is the probability of occurrence and C is the cost/consequence if the risk occurs.

78. **What are the four risk management process steps?** Risk identification, risk analysis, risk planning, and risk monitoring.

79. **What is reactive risk management?** The project team reacts to risks when they occur; "fix on failure" approach; crisis management.

80. **What is proactive risk management?** Formal risk analysis is performed; the organization corrects root causes of risk; contingency plans are established upfront.

81. **What are the seven principles of risk management?** (1) Maintain a global perspective, (2) Take a forward-looking view, (3) Encourage open communication, (4) Integrate risk management, (5) Emphasize continuous process, (6) Develop a shared product vision, (7) Encourage teamwork.

82. **What are the four risk components?** Performance risk, cost risk, support risk, and schedule risk.

83. **What are the three risk response strategies?** Avoidance strategies (reduce probability), minimization strategies (reduce impact), and contingency plans (deal with risk if it arises).

84. **What is a risk table?** A table with columns: Risk Summary, Risk Category, Probability, Impact (1-4: catastrophic to negligible), and RMMM (Risk Mitigation, Monitoring, and Management plan).

### Comparisons

85. **Reactive vs. Proactive Risk Management:**
    - Reactive: Responds when risks occur, crisis management, no upfront planning
    - Proactive: Formal analysis upfront, contingency plans, corrects root causes

86. **Known vs. Predictable vs. Unpredictable risks:**
    - Known: Uncovered from careful evaluation of project plan
    - Predictable: Extrapolated from past project experience
    - Unpredictable: Occur but are extremely difficult to identify in advance

### Applications

87. **Calculate the risk exposure: Only 70% of planned reusable components will integrate. 60 components planned, each 100 LOC, cost $14/LOC. Probability: 80%.** Risk: 18 components must be custom-developed. Cost = 18 × 100 × $14 = $25,200. RE = 0.80 × $25,200 = $20,160.

88. **Identify the risk type: "A key developer leaves the project."** Project risk (schedule/resources affected). Category: People risk. Strategy: Reorganize team with more overlap of work.

---

## 7. ESTIMATION

### Definitions

89. **What is software project estimation?** Defining project scope (WBS), estimating time, and estimating cost (resources, licensing, training).

90. **What is the LOC metric?** Lines of Code — counts every line of source code except blanks and comments.

91. **What is a function point (FP)?** A measure based on program characteristics: external inputs, external outputs, external inquiries, internal logical files, and external interface files.

92. **What is UFC (Unadjusted Function Count)?** UFC = Σ (count of each information domain element × its complexity weight).

93. **What is VAF (Value Adjustment Factor)?** VAF = 0.65 + (0.01 × ΣFi), where Fi are ratings (0-5) for 14 General System Characteristics. Range: 0.65 to 1.35.

94. **What is the FP formula?** FP = UFC × VAF.

95. **What is Wideband Delphi?** A consensus-based estimation process: choose team → kickoff meeting → individual preparation → estimation session (multiple rounds until convergence) → assemble tasks → review results.

96. **What is a person-month (pm)?** The metric for expressing effort — the amount of time personnel devote to a project. 1 pm = one person working full-time for one month.

### Comparisons

97. **LOC vs. Function Points:**
    - LOC: Simple to count, language-dependent, measures size
    - FP: Language-independent, focuses on functionality, more complex to calculate

### Applications

98. **LOC Estimation Example:** A CAD system has 7 modules: 5300 + 6800 + 2300 + 3350 + 8400 + 4950 + 2100 = 33,200 LOC. Productivity: 620 LOC/pm, cost: $8000/pm.
    - Cost/LOC = $8000/620 = $12.90 ≈ $13
    - Effort = 33,200/620 = 53.5 person-months
    - Project cost = 33,200 × $13 = $431,600

99. **FP Estimation Example:** EI=10 (avg, weight 4), EO=15 (avg, weight 5), EQ=8 (simple, weight 3), ILF=6 (complex, weight 15), EIF=3 (avg, weight 7). ΣFi = 45.
    - UFC = (10×4) + (15×5) + (8×3) + (6×15) + (3×7) = 40+75+24+45+21 = 205
    - VAF = 0.65 + (0.01 × 45) = 1.10
    - FP = 205 × 1.10 = 225.5 ≈ 226 FP
    - If Java (46 LOC/FP): LOC = 226 × 46 = 10,396
    - If productivity = 500 LOC/pm: Effort = 10,396/500 = 20.8 person-months
    - Cost = 20.8 × $8,000 = $166,400

100. **Wideband Delphi Example:** Three estimators give Round 1 estimates of 20, 16, 29 days (total 65). After 3 rounds of discussion, estimates converge to 18, 19, 20 (total 57). The final estimate is the average: (18+19+20)/3 = 19 days.

---

## 8. PROJECT SCHEDULING

### Definitions

101. **What is project scheduling?** Splitting the project into tasks, estimating time/resources, organizing tasks concurrently, and minimizing dependencies to avoid delays.

102. **What is a Gantt chart (bar chart)?** A graphical chart showing project schedule against calendar time, with tasks as horizontal bars.

103. **What is an activity network diagram?** A diagram modeling project activities and their relationships as a network, using Activity-on-Arrow or Activity-on-Node notation.

104. **What is the Critical Path Method (CPM)?** A technique identifying the longest path through the network — the critical path determines minimum project duration.

105. **What is PERT?** Program Evaluation and Review Technique — similar to CPM but uses probabilistic time estimates.

106. **What is Total Float?** The amount of time an activity can be delayed from its ES date without delaying the project finish date. TF = LF - EF or TF = LS - ES.

107. **What is Free Float?** The amount of time an activity can be delayed without affecting the early start of the following activity. FF = MIN(ES_successor) - ES_activity - Duration.

108. **What are the rules for activity network diagrams?** Flow left to right, no activity begins until all predecessors done, every activity must have an ID, no looping, every activity ID > predecessor ID.

### Applications

109. **Activity Network Example:**
    Activities: A(3), B(4, pred=A), C(2, pred=A), D(5, pred=B), E(1, pred=C), F(2, pred=C), G(4, pred=D,E), H(3, pred=F,G).

    - Paths: A-B-D-G-H = 19 days, A-C-E-G-H = 13 days, A-C-F-H = 10 days
    - Critical Path: A → B → D → G → H = 19 days (longest path)
    - Activities on critical path have TF = 0: A, B, D, G, H
    - Activity C: TF = LS - ES = 9 - 3 = 6 days
    - Activity E: TF = 11 - 5 = 6 days
    - Activity F: TF = 14 - 5 = 9 days

110. **Why does adding people to a late project make it later?** Communication overhead increases quadratically with team size. More people means more coordination, more meetings, and more integration issues.

---

## 9. ARCHITECTURE DESIGN

### Definitions

111. **What is software design?** The creative process of translating requirements into a blueprint for constructing software, starting at high abstraction and iteratively refining.

112. **What is abstraction?** A view of a problem that extracts essential information relevant to a particular purpose and ignores the remainder.

113. **What is modularity?** Separately named and addressable components (modules) integrated to satisfy requirements, following the divide-and-conquer principle.

114. **What is information hiding?** Designing modules so algorithms and local data are inaccessible to other modules, enforcing access constraints to implementation details.

115. **What is functional independence?** Modules that have a single-minded function and minimal interaction with other modules, measured by coupling and cohesion.

116. **What is coupling?** A measure of interconnection among modules, depending on interface complexity, shared data references, and calling mechanisms.

117. **What is cohesion?** A measure of the relative functional strength of a module — how focused its responsibilities are.

118. **What are the five types of coupling (worst to best)?** Content, common, control, stamp, and data coupling.

119. **What are the seven types of cohesion (best to worst)?** Functional, sequential, communicational, procedural, temporal, logical, and coincidental.

120. **What is refinement?** The elaboration of details — a process of progressive detail that helps postpone decisions until later in design.

121. **What is refactoring?** Restructuring the design to separate concerns and remove duplication, reorganizing the class hierarchy.

122. **What is the 4+1 View Model?** Philippe Kruchten's model with 5 views: Logical (functionality for end users), Development (implementation), Process (system behavior/communication), Physical (system engineer's view), and Scenarios (use cases connecting all views).

123. **What are the four types of design classes?** Boundary classes (system-actor interface), Entity classes (long-lived persistent data), Control classes (mediate between boundary and entity), and Interface classes (user/system interfaces).

124. **What are architectural patterns?** Common solutions to recurring design problems that define overall software structure (e.g., layered, client-server, repository, MVC).

### Comparisons

125. **Coupling types — content vs. data:**
    - Content coupling (worst): One module modifies/relies on internal workings of another
    - Data coupling (best): Modules communicate via simple data items (parameters)

126. **Cohesion types — functional vs. coincidental:**
    - Functional (best): All elements contribute to a single well-defined task
    - Coincidental (worst): Elements are unrelated, grouped by chance

127. **Refinement vs. Refactoring:**
    - Refinement: Elaboration of details during initial design (top-down decomposition)
    - Refactoring: Restructuring existing code to improve structure without changing behavior

### Applications

128. **Module A passes a flag to Module B that controls B's execution logic. What type of coupling?** Control coupling — one module passes execution control (a flag) to another.

129. **A module groups three operations: generate report, send email, and print. They all run at startup. What type of cohesion?** Temporal cohesion — elements are grouped because they are processed at the same time.

130. **When would you choose a layered architecture pattern?** When the system can be decomposed into functional layers with well-defined interfaces, such as UI layer → business logic layer → data access layer. Each layer only communicates with adjacent layers.

131. **When would you use MVC (Model-View-Controller)?** When you need separation of concerns for user interfaces: Model (data), View (presentation), Controller (input handling). Common in web applications.

---

## 10. UI DESIGN

### Definitions

132. **What are Theo Mandel's three golden rules of UI design?** (1) Place the user in control, (2) Reduce user's memory load, (3) Make the interface consistent.

133. **What is the user model in UI design?** A profile of all end users (age, gender, abilities, education, preferences).

134. **What is the mental model (system perception)?** The user's mental image of what the interface is.

135. **What is the implementation model?** The interface "look and feel" coupled with supporting information describing interface syntax and semantics.

136. **What is task analysis?** Understanding what work the user performs, what tasks support the work, what problem-domain objects are manipulated, and the workflow sequence.

137. **What are the four steps of UI analysis & design?** Interface analysis & modeling, interface design, interface construction (prototyping), and interface validation. It is iterative (spiral model).

### Comparisons

138. **User model vs. Mental model:**
    - User model: What we know about users (objective profile)
    - Mental model: What users think the system is (subjective perception)
    - Effective design: User mental model and implementation model coincide

### Applications

139. **A user must enter state as a free-text field. Apply golden rules.** Replace with a dropdown (Reduce memory load). Label clearly "Select State" (Consistency). Allow user to see options without memorizing (Control).

140. **Why should Ctrl+S always mean Save?** Consistency principle — past interactive models create user expectations. Redefining established shortcuts causes errors and frustration.

---

## 11. QUALITY MANAGEMENT

### Definitions

141. **What is software quality?** The degree to which software possesses attributes satisfying customer expectations: reliability, efficiency, integrity, usability, maintainability, flexibility, testability, portability, reusability, interoperability.

142. **What is a product standard?** Standards for the software product itself (documentation standards, coding standards).

143. **What is a process standard?** Standards for the development process (development lifecycle standards).

144. **What is ISO 9001?** A quality management system standard specifying requirements for certification.

145. **What is process-based quality?** Quality achieved through quality processes, not just inspection of the final product.

### Applications

146. **Give an example of a quality trade-off.** Efficiency vs. maintainability: highly optimized code is often harder to read and maintain. Speed vs. security: additional security checks add processing overhead.

---

## 12. TESTING TOOLS & PATH TESTING

### Definitions

147. **What is JMeter?** A tool for load testing — creating test plans, thread groups, samplers, and listeners for performance testing.

148. **What is statement coverage?** Ensuring every statement in the program is executed at least once.

149. **What is branch coverage?** Ensuring every branch (true/false) of every decision is taken at least once.

150. **What is path coverage?** Ensuring every possible path through the program is executed at least once.

151. **What is a program flow graph?** A graph where nodes represent program decisions/statements and arcs represent flow of control.

### Applications

152. **For a program with 3 predicate nodes, how many independent paths exist in the basis set?** V(G) = 3 + 1 = 4 independent paths.

153. **Given the binary search flow graph with nodes 1-14, identify four independent paths:**
    - Path 1: 1-2-3-4-5-6-7-8-9-10-14 (key found on first iteration)
    - Path 2: 1-2-3-4-5-14 (key not found immediately)
    - Path 3: 1-2-3-4-5-6-7-11-12-5-... (search right half)
    - Path 4: 1-2-3-4-5-6-7-11-13-5-... (search left half)

---

## CROSS-TOPIC TRADEOFF QUESTIONS

154. **When would you NOT use agile development?** When requirements are fixed and well-understood upfront, when regulatory documentation is mandatory, when safety-critical systems require complete specification and verification, or when the team is distributed with poor communication infrastructure.

155. **Trade-off: High cohesion vs. Low coupling — why are both desirable?** High cohesion means each module does one thing well (easier to understand and maintain). Low coupling means modules are independent (changes in one don't ripple to others). Together they make the system modular, testable, and maintainable.

156. **Trade-off: Documentation vs. Working software (Agile value).** Too little documentation makes maintenance and handover difficult. Too much documentation wastes time and becomes outdated. Agile values working software but doesn't eliminate documentation — it prioritizes enough documentation for the team's needs.

157. **Trade-off: Early delivery vs. Quality (risk management).** Shipping early may satisfy the market but increase defect-related costs later. Risk management helps balance: identify high-impact risks, mitigate them, and deliver incrementally with quality gates.

158. **Trade-off: Waterfall's documentation discipline vs. Agile's flexibility.** Waterfall provides clear audit trails and traceability (good for regulated industries). Agile provides rapid feedback and adaptation (good for uncertain requirements). Many organizations use hybrid approaches.

159. **When is reuse-oriented development risky?** Requirements compromises are inevitable (system may not meet real user needs), loss of control over evolution of reused elements, and potential integration issues with COTS components.

160. **Trade-off: LOC estimation simplicity vs. FP estimation accuracy.** LOC is easy to count but language-dependent and doesn't reflect functionality. FP is language-independent and functionality-focused but requires more effort and expertise to calculate.

---

## QUICK-FIRE DEFINITION RECALL (Bonus Set)

161. **Software process model** — Abstract representation of a process from a particular perspective
162. **Cyclomatic complexity** — Number of independent paths = predicate nodes + 1
163. **Risk exposure formula** — RE = P × C
164. **VAF formula** — VAF = 0.65 + (0.01 × ΣFi)
165. **UFC formula** — UFC = Σ(count × weight) for 5 information domain types
166. **FP formula** — FP = UFC × VAF
167. **Total Float formula** — TF = LF - EF or TF = LS - ES
168. **Expected LOC (PERT)** — (Optimistic + 4×MostLikely + Pessimistic) / 6
169. **Content coupling** — One module relies on/modifies internal workings of another (worst)
170. **Functional cohesion** — All elements contribute to one well-defined task (best)
171. **Agile Manifesto value** — Individuals over processes, Working software over documentation, Collaboration over negotiation, Change over plan
172. **Verification question** — "Are we building the product right?"
173. **Validation question** — "Are we building the right product?"
174. **COTS** — Commercial Off-The-Shelf software components
175. **Refactoring** — Improving code structure without changing behavior
