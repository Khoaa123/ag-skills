---
trigger: always_on
---

# Universal Rules (TIER 0) - AG Kit

> Always-active rules that apply to every request, regardless of domain.

---

## 🌐 Language Handling

When user's prompt is NOT in English:

1. **Internally translate** for better comprehension
2. **Respond in user's language** - match their communication
3. **Code comments/variables** remain in English

---

## 🧹 Clean Code (Global Mandatory)

**ALL code MUST follow `@[skills/clean-code]` rules. No exceptions.**

- **Code**: Concise, direct, no over-engineering. Self-documenting.
- **Testing**: Mandatory. Pyramid (Unit > Int > E2E) + AAA Pattern.
- **Performance**: Measure first. Adhere to current Core Web Vitals standards.
- **Infra/Safety**: 5-Phase Deployment. Verify secrets security.

---

## 📁 File Dependency Awareness

**Before modifying ANY file:**

1. Check `CODEBASE.md` → File Dependencies
2. Identify dependent files
3. Update ALL affected files together

---

## 🗺️ System Map & Memory Read

> 🔴 **MANDATORY:** At session start, you MUST read:
> 1. `.agents/ARCHITECTURE.md` to understand Agents, Skills, and Scripts.
> 2. `.agents/memory/MEMORY.md` to load persistent project conventions, user preferences, and decisions.

**Path Awareness (Note: the project directory name is `.agents` plural):**

- Agents: `.agents/agent/` (Project)
- Skills: `.agents/skills/` (Project)
- Memory: `.agents/memory/` (Project)
- Runtime Scripts: `.agents/skills/<skill>/scripts/`

---

## 🧠 Read → Understand → Apply

```
❌ WRONG: Read agent file → Start coding
✅ CORRECT: Read → Understand WHY → Apply PRINCIPLES → Code
```

**Before coding, answer:**

1. What is the GOAL of this agent/skill?
2. What PRINCIPLES must I apply?
3. How does this DIFFER from generic output?
