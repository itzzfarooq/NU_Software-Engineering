# UI Design - Detailed Notes

## Interface Design Evolution

The evolution of interface design tells a story of transformation:

**Past (Technical-focused):**
- Initially users must adapt to complex systems
- Systems were built for technical users
- Users had to learn the system's language

**Present (Human-centered):**
- Now technology must consider human ease
- Usability matters a lot!
- Systems must adapt to users

This shift has led to issues observed in bad GUI designs: not user friendly, confusing, counterintuitive, and frustrating. To address these, a set of **golden rules** was defined and an **interaction mechanism** was created — the window world.

---

## Golden Rules of UI Design (by Theo Mandel)

Three fundamental principles form the foundation of good interface design:

| Principle | Focus |
|-----------|-------|
| **Principle 1** | Place the user in control |
| **Principle 2** | Reduce user's memory load |
| **Principle 3** | Make a consistent interface |

---

### Principle 1: Place the User in Control

This principle ensures users feel they are in charge of the interaction.

**1.1 Define Interactive Modes That Allow the User to Do Whatever They Want Freely**
- Define different modes and allow easy switching between modes
- Example: Spell check and editing modes in word processors, read mode, browser modes

**1.2 Allow Flexible Interaction**
- Allow users to interact via multiple ways: mouse, keyboard, digitizer pen, voice inputs, multitouch inputs

**1.3 Allow User Interaction to Be Uninterruptable and Undoable**
- Freely allows the user to quit a work and do another without losing changes
- Undo/redo also allowed

**1.4 Allow Customized Operations**
- Create macros for frequently occurring operations (e.g., MS Word macros)
- For advanced users to customize UI

**1.5 Hide Technical Internals from Casual Users**
- User is unaware of the underlying OS, file management operations, and other complexities
- Example: Application software doesn't require OS commands

**1.6 Design for Direct Interaction with On-Screen Objects**
- Icons or other objects could be dragged or scaled up or down as if they exist physically

---

### Principle 2: Reduce User's Memory Load

This principle ensures the system doesn't burden users with remembering information.

**2.1 Well-Designed System Doesn't Test User's Memory**
- Example: Use list boxes or checkbox inputs rather than text boxes

**2.2 Reduce Demand to Learn More**
- Users should not have to recall past inputs — they are saved and shown using visuals

**2.3 Establish Meaningful Defaults**
- User should have a preference to customize layout or change the default settings
- However, reset could change them to defaults again

**2.4 Define Intuitive Shortcuts**
- Bind shortcuts that are easy to remember like Ctrl+P for print

**2.5 Visual Layout Should Be Near to Real-Time Systems**
- Example: The bill paying process should be the same as in real life
- All steps must be fulfilled

**2.6 Disclose Information in a Progressive Fashion**
- Information displayed on multiple levels
- Example: E-commerce websites show pictures first, then detailed information on click, different options shown when clicked further

---

### Principle 3: Make a Consistent Interface

This principle ensures predictability and learnability.

**3.1 Allow Users to Put Tasks in Meaningful Context**
- User should have an idea of the work they are doing
- Windows should be labeled with titles, consistent color coding for the same tasks

**3.2 Maintain Consistency Across a Family of Applications**
- A set of applications must follow a particular pattern
- Example: Front and back view is the same across MS Office

**3.3 Don't Change the System Against User's Previous Habits**
- Don't redefine the user's past experiences in UI
- Example: Ctrl+S is used for save — don't bind it with scaling, as users expect it to save based on past experience

---

## UI Analysis & Design Process Flow

The process is iterative, using the **spiral process model**:

```
┌─────────────────────────────────────────────┐
│ 1. Segregate human-oriented and             │
│    computer-oriented tasks                  │
└───────────────────┬─────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────┐
│ 2. Think of design issues for UI design     │
└───────────────────┬─────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────┐
│ 3. Tools are used to prototype              │
└───────────────────┬─────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────┐
│ 4. Implement design model                   │
└───────────────────┬─────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────┐
│ 5. Users evaluate the design quality        │
└─────────────────────────────────────────────┘
```

Four main steps (iterative spiral):
1. **Interface analysis & modeling**
2. **Interface design**
3. **Interface construction** — involve prototyping approach
4. **Interface validation**

Since it's a spiral model, these steps need to be processed again and again for design betterment.

---

## UI Design Models

Four interconnected models:

| Model | Description |
|-------|-------------|
| **User Model** | Analyze all end user profiles (age, gender, physical abilities, education, culture, preferences) |
| **Design Model** | Design realization of end user's model |
| **System Perception / Mental Model** | End user's perspective of a system |
| **Implementation Model** | The interface look & feel along with supporting information (books, manuals, videotapes) showing interface semantics |

### User Types

| Type | Description |
|------|-------------|
| **Novice** | First-time or inexperienced users |
| **Knowledgeable, intermittent users** | Know the system but use it occasionally |
| **Knowledgeable, frequent users** | Regular power users |

> An effective design is one in which the **user mental model** and **implementation model coincide**.

---

## Interface Analysis

### User Analysis

Understand the problem before designing the solution:
- Understand **users of the system**
- The **system goals** (tasks)
- The **displayed content**
- The **environment** in which tasks are conducted

The mental image and the design model must converge. This can be achieved by understanding the users and how they use the system.

#### Sources of Information

| Source | Contribution |
|--------|-------------|
| **User interviews** | Development team members meet with end users to identify their needs and work culture |
| **Marketing & sales input** | Market survey to check how the product could be useful |
| **Support input** | Support staff takes feedback on what works, what doesn't, which features are easy to use |

#### User Analysis Questions

Key questions for better user categorization:
- Are users trained professionals, technicians, clerical, or manufacturing workers?
- Level of formal education of an average user?
- Are users capable of learning from written materials or do they prefer classroom training?
- Are users expert typists or keyboard-phobic?
- Age range of the user community?
- User's gender?
- How are users compensated for the work they perform?
- Working hours: normal office hours or until the job is done?
- Software usage frequency (mostly/occasionally)?
- Primary spoken language among users?
- Consequences of a user's mistake while using the system?
- Are users experts in the subject matter addressed by the system?
- Are users interested in learning about the technology behind the interface?

---

### Task Analysis

Detailed task analysis done after user analysis. The tasks that users will perform to accomplish system goals.

Task Analysis & Modelling answers:
- Task identification in specific circumstances
- Tasks and subtasks performed by user
- Sequence of work tasks — the workflow

#### Use-Cases
- Define basic interaction of actor and system
- Written using informal paragraphs
- Can be used to derive tasks, subtasks, and interfaces

#### Task Elaboration
- Stepwise elaboration or task refinement of interactive tasks
- Derive either manually or use a preexisting system to identify them

#### Object Elaboration
- Extract physical objects from system to define their classes and behavior

#### Workflow Analysis
- Defines how a work process is completed when several people (and roles) are involved
- Shown using **UML Swim Line Diagram**

---

### UML Swim Line Diagram

Example: Document Management System for ABC Co.

```
Role:     Author      │ Reviewer    │ Approver    │ Owner
──────────────────────┼─────────────┼─────────────┼─────────────
                      │             │             │
Create ──────────────►│             │             │
  │                   │             │             │
  ▼                   │             │             │
Document (Draft)      │             │             │
  │                   │             │             │
  ▼                   │             │             │
Update ───────────────┼──► Review   │             │
                      │    Draft    │             │
                      │             │             │
                      ▼             │             │
                Document (Reviewed) │             │
                      │             │             │
                      └─────────────┼──► Approve  │
                                    │             │
                                    ▼             │
                              Document (effective)│
                                    │             │
                                    └─────────────┼──► Archive
                                                  │
                                                  ▼
                                          Document (Archived)
```

Additional steps include change requests, review effective documents, and decision points at various stages.

---

### Display Content & Work Environment Analysis

**Analysis of Display Content:**
- Format of the content
- Aesthetics
- Content displayed using stepwise refinement approach

**Analysis of Physical Work Environment:**
- Work environment should be helpful in proper operation and concentration
- Must co-relate with the designed software aesthetics

---

## Interface Design Steps

Using information developed during interface analysis:

1. Define **interface objects** (buttons, text fields, video) and **operations** (tasks)
2. Define **events** (user actions) that will change the state of the UI
3. Depict each **interface state** as it will actually look to the end-user (using sketches)
4. Show how the user infers the **system state** from information provided through the interface

### Use-Case & Design Patterns

**Define the use-case:**
- Create the list of objects and actions
- These objects & actions are categorized into different types
- Identify which are source (e.g., printer icon), target (e.g., paper), and application objects (e.g., screen, entity/db table)

**Use UI design patterns:**
- A specific design pattern is formulated for a well-bounded solution
- Example: For a calendar UI, a Calendar Strip is created that allows traversal in future dates, marking the current one

---

## Design Issues

### 1. System Response Time

Primary complaint for almost every interactive system. Two characteristics:
- **Length**: Longer response times are not appreciated, leading to user frustration
- **Variability**: Varying response time leads to user confusion (whether something went wrong at backend)

### 2. Help Facilities

Online helpdesk and detailed user manuals. Design issues while providing help:
- Help availability for all functionalities?
- How will user demand help? (menu or function key)
- How is help presented? (another window or printed manual)
- How to return to normal UI after consulting help

### 3. Error Handling

Error messages & warnings are bad news to users. A good error message includes:
- **Describe problem** simply
- **Provide valuable advice**
- **List the negative consequences** of the error
- Message must **prompt visually** using color scheme that categorizes it as an error

| Bad Error Message | Good Error Message |
|-------------------|-------------------|
| "Whoops! Something went wrong" | "Unable to connect your account" |
| Passing the blame | "Your changes were saved, but we could not connect your account due to a technical issue on our end" |
| Technical jargon | "Please try connecting again" |
| Generic | "If the issue keeps happening, contact Customer Care" |
| Inappropriate tone | Buttons: Cancel, Try Again |

### 4. Menu & Command Labeling

Different styles like command-oriented and UI-based architecture. Both are used frequently. How commands are assigned to each menu item so that it may run without UI as well.

### 5. Application Accessibility

UI should cater the needs of physically challenged persons (e.g., voice inputs to facilitate handicapped).

### 6. Internationalization

UI must target the global market. Follow global design standards & facilitate multiple languages.

---

## Revised Interface Design Guidelines (8 Principles)

| # | Principle | Description |
|---|-----------|-------------|
| 1 | **Anticipation** | Application must depict the user's expected move. E.g., software installation procedures predict next step |
| 2 | **Communication** | Application must show the status of an activity initiated by user. E.g., file copying shown via progress bar |
| 3 | **Consistency** | Navigation controls, menu, icons, aesthetics should be consistent throughout. E.g., yellow triangle shows warning signs — use only for warnings |
| 4 | **Controlled Autonomy** | Revising golden rule: place user in control but restrict controls as per user's role. Enforce ID and password for no-go options |
| 5 | **Efficiency** | Design must work on user's efficiency. E.g., input CNIC or phone number without space or hyphen for less processing time |
| 6 | **Focus** | Interface should help user stay focused and give relevant options and data first |
| 7 | **Fitt's Law** | "The time to acquire a target is a function of the distance to the target and the size of the target" |
| 8 | **Latency Reduction** | Interface must multitask rather than keep user waiting. E.g., display progress bar or animated visuals |

---

## Web App Design Guidelines

| Guideline | Description |
|-----------|-------------|
| **Learnability** | Minimize learning time by creating simple & intuitive designs |
| **Maintain Work Product Integrity** | Interface should autosave user data. E.g., filling long forms and losing data on error leads to frustration |
| **Readability** | All information presented should be readable by all age group users |
| **Track State** | Cookies can track user activities so user may logout and continue from same state after logging in again |
| **Visible Navigation** | Obvious navigation bars mentioned on every interface of the application |

---

## Aesthetic Design Guidelines

- Visual layout should be near to real-time systems
- Consistent color coding
- Progressive disclosure of information
- Meaningful context for tasks

---

## Typical Design Errors

| Error | Description |
|-------|-------------|
| Ignoring user analysis | Not understanding who will use the system |
| Skipping prototyping | Going straight to implementation without validation |
| Inconsistent interface | Different look and feel across screens |
| Poor error handling | Unhelpful error messages |
| No undo/redo capability | Users can't recover from mistakes |
| Ignoring accessibility | Excluding users with disabilities |
| Overloading interface | Too much information on one screen |
| Not testing with real users | Assuming design works without validation |

---

## Interface Design Workflow

1. Derive and refine information from requirements
2. Develop rough layout sketch
3. Map user objective to actions (Home, Contact, booking, facilities)
4. Create storyboard screen images for every interface
5. Refine layouts by improving aesthetics
6. Develop an activity diagram to show the design flow
7. Develop state diagrams to show changes in state after transitions
8. Describe interface layout for every state
9. Refine & review the model

---

## Interface Design Evolution (Iterative Cycle)

```
┌────────────────────────────────────────────────────┐
│ 1. Preliminary design                              │
└───────────────────┬────────────────────────────────┘
                    │
                    ▼
┌────────────────────────────────────────────────────┐
│ 2. Build prototype #1 interface                    │
└───────────────────┬────────────────────────────────┘
                    │
                    ▼
┌────────────────────────────────────────────────────┐
│ 3. User evaluates interface                        │
└───────────────────┬────────────────────────────────┘
                    │
                    ▼
┌────────────────────────────────────────────────────┐
│ 4. Evaluation is studied by designer               │
└───────────────────┬────────────────────────────────┘
                    │
                    ▼
┌────────────────────────────────────────────────────┐
│ 5. Design modifications are made                   │
└───────────────────┬────────────────────────────────┘
                    │
                    ▼
┌────────────────────────────────────────────────────┐
│ 6. Build prototype #n interface                    │
└───────────────────┬────────────────────────────────┘
                    │
                    └──────────► (cycle repeats until
                                  interface design is
                                  complete)
```

---

## Key Connections

- **Golden Rules** (Mandel) provide foundational principles for all UI decisions
- **UI Design Models** (User → Design → System Perception → Implementation) ensure alignment between user needs and final product
- **Interface Analysis** (User, Task, Environment) feeds into **Interface Design Steps**
- **Design Issues** (response time, help, error handling) are addressed by the **Revised Guidelines**
- **Web App Guidelines** extend general guidelines for web-specific contexts
- The **iterative spiral process** ensures continuous improvement through prototyping and user evaluation
