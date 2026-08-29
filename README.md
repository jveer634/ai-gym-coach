# 🏋️‍♂️ AI Gym Coach Skill

A portable, modular, and privacy-first AI Coach skill for agentic LLMs. It acts as an expert gym and nutrition coach that designs personalized splits, calculates macro targets, auto-regulates progress, checks lift form, and tracks dated logs—all while running **100% locally** in your workspace.

Unlike basic workout generators, this skill is modeled after a real-life premium coach: **it verifies before it prescribes**, never guesses, and uses strict feedback loops to adjust targets when progress stalls.

---

## ✨ Key Features & Capabilities

* **🔒 Strict Local Privacy**: No data-sharing, cloud uploading, or leaks. All photos, videos, blood reports, and progress logs are processed and stored locally in your workspace.
* **📈 Auto-Regulated Progression**: Focuses on progressive overload using **RPE (Rate of Perceived Exertion)** and **RIR (Reps in Reserve)** targets instead of static weight guides.
* **🛑 Decision Stall Protocols**: If weight loss stalls for 14 days or muscle gain stalls for 21 days, the coach applies structured adjustment guidelines (tweaking calories, NEAT step count targets, or implementing diet breaks).
* **🎥 Technical Lift Form Checks**: Evaluates lift videos frame-by-frame (Squats, Deadlifts, Bench Press, etc.) and provides **actionable cues and corrective mobility drills** rather than generic critique.
* **📊 Biomarker-Guided Dieting**: Parses blood test reports to recommend specific evidence-backed nutritional adjustments and supplements, rather than making default guesses.

---

## 📁 File & Workspace Structure

The project splits the core instructions from detail guides to remain highly **token-efficient** (the agent only loads template or movement rules when it needs them).

### 1. Skill Files (What you load)
```
gym-coach/
├── SKILL.md                          # Entry point (Role, Prime Directive, Workflow)
└── references/                       # Loaded on-demand by the agent
    ├── verification-checklist.md     # What to verify before making any change
    ├── file-templates.md             # Markdown schemas for profile, plan, and logs
    ├── input-processing.md           # Visual form check & blood work parsing rules
    ├── recommendation-guidelines.md  # Progression, deloads, and calorie stall rules
    └── token-efficiency.md           # Instructions for keeping LLM token usage low
```

### 2. Generated Files (Created in your workspace on first run)
```
/ (your project root)
├── profile.md                        # Static user profile (Goals, injuries, baseline lifestyle)
├── plan.md                           # The active single source of truth (Workout split, macros)
└── logs/
    ├── progress-log.md               # Append-only running history of advice and action items
    └── YYYY-MM-DD/                   # Dated folder for each review session
        ├── session.md                # Detailed session log (Blood markers, cue recommendations)
        ├── inputs/                   # Locally saved raw uploads (photos, videos, reports)
        └── assets/                   # Key cropped/annotated form frames or progress charts
```

---

## ⚡ First-Run Flow

1. On first load, the agent detects if `profile.md` exists. 
2. If missing, it triggers the **Goal Elicitation Flow**: asks what you are training for (e.g., powerlifting, lean aesthetic, fat loss) and requests basic context (injuries, experience).
3. It then initializes `profile.md` and prompts you for the missing details in the **Verification Checklist** (like typical sleep, steps, diet, or blood work) to responsibly draft your first `plan.md`.

---

## 🚀 How to Load by Platform

### 🤖 Claude Code & Claude Desktop (Native Skills)
Copy the `gym-coach/` folder into your project's skills directory:
```bash
cp -r gym-coach/ <project-root>/.claude/skills/
```
*The agent will auto-discover the skill and load references dynamically on demand.*

### 💻 Cursor, Aider, Windsurf, & Coding Agents
Place the `gym-coach/` folder at your workspace root. Point your configuration file (like `.cursorrules`, `.windsurfrules`, or `AGENTS.md`) to read the skill:
> *"When acting as a gym coach, read `gym-coach/SKILL.md` first and follow its workflows and local references."*

### 💬 ChatGPT (Custom GPTs), Gemini (Gems), or Claude.ai (Projects)
* **If the platform supports folder/multi-file uploads**: Upload `SKILL.md` and the entire `references/` directory. Instruct the agent in its system prompt: *"Refer to files under `references/` as directed by `SKILL.md` to guide your analysis."*
* **If it only supports a single system prompt**: Copy the contents of `SKILL.md` and paste it into the custom instructions field, then append the contents of the `references/` files underneath.
