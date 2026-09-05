# Orchestra-Adapted Writing Principles

Use this reference when `paper-plan` needs help shaping the paper's story or when `paper-write` needs stronger drafting and revision guidance.

This is the expanded English counterpart to the detailed Chinese version. It is not a new workflow phase. Its purpose is to provide a stronger writing model on top of the existing `insleep` pipeline.

## Contents

- [When to Read](#when-to-read)
- [The Narrative Principle](#the-narrative-principle)
- [Time Allocation and Reviewer Reading Order](#time-allocation-and-reviewer-reading-order)
- [Paper Titles](#paper-titles)
- [How to Write the Abstract](#how-to-write-the-abstract)
- [Introduction Structure](#introduction-structure)
- [Sentence-Level Clarity](#sentence-level-clarity)
- [Micro-Level Writing Tactics](#micro-level-writing-tactics)
- [Word Choice and Precision](#word-choice-and-precision)
- [Evidence-Bounded Audit and Case-Study Papers](#evidence-bounded-audit-and-case-study-papers)
- [Mathematical Writing](#mathematical-writing)
- [Figure Design](#figure-design)
- [Common Mistakes](#common-mistakes)
- [Pre-Submission Checklist](#pre-submission-checklist)

## When to Read

- Read before locking the framing of the paper.
- Read before drafting the Abstract and Introduction.
- Read when Related Work feels like a literature dump.
- Read when the prose feels generic, templated, or overly AI-shaped.
- Read when the structure looks fine on paper but the draft still feels unconvincing.

## The Narrative Principle

### Neel Nanda's Core View

A paper should be a **short, rigorous, evidence-backed technical story**, not a pile of experiments.

By the end of the Introduction, the reader should clearly understand:

- **The What**: the 1-3 specific claims the paper makes,
- **The Why**: the evidence that supports those claims,
- **The So What**: why the community should care.

### Andrej Karpathy's Complement

A strong paper “sells” **one thing** that was previously absent or non-obvious. The full paper should be organized around that single contribution.

### Practical Rules

- If the core contribution cannot be stated in one sentence, the framing has not converged.
- Every section should serve the same story instead of launching a second one.
- Experiments, related work, and discussion are there to support the main claim, not to operate as independent mini-papers.

### One-Sentence Contribution Test

If you cannot write something like the following, the framing is still too loose:

- “We prove that X converges under assumption Y.”
- “We show that method A improves B by 15% on benchmark C.”
- “We identify failure mode D and propose mechanism E that removes it.”

If the one-sentence contribution is hard to write, the usual causes are:

- the contribution is still too vague,
- the evidence is not yet tightly coupled to the claims,
- or the paper does not yet know what story it is telling.

## Time Allocation and Reviewer Reading Order

### Where Effort Should Go

A useful rule of thumb is to spend roughly the same amount of time on:

1. the Abstract,
2. the Introduction,
3. the Figures,
4. everything else combined.

This is not an exaggeration. Many reviewers form a preliminary judgment before they read the full methods section carefully.

### Common Reviewer Reading Order

Most reviewers encounter the paper in this order:

1. Title
2. Abstract
3. Introduction
4. Figures, especially Figure 1
5. The rest

### Writing Implications

- Put disproportionate effort into the title, abstract, introduction, and hero figure.
- Do not bury the main contribution after Section 3.
- Make the value of the paper legible before the reader reaches the full method.
- If the first two pages are unclear, later brilliance may never be seen.

## Paper Titles

A title is the paper's program-level interface, not a compressed abstract. A reader scanning a venue program should understand the paper's subject and main contribution in one pass, before seeing the abstract.

### Title Rules

- State the core subject and contribution in plain, recognizable language.
- Prefer one clean noun phrase or short declarative claim. Do not stack mechanisms, evaluation details, scope clauses, and secondary contributions into the title.
- Minimize jargon. Do not introduce a new acronym in the title; retain only established technical terms that are necessary to identify the work accurately.
- Avoid `X: Y` and multi-clause titles when the subtitle merely adds method detail. Use a subtitle only when it materially improves recognition or supplies a necessary scope qualifier.
- Draft at least three accurate candidates and choose the shortest one that still distinguishes the paper and preserves its claim boundary.
- As a default heuristic, aim for roughly 8--14 English words. A title longer than about 16 words, or one with multiple colon/dash clauses, requires an explicit accuracy or scope justification and should normally be shortened.
- Accuracy beats brevity: never delete a qualifier whose removal would overclaim. Move nonessential qualifiers and method details into the abstract.

### Program-List Test

Read the title by itself, without the abstract. If an adjacent-domain researcher cannot paraphrase what the paper is about after one reading, rewrite it. A title that is bloated, jargon-stacked, or hard to follow fails even if every individual term is technically correct.

## How to Write the Abstract

### Sebastian Farquhar's Five-Sentence Formula

Prefer a compact five-part abstract:

1. What you achieved
2. Why the problem is important and difficult
3. How you approached it
4. What evidence supports the claim
5. What number, result, or guarantee the reader should remember

### What a Good Abstract Should Do

- Enter the paper's specific contribution in the first one or two sentences.
- Include at least one explicit quantitative result.
- Be understandable without the main text.
- Avoid undefined acronyms.
- Avoid depending on citations to explain itself.

### A Good Abstract Sketch

```text
We prove that X converges linearly under assumption Y.
This addresses a long-standing question about why optimization remains stable in an apparently non-convex setting.
Our analysis reduces the training dynamics to Z, which yields a tractable theoretical structure.
We validate the prediction on datasets A and B and observe close agreement between theory and experiment.
Compared with prior methods, we reduce error by 15% and provide the first convergence guarantee in this setting.
```

### Openings to Delete

If the first sentence could fit almost any ML paper, delete it.

For example:

- “Large language models have achieved remarkable success...”
- “In recent years, deep learning has...”
- “Neural networks have revolutionized...”

The problem is not just that these openings sound stale. They carry **too little information** to help a reviewer judge the paper's specific contribution.

## Introduction Structure

### Basic Requirements

In two-column conference papers, the Introduction is usually best at about 1-1.5 pages.

It should satisfy the following:

- the method should start appearing by page 2-3 at the latest,
- the Introduction should include 2-4 contribution bullets,
- the central story should already make sense before technical detail arrives.

### Plain-Language Opening Contract

The first one or two paragraphs must make three things explicit in plain language:

1. **Research question** — what concrete problem is the paper trying to solve or understand?
2. **Why it matters** — what scientific or practical consequence makes the question worth answering?
3. **Primary finding** — what did the paper actually find, prove, or build?

A useful diagnostic form is: “We study [question]. This matters because [consequence]. We find [primary result].” The prose need not use these exact words, but a reader should be able to recover all three answers immediately. Do not delay the primary finding until the contribution bullets or experiments section.

### Sentence and Vocabulary Rules

- Give each sentence one main job. Prefer a direct subject, an early verb, and one main clause.
- As a default heuristic, aim for no more than about 25 English words per sentence. A sentence longer than about 35 words should normally be split; keep it only when technical precision genuinely requires the structure.
- Remove nested clauses, long parenthetical interruptions, nominalizations, and decorative transitions when a shorter construction says the same thing.
- Prefer familiar, field-standard words. Use “analysis” or “investigation” instead of an unusual label such as “postmortem” unless the unusual term is established in the field and adds necessary meaning.
- Do not rename a familiar method or activity merely to sound novel. Define any unavoidable specialist term in plain language at first use.
- Every sentence must advance the problem, importance, gap, research question, approach, finding, contribution, or scope. If it does none of these, delete it.
- Never add prose to fill space, create an academic tone, or make simple work sound sophisticated. Brevity is preferable to empty polish.

### Introduction Comprehension Test

Give an adjacent-domain reader only the first two paragraphs. If they cannot paraphrase the research question, why it matters, and the primary finding, rewrite the opening. If they stumble over a sentence or non-standard term, simplify it rather than expecting the reader to decode it.

### Recommended Structure

1. **Opening hook**
   - What problem does the paper address?
   - Why does it matter now?

2. **Background / challenge**
   - Why is the problem hard?
   - What has prior work tried, and why is it insufficient?

3. **Approach overview**
   - What does this paper do differently?
   - What is the key insight?

4. **Contribution bullets**
   - 2-4 items
   - specific and falsifiable
   - ideally no longer than 1-2 lines each

5. **Results preview**
   - surface the strongest result early
   - tell the reader what is worth remembering

6. **Optional roadmap**
   - briefly describe the remaining sections

### Contribution Bullets: Good vs Bad

Good:

- We prove that X converges in O(n log n) under assumption Y.
- We introduce architecture Z, which reduces memory by 40%.
- We improve method A by 15% on benchmark C.

Bad:

- We study problem X.
- We perform extensive experiments.
- We make several contributions to the field.

The problem with the “bad” bullets is not grammar. It is that a reviewer cannot cleanly agree, disagree, or challenge them.

## Sentence-Level Clarity

### The Core Insight from Gopen and Swan

Readers have strong structural expectations about prose. If you repeatedly violate those expectations, readers spend effort decoding the sentence instead of understanding the idea.

### Seven Key Principles

#### 1. Keep Subject and Verb Close

Weak:

```text
The model, which was trained on 100M tokens and then fine-tuned with several domain-specific modifications, achieves strong results.
```

Strong:

```text
The model achieves strong results after training on 100M tokens and fine-tuning with domain-specific modifications.
```

#### 2. Put Important Information Near the End

Weak:

```text
Accuracy improves by 15% when using attention.
```

Strong:

```text
When using attention, accuracy improves by 15%.
```

#### 3. Put Context at the Start

Weak:

```text
A new attention mechanism is introduced to solve the alignment problem.
```

Strong:

```text
To address the alignment problem, we introduce a new attention mechanism.
```

#### 4. Move from Old to New

Readers track arguments more easily when the sentence begins with what is already familiar and ends with what is newly important.

#### 5. One Unit, One Function

- A paragraph should ideally do one main job.
- If a sentence is carrying two layers of logic at once, it probably wants to become two sentences.

#### 6. Put Actions in Verbs

Weak:

```text
We performed an analysis of the results.
```

Strong:

```text
We analyzed the results.
```

#### 7. Set the Stage Before New Material

Before presenting an equation, theorem, or experimental result, tell the reader why it matters.

### Fast Revision Questions

When revising a paragraph, ask:

- Is the subject separated from the verb by too much material?
- Does the sentence begin with context?
- Does the sentence end on the point that matters most?
- Is this paragraph trying to do two jobs at once?

## Micro-Level Writing Tactics

### Reduce Ambiguous Pronouns

When `this`, `it`, or `these` could be unclear, replace them with a specific noun.

Weak:

```text
This shows the method is robust.
```

Strong:

```text
These ablation results show that the method is robust to label noise.
```

### Move Verbs Earlier

Readers parse sentences faster when the main verb arrives early.

### Remove Low-Information Fillers

These words can usually be deleted:

- actually
- very
- really
- quite
- basically
- essentially
- Importantly,
- Notably,
- It is worth noting that

### Paragraph Shape

A useful paragraph skeleton is:

- first sentence: the point,
- middle: support,
- last sentence: reinforcement or transition.

Do not bury the key sentence in the middle.

## Word Choice and Precision

### Zachary Lipton Style: Remove Needless Hedging

Unless uncertainty is genuine, avoid overusing:

- may
- can
- might
- potentially

Excessive hedging often reads less like rigor and more like self-doubt.

### Replace Vague Terms with Specific Ones

| Vague Term | Better Alternative |
|-----------|--------------------|
| performance | accuracy / F1 / latency / throughput |
| improves | increases by X% / reduces by Y |
| large | 1B parameters / 100M tokens |
| fast | 3x faster / 50ms latency |
| good results | 92% accuracy / 0.85 F1 |

### Terminology Consistency

Do not rename the same concept across the paper.

For example, avoid mixing:

- model / network / architecture
- training / learning / optimization
- sample / instance / example

Choose the best term and keep it stable.

### Define Technical Terms and Abbreviations on First Use

Never make readers guess an abbreviation. At its first reader-facing use, write the full technical term followed by the abbreviation in parentheses: `command-line interface (CLI)`. This applies even to abbreviations that may feel familiar to the authors, including API, CLI, GPU, and LLM.

- Treat the Abstract and main text as separate scopes. Define an abbreviation in the Abstract, then define it again at its first occurrence in the main text.
- Define before use, never in a later sentence or section.
- Make figure and table captions self-contained: define any abbreviation needed to understand the caption, or avoid the abbreviation there.
- Introduce an abbreviation only when it improves repeated reading. If a term appears fewer than about three times, normally spell it out instead.
- Avoid acronym overload. Prefer a plain, standard term when a short label is unnecessary.
- Standard mathematical symbols, units, and venue names may remain unexpanded only when expansion would reduce rather than improve clarity.

An automated uppercase-token scan can find candidates, but it does not replace reading the Abstract, main text, and captions in order. The final test is whether an adjacent-domain reader encounters the definition before needing the abbreviation.

## Evidence-Bounded Audit and Case-Study Papers

Papers that audit, reproduce, correct, or analyze a specific prior artifact must make the object and evidence boundary obvious on the first page.

### Identify the Object Under Study

- State whether the target is a published paper, public artifact, unpublished internal experiment, or reconstructed project record.
- Cite a published or public target directly. Double-blind review is not a reason to omit a scientifically necessary citation; use third-person self-citation or an allowed anonymous artifact link.
- If the target is unpublished or cannot be cited, say so plainly and explain what inspectable material defines it. Do not write “the original work” or “one audit” as if the reader already knows what that means.

### Make Artifacts Reviewer-Visible

- A local repository or archive does not count as available evidence. Verify the exact reviewer-facing upload or anonymous link after submission packaging.
- Point from the paper to the precise supplement directory, entry command, and evidence files. A reviewer should locate the relevant code or data in under a minute.
- Test the submitted archive from a clean directory. Label missing artifacts explicitly; do not imply that a current implementation reproduces a historical execution.

### Match Generality to Evidence

- One case supports a case-study conclusion, not a validated general framework.
- Claim a reusable method or framework only when independent cases, controlled fault injection, comparative evaluation, or another direct validation tests its general operation.
- Without that validation, call the contribution a checklist, reporting aid, hypothesis, or recommendation and state that it remains unvalidated.

### Keep Claim Strength Consistent

Write one canonical main-claim sentence with its necessary qualifier. The title, Abstract, Introduction, results, and Conclusion must preserve the same certainty and scope. The title may be clearer and shorter, but never stronger. Use necessary qualifiers once near the claim; do not scatter stacked hedges that make the claim impossible to recover.

### Separate Code Presence from Execution Evidence

For every implementation component material to a claim, distinguish:

1. present in the archive,
2. reachable or called by the evaluated pipeline,
3. executed in the reported run,
4. backed by a preserved result.

Never infer a later level from an earlier one. Explain why material uncalled or stub code is included, or omit it from the reviewer-facing artifact if it is irrelevant.

### Vocabulary Signaling

Some verbs make the work sound like a loose combination of existing pieces:

- combine
- modify
- extend
- expand

Stronger alternatives are often:

- develop
- propose
- introduce
- characterize

This is not about mechanical substitution. It is about how wording changes a reviewer's intuition about whether the work is a real contribution.

## Mathematical Writing

### Core Principle

The goal of mathematical writing is not to sound sophisticated. It is to let the reader **follow** the argument.

Prefer the following:

1. state assumptions formally before the theorem,
2. pair proofs and derivations with intuition,
3. keep notation consistent,
4. define symbols at first use.

### Recommended Notation Habits

```latex
% Scalars: lowercase italic
$x$, $y$, $\alpha$, $\beta$

% Vectors: lowercase bold
$\mathbf{x}$, $\mathbf{v}$

% Matrices: uppercase bold
$\mathbf{W}$, $\mathbf{X}$

% Sets: uppercase calligraphic
$\mathcal{X}$, $\mathcal{D}$

% Named functions: roman
$\mathrm{softmax}$, $\mathrm{ReLU}$
```

### Common Mathematical Writing Mistakes

- presenting equations without telling the reader why they matter,
- introducing assumptions too late,
- reusing symbols with different meanings across sections,
- moving all proof intuition to the appendix and leaving only bare statements in the main text.

For theory papers especially, **intuition and rigor** should coexist.

## Figure Design

### Why Figure 1 Matters

Figure 1 is often one of the first artifacts a reviewer studies after the abstract.

It should usually do at least one of the following:

- explain the core system or method idea,
- show the strongest comparison that justifies the paper,
- or provide the simplest visual summary of the main claim.

### Design Principles

1. **Figure 1 is crucial**
2. **captions should be self-contained**
3. **do not place a decorative title inside the figure**
4. **plots should use vector graphics whenever possible**

### Accessibility

Account for color-vision deficiency.

Do:

- use colorblind-safe palettes,
- avoid red-green pairings,
- make sure the figure still works in grayscale,
- use line styles and markers in addition to color.

### Caption Rules

- A reader should understand the point of the figure from the caption alone.
- State what is being compared.
- State what the reader should notice.
- Do not make the caption depend on the surrounding paragraph for essential meaning.

## Common Mistakes

### Structural Mistakes

| Mistake | Fix |
|--------|-----|
| Introduction longer than 1.5 pages | Move background to Related Work |
| Method buried too late | Front-load the contribution and compress the intro |
| Missing contribution bullets | Add 2-4 concrete claims |
| Experiments not tied to claims | State what each experiment tests |

### Writing Mistakes

| Mistake | Fix |
|--------|-----|
| Generic abstract opening | Start from the paper's actual contribution |
| Bloated or jargon-heavy title | Rewrite for one-pass program-list comprehension; move secondary details to the abstract |
| Introduction hides the research question or finding | State the question, importance, and primary finding in the first one or two paragraphs |
| Technical abbreviation used before definition | Write the full term first, followed by the abbreviation in parentheses; repeat this for its first use in both the Abstract and main text |
| Audit target is unnamed or uncited | Identify whether it is published, public, internal, or reconstructed; cite it or explain the evidence that defines it |
| Single case presented as a validated framework | Add independent validation or narrow the contribution to a case study or unvalidated reporting aid |
| Artifact exists locally but reviewers cannot locate it | Verify the reviewer-facing upload and point to exact files and commands in the paper |
| Title is stronger than the qualified body claim | Use one canonical claim boundary across title, Abstract, Introduction, and Conclusion |
| Implemented code described as executed evidence | Record present, called, executed, and result-backed status separately |
| Long, clause-heavy sentence | Split it into direct sentences with one job each |
| Novel-sounding name for a familiar activity | Use the field-standard term unless the new term adds necessary meaning |
| Filler written only to sound academic | Delete it; do not write to fill space |
| Inconsistent terminology | Keep one name per concept |
| Too much passive voice | Prefer active constructions |
| Hedging everywhere | Keep hedging only where uncertainty is real |

### Figure Mistakes

| Mistake | Fix |
|--------|-----|
| Raster plots | Use PDF / EPS or other vector output |
| Red-green color schemes | Switch to colorblind-safe palettes |
| Titles inside figures | Move the title into the caption |
| Captions that require the main text | Rewrite them to be self-contained |

### Citation Mistakes

| Mistake | Fix |
|--------|-----|
| Related Work as paper-by-paper summary | Reorganize by method family or research question |
| Missing important references | Proactively expand the search |
| AI-generated citations | Use a verification workflow |
| Inconsistent key or style format | Normalize the bibliography |

## Pre-Submission Checklist

### Title

- [ ] The title alone makes the subject and main contribution understandable in one pass.
- [ ] The title contains no stacked jargon or abstract-level method and evaluation detail.
- [ ] At least three accurate candidates were considered, and the shortest accurate one was chosen.
- [ ] Any title longer than about 16 English words or using multiple subtitle clauses has a concrete accuracy or scope justification.

### Narrative

- [ ] The contribution can be stated in one sentence.
- [ ] The Introduction makes the What / Why / So What clear.
- [ ] The first two Introduction paragraphs state the research question, why it matters, and the primary finding.
- [ ] Every major experiment supports a clear claim.
- [ ] The title, Abstract, Introduction, results, and Conclusion preserve the same claim strength and scope.

### Audit and Case-Study Papers

- [ ] The first page identifies the audited object and either cites it or plainly explains why it is unpublished or uncitable.
- [ ] The paper points to reviewer-visible artifact files and an entry command, verified from the actual submission package.
- [ ] A single case is labeled as a case study unless independent evidence validates a broader method or framework.
- [ ] Material components are labeled separately as present, called, executed, and result-backed.

### Structure

- [ ] The abstract follows the five-sentence formula.
- [ ] The Introduction stays within about 1-1.5 pages.
- [ ] The method starts by page 2-3.
- [ ] There are 2-4 concrete contribution bullets.
- [ ] Limitations are clearly stated.

### Writing

- [ ] Every technical abbreviation is expanded before first use in the Abstract and again in the main text.
- [ ] Figure and table captions define abbreviations needed for standalone interpretation.
- [ ] Abbreviations used fewer than about three times were removed unless they materially improve clarity.
- [ ] Introduction sentences are direct and normally stay below about 25 English words; every sentence above about 35 words was split or justified by technical necessity.
- [ ] Familiar, field-standard terms replace unusual or novelty-seeking vocabulary.
- [ ] Every Introduction sentence advances the argument; no filler remains.
- [ ] Terminology is consistent.
- [ ] There are no generic field-background openings.
- [ ] Unnecessary hedging has been removed.
- [ ] All key figures have self-contained captions.

### Technical

- [ ] Citations are verified.
- [ ] Error bars and statistical reporting are clear.
- [ ] Compute resources are documented.
- [ ] Code / data availability is stated.

## Final Sentence

**A paper is not just a written record of experiments. It is a technical conclusion organized into a story that a reviewer is willing to believe.**
