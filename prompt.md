# Course: Software Engineering

## Objective

Transform the provided Software Engineering course materials into a high-efficiency exam preparation system optimized for a final exam occurring the day after tomorrow.

The goal is not to summarize slides.

The goal is to maximize exam performance per hour studied while preserving complete coverage of examinable material.

---

# Source Materials

All source materials are located in:

./resources/slides

Source files consist primarily of lecture-slide PDFs.

---

# Scope

Cover all material present in the provided slide decks.

Do not assume textbook chapters or syllabus structure.

Instead:

1. Extract concepts from all slides.
2. Construct a topic hierarchy.
3. Group concepts into coherent major topics.
4. Organize all final study artifacts around major topics.

---

# Priorities

Optimize for:

1. Coverage completeness
2. Exam relevance
3. Active recall
4. Retrieval speed
5. Conceptual understanding
6. Recognition of subtle distinctions
7. Identification of common misconceptions
8. Identification of exam traps
9. Fast revision before the exam

---

# Processing Pipeline

Execute the following phases sequentially.

---

# Phase 1: Slide Extraction

## Step 1

Convert each slide deck PDF into images.

Output directory:

./resources/slide_images/

For every slide deck:

./resources/slide_images/<presentation_name>/

Create images where:

* image_001 contains slides 1–3
* image_002 contains slides 4–6
* image_003 contains slides 7–9

and so on.

---

## Step 2

Spawn parallel extraction agents.

Each agent is assigned one presentation-image folder.

Agents must:

1. Read images directly.
2. Extract all textual content.
3. Reconstruct missing context when possible.
4. Explain diagrams.
5. Explain figures.
6. Explain workflows.
7. Explain UML diagrams.
8. Explain architecture diagrams.
9. Explain process models.

When possible:

* Generate Mermaid diagrams.
* Otherwise generate ASCII diagrams.
* Otherwise provide textual explanations.

Store outputs in:

./generated/extracted_content/

Example:

./generated/extracted_content/week01.txt
./generated/extracted_content/week02.txt
...

The extracted files should function as a faithful textual representation of the slide decks.

---

# Phase 2: Topic Discovery

Analyze all extracted content.

Build:

1. Topic hierarchy
2. Concept graph
3. Dependency graph between concepts

Identify:

* Major topics
* Subtopics
* Definitions
* Models
* Methodologies
* Processes
* Frameworks
* Diagrams
* Algorithms
* Metrics
* Tradeoffs
* Case studies
* Frequently repeated concepts

Verify that no major topic is omitted.

---

# Phase 3: Study Material Synthesis

Generate all artifacts inside:

./generated/

---

# Required Deliverables

## 01_topic_map.md

Hierarchical topic map covering all course content.

---

## 02_topic_priority_matrix.md

For every major topic:

* Importance
* Difficulty
* Exam risk
* Dependency level
* Recommended study order

---

## 03_detailed_notes/

Create one file per major topic.

Example:

./generated/03_detailed_notes/software_process_models.md
./generated/03_detailed_notes/requirements_engineering.md
./generated/03_detailed_notes/software_testing.md

Required structure:

* Topic Overview
* Why This Topic Exists
* Core Concepts
* Definitions
* Key Models / Frameworks
* Detailed Explanations
* Relationships to Other Topics
* Examples
* Common Mistakes
* Exam Traps
* Active Recall Questions
* Potential Exam Questions
* Topic Summary

### Writing Style

Detailed Notes serve as the primary learning resource.

Requirements:

* Story-like flow
* Build concepts progressively
* Continuously connect related topics
* Preserve context
* Optimize verbosity for exam preparation
* Avoid textbook-style bloat
* Prefer conceptual clarity over exhaustive detail
* Use tables when useful
* Highlight instructor-emphasized material

A student should be able to learn the topic from these notes alone.

---

## 04_active_recall_bank.md

Comprehensive active recall question bank.

Include:

* Definitions
* Comparisons
* Applications
* Scenario questions
* Design questions
* Process questions
* Tradeoff questions

---

## 05_worked_examples.md

Worked examples and reasoning patterns.

Focus on:

* Requirements analysis
* Design decisions
* Process selection
* Testing strategies
* Risk management
* Project management decisions
* Architecture tradeoffs

Explain reasoning, not just answers.

---

## 06_confusion_map.md

Document:

* Similar concepts
* Common misunderstandings
* Frequently confused terminology
* Exam traps

---

## 07_reference_sheet.md

Compressed exam reference.

Include:

* Definitions
* Models
* Processes
* Frameworks
* Metrics
* Methodologies
* Key comparisons

Designed for rapid lookup.

---

## 08_final_rapid_review.md

High-density review document.

Intended for the final 30–60 minutes before the exam.

Include only the highest-yield material.

---

## 09_coverage_checklist.md

Checklist verifying complete topic coverage.

---

## 10_mind_maps/

Create one Mermaid mind map per major topic.

Example:

./generated/10_mind_maps/software_testing.md
./generated/10_mind_maps/requirements_engineering.md

Each file should contain valid Mermaid mind-map code.

Mind maps should:

* Capture the entire topic
* Show relationships
* Show hierarchy
* Show dependencies
* Be useful for rapid revision

---

## 11_comparison_tables.md

Create comparison tables for related concepts.

Examples:

* Verification vs Validation
* Waterfall vs Agile
* Functional vs Non-Functional Requirements
* Unit Testing vs Integration Testing
* Black Box vs White Box Testing

Include:

* Purpose
* Inputs
* Outputs
* Advantages
* Disadvantages
* Use Cases
* Common Exam Distinctions

Add all relevant comparisons discovered in the course material.

---

## 12_computation_algorithms.md

For any topic involving calculations, procedures, evaluation methods, estimation techniques, metrics, prioritization methods, or systematic problem solving:

Create memorization-friendly algorithms.

For each:

* Problem Type
* Recognition Pattern
* Step-by-Step Algorithm
* Shortcut Heuristics
* Common Mistakes
* Example Walkthrough

Goal:

Enable rapid recall and execution during the exam.

Focus on procedural fluency rather than theoretical explanation.

---

# Quality Requirements

* Maximize exam performance per hour studied.
* Preserve subtle concepts.
* Preserve instructor emphasis.
* Preserve nuances and caveats.
* Favor retrieval-oriented learning.
* Favor active recall.
* Favor conceptual connections.
* Maintain consistency across all artifacts.

---

# Epistemic Constraints

* Do not invent content not supported by source material.
* Explicitly label uncertainty.
* Document conflicting information when discovered.
* Distinguish clearly between extracted information and inferred explanations.

---

# Success Criterion

A student should be able to study only the contents of ./generated and achieve comprehensive, exam-focused coverage of the Software Engineering course with minimal wasted effort.

The generated artifacts should function as a complete exam-preparation system rather than a collection of summaries.
