# gym-coach

A portable AI skill: a gym coach that verifies blood work, current nutrition, dietary preferences, and health/hair/skin conditions before designing a workout split and diet — asks clarifying questions instead of assuming conditions, and tracks progress and the current plan across dated session logs.

## Contents

```
gym-coach/
├── SKILL.md                              # entry point — always loaded when the skill triggers
└── references/                           # loaded on demand, only when SKILL.md points to them
    ├── verification-checklist.md         # what to verify before recommending anything
    ├── file-templates.md                 # exact formats for profile.md, plan.md, logs/
    ├── input-processing.md               # per-file-type rules (blood work, posture, skin, hair, video, text)
    └── recommendation-guidelines.md      # how to shape workout/supplement/diet suggestions
```

`SKILL.md` is intentionally short — it's the always-loaded core (role, prime directive, goal elicitation, workflow) and tells the agent exactly which `references/*.md` file to pull in and when, by relative path from the skill's own folder. None of the reference files load until the workflow step that needs them is actually reached, so a simple query doesn't pull in templates or per-input-type rules it doesn't need.

The skill will create `profile.md`, `plan.md`, and a `logs/` folder in your **workspace** (not inside the skill folder) the first time it runs — you don't need to create those yourself.

## How to load it, by platform

**Claude Code / Claude Desktop (native Skills support)**
Copy the whole `gym-coach/` folder — including `references/` — into your project's skills directory, e.g.:
```
<project-root>/.claude/skills/gym-coach/
```
It will be auto-discovered, and the agent will read `references/*.md` files by their relative path as `SKILL.md` directs — no manual instruction needed.

**Claude.ai (Projects) or any chat-based agent without native skill folders**
Upload the whole `gym-coach/` folder (or all its files, preserving the `references/` subfolder) as project files. At the start of a session say something like: *"Follow the instructions in gym-coach/SKILL.md, and read files under gym-coach/references/ as it directs."*

**Any other agent (ChatGPT custom GPT/Projects, Gemini Gems, local LLM agent, etc.)**
These typically don't support relative file loading or subfolders. Either upload all files (`SKILL.md` + everything in `references/`) if the platform supports multi-file project knowledge, or — if it only takes a single system prompt — paste `SKILL.md` first, then append the contents of each `references/*.md` file underneath it (still fine to keep the section headers) so nothing is missing at load time.

**Coding agents with a working directory (Cursor, Aider, etc.)**
Place the whole `gym-coach/` folder at your workspace root and reference `gym-coach/SKILL.md` in whatever "always read this first" mechanism the tool supports (e.g., a `.cursorrules` or `AGENTS.md` pointer file). The agent can then follow the relative `references/...` links itself since it has file-read access.

## First run

On first use, the skill will ask for your goal (e.g., powerlifting, lean physique, fat loss) before analyzing anything, then create `profile.md` to store it. Every session after that reads `profile.md`, `plan.md`, and the `logs/` folder before responding, pulls in only the `references/` files it needs for that specific query, and logs its own findings when it's done.
