---
description: Implement tasks incrementally — build, test, verify, commit. Add "auto" to run the whole plan in one approved pass.
---

# /build - Incremental Build Mode

$ARGUMENTS

---

## 🔴 CRITICAL RULES

1. **Incremental Implementation:** Always implement code in small, vertical slices. One task at a time.
2. **Test-Driven:** Write tests first (RED), then code to pass (GREEN), then verify and commit.
3. **Clean Baseline:** Before `/build auto` runs, the git working directory must be clean of unrelated changes.
4. **Autonomous Sequence:** In `auto` mode, execute tasks in order automatically. Stop only on blockers, test failures, or high-risk tasks.

---

## Modes

- `/build` — Implement the next pending task in the plan, verify it, commit it, and stop.
- `/build auto` — Generate tasks from the spec, get approval for the plan, then execute and commit every task autonomously without human intervention between tasks.

---

## Task Execution Loop (Per Task)

For the target task (next pending task):
1. **Understand:** Read acceptance criteria and load relevant code context.
2. **Red:** Write a failing unit or integration test representing the requirement.
3. **Green:** Implement the minimum code to make the test pass.
4. **Regression Check:** Run the full test suite to check for regressions.
5. **Verify Build:** Run the build/compile step.
6. **Commit:** Commit with a descriptive message (e.g. `feat: add task creation endpoint`).
7. **Mark Done:** Mark the task complete and stop (or proceed if in `auto` mode).

---

## Autonomous Mode (`/build auto`)

1. **Verify Spec:** Must have a specification file (e.g., `spec-{task-slug}.md` or `spec.md` or `docs/SPEC.md`). If none exists, stop and tell the user to run `/spec` first.
2. **Baseline Check:** Run `git status`. If there are uncommitted changes, stop and ask the user to commit or stash.
3. **Create Plan:** If no tasks plan file (e.g. `task.md` or `tasks/plan.md`) exists, create it using `planning-and-task-breakdown` skill.
4. **Approval Gate:** Present the plan to the user and wait for explicit approval (e.g. "go", "yes").
5. **Run Loop:** Execute tasks in order using the Task Execution Loop. Stage only relevant files and commit task-by-task.
6. **Stop & Escalate:** Immediately pause and ask the user when:
   - A test fails or build breaks and can't be easily fixed.
   - The spec is ambiguous or requires a decision.
   - The task is high-risk/irreversible (e.g. payments, auth, data migration, secrets) -> triggers `doubt-driven-development` and requires explicit sign-off.
7. **Summary:** List completed tasks, added tests, commits, and any skipped/flagged items.
