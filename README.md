# 🏋️‍♂️ AI Gym Coach Skill (v4.0.0)

A modular, privacy-first, evidence-informed AI Coach skill for agentic LLMs (Google Antigravity, Claude Code, Cursor, Windsurf, Aider, and ChatGPT/Gemini). It acts as an elite strength and nutrition coach that designs personalized splits, calculates macro targets, auto-regulates progress, performs technical lift form checks, and tracks dated logs—all running **100% locally** in your workspace.

Unlike basic generic workout generators, this skill is modeled after a real-world elite coach: **it verifies before it prescribes**, never guesses, respects athletic physiology, and utilizes closed-loop autoregulation.

---

## ✨ Key Features & Capabilities

* **🔒 Strict Local Privacy (100% Local)**: Zero cloud leakage or third-party API exposure. All blood test reports, form check videos, photos, and progress logs are processed and stored strictly within your local workspace.
* **🔬 Athletic Biomarker & Metabolic Engine**: Parses blood panels (hormones, thyroid, lipid panel, iron stores, metabolic markers) with athletic nuance (e.g., understanding resistance-training induced AST/ALT/CK and creatine-induced creatinine elevations without false alarms).
* **🎥 Technical Movement Screening & Joint Audits**: Audits lift videos (Squats, Deadlifts, Bench Press, OHP, Rows) frame-by-frame with joint alignment checkpoints, J-curve bar path tracking, external coaching cues, and targeted corrective drills.
* **📊 Scientific Periodization & Volume Landmarks**: Implements evidence-based volume landmarks (**MEV, MAV, MRV**), **Dynamic Double Progression (DDP)**, RPE/RIR intensity targets, and proactive/reactive deload protocols.
* **🥗 Precision Nutrition & Metabolic Stall Protocols**: Calculates TDEE via Mifflin-St Jeor / Katch-McArdle, enforces protein and essential fat floors, and implements structured **48-hour carbohydrate refeeds**, diet breaks, and post-cut reverse dieting.
* **🩹 5-Step Movement Pain Regression Ladder**: Systematically regresses movements when joint discomfort occurs (Setup $\rightarrow$ Load $\rightarrow$ Range of Motion $\rightarrow$ Implement Swap $\rightarrow$ Tendon Isometrics) while triaging clinical red flags.
* **💊 3-Tier Evidence-Based Supplementation**: Categorizes recommendations into Tier A (Gold Standard), Tier B (Context-Dependent), and Tier C (Ineffective/Avoid) with strict medication interaction checks.

---

## 📁 File & Workspace Structure

The project employs **progressive disclosure**: high-level orchestration remains in `SKILL.md`, while specialized domain guides under `references/` are lazy-loaded only when triggered.

### 1. Skill Files (Included in Repository)
```
gym-coach/
├── SKILL.md                          # Main orchestrator (Role, Prime Directive, Workflow, Checklist)
├── README.md                         # Documentation & platform installation guide
└── references/                       # Loaded dynamically on demand
    ├── verification-checklist.md     # Pre-prescription verification checkpoints
    ├── file-templates.md             # Markdown schemas for profile.md, plan.md, and logs/
    ├── token-efficiency.md           # Progressive disclosure & media extraction rules
    ├── input-processing.md           # Media ingestion & local privacy rules
    ├── biomarker-guide.md            # Athletic lab panel interpretations & non-diagnostic phrasing
    ├── movement-analysis.md          # Joint checkpoints, bar paths, and corrective drills
    ├── pain-management.md            # 5-step regression ladder & injury triage
    └── recommendation-guidelines.md  # Volume landmarks, macros, refeeds, and supplements
```

### 2. Workspace Files (Generated Automatically on First Run)
```
/ (your workspace root)
├── profile.md                        # Static user profile (Goals, injuries, biometrics, baselines)
├── plan.md                           # Active single source of truth (Split, volume, macros, supplements)
└── logs/
    ├── progress-log.md               # Append-only chronological master log & deltas
    └── YYYY-MM-DD/                   # Dated folder for each coaching interaction
        ├── session.md                # Detailed session log (Extracted markers, cues, rationale)
        ├── inputs/                   # Locally saved raw uploads (reports, videos, photos)
        └── assets/                   # Representative freeze-frames and posture crops
```

---

## ⚡ First-Run Flow

1. **Detection**: On initial execution, the agent checks whether `profile.md` exists with an active goal.
2. **Goal Elicitation**: If missing, it elicits your primary training objective (e.g., lean aesthetic hypertrophy, powerlifting, fat loss) and baseline training experience.
3. **Verification Checklist**: Prompts for relevant context (schedule, equipment access, injuries, blood work, daily sleep/step baseline).
4. **Plan Creation**: Formulates your initial `plan.md` tied directly to verified data, initializing the version history and local logging system.

---

## 🚀 How to Load by Platform

### 🛸 Google Antigravity
The skill is located at your workspace root or inside `.agents/skills/gym-coach/`. Antigravity auto-discovers `SKILL.md` and lazy-loads the reference files when needed.

### 🤖 Claude Code & Claude Desktop (Native Skills)
Copy the `gym-coach/` folder into your project's skills directory:
```bash
cp -r gym-coach/ <project-root>/.claude/skills/
```
The agent will auto-discover the skill and load references dynamically on demand.

### 💻 Cursor, Windsurf, Aider & Coding Agents
Place the `gym-coach/` folder at your workspace root. Point your configuration file (like `.cursorrules`, `.windsurfrules`, or `AGENTS.md`) to read the skill:
> *"When acting as a gym coach, read `gym-coach/SKILL.md` first and follow its workflows and local references."*

### 💬 ChatGPT (Custom GPTs), Gemini (Gems), or Claude.ai (Projects)
* **Multi-file / Project Upload**: Upload `SKILL.md` and all files under `references/`. Instruct the agent in its system prompt: *"Refer to files under `references/` as directed by `SKILL.md` to guide your analysis."*
* **Single Prompt**: Copy `SKILL.md` and append the contents of the `references/` files underneath into the custom instruction prompt.
