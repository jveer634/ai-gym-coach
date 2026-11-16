# Token-Efficient Handling & Progressive Disclosure

Read this whenever a query involves uploaded media (video, PDF, image), extensive log history, or when deciding which modular reference guides to load.

---

## 1. Progressive Disclosure of Reference Files

To minimize context window consumption, **never load all reference files on every turn**. Load modular references on demand only when the user query requires that specific domain:

| Reference File | When to Load | Do NOT Load When |
| :--- | :--- | :--- |
| `references/token-efficiency.md` | Session start / file ingestion | Query is a simple text question already covered |
| `references/verification-checklist.md` | Designing or revising workout/diet | User is merely checking in with casual questions |
| `references/file-templates.md` | Creating or modifying profile/plan/logs | Purely conversational turn without file writes |
| `references/biomarker-guide.md` | Blood report uploaded or lab values cited | No blood work or lab tests involved |
| `references/movement-analysis.md` | Lift video, posture photo, or form check | Diet-only or general programming inquiries |
| `references/pain-management.md` | User reports joint pain, pinch, or injury | User reports normal muscle soreness (DOMS) |
| `references/recommendation-guidelines.md` | Calculating macros, splits, or adjustments | Reviewing historical logs or answering basic Qs |

---

## 2. Core Directive: Extract Once, Store Compact, Never Re-Process

The first time any PDF, video, or photo is processed:
1. Ingest the file once and summarize into a compact markdown table or bullet list in that day's `session.md`.
2. Save representative freeze-frame assets (if video) into `logs/<date>/assets/`.
3. The extracted text artifact — **never the original raw file** — becomes the single source of truth for all subsequent turns and future sessions.
4. **Never re-attach, re-read, or re-parse a previously processed file** unless the user uploads a newer version or explicitly requests a re-examination.
5. If you need a past result (e.g., prior Vitamin D level or prior squat cue), read the compact line from `progress-log.md` or the corresponding `session.md` — never re-open the source media.

---

## 3. Video Handling (High-Cost Media)

- **Trimming**: If an uploaded video is longer than ~30–45 seconds or contains multiple sets/angles, request the user to trim to 1–2 clean working reps.
- **Representative Frames**: Analyze 2–3 critical biomechanical points (e.g., bottom of squat, turnaround of bench press, floor break of deadlift) rather than parsing every continuous frame.
- **Store Findings Once**: Describe the movement flaws, verbal cues, and corrective drills in `session.md`. Do not repeat long descriptions in future turns; reference the dated log entry.

---

## 4. Image Handling (Skin, Hair, Posture Photos)

- One clear photo per angle/area is sufficient. Do not request redundant shots unless the initial photo is completely obscured or unreadable.
- Store the objective, non-diagnostic visual description in `session.md` and reference that text in later discussions.

---

## 5. Blood Work Reports (PDFs & Scans)

- Parse blood reports directly into the compact markdown table schema (Marker | Result | Range | Status | Athletic Context).
- If the user provides lab values directly as plain text, prefer and encourage it: plain text avoids all PDF extraction overhead.

---

## 6. Efficient Log Reading Protocols

1. **Default to the Summary**: At the start of a session, read only `profile.md` and `logs/progress-log.md`.
2. **Drill Down Only on Direct Triggers**: Only open a specific `logs/YYYY-MM-DD/session.md` if:
   - The user explicitly asks about that specific past session, or
   - `progress-log.md` flags an unresolved open item or delta requiring detailed historical context.
3. **Consolidating Old Logs**:
   - When `progress-log.md` exceeds 12–15 dated entries, condense the oldest entries into a single rolled-up summary block (e.g., *"Sessions Jan–Apr 2026: Goal was lean bulk; scale weight increased 78kg → 81kg; Vitamin D resolved 22 → 46 ng/mL; active plan transitioned to Upper/Lower"*).
   - Never purge active medical flags or unresolved injury notes during consolidation.
