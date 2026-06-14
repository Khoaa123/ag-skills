---
description: Create project specification (PRD) before planning and coding. No code writing - only spec file generation.
---

# /spec - Spec-Driven Development Mode

$ARGUMENTS

---

## 🔴 CRITICAL RULES

1. **NO CODE WRITING** - This command creates a specification file only
2. **Clarify Assumptions** - Surface key assumptions for user confirmation before compiling the spec
3. **Six Core Areas** - Spec file must cover: Objective, Tech Stack, Commands, Project Structure, Code Style, Testing Strategy, Boundaries
4. **Dynamic Naming** - Spec file named `spec-{task-slug}.md` in the project root

---

## Task

Create the specification document with this context:

```
CONTEXT:
- User Request: $ARGUMENTS
- Mode: SPECIFICATION ONLY (no code, no execution plan yet)
- Output: spec-{task-slug}.md in project root

NAMING RULES:
1. Extract 2-3 key words from request
2. Lowercase, hyphen-separated, prefixed with "spec-"
3. Max 35 characters
4. Example: "add auth feature" → spec-auth-feature.md

RULES:
1. First, list assumptions and ask user for confirmation/clarification.
2. Build a clear specification based on approved assumptions.
3. Save the spec to spec-{task-slug}.md in the project root.
4. DO NOT write any implementation code files.
5. REPORT the exact file name created.
```

---

## Expected Spec Structure

Inside the `spec-{task-slug}.md` file, use the following structure:

```markdown
# Spec: [Project/Feature Name]

## Objective
[Clear goal, user stories, and acceptance criteria]

## Tech Stack
[Frameworks, libraries, exact versions to detect or ask]

## Commands
- Build: [command]
- Test: [command]
- Dev: [command]

## Project Structure
- [Path/]: [Description]

## Code Style
[Naming, patterns, and a code block snippet showing the style]

## Testing Strategy
[Framework, unit/integration/E2E breakdown, and coverage targets]

## Boundaries
- **Always do**: [Things that must be done]
- **Ask first**: [Things requiring user approval before acting]
- **Never do**: [Prohibited behaviors]
```

---

## After Specification

Tell the user:
```
[OK] Specification created: spec-{slug}.md in project root

Next steps:
- Review the specification
- Run `/plan` to create the implementation plan
- Or modify the specification manually
```

---

## Naming Examples

| Request | Spec File |
|---------|-----------|
| `/spec e-commerce cart feature` | `spec-ecommerce-cart.md` |
| `/spec user authentication module` | `spec-user-auth.md` |
| `/spec dark mode toggle` | `spec-dark-mode.md` |

---

## Usage

```
/spec e-commerce cart feature
/spec user authentication module
/spec dark mode toggle
```
