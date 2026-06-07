# UI Design — Mind Map

```
                                    +================================+
                                    |      USER INTERFACE DESIGN     |
                                    |  "Bridge between human & machine"|
                                    +================================+
                                             |
             +-------------------------------+-------------------------------+
             |                               |                               |
             v                               v                               v
+------------------------+   +-----------------------------+   +-----------------------------+
|    GOLDEN RULES        |   |      UI DESIGN MODELS       |   |    UI DESIGN PROCESS         |
| (Theo Mandel)          |   |                             |   |    (Iterative / Spiral)      |
+------------------------+   +-----------------------------+   +-----------------------------+
  |                         |                                 |                               |
  |  +------------------+   |  +--------------------------+   |  +-------------------------+ |
  |  | 1. User Control   |   |  | User Model               |   |  | Phase 1: Analysis        | |
  |  |                   |   |  | - End user profile       |   |  | - User analysis          | |
  |  | +---------------+ |   |  | - Age, gender, edu,      |   |  | - Task analysis          | |
  |  | | Modes         | |   |  |   culture, physical,     |   |  | - Display content       | |
  |  | | Flex          | |   |  |   preferences            |   |  | - Work environment      | |
  |  | | interaction   | |   |  | - User types:            |   |  +-------------------------+ |
  |  | | Interruptible | |   |  |   Novice                 |   |            |                  |
  |  | | Undoable      | |   |  |   Knowledgeable int.     |   |            v                  |
  |  | | Customization | |   |  |   Knowledgeable freq.    |   |  +-------------------------+ |
  |  | | Hide tech     | |   |  +--------------------------+   |  | Phase 2: Design          | |
  |  | | Direct manip. | |   |  | Design Model              |   |  | - Define objects/actions| |
  |  | +---------------+ |   |  | - Designer's translation  |   |  | - Define events         | |
  |  +------------------+   |  | - Interface objects & ops  |   |  | - Depict states         | |
  |                         |  +--------------------------+   |  | - Use design patterns   | |
  |  +------------------+   |  | Mental Model (System       |   |  +-------------------------+ |
  |  | 2. Reduce Memory  |   |  | Perception)                |   |            |                  |
  |  | Load              |   |  | - User's image of system  |   |            v                  |
  |  |                   |   |  +--------------------------+   |  +-------------------------+ |
  |  | +---------------+ |   |  | Implementation Model      |   |  | Phase 3: Construction   | |
  |  | | List/checkbox | |   |  | - Look & feel             |   |  | - Prototyping           | |
  |  | | Defaults      | |   |  | - Manuals, help, docs     |   |  | - Use-case scenarios   | |
  |  | | Shortcuts     | |   |  +--------------------------+   |  +-------------------------+ |
  |  | | Real-world    | |   |                                 |            |                  |
  |  | |   metaphor    | |   |  GOAL: Mental Model ≈          |            v                  |
  |  | | Progressive   | |   |  Implementation Model          |  +-------------------------+ |
  |  | |   disclosure  | |   |                                 |  | Phase 4: Validation     | |
  |  | +---------------+ |   |                                 |  | - Task accommodation   | |
  |  +------------------+   |                                 |  | - Ease of use/learn    | |
  |                         |                                 |  | - User acceptance      | |
  |  +------------------+   |                                 |  +-------------------------+ |
  |  | 3. Consistency   |   |                                 |                               |
  |  |                   |   |                                 +-------------------------------+
  |  | +---------------+ |   |
  |  | | Task context  | |   |
  |  | | Cross-app     | |   |
  |  | |   consistency| |   |
  |  | | Respect past  | |   |
  |  | |   experience  | |   |
  |  | +---------------+ |   |
  |  +------------------+   |
  +------------------------+
             |
             +------------------------------------+------------------------------------+
             |                                    |                                    |
             v                                    v                                    v
+---------------------------+   +--------------------------------+   +-----------------------------+
|    TASK ANALYSIS &        |   |       DESIGN ISSUES            |   |   DESIGN PRINCIPLES         |
|    MODELING               |   |                                |   |                             |
+---------------------------+   +--------------------------------+   +-----------------------------+
  |                         |     |                             |     |              |              |
  |  +--------------------+ |     |  +-----------------------+  |     |  +---------+ +----------+  |
  |  | 5 Key Questions    | |     |  | 1. Response Time      |  |     |  | Primary | | WebApp   |  |
  |  | - What work?       | |     |  |    - Length           |  |     |  |         | | Specific |  |
  |  | - What tasks?      | |     |  |    - Variability      |  |     |  | +-----+ | | +------+ |  |
  |  | - What objects?    | |     |  +-----------------------+  |     |  | | Ant | | | |Learn | |  |
  |  | - What sequence?   | |     |  | 2. Help Facilities    |  |     |  | +-----+ | | +------+ |  |
  |  | - What hierarchy?  | |     |  |    - Availability     |  |     |  | +-----+ | | +------+ |  |
  |  +--------------------+ |     |  |    - How requested    |  |     |  | | Com | | | |Work  | |  |
  |                         |     |  |    - How presented    |  |     |  | +-----+ | | |Prod  | |  |
  |  +--------------------+ |     |  |    - Return path      |  |     |  | +-----+ | | |Integ | |  |
  |  | Techniques         | |     |  +-----------------------+  |     |  | | Con | | | +------+ |  |
  |  | - Use-cases        | |     |  | 3. Error Handling     |  |     |  | +-----+ | | +------+ |  |
  |  | - Task elaboration  | |     |  |    - Explain problem  |  |     |  | |CAut | | | |Read  | |  |
  |  | - Object elabor.   | |     |  |    - Provide remedy   |  |     |  | +-----+ | | +------+ |  |
  |  | - Workflow (swim)  | |     |  |    - Consequences     |  |     |  | +-----+ | | +------+ |  |
  |  | - User interviews  | |     |  |    - Visual cues      |  |     |  | | Eff | | | |Track | |  |
  |  | - Market/sales     | |     |  +-----------------------+  |     |  | +-----+ | | |State | |  |
  |  | - Support feedback | |     |  | 4. Menu & Command     |  |     |  | +-----+ | | +------+ |  |
  |  +--------------------+ |     |  |    Labeling            |  |     |  | | Foc | | | +------+ |  |
  |                         |     |  +-----------------------+  |     |  | +-----+ | | |VisNv | |  |
  |  +--------------------+ |     |  | 5. Accessibility      |  |     |  | +-----+ | | +------+ |  |
  |  | Swimlane Diagram   | |     |  |    - Voice input      |  |     |  | |Fitts| | +----------+  |
  |  | (Roles + States)   | |     |  |    - Screen readers   |  |     |  | +-----+ |              |
  |  | Author, Reviewer,  | |     |  |    - High-contrast    |  |     |  | +-----+ |              |
  |  | Approver, Owner    | |     |  |    - Keyboard nav     |  |     |  | | Lat | |              |
  |  | Draft -> Reviewed  | |     |  +-----------------------+  |     |  | | Red | |              |
  |  | -> Effective ->    | |     |  | 6. Internationaliz.  |  |     |  | +-----+ |              |
  |  | Archived           | |     |  |    - Multi-language   |  |     |  +---------+              |
  |  +--------------------+ |     |  |    - Global standards  |  |     |                           |
  +---------------------------+     |    - Cultural respect  |  |     +---------------------------+
                                    +-----------------------+  |
                                    +---------------------------+
             |
             v
+---------------------------------------+
|       AESTHETIC DESIGN                |
+---------------------------------------+
  |  +-------------------------------+  |
  |  | White space — reduces clutter |  |
  |  | Emphasize content             |  |
  |  | Top-left to bottom-right      |  |
  |  | Group elements geographically  |  |
  |  | Minimize scrolling            |  |
  |  | Consider resolution/browser   |  |
  +-----------------------------------+  |
+---------------------------------------+

===============================
        COMMON MISTAKES
===============================
  |
  +-- UI is just "making it pretty"
  +-- Ignoring user diversity
  +-- Inconsistent navigation
  +-- Memory overload
  +-- Bad error messages
  +-- Skipping prototyping
  +-- Forgetting accessibility
  +-- Ignoring internationalization
  +-- Varying response times

===============================
     KEY RELATIONSHIPS
===============================
  |
  +-- User Model informs Design Model
  +-- Design Model built as Implementation Model
  +-- Mental Model must align with Implementation Model
  +-- Golden Rules apply to ALL phases
  +-- Task Analysis feeds User Analysis
  +-- Design Issues constrain Design phase
  +-- Prototyping enables Validation
  +-- Validation feedback goes back to Analysis
```

*End of Mind Map*