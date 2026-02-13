# General Rules for Prompt Architecture

---

## Introduction

These rules govern the logical structure of prompts, not their visual formatting. A prompt does not require headings, numbering, or special layout to satisfy these principles. It may be written entirely in natural language, provided that:

* the governing end is clear,
* constraints are identifiable,
* priority relations (if any) are intelligible, and
* stop conditions are unambiguous (e.g., expressed using terms such as “until,” “after,” “once,” or “when complete”).

Structure concerns cognitive organization, not typography.

All examples below are written in ordinary natural language. They demonstrate that a prompt may satisfy these rules without formal sectioning or rigid formatting.

---

# Meta-Governing Principles

## 0.1 Instructional Legibility

A prompt must state plainly:

* what act is required,
* what standard determines success,
* what constraints apply, and
* when the task is complete.

If any element requires guesswork, the prompt fails.

**Adequate Example ⭕**
“Summarize the attached article in 300 words. Preserve the author’s main argument. Do not add new claims. End after the summary.”

**Inadequate Example ❌**
“Write something about this article.”

## 0.2 Proportionate Specification

State constraints explicitly when they are not obvious.

* If a violation would not be immediately noticeable, make the constraint explicit.
* As complexity increases, specify more constraints.

**Adequate Example ⭕**
“Rank the proposals by cost-effectiveness. Use only the data provided. Explain your ranking criteria.”

**Inadequate Example ❌**
“Evaluate these proposals.”
(No criteria given despite non-obvious standards.)

---

# I. End and Admissibility

## 1. Ontological Admissibility

Determine whether the act is possible before adding constraints.

An act may be impossible in kind, impossible given available material, or normatively excluded.

**Adequate Example ⭕**
“If the dataset is incomplete, state that analysis cannot be performed.”

**Inadequate Example ❌**
“Provide a statistical comparison,”
when no data has been supplied.

## 1a. Conditional Impossibility

A task is conditionally impossible when required material:

* does not exist,
* is inaccessible,
* was not supplied, or
* cannot be reached with available means.

**Adequate Example ⭕**
“Translate the following paragraph into Spanish:” (paragraph included)

**Inadequate Example ❌**
“Translate the following paragraph into Spanish:”
(no paragraph provided)

## 2. Single Governing End

Each prompt must specify one governing end.

Other constraints may guide how it is achieved but may not function as independent ends.

**Adequate Example ⭕**
“Argue that policy X is economically beneficial. Use three empirical studies as support.”

**Inadequate Example ❌**
“Argue for policy X, summarize three studies, and provide a neutral overview.”
(Competing ends.)

## 3. Kinds of End

* The **governing end** defines success.
* The **intrinsic end** defines correctness for the act-type.
* **Instrumental ends** support the governing end.
* **Stop conditions** mark termination only.

Instrumental or terminal ends may not override governing or intrinsic ends.

**Adequate Example ⭕**
“Explain the theorem accurately. Use clear headings. Limit to 500 words.”
(Accuracy governs; clarity and length are subordinate.)

**Inadequate Example ❌**
“Keep it under 200 words even if key definitions must be omitted.”
(Word limit overrides intrinsic end of explanation.)

---

# II. Constraint Governance

## 4. Constraints Shape Reasoning

Each constraint must affect reasoning, ordering, or success conditions.

**Adequate Example ⭕**
“Evaluate only arguments explicitly stated in the text.”
(Changes scope of reasoning.)

**Inadequate Example ❌**
“Write in an interesting way.”
(No clear effect on reasoning or success criteria.)

## 5. Declared Priority Rules

If constraints could conflict, specify which overrides which.

Priority rules must be explicit and consistent.

**Adequate Example ⭕**
“If factual accuracy conflicts with brevity, prioritize accuracy.”

**Inadequate Example ❌**
“Be thorough and concise.”
(No rule for resolving conflict.)

---

# III. Structural Expression

## 6. Structure Mirrors the Cognitive Task

Output structure must reflect stages of reasoning.

**Adequate Example ⭕**
“First define the problem, then evaluate the options, and finally justify the conclusion.”

**Inadequate Example ❌**
“Discuss the issue.”
(No structural guidance.)

## 7. Define Key Distinctions Once

Introduce key terms once and use them consistently.

**Adequate Example ⭕**
“Define ‘intrinsic end’ and ‘instrumental end’ before applying them.”

**Inadequate Example ❌**
Use “goal,” “purpose,” and “end” interchangeably without definition.

## 8. Material Adequacy

Provide or delimit the material required for judgment.

**Adequate Example ⭕**
“Using only the attached five proposals, rank them by feasibility.”

**Inadequate Example ❌**
“Select the best proposal.”
(No proposals supplied.)

---

# IV. Failure Prevention

## 9. Explicit Failure Conditions

Failure must be structurally diagnosable.

**Adequate Example ⭕**
“The response fails if it introduces claims not present in the source text.”

**Inadequate Example ❌**
“The response fails if it is unsatisfactory.”
(Subjective and undefined.)

## 10. Near-Miss Exclusion

Prevent responses that satisfy surface constraints while missing the governing end.

**Adequate Example ⭕**
“Do not summarize; analyze the author’s reasoning.”

**Inadequate Example ❌**
“Write about the article.”
(Allows summary instead of analysis.)

---

# V. Agency and Termination

## 11. Agent Role

Specify the species of act required.

**Adequate Example ⭕**
“Provide a formal logical proof, not an intuitive explanation.”

**Inadequate Example ❌**
“Explain why this is true.”
(Does not distinguish proof from explanation.)

## 12. Instrumental Specification

If tools are required, specify them or state selection criteria.

**Adequate Example ⭕**
“Use only peer-reviewed sources published after 2015.”

**Inadequate Example ❌**
“Research this topic.”
(No instrument conditions.)

## 13. Structural Stop Conditions

Specify when the task is complete in structural terms.

**Adequate Example ⭕**
“Revise the draft until each paragraph has one clear claim and supporting evidence. Stop once all paragraphs meet this condition.”

**Inadequate Example ❌**
“Write at least 1,000 words.”
(Quantitative but not structurally complete.)
