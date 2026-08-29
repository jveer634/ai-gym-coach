# gym-coach

A portable AI skill: a gym & nutrition specialist that analyzes blood work, posture/movement videos, and skin photos, asks clarifying questions instead of assuming conditions, and tracks progress across dated session logs.

## Contents

```
gym-coach/
└── SKILL.md      # the skill definition — this is the only file the agent needs to read
```

The skill will create `profile.md` and a `logs/` folder in your workspace the first time it runs — you don't need to create those yourself.

## How to load it, by platform

**Claude Code / Claude Desktop (native Skills support)**
Copy the whole `gym-coach/` folder into your project's skills directory, e.g.:
```
<project-root>/.claude/skills/gym-coach/
```
It will be auto-discovered — no manual instruction needed.

**Claude.ai (Projects) or any chat-based agent without native skill folders**
Upload `SKILL.md` as a project file, or paste its contents into the project/custom instructions. At the start of a session say something like: *"Follow the instructions in SKILL.md for this conversation."*

**Any other agent (ChatGPT custom GPT/Projects, Gemini Gems, local LLM agent, etc.)**
Paste the contents of `SKILL.md` into the system prompt / custom instructions field. These frameworks don't auto-discover skill folders, so the instructions need to be supplied directly as the system prompt for the workspace.

**Coding agents with a working directory (Cursor, Aider, etc.)**
Place `SKILL.md` at the root of your workspace and reference it in whatever "always read this first" mechanism the tool supports (e.g., a `.cursorrules` or `AGENTS.md` pointer file that says "Also read SKILL.md and follow it").

## First run

On first use, the skill will ask for your goal (e.g., powerlifting, lean physique, fat loss) before analyzing anything, then create `profile.md` to store it. Every session after that reads `profile.md` and the `logs/` folder before responding, and logs its own findings there when it's done.
