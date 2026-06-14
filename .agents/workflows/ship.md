---
description: Run the pre-launch checklist via parallel fan-out to specialist personas, then synthesize a go/no-go decision.
---

# /ship - Pre-Launch Release Gate

$ARGUMENTS

---

## 🔴 CRITICAL RULES

1. **Parallel Auditing:** Always spawn `code-reviewer`, `security-auditor`, and `test-engineer` in parallel (in a single assistant turn) to avoid sequential delays.
2. **GO/NO-GO Verdict:** Default verdict is NO-GO if any critical security vulnerability or blocking code-review issue is found.
3. **Rollback Plan Mandatory:** A GO decision is prohibited without a documented rollback plan.
4. **Skip Rule:** Only skip this fan-out if the change is ≤2 files, ≤50 lines, and does not touch auth, payments, database, or secrets.

---

## Phase A — Parallel Fan-Out

Spawn three subagents concurrently using the `invoke_subagent` tool:
1. **`code-reviewer`** — Run a five-axis code review (correctness, readability, architecture, security, performance) on staged changes/recent commits.
2. **`security-auditor`** — Run threat-model and vulnerability check (OWASP, secrets, rate-limiting).
3. **`test-engineer`** — Analyze test coverage, identify gaps in happy path, edge cases, and error paths.

*Note: Spawn them concurrently in a single turn. Do not let them delegate to each other.*

---

## Phase B — Synthesis & Merge

Collect all reports and synthesize findings:
1. **Code Quality:** Aggregate critical/important findings and test results.
2. **Security:** Promote critical/high security issues to blocker status.
3. **Performance & Accessibility:** Review performance bottlenecks and WCAG accessibility.
4. **Infrastructure:** Check environment variables, migrations, and feature flags.

---

## Phase C — Release Decision

Format the final output exactly as:

```markdown
## Ship Decision: [GO | NO-GO]

### Blockers (must fix before ship)
- [Source: Finding + File:Line]

### Recommended fixes (should fix before ship)
- [Source: Finding + File:Line]

### Acknowledged risks (shipping anyway)
- [Risk + mitigation]

### Rollback plan
- Trigger conditions: [signals to prompt rollback]
- Rollback procedure: [exact commands/steps]
- Recovery time objective: [target timeframe]

### Specialist reports (full)
- [code-reviewer report]
- [security-auditor report]
- [test-engineer report]
```
