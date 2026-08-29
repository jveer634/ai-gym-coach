# Recommendation Guidelines

Read this when about to write or revise workout, supplement, or diet recommendations (i.e., before creating or updating `plan.md`).

- **Workouts**: base changes on stated training experience, equipment access, current split, and any physical limitations mentioned. If any of these aren't known yet, ask before prescribing.
- **Supplements**: tie each suggestion to an actual gap or deficiency found in provided data or explicitly stated symptoms — never suggest a supplement "just in case." Note any that should be checked with a doctor first (e.g., interactions with medications the user has mentioned).
- **Diet**: respect stated dietary restrictions/preferences from `profile.md` (e.g., vegetarian). If a restriction is unconfirmed, ask rather than assuming.
- Keep dosages, calorie targets, and macro numbers concrete and specific once you have enough information — vague advice is a sign you skipped the "ask" step, not a safer alternative.

---

## Workout Progression & Fatigue Management

A one-off workout list isn't a program — a program says how it changes over time. Include this whenever `plan.md`'s Workout Split is created or revised.

- **Express intensity, don't leave it implicit.** Give lifts a target using RPE (Rate of Perceived Exertion) or RIR (Reps In Reserve) alongside sets/reps, e.g., "Squat: 3x5 @ RPE 8" — not just "3x5." If the user has never used RPE/RIR, briefly explain it once rather than assuming familiarity.
- **Progression model — default to double progression**: the user stays at a given weight across a rep range (e.g., 8-12) until they hit the top of the range for all sets, then increases weight by the smallest available increment and drops back to the bottom of the rep range. Use a different model only if the user's goal or experience calls for one (e.g., a linear-progression novice program for a beginner powerlifting goal) — state which model you're using and why.
- **Deload protocol**: suggest a deload (roughly -10% load, -50% sets) every 6-8 weeks of a running program, or sooner if the user reports performance dropping across consecutive sessions (weights stalling or regressing, unusual fatigue) rather than waiting for a fixed schedule to catch it. Don't assume a deload is needed without either a completed time block or the user actually reporting the drop — ask if it's unclear.
- Log the progression model and current deload timing in `plan.md`'s Workout Split section, and note in Version History whenever a deload is applied or a rep range/weight increment changes.

---

## Nutrition Feedback Loops (Calorie & Step Adjustment)

A diet plan stalls eventually — a coach adjusts based on actual tracked results, not on a fixed schedule or a guess. Only apply these rules when the underlying data is actually being tracked and reported (see the weight/measurement field in `progress-log.md`); if it isn't being tracked, ask the user to start logging it rather than assuming a stall or assuming compliance.

- **Fat-loss stall**: if the user's tracked weight hasn't trended down over roughly 14 days AND they've confirmed they're actually hitting their calorie/macro targets (don't assume compliance — ask if it's unconfirmed), offer a choice: reduce daily calories by about 10%, or increase the daily step target by about 2,000 steps. Present both options rather than picking one for them.
- **Muscle-gain stall**: if tracked weight/strength hasn't trended up over roughly 21 days despite confirmed adherence, increase daily calories by about 100-150 kcal.
- **Compliance stall** (the user isn't sticking to the plan, rather than the plan not working): don't just repeat the same numbers. Ask what's making it hard, and consider suggesting higher-volume/more-satiating food choices, checking whether fiber/protein targets are actually being met, or a temporary diet break at maintenance calories before resuming.
- Any adjustment made this way goes in `plan.md`'s Diet section and gets a Version History line explaining the trigger (e.g., "reduced calories 10% — weight flat 16 days, adherence confirmed").

