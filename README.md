# Software Engineering — Exam Prep Toolkit

> A complete, AI-generated exam preparation system built from 19 lecture PDFs.
> Designed for maximum exam performance per hour studied.

---

## What's Inside

```
generated/
├── 01_topic_map.md              ← Start here — see what exists
├── 02_topic_priority_matrix.md  ← What to study first
├── 03_detailed_notes/           ← 12 topic files — deep learning
├── 04_active_recall_bank.md     ← 175 self-test questions
├── 05_worked_examples.md        ← 18 step-by-step problems
├── 06_confusion_map.md          ← Where people lose marks
├── 07_reference_sheet.md        ← One-page lookups
├── 08_final_rapid_review.md     ← Last 30 min before exam
├── 09_coverage_checklist.md     ← Track what you've done
├── 10_mind_maps/                ← 12 visual topic maps
├── 11_comparison_tables.md      ← 20 side-by-side tables
├── 12_computation_algorithms.md ← 9 algorithms with examples
└── extracted_content/           ← Raw text from slides (reference only)
```

---

## How to Study — Recommended Sequence

### Phase 1: Orient (10 min)

1. **Open `01_topic_map.md`** — understand the full scope
2. **Open `02_topic_priority_matrix.md`** — know what's high-yield
3. **Open `09_coverage_checklist.md`** — check what you already know

### Phase 2: Learn Core Concepts (3–5 hours)

Go through topics in this order (optimized for building knowledge):

| # | Topic | File | Why This Order |
|---|-------|------|----------------|
| 1 | Software Processes | `03_detailed_notes/software_process_models.md` | Foundation — everything else builds on this |
| 2 | Agile Development | `03_detailed_notes/agile_software_development.md` | Core syllabus topic, contrasts with processes |
| 3 | Risk Management | `03_detailed_notes/risk_management.md` | High exam weight, often tested |
| 4 | Architecture & Design | `03_detailed_notes/architecture_and_design.md` | High risk topic, many exam traps |
| 5 | Requirements Engineering | `03_detailed_notes/requirements_engineering.md` | Pairs with architecture |
| 6 | Estimation | `03_detailed_notes/estimation.md` | Computation-heavy — do the examples |
| 7 | Project Management | `03_detailed_notes/project_management.md` | Conceptual, easier after harder topics |
| 8 | Project Scheduling & WBS | `03_detailed_notes/project_scheduling_and_wbs.md` | Computation + diagrams |
| 9 | Software Testing | `03_detailed_notes/software_testing.md` | Another heavy topic |
| 10 | Testing Tools | `03_detailed_notes/testing_tools.md` | JMeter specifics |
| 11 | UI Design | `03_detailed_notes/ui_design.md` | Design patterns, evaluation methods |
| 12 | Quality Management | `03_detailed_notes/quality_management.md` | Definitions-heavy, memorize last |

### Phase 3: Practice & Reinforce (2–3 hours)

1. **`12_computation_algorithms.md`** — walk through each algorithm with pen and paper
2. **`05_worked_examples.md`** — solve before reading the answer
3. **`04_active_recall_bank.md`** — cover answers, test yourself
4. **`11_comparison_tables.md`** — memorize the tables

### Phase 4: Find & Fix Gaps (1–2 hours)

1. **`06_confusion_map.md`** — review exam traps
2. **`07_reference_sheet.md`** — fill gaps in memory
3. **`10_mind_maps/`** — open the Mermaid maps for visual reinforcement
4. **`09_coverage_checklist.md`** — re-check your confidence levels

### Phase 5: Final Review (30–60 min before exam)

1. **`08_final_rapid_review.md`** — read cover to cover
2. **`07_reference_sheet.md`** — skim for anything fuzzy
3. **`11_comparison_tables.md`** — glance at key tables

---

## Reading in Obsidian

### Setup (5 min)

**Option A: PC (Recommended)**

1. Download Obsidian from [obsidian.md](https://obsidian.md)
2. Create a new vault: `File → Open vault → Create new vault`
3. Name it `SE-Exam-Prep` and point it to the `generated/` folder
4. Done — Obsidian reads `.md` files natively

**Option B: Phone + PC Sync**

1. Set up the vault on PC first (Option A)
2. Install the **Obsidian Mobile** app (iOS/Android)
3. Sign in with the same Obsidian account
4. On PC: `Settings → Sync → Enable Obsidian Sync`
   - Free tier: vault settings only
   - Paid: full file sync ($4/month) — worth it for exam season
5. **Alternative (free):** Use **Syncthing** or **Remotely Save** plugin:
   - Install **Remotely Save** plugin on both PC and phone
   - Connect to a shared folder (Google Drive, Dropbox, etc.)
   - Sync happens automatically

**Option C: Quick Phone Reading (No Sync Setup)**

1. Open any `.md` file in your phone's browser (if hosted on GitHub/GitLab)
2. Or use the **GitHub mobile app** to browse the repo
3. Or use **Markdown Reader** app (iOS/Android) — just open the `.md` files

### Obsidian Tips for Studying

- **Graph View** (`Ctrl/Cmd + G`) — see how topics connect visually
- **Tags** — search for `#priority` or `#risk` in the priority matrix
- **Bookmarks** (`Ctrl/Cmd + B`) — pin `08_final_rapid_review.md` for quick access
- **Split View** — read notes on left, active recall questions on right
- **Search** (`Ctrl/Cmd + P`) — type any keyword to find it across all files
- **Mermaid rendering** — Obsidian renders mind maps natively (the `10_mind_maps/` files will show as diagrams)

### Recommended Obsidian Plugins

| Plugin | Why |
|--------|-----|
| **Mermaid** | Renders the mind map diagrams |
| **Checklist** | Track coverage in `09_coverage_checklist.md` |
| **Spaced Repetition** | Turn `04_active_recall_bank.md` into flashcards |
| **Remotely Save** | Free phone sync via Google Drive/Dropbox |

---

## Quick Reference

| I want to... | Open this |
|--------------|-----------|
| See all topics | `01_topic_map.md` |
| Know what to study first | `02_topic_priority_matrix.md` |
| Deep-dive a topic | `03_detailed_notes/[topic].md` |
| Test myself | `04_active_recall_bank.md` |
| Practice computations | `12_computation_algorithms.md` |
| Work through examples | `05_worked_examples.md` |
| Avoid common mistakes | `06_confusion_map.md` |
| Look up a formula/definition | `07_reference_sheet.md` |
| Last-minute review | `08_final_rapid_review.md` |
| Check my progress | `09_coverage_checklist.md` |
| See visual topic maps | `10_mind_maps/[topic].md` |
| Compare concepts | `11_comparison_tables.md` |

---

## Tips

- **Don't read everything.** Use the priority matrix to focus on high-yield topics.
- **Active recall > passive reading.** Cover the answer before reading it.
- **Do computations by hand.** The exam will test you on paper, not screen.
- **Teach it.** If you can explain `10_detailed_notes/risk_management.md` to someone else, you know it.
- **Take breaks.** 25 min study, 5 min break (Pomodoro). The notes are designed for chunked study.
- **Use the checklist.** Mark topics as green/yellow/red to track your progress.

---

## File Sizes

| File | Approx. Words | Study Time |
|------|--------------|------------|
| Topic Map | 1,500 | 10 min |
| Priority Matrix | 4,000 | 15 min |
| Detailed Notes (each) | 2,000–6,000 | 30–45 min each |
| Active Recall Bank | 7,000 | 1–2 hours |
| Worked Examples | 7,500 | 1–2 hours |
| Confusion Map | 3,000 | 20 min |
| Reference Sheet | 6,000 | 30 min |
| Final Rapid Review | 4,000 | 30–60 min |
| Coverage Checklist | 4,000 | 15 min |
| Comparison Tables | 5,500 | 30 min |
| Computation Algorithms | 8,500 | 1–2 hours |

**Total study time estimate: 8–15 hours** (depending on prior knowledge)

---

*Generated from 19 lecture PDFs. Content is based on lecture slides only — verify against official course materials for anything unclear.*
