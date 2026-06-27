# ag-skills

A workspace configuration toolkit containing custom AI Agent templates, conditional Skills, and automated Workflows. This repository is a fork combining **antigravity-kit**, **addyosmani/agent-skills**, and inspired by **[DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail)**, designed to enforce production-grade software engineering discipline on AI coding agents.

🇻🇳 **[Tiếng Việt (Vietnamese Version)](./README-VI.md)**

---

## 📦 What's Included

The `.agents/` folder contains the following core components to instruct and guide AI agents:

| Component | Count | Description |
| :--- | :--- | :--- |
| **Agents** | 20 | Specialist AI personas (Frontend, Backend, Security, PM, QA, etc.) |
| **Skills** | 54 | Domain-specific context modules with conditional loading rules (including Ponytail minimal-code discipline) |
| **Workflows** | 19 | Pre-configured interactive developer procedures (slash commands, including `/ship-fast`) |

---

## 🛠️ Usage in IDEs (Cursor, Windsurf, Antigravity)

### 1. Symbolic Link (Recommended)
To share this configuration across multiple local projects, you can symlink the `.agents/` directory into your project root:

- **macOS / Linux:**
  ```bash
  ln -s /path/to/ag-skills/.agents /path/to/project/.agents
  ```
- **Windows (PowerShell - Run as Administrator):**
  ```powershell
  New-Item -ItemType SymbolicLink -Path "C:\path\to\project\.agents" -Target "C:\path\to\ag-skills\.agents"
  ```

### 2. Autocomplete Support (Cursor/Windsurf)
To keep the `.agents/` directory out of your remote Git repository without losing the editor's autocomplete suggestions:
1. Ensure `.agents/` is **NOT** listed in your project's `.gitignore`.
2. Add `.agents/` to your local Git exclude file: `.git/info/exclude` instead.

---

## 📥 Available Workflows (Slash Commands)

Execute these workflows by typing their slash commands in your AI agent chat:

| Command | Description |
| :--- | :--- |
| `/spec` | Write a structured specification (PRD) before coding |
| `/plan` | Generate a structured implementation plan and checklist |
| `/build` | Implement tasks incrementally using TDD (supports `/build auto` for autonomous loops) |
| `/test` | Generate and execute comprehensive tests |
| `/verify` | Prove code works via execution checklists and build validation |
| `/code-simplify` | Simplify code complexity using Chesterton's Fence and Rule of 500 |
| `/ship-fast` | **NEW** Fast staged-only release gate check on current Git changes |
| `/ship` | Comprehensive release gate audit of the entire project |
| `/debug` | Activate evidence-based systematic debugging |
| `/coordinate` | Orchestrate multiple specialist agents in parallel |
| `/remember` | Save custom project conventions to persistent memory |
| `/webperf` | Run web performance audits via Lighthouse |

---

## 📄 License

Released under the [MIT License](LICENSE) © [Vudovn](https://github.com/vudovn).
