---
name: ponytail
description: Lazy Senior Dev decision ladder - enforces minimal code writing, standard lib reuse, zero unnecessary dependencies, and YAGNI.
when_to_use: "Apply during code implementation, editing, or refactoring. Forces the AI to think like the laziest senior dev before writing code. NOT for initial architectural planning or spec writing."
allowed-tools: Read, Write, Edit, Grep, Glob
effort: medium
---

# Ponytail — The Laziest Senior Dev Mindset

> **Core Philosophy:** *The best code is the code you never wrote. The second best is code anyone can read.*

Complexity is an expensive debt. Before writing any new code, abstractions, or installing dependencies, you MUST pass through the **Ponytail Decision Ladder**.

---

## 🪜 The Ponytail Decision Ladder

Before adding or modifying code, evaluate these 6 steps sequentially:

| Step | Question | Action if YES |
|---|---|---|
| **1. Is it necessary?** | Is this feature/code strictly required right now? (YAGNI) | If NO, **do not write it**. |
| **2. Does it exist?** | Can existing code in the project be reused or refactored? | Reuse existing functions/modules instead of rewriting. |
| **3. Standard Library?** | Can the programming language's standard library do this? | Use native built-in methods (e.g., `Array.prototype`, `path`, `math`). |
| **4. Native Platform?** | Does the browser or OS platform support this natively? | Use native platform capabilities (e.g., `<input type="date">`, Web APIs). |
| **5. Existing Package?** | Can an already-installed dependency handle this? | Use existing dependencies. **Do NOT add new npm/pip packages** without explicit need. |
| **6. Can it be a One-Liner?** | Is a dedicated helper function unnecessary? | Inline the expression directly where used. |

---

## 🛡️ AG-Skills Guardrails (Non-Interference Guarantee)

To maintain 100% compatibility with the `ag-skills` architecture:

1. **Phase Isolation:** Ponytail rules apply **ONLY during active code writing, editing, or refactoring**. They must NOT block or alter high-level project planning (`project-planner`), specification writing (`spec-driven-development`), or architectural designs (`architecture`).
2. **Quality Alignment:** Ponytail works hand-in-hand with `clean-code` and `simplify-code`. It acts as a pre-execution gatekeeper to prevent bloat before code hits disk.
3. **No Compromise on Security/Correctness:** "Laziness" means eliminating unnecessary abstractions and code bloat, **NEVER** skipping security validations, tests, or error handling.

---

## ❌ Anti-Patterns Ban List

| ❌ Forbidden Pattern | ✅ Ponytail Remedy |
|---|---|
| Installing a library for simple tasks (e.g., `lodash`, `moment`) | Use native JS methods or standard libraries |
| Creating wrapper classes for single third-party calls | Call the API or SDK directly |
| Adding config objects for 1-2 static parameters | Pass direct arguments or hardcode if invariant |
| Creating a `utils.ts` file for one single helper function | Co-locate or inline the logic directly where used |
| Writing custom UI components for features built into browsers | Use native semantic HTML5 tags |
