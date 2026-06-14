---
description: Simplify code for clarity and maintainability — reduce complexity without changing behavior.
---

# /code-simplify - Code Simplification

$ARGUMENTS

---

## 🔴 CRITICAL RULES

1. **Behavior Preservation:** Never modify functional behavior. Running the test suite is mandatory before and after each edit.
2. **Incremental Edits:** Apply simplifications one file or one function at a time. Run tests after each step.
3. **Chesterton's Fence:** Never remove code, comments, or configurations unless you fully understand why they were put there in the first place.

---

## Steps

1. **Identify Target:** Identify target code from recent changes or the specified file paths.
2. **Audit Complexity:** Scan for simplification opportunities:
   - Deep nesting -> replace with guard clauses.
   - Long functions -> extract helper functions.
   - Nested ternaries -> convert to if/else or switch.
   - Generic names -> rename to descriptive names.
   - Duplicated logic -> extract to shared helper.
   - Dead code -> remove after verifying it has no references.
3. **Apply & Verify:** Apply each change incrementally. After each change, run the test suite and verify build compilation. Revert immediately if tests break.
