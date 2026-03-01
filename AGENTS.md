# Claude Working Agreement (Repo Rules)

## 0) Core Principles

- **Simplicity first:** Every change must be as small and localized as possible.
- **No guessing:** Never make claims about code or architecture you have not opened.
- **Stay grounded:** If something is unclear, say so and explain what you checked.

---

## 1) Standard Workflow for Any Task

### 1. Understand & Scope

- Restate the problem briefly in your own words.
- Identify likely relevant files as candidates (do not assume their contents).

### 2. Read Before Proposing

- Open and read all relevant files before suggesting solutions.
- If the user references a specific file: **read that file first**, then respond.
- Do not speculate about implementation details.

### 3. Propose a Plan (Before Major Changes)

- For non-trivial changes:
  - Present 1–3 possible approaches (if applicable).
  - Recommend the simplest one.
  - Describe the smallest possible patch.
- **Stop and check in** before proceeding with major changes.

### 4. Implement (Minimal Patch Only)

- Modify the smallest possible surface area.
- Avoid incidental refactors (renaming, formatting, restructuring).
- Do not introduce architectural shifts without explicit approval.

### 5. After Each Step

- Provide a concise, high-level explanation of:
  - What was changed
  - Why it was changed
  - Which key files were affected

---

## 2) Definition of a "Major Change" (Requires Check-In)

You must check in before proceeding if the change:

- Introduces new dependencies or services
- Modifies database schemas or migrations
- Changes core interfaces or contracts
- Involves significant refactoring
- Alters build, CI, or deployment logic
- Affects multiple modules or exceeds ~100 lines

If unsure whether something is major → check in first.

---

## 3) Architecture Documentation (Must Stay Updated)

Maintain a documentation file that explains:

- System components/modules and their responsibilities
- Key data flows
- Important dependencies and integrations
- Runtime and deployment overview
- How to navigate and reason about the codebase

Recommended location: `docs/architecture.md` (or use existing file if present).

Any architectural or flow-related change must be reflected in this document.

---

## 4) Communication Rules

- Clearly state which files were opened when relevant.
- If something cannot be determined without reading a file, say so.
- No speculation. No assumptions. No hallucinated structure.
- If information is missing, request it explicitly.
