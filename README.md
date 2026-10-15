# Personal & Team Agent Kit

A reusable rule set for AI coding agents (Antigravity and other Agent Skills IDEs) across personal and professional projects.

## Layout

```text
AGENTS.md          always-on constitution (workflow, hierarchy of truth, safety, git, sub-agents, circuit breaker)
PROJECT.md         per-project facts: stack, commands, docs/schema locations, external tools, conventions
init.sh            Linux/macOS init script (copies kit without overwriting)
init.ps1           Windows PowerShell init script (copies kit without overwriting)
.agents/
  agents/          specialized sub-agents: project-reviewer, plan-reviewer, codebase-reviewer
  rules/           loaded by context: coding, testing, security, data
  skills/          loaded by task: spec, architect, build, debug, review, db-migration
  tasks/           active execution plans (auto-archived to tasks/archive/ upon DoD)
```
## Use

**Linux / macOS (Bash):**
```bash
./init.sh /path/to/new-project
```

**Windows (PowerShell):**
```powershell
.\init.ps1 -Target "D:\path\to\new-project"
```

Then ask the agent: "Read AGENTS.md. Inspect the repo and draft PROJECT.md (stack, commands, structure). Do not change any code."

Optional: keep this kit in its own git repo or a GitHub template repo so every new project starts from the same copy.

## Prompts

- Small task: "Quick mode: fix [issue]. Minimal change, run checks, report."
- Big task: "Plan-first: [feature]. Inspect the repo and propose a plan. Do not edit code yet."
- Sub-agent Delegation & Collaboration:
  - Khảo sát rộng & Web search: "Dùng `research` tra cứu tài liệu thư viện X và giải pháp tốt nhất."
  - Kiến trúc & nghiệp vụ nội bộ: "Dùng `project-reviewer` khảo sát toàn bộ tech stack, DB schema và luồng nghiệp vụ."
  - Phản biện kế hoạch: "Dùng `plan-reviewer` đánh giá kế hoạch trong .agents/tasks/[task].md trước khi code."
  - Thử nghiệm / Nhánh song song: "Ủy quyền cho `self` trên workspace nhánh riêng để làm PoC phần này."
  - Kiểm tra an ninh & chất lượng: "Dùng `codebase-reviewer` kiểm tra diff, AppSec và convention trước khi merge."
  - Quy tắc Firestore: "Ủy quyền cho `firestore-rules-author` cấu hình firestore.rules."

## Model tiering (for you, not for the agent)

- Strongest model: architecture, hard debugging, large refactors, final review.
- Mid-tier model: implementing an approved plan, writing tests, fixing diagnosed bugs.
- Cheapest model: formatting, docstrings, README upkeep, mechanical cleanup.

## Using other AI tools

`AGENTS.md` is the single source of truth. If you also use a tool that looks for its own file (for example `CLAUDE.md`), create that file with one line: `Read and follow AGENTS.md and PROJECT.md.` Do not copy the rules into it, so they cannot drift apart. Check each tool's docs for the file name it expects.

## Adding project-specific rules

Put stack-specific guidance (e.g. a React or Django skill) in that project's own `.agents/skills/`, not in this shared kit. Keep the shared kit stack-agnostic.

## Verify once per IDE version

Folder names (`.agents/` vs `.agent/`), the `trigger: model_decision` frontmatter, and auto-detection of `AGENTS.md` depend on your Antigravity version. Check the official docs, then run a test prompt and confirm the agent mentions `PROJECT.md` and the Circuit Breaker.
