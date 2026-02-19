# General Rules of Prompt Architecture

*A practical framework for writing clear, well-structured prompts*

---

## Introduction

These principles describe what makes a prompt clear and well-formed. They concern structure and clarity, not formatting. A prompt does not need headings, numbering, or rigid layout to follow these guidelines. It can be written in plain language.

Not every principle applies to every prompt. Some may be:

* **Explicitly stated**
* **Implicit but clearly satisfied**
* **Not relevant to the task**

As prompts become more complex, more principles become relevant and more details need to be stated explicitly.

The goal is clarity without unnecessary complication.

---

# Foundational Principles

## 1. Calibrate to the Agent

A prompt should match the ability, tools, and information available to the person or system responding.

* Don’t demand what cannot realistically be done.
* Don’t oversimplify when deeper work is expected.

Clarity depends partly on who the prompt is written for.

---

## 2. Be Explicit in Proportion to Risk

State constraints clearly when they are not obvious.

* If breaking a rule would not obviously count as failure, state the rule.
* If the task is simple and the expectations are obvious, avoid unnecessary detail.
* As complexity increases, increase specificity.

Too little detail causes confusion.
Too much detail causes rigidity.

**Adequate Example ⭕**
“Rank the proposals by cost-effectiveness. Use only the data provided. Explain your ranking criteria.”

**Inadequate Example ❌**
“Evaluate these proposals.”
(No criteria given.)

---

# Core Rules

---

## Rule 1. Make the Task Clear

The prompt must make clear:

* What to do
* What counts as success
* Any important constraints
* When the task is finished

If a reasonable person would have to guess, the prompt is unclear.

**Adequate Example ⭕**
“Summarize the attached article in 300 words. Preserve the author’s main argument. Do not add new claims. End after the summary.”

**Inadequate Example ❌**
“Write something about this article.”

---

## Rule 2. Make Sure the Task Is Possible

Before adding constraints, make sure the task can actually be completed with the information and tools available.

If it depends on missing material, say so.

**Adequate Example ⭕**
“If the dataset is incomplete, state that analysis cannot be performed.”

**Inadequate Example ❌**
“Provide a statistical comparison,”
when no data has been supplied.

---

## Rule 3. Focus on One Main Objective

A prompt should have one primary goal.

Other instructions may shape how it’s done, but they should not introduce separate competing goals.

**Adequate Example ⭕**
“Argue that policy X is economically beneficial. Use three empirical studies as support.”

**Inadequate Example ❌**
“Argue for policy X, summarize three studies, and provide a neutral overview.”

---

## Rule 4. Keep Priorities Straight

If instructions could conflict, say which one takes priority.

**Adequate Example ⭕**
“If factual accuracy conflicts with brevity, prioritize accuracy.”

**Inadequate Example ❌**
“Be thorough and concise.”

---

## Rule 5. Make Constraints Meaningful

Every constraint should affect how the task is carried out.

Avoid vague instructions that don’t change anything.

**Adequate Example ⭕**
“Evaluate only arguments explicitly stated in the text.”

**Inadequate Example ❌**
“Write in an interesting way.”

---

## Rule 6. Match Structure to the Task

If the task has logical steps, reflect them in the requested output.

**Adequate Example ⭕**
“First define the problem, then evaluate the options, and finally justify the conclusion.”

**Inadequate Example ❌**
“Discuss the issue.”

---

## Rule 7. Use Terms Consistently

If you introduce important distinctions, define them once and use them consistently.

Avoid switching terms without explanation.

**Adequate Example ⭕**
“Define ‘intrinsic end’ and ‘instrumental end’ before applying them.”

**Inadequate Example ❌**
Using “goal,” “purpose,” and “end” interchangeably without clarification.

---

## Rule 8. Provide the Necessary Material

If the task requires selecting, evaluating, or comparing, provide the material needed to do so.

**Adequate Example ⭕**
“Using only the attached five proposals, rank them by feasibility.”

**Inadequate Example ❌**
“Select the best proposal.”

---

## Rule 9. Define the Scope

If the topic is broad, set boundaries.

Scope may include:

* Time period
* Location
* Context
* Comparison group
* Type of evidence

**Adequate Example ⭕**
“Evaluate the economic effects of policy X in the United States from 2015–2023.”

**Inadequate Example ❌**
“Evaluate the economic effects of policy X.”

---

## Rule 10. Clarify the Level of Analysis

If multiple interpretations are possible, clarify what kind of analysis is required.

Examples of different levels:

* Conceptual vs. empirical
* Descriptive vs. evaluative
* Theoretical vs. applied
* Summary vs. analysis

**Adequate Example ⭕**
“Provide a normative analysis of justice in Rawls’s theory.”

**Inadequate Example ❌**
“Analyze justice.”

---

## Rule 11. Make Failure Identifiable

If precision matters, specify what counts as failure.

Failure should be objectively identifiable, not based on taste.

**Adequate Example ⭕**
“The response fails if it introduces claims not present in the source text.”

**Inadequate Example ❌**
“The response fails if it is unsatisfactory.”

---

## Rule 12. Prevent Near-Miss Responses

Guard against answers that technically comply but miss the point.

If confusion is likely, clarify what the task is *not*.

**Adequate Example ⭕**
“Do not summarize; analyze the author’s reasoning.”

**Inadequate Example ❌**
“Write about the article.”

---

## Rule 13. Specify the Kind of Task

If different types of response are possible, clarify which one is required.

**Adequate Example ⭕**
“Provide a formal logical proof, not an intuitive explanation.”

**Inadequate Example ❌**
“Explain why this is true.”

---

## Rule 14. Specify Required Tools (If Any)

If specific sources, methods, or tools are required, say so.

If none are required, no special specification is needed.

**Adequate Example ⭕**
“Use only peer-reviewed sources published after 2015.”

**Inadequate Example ❌**
“Research this topic.”

---

## Rule 15. Define When the Task Is Complete

Completion should be based on structural criteria, not just length.

**Adequate Example ⭕**
“Revise the draft until each paragraph has one clear claim and supporting evidence.”

**Inadequate Example ❌**
“Write at least 1,000 words.”

---

# Summary

A well-formed prompt:

* States one clear objective
* Ensures the task is possible
* Uses constraints that actually matter
* Sets scope and level when needed
* Prevents ambiguity and drift
* Makes completion and failure identifiable

Clarity increases as complexity increases.
Explicitness should always be proportionate to risk.
