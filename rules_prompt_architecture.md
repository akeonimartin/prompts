# General Principles of Prompt Architecture

---

## Introduction

These principles govern the logical structure of prompts, not their visual formatting. A prompt need not use headings, numbering, or special layout to satisfy them. It may be written entirely in natural language, provided that:

* the governing end is intelligible,
* material constraints are identifiable,
* priority relations (if relevant) are clear, and
* termination conditions are unambiguous (e.g., expressed with “until,” “after,” “once,” or “when complete”).

Structure concerns cognitive organization, not typography.

These principles are architectural rather than mechanical. They are to be applied with judgment. Not every prompt requires maximal explicitness. Explicit articulation is required only to the degree necessary to prevent reasonable ambiguity or structural failure.

The examples below demonstrate compliance in ordinary natural language without rigid formatting.

---

# Meta-Principles

## 0.1 Instructional Legibility

A prompt must make the governing act intelligible without requiring reasonable guesswork.

It should make clear—explicitly or implicitly:

* what act is required,
* what standard determines success,
* what constraints materially affect the outcome, and
* when the task is complete.

Constraints intrinsic to the act-type need not be redundantly stated.
If an essential element would require interpretation by guesswork, the prompt fails.

**Adequate Example ⭕**
“Summarize the attached article in 300 words. Preserve the author’s main argument. Do not add new claims. End after the summary.”

**Inadequate Example ❌**
“Write something about this article.”

---

## 0.2 Proportionate Specification

Explicitness should be proportionate to interpretive risk.

* State constraints explicitly when their violation would not be immediately recognizable as failure relative to the governing end.
* Do not restate constraints intrinsic to the act-type.
* Increase specificity as task complexity increases.

Under-specification invites drift. Over-specification introduces unnecessary rigidity. The aim is structural sufficiency.

**Adequate Example ⭕**
“Rank the proposals by cost-effectiveness. Use only the data provided. Explain your ranking criteria.”

**Inadequate Example ❌**
“Evaluate these proposals.”
(No criteria given despite non-obvious standards.)

---

# I. End and Admissibility

## 1. Ontological Admissibility

The act required must be possible.

Before adding constraints, ensure the task is:

* possible in kind,
* possible given available material, and
* not normatively excluded.

If feasibility depends on conditions, state them.

**Adequate Example ⭕**
“If the dataset is incomplete, state that analysis cannot be performed.”

**Inadequate Example ❌**
“Provide a statistical comparison,”
when no data has been supplied.

---

## 1a. Conditional Impossibility

A task is conditionally impossible when required material:

* does not exist,
* is inaccessible,
* was not supplied, or
* cannot be reached with available means.

Where such risk exists, delimit it.

**Adequate Example ⭕**
“Translate the following paragraph into Spanish:” (paragraph included)

**Inadequate Example ❌**
“Translate the following paragraph into Spanish:”
(no paragraph provided)

---

## 2. Single Governing End

A prompt must have one governing end.

Other instructions may guide execution, but they may not function as independent, competing ends.

**Adequate Example ⭕**
“Argue that policy X is economically beneficial. Use three empirical studies as support.”

**Inadequate Example ❌**
“Argue for policy X, summarize three studies, and provide a neutral overview.”
(Competing ends.)

---

## 3. Hierarchy of Ends

Distinguish:

* **Governing end** — defines success
* **Intrinsic end** — defines correctness for the act-type
* **Instrumental ends** — support the governing end
* **Stop conditions** — define termination only

Instrumental or terminal conditions may not override governing or intrinsic ends.

**Adequate Example ⭕**
“Explain the theorem accurately. Use clear headings. Limit to 500 words.”
(Accuracy governs; clarity and length are subordinate.)

**Inadequate Example ❌**
“Keep it under 200 words even if key definitions must be omitted.”
(Word limit overrides intrinsic end.)

---

# II. Constraint Governance

## 4. Material Relevance of Constraints

Every stated constraint must affect reasoning, ordering, or success conditions.

Decorative or vague constraints degrade clarity.

**Adequate Example ⭕**
“Evaluate only arguments explicitly stated in the text.”
(Alters scope of reasoning.)

**Inadequate Example ❌**
“Write in an interesting way.”
(No determinate effect on reasoning.)

---

## 5. Declared Priority

If constraints could conflict, establish priority.

Priority relations must be explicit where ambiguity is plausible.

**Adequate Example ⭕**
“If factual accuracy conflicts with brevity, prioritize accuracy.”

**Inadequate Example ❌**
“Be thorough and concise.”
(No conflict resolution.)

---

# III. Structural Expression

## 6. Structure Should Mirror the Task

Where the task has ordered stages of reasoning, the output structure should reflect them.

Explicit staging is required when the sequence materially affects correctness.

**Adequate Example ⭕**
“First define the problem, then evaluate the options, and finally justify the conclusion.”

**Inadequate Example ❌**
“Discuss the issue.”
(No structural guidance.)

---

## 7. Terminological Stability

Key distinctions should be defined once and used consistently.

Synonym drift creates conceptual instability.

**Adequate Example ⭕**
“Define ‘intrinsic end’ and ‘instrumental end’ before applying them.”

**Inadequate Example ❌**
Using “goal,” “purpose,” and “end” interchangeably without clarification.

---

## 8. Material Adequacy

Provide or delimit the material required for judgment when it is not self-evident.

**Adequate Example ⭕**
“Using only the attached five proposals, rank them by feasibility.”

**Inadequate Example ❌**
“Select the best proposal.”
(No proposals supplied.)

---

# IV. Failure Prevention

## 9. Diagnosable Failure Conditions

Where ambiguity is likely, define structural failure conditions.

Failure should be determinable without subjective preference.

**Adequate Example ⭕**
“The response fails if it introduces claims not present in the source text.”

**Inadequate Example ❌**
“The response fails if it is unsatisfactory.”
(Undefined standard.)

---

## 10. Near-Miss Prevention

Guard against responses that satisfy surface constraints while violating the governing end.

Clarify the species of act when confusion is plausible.

**Adequate Example ⭕**
“Do not summarize; analyze the author’s reasoning.”

**Inadequate Example ❌**
“Write about the article.”
(Allows drift.)

---

# V. Agency and Termination

## 11. Specify the Species of Act

Where ambiguity is plausible, identify the act-type required.

Explanation, proof, summary, analysis, critique, and synthesis are distinct species.

**Adequate Example ⭕**
“Provide a formal logical proof, not an intuitive explanation.”

**Inadequate Example ❌**
“Explain why this is true.”
(Ambiguous act-type.)

---

## 12. Instrumental Conditions

If particular tools, sources, or methods are required, specify them when omission would materially alter the result.

**Adequate Example ⭕**
“Use only peer-reviewed sources published after 2015.”

**Inadequate Example ❌**
“Research this topic.”
(No instrument conditions.)

---

## 13. Structural Termination

Termination should correspond to structural completion, not mere quantity.

Quantitative limits are subordinate unless they define the governing end.

**Adequate Example ⭕**
“Revise the draft until each paragraph has one clear claim and supporting evidence. Stop once all paragraphs meet this condition.”

**Inadequate Example ❌**
“Write at least 1,000 words.”
(Quantitative but not structurally complete.)

---

# Closing Note

These principles aim at structural clarity, unity of end, and proportional explicitness. They do not require maximal verbosity or formalized layout. A prompt satisfies them when it secures intelligible action without inviting ambiguity or internal contradiction.
