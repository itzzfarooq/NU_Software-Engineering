# Active Recall Question Bank — Software Engineering

---

## Topic 1: Introduction to Software Engineering

**Q1: What is software engineering?**
A: Software engineering is an engineering discipline concerned with all aspects of software production, from early-stage system specification through maintaining the system after it has gone into use.

**Q2: What are the four fundamental software engineering activities?**
A: Software specification, software development, software validation, and software evolution.

**Q3: List the essential attributes of good software.**
A: Maintainability (can evolve to meet changing needs), dependability and security (reliable, safe, secure), efficiency (no wasteful use of resources), and acceptability (understandable, usable, compatible).

**Q4: Differentiate between generic products and customized products.**
A: Generic products are stand-alone systems sold to any customer (e.g., PC software). Customized products are commissioned by a specific customer (e.g., air traffic control). For generic, the developer owns the specification; for customized, the customer owns it.

**Q5: What is the difference between software engineering and computer science?**
A: Computer science focuses on theory and fundamentals; software engineering is concerned with the practicalities of developing and delivering useful software.

**Q6: What is the difference between software engineering and system engineering?**
A: System engineering covers all aspects of computer-based systems development (hardware, software, process engineering). Software engineering is part of this broader process.

**Q7: What are the key challenges facing software engineering today?**
A: Coping with increasing diversity (heterogeneity), demands for reduced delivery times, and developing trustworthy software (security and trust).

**Q8: What approximate percentage of software costs go to development vs. testing vs. maintenance?**
A: Roughly 60% development costs, 40% testing costs. For custom software, evolution/maintenance costs often exceed development costs (60-70% of total lifecycle cost).

**Q9: What does "software dependability" include?**
A: Reliability, security, and safety. Dependable software should not cause physical or economic damage in the event of failure, and malicious users should not be able to access or damage the system.

**Q10: Why is software reuse the dominant approach for web-based systems?**
A: Systems are assembled from pre-existing software components/systems, reducing development time and cost.

**Q11: List the ACM/IEEE Code of Ethics requirements.**
A: Act in the best interests of client/employer; ensure software is trustworthy/dependable; respect intellectual property rights; only approve software if confident it is safe/reliable; maintain skills and professionalism.

**Q12: What does "heterogeneity" mean in software engineering?**
A: Systems must operate as distributed systems across networks with different types of computers and mobile devices.

**Q13: What is the difference between a stand-alone application and an interactive transaction-based application?**
A: Stand-alone runs on a local computer with all necessary functionality. Interactive transaction-based executes on a remote computer and is accessed by users from their own PCs/terminals (e.g., web applications).

**Q14: What is legacy software and why is it challenging?**
A: Old systems that remain in use, often business-critical, based on obsolete technology, with incomplete documentation and unavailable original developers.

**Q15: What is component-based software engineering (CBSE)?**
A: Design and development of systems using reusable software components that are independent, reusable units assembled to create larger systems through standard interfaces.

**Q16: True or False: The same software engineering techniques are appropriate for all types of systems.**
A: False. Different types of systems require different approaches. Games use prototypes; safety-critical systems require complete, analyzable specifications.

**Q17: What are the three software process models introduced in Chapter 1?**
A: Waterfall model (sequential phases), incremental development (iterative with interleaved activities), and reuse-oriented development (assembling from existing components).

**Q18: How has the web changed software engineering?**
A: Made software services available, enabled highly distributed service-based systems, led to advances in programming languages and software reuse, and enabled cloud computing (pay-per-use).

---

## Topic 2: Software Processes (Waterfall, Incremental, Reuse-Oriented)

**Q1: What is a software process model?**
A: An abstract representation of a software process that presents a description from some particular perspective.

**Q2: List the four basic process activities in software development.**
A: Specification (defining what the system should do), design and implementation (organizing and implementing the system), validation (checking it does what the customer wants), and evolution (changing the system in response to changing needs).

**Q3: What is the waterfall model and when is it appropriate?**
A: A plan-driven model with separate sequential phases (requirements → design → implementation → testing → maintenance). Appropriate when requirements are well-understood and changes will be limited. Used for large systems engineering projects at several sites.

**Q4: What is the main drawback of the waterfall model?**
A: Inflexible partitioning into distinct stages makes it difficult to respond to changing customer requirements.

**Q5: What are the phases of the waterfall model?**
A: Requirements analysis and definition, system and software design, implementation and unit testing, integration and system testing, operation and maintenance.

**Q6: List three benefits of incremental development.**
A: (1) Reduced cost of accommodating changing requirements. (2) Easier customer feedback on demonstrations. (3) More rapid delivery and deployment of useful software.

**Q7: What are two problems with incremental development?**
A: (1) The process is not visible — managers need regular deliverables to measure progress. (2) System structure degrades as new increments are added unless refactoring is performed.

**Q8: What is integration and configuration (reuse-oriented development)?**
A: Systems are assembled from existing configurable components or application systems (COTS), with reused elements configured to adapt behavior to user requirements.

**Q9: What are three types of reusable software?**
A: (1) Stand-alone application systems (COTS). (2) Collections of objects for component frameworks (.NET, J2EE). (3) Web services for remote invocation.

**Q10: What are the key process stages in reuse-oriented development?**
A: Requirements specification, software discovery and evaluation, requirements refinement, application system configuration, component adaptation and integration.

**Q11: State two advantages and two disadvantages of reuse-oriented development.**
A: Advantages: Reduced costs/risks (less developed from scratch), faster delivery. Disadvantages: Requirements compromises inevitable, loss of control over evolution of reused elements.

**Q12: What is the difference between plan-driven and agile processes?**
A: Plan-driven: all activities planned in advance, progress measured against plan. Agile: planning is incremental, easier to change process to reflect changing requirements.

**Q13: What are the four design activities?**
A: Architectural design (overall structure), interface design (user interactions), component design (system components), database design (system database).

**Q14: What is validation testing?**
A: The process of demonstrating that a system meets its requirements and is fit for purpose. It may take 30-50% of total development cost.

**Q15: List the testing stages in order.**
A: Module/unit testing → Integration testing → System testing → Acceptance testing.

**Q16: What are the three types of software maintenance?**
A: Corrective maintenance (fixing bugs), adaptive maintenance (adapting to new environments), perfective maintenance (adding new features).

**Q17: What is refactoring?**
A: Changing software to improve its structure without changing its functionality.

**Q18: What are the six SPICE capability levels?**
A: Level 0 — Incomplete, Level 1 — Performed, Level 2 — Managed, Level 3 — Defined, Level 4 — Quantitatively managed, Level 5 — Optimizing.

**Q19: What is the difference between software evolution and software servicing?**
A: Evolution involves changing the system to meet new requirements. Servicing involves keeping the system operational (fixing problems as they arise).

**Q20: What are the design principles guiding the design process?**
A: Separation of concerns, modularity, abstraction, information hiding, reuse, coupling and cohesion.

**Q21: What is the difference between coupling and cohesion?**
A: Coupling measures interdependencies between modules (prefer LOW coupling). Cohesion measures how well elements of a module work together as a functional unit (prefer HIGH cohesion).

---

## Topic 3: Agile Software Development (XP, Scrum, Agile Principles)

**Q1: What are the four values of the Agile Manifesto?**
A: (1) Individuals and interactions over processes and tools. (2) Working software over comprehensive documentation. (3) Customer collaboration over contract negotiation. (4) Responding to change over following a plan.

**Q2: List the five principles of agile methods.**
A: Customer involvement, incremental delivery, people not process, embrace change, maintain simplicity.

**Q3: What is Extreme Programming (XP) and its key practices?**
A: An agile method using extreme approaches: incremental planning (story cards), small releases, simple design, test-first development, refactoring, pair programming, collective ownership, continuous integration, sustainable pace, on-site customer.

**Q4: How often are increments delivered in XP?**
A: New versions may be built several times per day; increments are delivered to customers every 2 weeks.

**Q5: What is test-first development?**
A: An automated unit test framework is used to write tests for new functionality BEFORE that functionality is implemented. Tests must pass before code is accepted.

**Q6: What is refactoring in XP?**
A: Constant code improvement to keep code simple and maintainable. Developers continuously look for improvements and make them even without immediate need.

**Q7: What is pair programming?**
A: Two developers work together at one workstation. One drives (types code), the other watches (finds errors/improvements). They check each other's work.

**Q8: What is continuous integration?**
A: As soon as work on a task is complete, it is integrated into the whole system. All unit tests must pass after any integration.

**Q9: What is the difference between Scrum and XP?**
A: Scrum focuses on managing the development process (project management). XP focuses on technical practices (testing, refactoring, programming). They are complementary.

**Q10: What is a Scrum Sprint?**
A: A time-boxed period of 2-4 weeks during which a potentially shippable product increment is created.

**Q11: What are the three Scrum roles?**
A: Scrum Master (facilitates team process, protects team from interference), Product Owner (represents customer, manages backlog, decides priorities), Scrum Team (self-organizing, cross-functional, 5-7 people).

**Q12: What is a burndown chart?**
A: A chart showing work remaining over time. If it does not point downward, the team is behind schedule.

**Q13: What is a Sprint Retrospective?**
A: Meeting at end of each sprint where the team reflects on what went well and what could be improved.

**Q14: What are three problems with scaling agile methods?**
A: (1) Hard to maintain pair programming and collective ownership in large teams. (2) Communication overhead in large projects. (3) Large systems depend on legacy components developed with plan-driven approaches.

**Q15: What are the two strategies for scaling agile?**
A: Scale up — use agile for the whole system, adapting methods. Scale out — use agile for components but plan-driven approach for system integration.

**Q16: List the Scrum principles.**
A: Controlled chaos (team decides how to work), commitment (team commits to time-box goals), information radiator (visible status), time-boxing (fixed deadlines), emergent requirements, people not process.

**Q17: When is agile not suitable?**
A: Complex non-functional requirements, critical systems requiring extensive documentation, systems developed by separate teams, outsourced development (needs defined contract).

**Q18: What is the planning game in XP?**
A: A team-based estimation process: split stories into tasks, each member estimates, compare and discuss differences, allocate work to pairs.

**Q19: What is a user story?**
A: A short description of a feature from the user's perspective, typically following the format: "As a [role], I want [goal] in order to [reason]."

**Q20: What is sustainable pace?**
A: Large amounts of overtime are not acceptable as it reduces code quality and medium-term productivity. A software project is a marathon, not a sprint.

---

## Topic 4: Agile vs Traditional (17 Differences)

**Q1: How does team structure differ between traditional and agile?**
A: Traditional: hierarchical (analyst, designer, coder, tester, architect, team lead, QA manager, PM). Agile: whole team, self-organizing, customer is a team member.

**Q2: How are requirements captured in traditional vs agile?**
A: Traditional: requirements captured and written by analyst/PM, verified from customer. Agile: user stories written by customers on index cards.

**Q3: How do development iterations differ?**
A: Traditional: 2-3 month iterations, first iteration is detailed design/plan. Agile: short cycles of 1-4 weeks, each producing working software.

**Q4: How do acceptance tests differ?**
A: Traditional: initial contracted requirements used as acceptance tests at end. Agile: acceptance tests written by BAs, QA, testers during iteration; once passed, never allowed to fail again.

**Q5: How does programming style differ?**
A: Traditional: each coder assigned task by team lead/PM, QA team checks errors. Agile: pair programming — two programmers at same workstation.

**Q6: How does testing differ?**
A: Traditional: test cases at prototype approval, then code written, QA tests for errors. Agile: Test-Driven Development — write failing unit test first, then write code to make it pass.

**Q7: How does ownership differ?**
A: Traditional: manager is solely responsible for the whole project. Agile: collective ownership — no individual responsible for one module; everyone works on everything.

**Q8: How does integration differ?**
A: Traditional: integration at end of module/project by QA team. Agile: continuous integration — code checked in and integrated several times per day.

**Q9: How does development pace differ?**
A: Traditional: 80/20 principle — high speed early, moderate in middle, speed up at end. Agile: sustainable pace — no overtime; team maintains constant pace.

**Q10: How does workspace differ?**
A: Traditional: separate rooms/cubicles, tasks assigned by PM or software. Agile: open workspace — team works together in open room with status charts, task breakdowns visible.

**Q11: How does design/architecture differ?**
A: Traditional: design and architect the whole project at beginning. Agile: simple design — focus only on current iteration stories, migrate design iteration to iteration.

**Q12: How does refactoring differ?**
A: Traditional: done at end of project, initiated by QA. Agile: continuous refactoring — done every hour/half hour to keep code clean, simple, expressive.

**Q13: How does documentation differ?**
A: Traditional: intensive documentation of diagrams and specifications. Agile: light documentation — produce no document unless its need is immediate and significant.

**Q14: How does task allocation differ?**
A: Traditional: PM/team lead assigns tasks to team. Agile: task selection — team decides/selects how much work they commit to complete.

**Q15: How does progress monitoring differ?**
A: Traditional: monitored by how many tasks are developed. Agile: burndown chart — shows work remaining each day in hours/days.

**Q16: How do status meetings differ?**
A: Traditional: weekly meetings, everyone reports to PM. Agile: daily standup — each member reports: (1) what done since last meeting, (2) what aiming to do, (3) any blocks.

**Q17: How is project status shown?**
A: Traditional: shown by number of tasks completed. Agile: status board — two sheets labeled "What's Working Well" and "What's Not Working, or Could Work Better."

---

## Topic 5: Architecture & Design

**Q1: What are the three characteristics of good design (Vitruvian)?**
A: Firmness (no bugs inhibiting function), Commodity (suitable for intended purpose), Delight (pleasurable user experience).

**Q2: List the 10 design concepts.**
A: Abstraction, Architecture, Design Patterns, Modularity, Information Hiding, Functional Independence, Refinement, Refactoring, OO Design Concepts, Design Classes.

**Q3: What is the 4+1 View Model?**
A: Logical view (end users — functionality), Development view (programmers — packaging/layering), Process view (system integrators — performance/scalability), Physical view (system engineers — topology/deployment), Scenarios (center — use cases tie views together).

**Q4: What is separation of concerns?**
A: Breaking a system into distinct features that overlap as little as possible, reducing complexity.

**Q5: What is information hiding?**
A: Designing modules so that algorithms and local data are inaccessible to other modules, enforcing access constraints and hiding design decisions.

**Q6: Describe the Layers architectural pattern.**
A: System divided into layers, each performing specific function. Layers arranged hierarchically — each layer uses services of layer below, provides services to layer above. Top layer = UI, bottom layer = system utilities.

**Q7: Describe the Model-View-Controller (MVC) pattern.**
A: Model — manages data and business logic, independent of UI. View — displays data, sends user actions to controller. Controller — handles user input, updates model, selects view.

**Q8: Describe the Client-Server pattern.**
A: System divided into servers (offer services) and clients (request services). Server always on, listens for requests. Client initiates communication via network.

**Q9: What is SOA (Service-Oriented Architecture)?**
A: Architectural style supporting service orientation. Services are discrete units of functionality accessed remotely. Principles: loose coupling, reusability, composability, statelessness.

**Q10: What are the principles of SOA?**
A: Loose coupling (minimal dependencies), reusability (services reusable across applications), composability (services composed into larger services), statelessness (no state maintained between requests).

**Q11: What is Microservices Architecture?**
A: Application structured as a collection of loosely coupled, independently deployable small services. Each performs a specific business function. Communicate via HTTP/REST or message queues.

**Q12: What is the Repository pattern?**
A: A central data store (repository) shared among several components. Components access data store through well-defined interfaces. Data store is passive; components are active.

**Q13: Describe the Pipe-and-Filter pattern.**
A: Each processing step encapsulated in a filter component. Data passed between adjacent components via pipes. No shared state between filters. Filters are independent, reusable, replaceable.

**Q14: What is the Broker pattern?**
A: A broker acts as mediator between client and server. It forwards requests, provides interface repository, hides communication details, locates servers.

**Q15: List the quality attributes affected by architectural design.**
A: Performance, scalability, extensibility, modifiability, testability, reusability, security, data integrity.

**Q16: What are the three types of architectural views?**
A: Module views (static organization), Component-and-Connector views (runtime behavior), Allocation views (software-to-hardware mapping).

**Q17: What is the Three-Tier Architecture?**
A: Extension of client-server. Three tiers: Presentation (UI), Application (business logic), Data (database). Each tier can be scaled independently.

**Q18: What is the Blackboard pattern?**
A: Three components: Knowledge Sources, Blackboard (central data store), Controller. Knowledge sources interact with blackboard; controller waits for changes and acts on them.

**Q19: What are design patterns?**
A: A reusable solution to a common design problem within a specific context. Documented with: pattern name, problem description, solution description, consequences.

**Q20: What questions should an architect answer in the first stage?**
A: (1) Who is the primary user? (2) What is the primary functionality? (3) What are the expected quality attributes? (4) What design principles will the system adhere to?

---

## Topic 6: UI Design

**Q1: What are the three golden rules of UI design?**
A: (1) Place the user in control. (2) Reduce the user's memory load. (3) Make the interface consistent.

**Q2: What does "place the user in control" mean?**
A: Define interactive modes with easy switching, allow flexible interaction (mouse, keyboard, voice), allow undo/redo, allow customization, hide technical internals, design for direct interaction.

**Q3: What does "reduce the user's memory load" mean?**
A: Use lists/checkboxes instead of text entry, establish meaningful defaults, define intuitive shortcuts, use real-world metaphors, disclose information progressively.

**Q4: What does "make the interface consistent" mean?**
A: Put tasks in meaningful context, maintain consistency across application family, don't change user expectations (Ctrl+S must remain save).

**Q5: What are the four UI design models?**
A: User model (end-user profile), Design model (design realization), Mental model (user's perception), Implementation model (look and feel + documentation).

**Q6: What are the three user types based on skill?**
A: Novice, knowledgeable intermittent users, knowledgeable frequent users.

**Q7: What are the four steps in the UI design process?**
A: Interface analysis, interface design, interface implementation (prototyping), interface validation. Iterative using the spiral model.

**Q8: What is Fitt's Law?**
A: The time to acquire a target is a function of the distance to the target and the size of the target.

**Q9: List five common UI design errors.**
A: Lack of consistency, too much memorization, no guidance/help, no context sensitivity, poor response time.

**Q10: What is latency reduction in UI design?**
A: Interface should multitask rather than keep user waiting. Display progress bars, animations to keep user focused during operations.

**Q11: What should a good error message include?**
A: Describe the problem simply, provide valuable advice, list negative consequences, be visually distinctive (color coding).

**Q12: What is the goal of user analysis?**
A: Understand who will use the system, their skill levels, business perception, user diversity, so the mental image and design model converge.

**Q13: What is the difference between length and variability of response time?**
A: Length — longer response times cause frustration. Variability — varying response times cause confusion (user wonders if something went wrong).

**Q14: List the revised UI design guidelines for web apps.**
A: Learnability, maintain work product integrity (autosave), readability, track state (cookies), visible navigation.

**Q15: What is the UI design workflow?**
A: Derive info from requirements → develop rough layout sketch → map user objectives to actions → create storyboard → refine layouts → develop activity diagram → develop state diagram → describe layout for each state → refine and review.

---

## Topic 7: Testing

**Q1: What is the fundamental limitation of testing?**
A: Testing can reveal the presence of errors, NOT their absence.

**Q2: What is the difference between validation and verification?**
A: Verification: "Are we building the product right?" (conforms to specification). Validation: "Are we building the right product?" (does what the user really requires).

**Q3: What is the difference between validation testing and defect testing?**
A: Validation testing: demonstrate system meets requirements (test cases reflect expected use). Defect testing: discover situations where behavior is incorrect (deliberately obscure test cases).

**Q4: What are the three stages of development testing?**
A: Unit testing (individual components), Component testing (integrated units, focus on interfaces), System testing (some/all components integrated, focus on interactions).

**Q5: What is test-driven development (TDD)?**
A: Approach where tests are developed BEFORE code. Steps: write test → run test (fails) → implement code → run test (passes) → refactor → next increment.

**Q6: What are four benefits of TDD?**
A: Code coverage (all code tested), regression testing (incremental test suite), simplified debugging (problem localized in recent code), system documentation (tests describe what code does).

**Q7: What is the difference between alpha testing and beta testing?**
A: Alpha testing: potential users test at the developer's location. Beta testing: release tested at potential users' sites, exposing system to larger/more representative users.

**Q8: What is acceptance testing?**
A: Customer formally accepts the system from suppliers as part of handover. For custom software, based on pre-agreed contract tests.

**Q9: What is the difference between unit testing and integration testing?**
A: Unit testing tests individual components in isolation. Integration testing tests interactions between components.

**Q10: What are the three automated test components?**
A: Setup (initialize system with inputs/expected outputs), Call (call object/method to test), Assertion (compare result with expected result).

**Q11: What is regression testing?**
A: Re-running all existing tests after code changes to ensure new changes have not introduced new bugs.

**Q12: What are inspections in testing?**
A: Static verification — people examine source representation (requirements, design, code) without executing the system to discover anomalies and defects.

**Q13: What are the advantages of inspections over testing?**
A: (1) Errors don't mask other errors (static process). (2) Incomplete versions can be inspected. (3) Can assess broader quality attributes (standards compliance, portability).

**Q14: What is basis path testing?**
A: Steps: (1) Draw control flow graph to determine program paths. (2) Find a basis set of independent paths. (3) Generate test cases to exercise each path.

**Q15: What is error guessing?**
A: Using knowledge of the system, platform, and domain to derive test cases likely to cause errors (e.g., zero input, huge numbers, alphabetic characters in numeric fields).

**Q16: What are the three reliability metrics?**
A: Mean Time to Failure (MTTF), Failure intensity, Probability of Failure on Demand (POFOD).

**Q17: What is an operational profile?**
A: A specification of how a system is used — defines types of user interactions, their frequency, and expected response time.

**Q18: What is penetration testing?**
A: Security testing where testers examine the system to find security weaknesses and exploit them to gain access.

**Q19: What is the difference between release testing and system testing during development?**
A: System testing during development is primarily defect testing by the development team. Release testing is primarily validation by a separate team.

**Q20: What is the testing process model?**
A: Design test cases → Prepare test data → Run program with test data → Compare results to test cases → Test reports.

---

## Topic 8: Quality Management

**Q1: What is quality management?**
A: An independent check on the software development process that checks project deliverables for consistency with organizational standards and goals.

**Q2: Why should the quality team be independent from the development team?**
A: To take an objective view of the software and report on quality without being influenced by development issues.

**Q3: List the software quality attributes.**
A: Safety, Security, Reliability, Resilience, Robustness, Understandability, Testability, Adaptability, Modularity, Complexity, Portability, Usability, Reusability, Efficiency, Learnability.

**Q4: Why is it impossible to optimize for all quality attributes?**
A: Quality conflicts exist — e.g., improving robustness may lead to loss of performance. The quality plan must define the most important attributes.

**Q5: What are product standards vs process standards?**
A: Product standards apply to the software product (document structure, coding standards). Process standards define the processes to follow (specification, design, validation processes).

**Q6: What is ISO 9001?**
A: An international standard that applies to organizations that design, develop, and maintain products. A framework for developing software standards.

**Q7: What are the ISO 9001 core processes?**
A: Business acquisition, Design and development, Business management, Supplier management, Production and delivery, Test, Service and support, Configuration management, Inventory management.

**Q8: What is the process-based quality model?**
A: Define process → Develop product → Assess product quality → Quality OK? → Yes: Standardize process / No: Improve process.

**Q9: What is the importance of standards?**
A: (1) Encapsulation of best practice — avoids repeating mistakes. (2) Framework for defining quality. (3) Provides continuity — new staff can understand the organization through standards.

**Q10: What is ISO 9001 certification?**
A: An external body certifies that an organization's quality manual conforms to ISO 9000 standards.

---

## Topic 9: Project Management (WBS, Planning, Scheduling, CPM)

**Q1: What is the difference between plan, estimate, and schedule?**
A: Plan: Identify activities (no specific dates). Estimate: Determine size/duration of activities. Schedule: Add specific start/end dates, relationships, and resources.

**Q2: What is a Work Breakdown Structure (WBS)?**
A: A deliverable-oriented decomposition of a project into smaller, manageable components organized in a hierarchy. Lowest level = work packages that can be estimated, scheduled, and tracked.

**Q3: What are the goals of a WBS?**
A: Give visibility to important/risky work efforts, illustrate correlation between activities and deliverables, show clear ownership, enable effective delegation, ensure nothing is forgotten.

**Q4: What is a work package?**
A: A group of related tasks at the same level within a WBS, measurable and definable, used for estimates and schedule monitoring.

**Q5: What are the common pitfalls in creating a WBS?**
A: Wrong level of work package detail, focusing on activities instead of deliverables, treating WBS as a plan/schedule, ignoring change control, treating WBS as an organizational hierarchy.

**Q6: What is a WBS dictionary?**
A: Companion document describing each WBS element — includes statement of work, associated activities, milestones, responsible organization, start/end dates, resources.

**Q7: What are the four common elements in the project life cycle?**
A: Defining (goals, specifications, tasks, responsibilities), Planning (schedule, budget, resources, risks, staff), Executing (status reports, quality, changes, reviews), Closing (train customer, transfer documents, release resources).

**Q8: What is CPM (Critical Path Method)?**
A: A scheduling technique that determines the longest path through the network, identifies tasks that cannot be delayed, and calculates slack/float time.

**Q9: What is the critical path?**
A: The longest path through the activity network. Tasks on this path have zero slack/float — any delay delays the entire project.

**Q10: What is early start (ES) and early finish (EF)?**
A: ES = earliest time an activity can start (forward pass). EF = ES + duration.

**Q11: What is late start (LS) and late finish (LF)?**
A: LF = latest time an activity can finish without delaying project. LS = LF - duration (backward pass).

**Q12: What is total float (slack) and free float?**
A: Total Float = LF - EF or LS - ES (delay without delaying project). Free Float = min(ES_successors) - ES_activity - Duration (delay without affecting next activity's early start).

**Q13: What is resource leveling?**
A: Resolving resource conflicts and balancing resource usage. May extend project duration and increase cost.

**Q14: What are the three types of estimates and their accuracy ranges?**
A: Rough Order of Magnitude (-25% to +75%), Budget Estimate (-10% to +25%), Definitive Estimate (-5% to +10%).

**Q15: What is Earned Value Management (EVM)?**
A: Measures: Planned Value (PV), Earned Value (EV), Actual Cost (AC). Schedule Variance (SV) = EV - PV. Cost Variance (CV) = EV - AC.

**Q16: What is the Wideband Delphi technique?**
A: Consensus-based estimation: (1) Choose team (3-7 members + moderator). (2) Kickoff meeting. (3) Individual preparation. (4) Multi-round estimation session with convergence. (5) Assemble tasks. (6) Review results.

**Q17: What are the rules for creating an activity network diagram?**
A: Flow left to right; activity cannot begin until all predecessors done; arrows can overlap; every activity must have an ID; no looping; ID > preceding activity ID.

**Q18: What is a Gantt chart?**
A: A bar chart showing tasks over calendar time, with horizontal bars representing each activity's duration.

---

## Topic 10: Estimation (LOC, FP, COCOMO)

**Q1: What are the two main measures used for project size estimation?**
A: Lines of Code (LOC) and Function Points (FP).

**Q2: What is the three-point LOC estimation formula?**
A: Expected LOC = (S_optimistic + 4 x S_most_likely + S_pessimistic) / 6

**Q3: What are the advantages and disadvantages of LOC?**
A: Advantages: Easy to count and calculate. Disadvantages: Highly dependent on programming language, not a good metric for estimation across languages.

**Q4: What are the five information domain values in Function Point Analysis?**
A: External Inputs (EI), External Outputs (EO), External Inquiries (EQ), Internal Logical Files (ILF), External Interface Files (EIF).

**Q5: What is the Function Point formula?**
A: FP = UFP x CAF, where CAF = 0.65 + (0.01 x sum of Fi) and Fi are 14 complexity adjustment factors rated 0-5.

**Q6: What is the range of CAF?**
A: Minimum 0.65 (when sum Fi = 0) to maximum 1.35 (when sum Fi = 70).

**Q7: What are the weighting factors for Simple, Average, and Complex?**
A: EI: 3,4,6. EO: 4,5,7. EQ: 3,4,6. ILF: 7,10,15. EIF: 5,7,10.

**Q8: Name three advantages of FP over LOC.**
A: (1) Independent of programming language. (2) Better for estimation (functional size). (3) Measures what the user needs, not implementation details.

**Q9: What is COCOMO?**
A: Constructive Cost Model — an algorithmic cost model that estimates effort, development time, and staff size based on project size (KLOC) and project mode.

**Q10: What are the three COCOMO project modes?**
A: Organic (familiar team, small, simple), Semi-detached (mixed), Embedded (highly complex, unfamiliar team).

**Q11: What are the COCOMO basic effort equations?**
A: Effort = a x (KLOC)^b where:
- Organic: a=2.4, b=1.05
- Semi-detached: a=3.0, b=1.12
- Embedded: a=3.6, b=1.20

**Q12: What is the COCOMO development time equation?**
A: Time = c x (Effort)^d where:
- All modes: c=2.5
- Organic: d=0.38
- Semi-detached: d=0.35
- Embedded: d=0.32

**Q13: What is average staff size in COCOMO?**
A: S = Effort / Development Time

**Q14: What are the three COCOMO II models?**
A: Application Composition (early prototype stage), Early Design (requirements understood, basic architecture), Post-Architecture (detailed design available).

**Q15: What are the COCOMO II scale factors?**
A: Precedentedness (PREC), Development Flexibility (DFLEX), Architecture/Risk Resolution (RESL), Team Cohesion (TEAM), Process Maturity (PMAT).

**Q16: How do you compute the COCOMO II exponent B?**
A: B = 0.91 + 0.01 x (sum of five scale factors)

**Q17: What are the four categories of COCOMO II cost drivers?**
A: Product factors (RELY, DATA, CPLX, RUSE, DOCU), Platform factors (TIME, STOR, PVOL), Personnel factors (ACAP, PCAP, AEXP, PEXP, LTEX), Project factors (TOOL, SITE, SCED).

**Q18: What is the relationship between FP and LOC?**
A: They can be converted using language-specific ratios. Example: 1 FP = 60 lines of Java code (varies by language).

**Q19: How do you calculate cost per LOC?**
A: Cost per LOC = Cost per person-month / (LOC per person-month)

**Q20: What are the seven cost estimation strategies?**
A: Algorithmic cost modeling, expert judgment, estimation by analogy, Parkinson's Law, price-to-win, top-down estimation, bottom-up estimation.

---

## Topic 11: Risk Management

**Q1: What is risk in software engineering?**
A: A potential problem — an uncertainty that may or may not occur, but if it does, has a negative impact on the project.

**Q2: What are the two characteristics of risk?**
A: Uncertainty (the risk may or may not happen — no 100% risks) and Loss (if the risk becomes reality, unwanted consequences occur).

**Q3: What is the Risk Exposure formula?**
A: RE = P x C where P = probability of occurrence, C = cost to the project if the risk occurs.

**Q4: Give an example of calculating Risk Exposure.**
A: If 18 components need custom development, each 100 LOC at $14/LOC, impact = $25,200. Probability = 80%. RE = 0.80 x $25,200 = $20,200.

**Q5: What is reactive risk management?**
A: Project team reacts to risks when they occur. May involve mitigation (planning resources for firefighting), fix-on-failure, or crisis management.

**Q6: What is proactive risk management?**
A: Formal risk analysis is performed, organization corrects root causes of risk (TQM, statistical SQA), develops skill to manage change.

**Q7: List the seven principles of risk management.**
A: (1) Maintain global perspective. (2) Take forward-looking view. (3) Encourage open communication. (4) Integrate risk into software process. (5) Emphasize continuous process. (6) Develop shared product vision. (7) Encourage teamwork.

**Q8: What are the three categories of risk?**
A: Project risks (affect schedule/resources), Product risks (affect quality/performance), Business risks (affect organization developing or procuring software).

**Q9: List the risk management process steps.**
A: Risk identification → Risk analysis → Risk planning → Risk monitoring. Also: track and control (5-part paradigm).

**Q10: What are the seven risk identification categories?**
A: Product size, business impact, customer characteristics, process definition, development environment, technology to be built, staff size and experience.

**Q11: What are known, predictable, and unpredictable risks?**
A: Known: uncovered by careful evaluation (e.g., unrealistic deadlines). Predictable: extrapolated from past experience (e.g., staff turnover). Unpredictable: extremely difficult to identify in advance.

**Q12: What are the four risk components?**
A: Performance risk (meeting requirements), Cost risk (staying within budget), Support risk (ease of correction/adaptation), Schedule risk (on-time delivery).

**Q13: What is a risk table?**
A: Columns: Risk Summary, Risk Category, Probability, Impact (1-5 scale, 1=low, 5=catastrophic), RMMM reference. Sorted by probability and impact.

**Q14: What are the four impact levels?**
A: Negligible, marginal, critical, catastrophic.

**Q15: What is the difference between risk mitigation, monitoring, and management (RMMM)?**
A: Mitigation — how to avoid the risk (proactive steps). Monitoring — what factors to track to determine if risk is becoming more/less likely. Management — contingency plans if risk becomes reality.

**Q16: What is the difference between a problem and a risk?**
A: A problem has already occurred. A risk is something that is unpredictable — it might happen and it might not.

**Q17: What are the sub-categories of business risks?**
A: Market risk (building product no one wants), Strategic risk (product no longer fits business strategy), Sales risk (sales force doesn't understand how to sell), Management risk (losing senior management support), Budget risk (losing budgetary commitment).

**Q18: What are the risk projection steps?**
A: (1) Establish scale for likelihood. (2) Delineate consequences. (3) Estimate impact on project/product. (4) Note overall accuracy.

**Q19: What questions should be asked to assess project risk?**
A: Are top software/customer managers committed? Are end-users enthusiastically committed? Are requirements fully understood? Is scope stable? Does the team have the right skills? Are requirements stable?

**Q20: What are example risk strategies?**
A: Staff turnover → reorganize for overlap. Defective components → replace with bought-in reliable components. Requirements changes → traceability, information hiding. Budget cuts → briefing documents on project importance.