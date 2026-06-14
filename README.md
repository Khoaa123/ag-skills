# AG KIT & AGENT-SKILLS

AI Agent templates with Skills, Agents, and Workflows — combining Antigravity-Kit and addyosmani/agent-skills. Features Coordinator Mode, Persistent Memory, and Context Compression.

🇻🇳 **[Tiếng Việt (Vietnamese Version)](./README-VI.md)**

---

## ⚡ Quick Start

Install and initialize AG Kit to inject the `.agents/` configuration folder directly into your local project.

### Method 1: On-demand Execution (Recommended)

```bash
npx @vudovn/ag-kit init
```

### Method 2: Global Installation

```bash
npm install -g @vudovn/ag-kit
ag-kit init
```

---

## 🌍 Global Shared Setup (Symlinks)

If you work across multiple repositories and want to avoid duplicating the `.agents/` folder in every single project, you can centralize AG Kit and use symbolic links.

1. **Install centrally** (e.g., to a global folder like `~/.ag-kit`):
   ```bash
   mkdir -p ~/.ag-kit && cd ~/.ag-kit
   npx @vudovn/ag-kit init
   ```

2. **Link it locally** from inside your project root:
   - **macOS / Linux:**
     ```bash
     ln -s ~/.ag-kit/.agents .agent
     ```
   - **Windows (CMD - Run as Administrator):**
     ```cmd
     mklink /D .agents "%USERPROFILE%\.ag-kit\.agents"
     ```
   - **Windows (PowerShell - Run as Administrator):**
     ```powershell
     New-Item -ItemType SymbolicLink -Path ".agents" -Target "$env:USERPROFILE\.ag-kit\.agents"
     ```

---

## ⚠️ Important Note on `.gitignore`

If you are using AI-native code editors (like **Cursor** or **Windsurf**), adding the `.agents/` directory to `.gitignore` will prevent the editor's language server from indexing the workflows, which disables autocomplete for slash commands (e.g. `/plan`, `/debug`).

### Recommended Solution:
To keep `.agents/` out of your remote repository without losing editor integration:
1. Ensure `.agents/` is **NOT** listed in your project's `.gitignore`.
2. Add `.agents/` to your local Git exclude file: `.git/info/exclude` instead.

---

## 📦 What's Included

AG Kit packages domain-specific knowledge, specialized agent personas, and automated workflows optimized for modern AI coding tools, now integrated with core engineering skills from `agent-skills`.

| Component | Count | Description |
| :--- | :--- | :--- |
| **Agents** | 20 | Specialist AI personas (Frontend, Backend, Security, PM, QA, etc.) |
| **Skills** | 53 | Domain-specific context modules with conditional loading rules (including 8 key skills from `agent-skills`) |
| **Workflows** | 18 | Pre-configured interactive developer procedures (slash commands, including 5 new workflows) |

---

## 🛠️ Usage

### 1. Zero-Setup Agent Auto-Routing

You don't need to manually orchestrate agents. The system silently classifies your request, auto-routes to the best domain experts, and applies their rules instantly:

```
You: "Add JWT authentication to the login API"
Agent: Applying @security-auditor + @backend-specialist...

You: "Align the checkout button to the center and fix dark mode"
Agent: Using @frontend-specialist...
```

### 2. Interactive Workflows (Slash Commands)

Execute structured development workflows by typing slash commands in your AI agent chat:

| Command | Description |
| :--- | :--- |
| `/brainstorm` | Structured exploration of options and architecture before coding |
| `/build` | **NEW** Implement tasks incrementally using TDD (supports `/build auto` for autonomous loops) |
| `/code-simplify` | **NEW** Simplify code complexity using Chesterton's Fence and Rule of 500 |
| `/coordinate` | Orchestrate multiple agents in parallel for complex reviews |
| `/create` | Create new features or full applications from scratch |
| `/debug` | Activate evidence-based systematic debugging |
| `/deploy` | Execute pre-flight checks and deploy to production |
| `/enhance` | Safely add or update features in an existing codebase |
| `/plan` | Generate a structured implementation plan and checklist |
| `/preview` | Start, stop, or check status of local preview servers |
| `/remember` | Save custom project conventions to persistent memory |
| `/ship` | **NEW** Release-gate checklist via parallel agents and rollback plan |
| `/spec` | **NEW** Write a structured specification (PRD) before coding |
| `/status` | Generate a clear status report of the agent's progress |
| `/test` | Generate and execute comprehensive tests |
| `/verify` | Prove code works via execution check lists and build validation |
| `/webperf` | **NEW** Web performance audit via upgraded `performance-optimizer` agent |

---

## 🧠 Core Architectural Concepts

AG Kit is built on production-tested agentic design patterns designed to reduce token usage by **13% to 33%** while yielding higher output quality:

*   **Coordinator Mode:** Multi-agent orchestration with parallel workers and synthesis, avoiding expensive sequential retries.
*   **Persistent Memory:** A 4-type taxonomy memory engine index (`MEMORY.md`) to prevent re-explaining project guidelines across sessions.
*   **Context Compression:** Automated summarization and micro-compaction routines to prevent context degradation in long-lived sessions.
*   **Conditional Skill Loading:** Context-aware loading of rules via custom frontmatter, preventing your context window from bloating with idle instructions.

---

## 📚 References & Attribution

AG Kit represents an original implementation of markdown-based prompt and rules engineering. It was built by analyzing production agent patterns to distill core agentic behaviors:
*   *No proprietary code or files were copied.*
*   All templates, rules, and scripts are rewritten as original, open-source implementations under the MIT license.



---

## 📄 License

Released under the [MIT License](LICENSE) © [Vudovn](https://github.com/vudovn).
