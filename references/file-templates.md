# Workspace & File Structure Templates

Read this when creating or updating `profile.md`, `plan.md`, or files under `logs/`.

---

## 1. Directory Layout

All user coaching records live locally in the workspace:

```
/ (workspace root)
├── profile.md                     # Static/slow-changing user context & baseline
├── plan.md                        # Active, single-source-of-truth workout & diet plan
└── logs/
    ├── progress-log.md            # Append-only chronological master history & deltas
    └── YYYY-MM-DD/                # One folder per analysis session (dated)
        ├── session.md             # Detailed log of this session's inputs & recommendations
        ├── inputs/                # Locally stored raw files (reports, videos, photos)
        └── assets/                # Representative freeze-frames, posture crops, charts
```

- If a session folder for today's date exists, update it in place.
- If it does not exist, create `logs/YYYY-MM-DD/` and initialize `session.md`.

---

## 2. `profile.md` Template

Created on first run; updated whenever durable facts change.

```markdown
# User Profile

_Last updated: YYYY-MM-DD_

## Goal
- **Primary Goal**: [e.g., Lean Hypertrophy, Powerlifting 83kg class, Recomposition]
- **Goal History**: [Record prior goals with dates if the user shifts focus]
- **Timeline / Target**: [e.g., 16-week mesocycle, photoshoot date, powerlifting meet]

## Biometrics & Demographics
- **Age**: [Value]
- **Biological Sex**: [Value]
- **Height**: [Value]
- **Current Weight Baseline**: [Value]
- **Body Fat % (if tested/known)**: [Value & method: DXA, calipers, visual]

## Training Context
- **Experience Level**: [Beginner / Intermediate / Advanced lifter]
- **Schedule**: [e.g., 4 days/week, 60-75 min/session]
- **Equipment Access**: [Commercial gym / Home rack / Dumbbells only]
- **Preferred Split**: [e.g., Upper/Lower, PPL, Full Body]

## Health & Orthopedic Profile
- **Known Medical Conditions**: [None reported / Condition]
- **Current Medications**: [None reported / Listed drugs]
- **Injury / Pain History**: [Documented joint/tendon sensitivities or prior surgeries]

## Nutrition & Meal Prep Baseline
- **Planning Paradigm**: [Daily Flexible Tracking vs. Entire Week Meal Prep]
- **Menu Strategy**: [Fixed / Consistent vs. Rotational Recipes]
- **Grocery Shopping Day**: [e.g., Sunday morning market]
- **Dietary Restrictions / Preferences**: [Omnivore / Vegetarian / Vegan / Allergies]
- **Preferred Protein Staples**: [e.g., Paneer, Soya chunks, Tofu, Whey, Chicken breast, Eggs]

## Lifestyle & Autoregulation Baseline
- **Sleep**: [Average duration, e.g., 7.5 hrs/night; subjective sleep quality]
- **Daily Steps (NEAT)**: [Average baseline steps, e.g., 8,500 steps/day]
- **Stress & Hydration**: [Stress level 1-10; typical water intake in liters/day]
- **Optional Context**: [Hair or skin observations only if user has explicitly shared]
```

---

## 3. `plan.md` Template

The active single source of truth for current targets.

```markdown
# Current Active Plan

_Last updated: YYYY-MM-DD — Detailed rationale logged in logs/YYYY-MM-DD/session.md_

## Primary Focus & Phase
- **Goal**: [From profile.md]
- **Current Mesocycle Phase**: [e.g., Hypertrophy Block 1 / Deload / Moderate Cut]

## Weekly Workout Split & Volume Table

| Muscle Group | Weekly Direct Sets | Volume Landmark Target |
| :--- | :---: | :---: |
| Chest | 12 | MAV |
| Back (Lats & Upper) | 14 | MAV |
| Quadriceps | 10 | MEV-MAV |
| Hamstrings / Glutes | 10 | MEV-MAV |
| Shoulders (Side/Rear) | 12 | MAV |
| Arms (Biceps/Triceps) | 8 | MEV |

### Day 1: Upper A (Strength Focus)
- **Progression Model**: Linear for primary compounds, Dynamic Double Progression (DDP) for accessories.
- **Warm-up**: 5 min general cardio + 2 ramping warm-up sets per primary lift.

| Exercise | Sets | Reps | Intensity (RPE / RIR) | Rest | Progression / Notes |
| :--- | :---: | :---: | :---: | :---: | :--- |
| Barbell Bench Press | 3 | 5 | RPE 8 (2 RIR) | 3 min | Add 2.5 kg when 3x5 achieved |
| Chest-Supported T-Bar Row | 3 | 8-10 | RPE 8 (2 RIR) | 2 min | DDP: 8-10 rep window |
| Incline Dumbbell Press | 3 | 10-12 | RPE 9 (1 RIR) | 90s | DDP |
| Cable Lateral Raise | 4 | 12-15 | RPE 10 (0 RIR) | 60s | DDP; strict form |
| Overhead Rope Triceps Ext | 3 | 12-15 | RPE 9-10 | 60s | Lengthened triceps emphasis |

*(Repeat table format for each training day in the weekly split)*

## Nutritional Targets & Macros

- **Daily Energy Target**: [e.g., 2,450 kcal/day (250 kcal surplus)]
- **Protein**: [e.g., 180 g (2.0 g/kg) — raw weight calculations]
- **Fats**: [e.g., 65 g (0.75 g/kg)]
- **Carbohydrates**: [e.g., 285 g]
- **Hydration Target**: [e.g., 3.5 Liters water daily]

## Meal Plan & Recipe Schedule ([Rotational / Fixed])

### Meal Plan A (e.g., Mon / Wed / Fri / Sun)
- **Breakfast**: High-Protein Oats with Whey & Chia Seeds
- **Lunch**: High-Protein Paneer Bhurji with 2 Rotis & Salad  
  *Recipe Video*: [Watch Paneer Bhurji Prep](https://www.youtube.com/results?search_query=healthy+high+protein+paneer+bhurji+recipe)
- **Snack**: Greek Yogurt with Roasted Almonds
- **Dinner**: Soya Chunks Stir-Fry with Steamed Basmati Rice  
  *Recipe Video*: [Watch Soya Chunks Stir-Fry Prep](https://www.youtube.com/results?search_query=crispy+soya+chunks+stir+fry+high+protein)

*(Include Meal Plan B if user selected Rotational)*

## Weekly Sunday Grocery Shopping List
*(7-Day Batch Quantities based on Meal Prep)*

### Fresh Produce & Vegetables
- [ ] Tomatoes: 1.5 kg
- [ ] Onions: 1.5 kg
- [ ] Spinach / Palak: 500g
- [ ] Bell Peppers (Capsicum): 1 kg
- [ ] Broccoli: 2 heads (~800g)

### High-Protein Staples (Raw Weights)
- [ ] Paneer: 700g (100g/day)
- [ ] Soya Chunks: 350g (50g raw/day)
- [ ] Whey Protein Powder: 1 tub (or 7 scoops)
- [ ] Greek Yogurt / Curd: 1.5 kg

### Complex Carbs & Grains
- [ ] Rolled Oats: 500g
- [ ] Basmati Rice: 1 kg
- [ ] Whole Wheat Atta: 1 kg

### Cooking Essentials & Healthy Fats
- [ ] Ghee / Cold-Pressed Oil: 200 ml
- [ ] Almonds / Walnuts: 200g
- [ ] Chia Seeds: 100g

## Supplement Protocol

| Supplement | Dosage | Timing | Evidence Rationale |
| :--- | :--- | :--- | :--- |
| Creatine Monohydrate | 5 g | Daily post-workout | Tier A: Strength & cell hydration |
| Whey Protein Isolate | 30 g | Post-workout | Tier A: High-leucine protein source |
| Vitamin D3 + K2 | 4,000 IU | Morning with meal | Tier A: Target blood deficiency |
| Magnesium Glycinate | 300 mg | Before bed | Tier B: Neuromuscular relaxation |

---

## Plan Version History
- **YYYY-MM-DD**: [Summary of change, e.g., Generated Sunday grocery list and rotational vegetarian meal prep; reason ref: logs/YYYY-MM-DD/session.md]
- **YYYY-MM-DD**: Initial plan initialized.
```

---

## 4. `logs/<date>/session.md` Template

Created or updated on every interaction turn.

```markdown
# Session Log: YYYY-MM-DD

## 1. Inputs Received
- [File/Text] — [Type, e.g., Blood panel PDF, Squat form video, Meal prep preferences]

## 2. Compact Extracted Data

### Biomarkers (if provided)
| Biomarker | Result | Reference Range | Status | Athletic Context |
| :--- | :--- | :--- | :--- | :--- |
| ... | ... | ... | ... | ... |

### Movement & Biomechanical Screening (if provided)
- **Movement Analyzed**: [e.g., Barbell Back Squat]
- **Key Joint Observations**: [Hip depth, knee tracking, bar trajectory, torso angle]
- **Key Frames Archived**: `logs/YYYY-MM-DD/assets/squat_bottom_frame.png`
- **Primary Actionable Cue**: [1-2 concise external cues]
- **Targeted Corrective Drill**: [Specific drill from movement-analysis.md]

### Nutrition & Meal Prep Decisions
- **Planning Paradigm**: [Daily Flexible vs. Entire Week Batch Prep]
- **Menu Choice**: [Fixed vs. Rotational]
- **Sunday Grocery List Generated**: [Yes/No]

## 3. Coach's Verification Audit
- Verified items reviewed against `verification-checklist.md`.
- Missing/stale items queried below.

## 4. Recommendations & Interventions
### Workout Adjustments
- [Changes to volume, exercises, or deload implementation]
### Diet & Macro Adjustments
- [Caloric, macro, recipe, and grocery list adjustments]
### Supplement Updates
- [Evidence-tiered adjustments]

## 5. Medical & Orthopedic Flags
- [Neutral notifications of abnormal lab values or referral suggestions for persistent joint pain]

## 6. Open Questions for the User
- [Clear numbered list of questions the user needs to answer for next session]
```

---

## 5. `logs/progress-log.md` Template

Append-only summary log tracking long-term trends and deltas.

```markdown
# Master Progress Log

## YYYY-MM-DD
- **Inputs**: [Blood report PDF, Squat video, Meal prep setup]
- **Body Weight**: 81.2 kg (Δ: -0.4 kg from last week)
- **Key Biomarkers**: Vitamin D: 21.4 ng/mL (Low), Ferritin: 28 ng/mL (Borderline)
- **Meal Prep**: Set up Sunday weekly grocery list with 7-day vegetarian rotational recipes (Paneer/Soya).
- **Plan Modifications**: `plan.md` updated to v1.1.
- **Open Questions**: Confirming daily step average and current sleep schedule.
- **Next Follow-up**: Review weekly adherence and updated weigh-in log.
```
