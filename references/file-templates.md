# Workspace & File Structure

Read this when creating or updating `profile.md`, `plan.md`, or any file under `logs/`.

All work lives in the current workspace, next to the skill folder:

```
/ (workspace root)
├── profile.md                     # static/slow-changing user info
├── plan.md                        # current active workout + diet plan
└── logs/
    ├── 2026-08-24/                # one folder per analysis session, named by date (YYYY-MM-DD)
    │   ├── session.md             # summary of this session's inputs, findings, recommendations
    │   ├── inputs/                # copies or references to raw uploaded files for this session
    │   └── assets/                # any generated charts/annotated images for this session
    ├── 2026-09-10/
    │   └── ...
    └── progress-log.md            # running, append-only master log across all sessions
```

If a session folder for today's date doesn't exist yet, create it. If it already exists (multiple queries same day), **update it in place** rather than creating a duplicate.

## `profile.md` (create on first run, update as facts change)

Holds durable facts that shouldn't be re-asked every session:
- `## Goal` — the user's stated goal (e.g., powerlifting, lean anime-physique aesthetic, general fat loss), captured verbatim during First Load elicitation; keep prior goals listed as history if it changes
- Age, sex, height, activity level, training experience
- Current nutrition choices (what they actually eat day to day, as stated)
- Known allergies, dietary restrictions/preferences (e.g., vegetarian)
- Known chronic conditions, medications, injuries (only what the user has explicitly told you)
- Lifestyle & recovery baseline: typical sleep duration/quality, average daily steps, stress level, water intake (as stated)
- Hair/skin conditions the user has explicitly mentioned (only if relevant to the query — don't ask unprompted)
- Equipment access / gym type / training split preference

## `plan.md` (the current active plan — create once enough is verified, then revise in place)

This is the single source of truth for "what is the user's plan right now." Don't let the plan live only inside a dated session log — it should always be readable on its own without digging through history.

Create it only once the Coach's Verification Checklist (see `references/verification-checklist.md`) has enough answered to responsibly design a plan — not before. When the plan changes, **update this file** and also note the change (with reason) in that day's `session.md` and in `progress-log.md`. Keep the file's own change history so past versions of the plan aren't lost.

```
# Current Plan

_Last updated: <date> — see logs/<date>/session.md for the reasoning behind this version_

## Goal
<pulled from profile.md, for context>

## Workout Split
<e.g., 4-day upper/lower, or a full weekly table: day → focus → exercises → sets x reps → load/RPE guidance>

## Supplements
<name — dose — timing — reason it was added (tied to a specific verified gap, not generic)>

## Diet
<daily calorie target, macro split, meal structure/timing, specific foods or swaps tied to preferences/restrictions>

## Lifestyle Targets
<sleep, daily step, and hydration targets — tied to the verified baseline in profile.md, not invented; only include a target the user's goal/plan actually needs>

## Notes / Constraints
<injuries to work around, equipment limits, schedule constraints>

---
## Version History
- <date>: <what changed and why, one line> — reason ref: logs/<date>/session.md
- <date>: initial plan created
```

When revising, move the previous version's summary line into Version History rather than deleting the reasoning — the user should be able to see how their plan evolved over time, not just what it is today.

## `logs/progress-log.md` (append-only)

One dated entry per session, short form:
```
## 2026-08-24
- Inputs: blood report (PDF), posture video, 2 skin photos
- Weight/measurements (if provided): [value] — needed to detect stalls per references/recommendation-guidelines.md
- Key findings: [bullet list]
- Recommendations given: [bullet list]
- Open questions sent to user: [bullet list]
- Follow-ups needed next session: [bullet list]
```

## `logs/<date>/session.md` (detailed, per session)

```
# Session: <date>

## Inputs Received
- [file name/type] — [what it is]

## Data Extracted
- Blood markers: [table of marker: value: reference range: flag]
- Posture observations: [bullet list, purely descriptive, no diagnosis]
- Lift form observations: [bullet list — joint/position audit, cues given, drills suggested]
- Skin observations: [bullet list, purely descriptive]
- Hair observations: [bullet list, purely descriptive]
- Lifestyle & recovery (if discussed): [sleep, steps, stress, hydration — as stated]

## Clarifying Questions Asked This Session
- [question] → [user's answer, once given]

## Assumptions Made (explicitly labeled)
- [assumption] — please confirm

## Recommendations
### Workouts
- ...
### Supplements
- ...
### Diet
- ...

## Flags for Medical Follow-up
- [anything outside normal range or concerning — recommend seeing a doctor]

## Carried Forward to Next Session
- [unresolved questions, things to re-check, metrics to re-test]
```
