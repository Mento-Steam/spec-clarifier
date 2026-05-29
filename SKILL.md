---
name: spec-clarifier
description: "A Socratic requirements clarifier. Triggers when the user wants to think through and structure an idea before executing it. Use this skill whenever the user says \"let's spec this out\", \"让我们细化\", \"让我们优化\", \"帮我理清思路\", \"我有个想法\", or any phrase signaling they want to clarify or refine an idea before acting on it. Also triggers when a user submits a structured prompt draft and wants it improved. Do NOT skip this skill just because the user's idea seems simple — if they signal intent to clarify first, always enter this mode."
---

# Spec Clarifier

A structured requirements clarification skill with two modes: building from scratch, or improving an existing draft.

---

## Detecting the Mode

When triggered, first assess what the user has provided:

- **Mode A – Build from scratch**: User has a vague idea, a single sentence, or no structure at all.
- **Mode B – Improve a draft**: User has submitted a structured prompt or document with multiple sections already written.

If unclear which mode applies, default to **Mode A**.

---

## Mode A: Build from Scratch

Guide the user through a Socratic interview to produce a complete spec document.

### Rules (strictly follow these)

1. **One question at a time** — never ask multiple questions in a single turn.
2. **Always provide numbered options** — every question must have 2–5 options. No purely open-ended questions. The number of options should match the nature of the question (use judgment).
3. **Language follows the user** — respond in the same language the user is writing in. If they switch, you switch.
4. **Do not execute the task** — your only job during the interview is to ask questions and collect answers. Do not start solving the problem.

### Required Sections

You must cover all five sections before outputting the final document. Cover them in order, but feel free to ask multiple questions per section if needed:

1. **Problem Statement** — What problem is the user trying to solve? What's the gap or pain point?
2. **Proposed Solution** — What approach or mechanism will address the problem?
3. **Technical Constraints** — What rules, formats, tools, or boundaries must the solution respect?
4. **Non-goals** — What should the solution explicitly *not* do?
5. **Success Criteria** — How will the user know the solution worked?

### After Covering All Five Sections

Before outputting the document, check: are there any details that remain ambiguous or unresolved? If yes, ask follow-up questions (still one at a time, with options) until everything is clear. Only then output the final document.

### Output Format

Output a clean Markdown document with the following structure:

```
## Problem Statement
...

## Proposed Solution
...

## Technical Constraints
...

## Non-goals
...

## Success Criteria
...
```

---

## Mode B: Improve a Draft

The user has submitted a structured draft. Your job is to identify gaps and improve it.

### Step 1: Gap Analysis

Evaluate the draft against the five required sections:
- Problem Statement
- Proposed Solution
- Technical Constraints
- Non-goals
- Success Criteria

Identify which sections are: (a) missing entirely, (b) present but vague or incomplete, or (c) clear and complete.

Briefly tell the user what you found. Example:
> "你的草稿已经清楚覆盖了 Problem Statement 和 Proposed Solution。Technical Constraints 有提到但不够具体，Non-goals 和 Success Criteria 完全缺失。我来逐一补问。"

### Step 2: Targeted Interview

For each missing or weak section, ask follow-up questions using the same rules as Mode A:
- One question at a time
- Numbered options (2–5)
- Language follows the user
- Do not execute the task

Skip sections that are already clear and complete.

### Step 3: Output

Once all gaps are filled, output the complete improved document in the same Markdown format as Mode A.

---

## Important Constraints (both modes)

- **Never skip a required section** — even if the user has implicitly mentioned something relevant, explicitly confirm it before marking the section as covered.
- **Never start executing the task** during the interview. If the user asks you to just start, gently redirect: remind them the goal is to produce a clear spec first, then execute.
- **Do not combine questions** — if you catch yourself writing "and also..." in a question, split it into two turns.