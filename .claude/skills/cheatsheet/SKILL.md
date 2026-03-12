---
name: cheatsheet
description: Build or update a cheat sheet section for a specific lecture. Reads the lecture PDF, identifies topics, dispatches one agent per topic to draft content, cross-references with homework/practice exams, and writes the final section to CheatSheet.md.
argument-hint: "[lecture name or number, e.g. L07 or L08 Warehouse Operations]"
---

You are building a cheat sheet for an exam. The cheat sheet lives at `CheatSheet.md` in the project root. Follow CLAUDE.md formatting rules strictly.

## Step 0: Determine the lecture

If `$ARGUMENTS` specifies a lecture (e.g., "L07", "L08 Warehouse Operations"), use that. Otherwise, ask the user which lecture they want to add or update.

Find the matching PDF in the `Lectures/` folder (use Glob for `Lectures/*`). If ambiguous, ask.

## Step 1: Read & understand the lecture

Read the full lecture PDF. Use PyMuPDF (`fitz`) via Bash since pdftoppm is unavailable on this system:
```python
import sys, fitz
sys.stdout.reconfigure(encoding='utf-8')
doc = fitz.open('Lectures/<filename>.pdf')
for i in range(doc.page_count):
    page = doc[i]
    print(page.get_text())
```

Also read `CheatSheet.md` to understand the existing format and what's already there.

## Step 2: Identify topics

Break the lecture into discrete topics/subjects (e.g., "Returnable Containers", "Equipment Selection", "10 Principles"). Each topic should be a self-contained chunk that could become one subsection of the cheat sheet.

List the topics to the user before proceeding.

## Step 3: Check homework & practice exams

Read all PDFs in `Problems/` to find which problems reference this lecture. Note what types of questions are asked (calculation procedures, conceptual matching, interpretation). This tells you which topics need step-by-step procedures vs. quick reference lists.

## Step 4: Dispatch one agent per topic

For each topic, spin up an agent (use the Agent tool) with:
- The relevant lecture content for that topic (paste the extracted text)
- What problem types test this topic (from Step 3)
- These formatting instructions:

> You are drafting one section of an exam cheat sheet. Rules:
> - SUPER slim and concise -- very limited physical space
> - Max 2 heading levels (# and ##). No ### or deeper
> - Prefer small code-block visuals (matrices, diagrams, formula blocks) over long text explanations
> - For calculation procedures, write clear step-by-step formulas in a code block
> - For conceptual/classification topics, use compact bullet points or a decision-logic code block
> - No emojis. No fluff. Only what's needed to solve exam problems from scratch
> - Output raw markdown only -- no commentary

Launch all agents in parallel (single message, multiple Agent tool calls).

## Step 5: Synthesize & write

Once all agents return:
1. Review each agent's output for accuracy against the lecture content
2. Combine them under a single `# L<number> <Lecture Title>` heading
3. Add any missing details you noticed from the homework/practice exam cross-reference
4. Compare against the user's existing reference material already in `CheatSheet.md` -- merge anything the agents missed
5. Write the final section to `CheatSheet.md` (append after the last lecture section, or replace if updating)

## Step 6: Present to user

Show the user what was written and ask if anything needs adjusting. Be ready to iterate.
