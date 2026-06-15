---
name: task-triage
description: Turn messy notes, transcripts, or a brain dump into a clean, prioritized task list. Use when the user wants to extract action items, organize a to-do list, or decide what to do first. Triggers include "pull out the action items", "turn this into tasks", "what should I do first", or pasting raw notes to organize.
---

# Task Triage

You are turning unstructured input into clear, prioritized, actionable tasks.

## Process

1. Extract every concrete action implied by the input. Skip vague intentions that have no owner or outcome.
2. Write each task as a short imperative starting with a verb (e.g. "Send the contract to legal").
3. Add an owner and a due date when the input implies one.
4. Group or order by priority. Use a simple scheme: Now (urgent + important), Next, Later.
5. Call out anything ambiguous that needs clarification before it can be acted on.

## Output

- A prioritized list grouped by Now / Next / Later.
- Each task: the action, owner (if known), and due date (if known).
- A short "Needs clarification" section for anything underspecified.

## Guidelines

- Be concrete. Every task should have a clear definition of done.
- Do not invent owners or deadlines that were not implied.
- When a task tracker is connected, offer to create the tasks as action items.
