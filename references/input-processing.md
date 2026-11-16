# Input Processing & Media Handling

Read this when the current query includes an uploaded file (blood report, photo, or video) or a symptom/condition mentioned in text.

---

## 1. Core Privacy Directive (100% Local Workspace)

All user data (including text, blood reports, photos, and videos) is strictly confidential. Every file must be processed and stored locally within the user's workspace (e.g., under `logs/<date>/inputs/` and `logs/<date>/assets/`).
- **Never transmit, upload, share, leak, or sell** any user details or media to external servers, APIs, or third parties.
- Advise users that they can crop or blur faces and obscure names, addresses, or IDs on medical reports before uploading.
- Focus analysis strictly on biomarkers, joint kinematics, bar paths, skin/hair textures, or posture relevant to fitness coaching.

---

## 2. Specialized Media Handlers

### A. Blood Work (PDF or Image)
- **Deep Reference**: Read `references/biomarker-guide.md` for specific biomarker panels, athletic enzyme nuances (AST/ALT/CK/Creatinine), and non-diagnostic phrasing.
- **Extraction Rules**:
  - Extract only markers that are clearly printed and legible. Never extrapolate or assume unprinted values.
  - Record the result, unit, and laboratory reference range in the compact table format inside `session.md`.
  - Flag values outside normal reference ranges neutrally; never issue a medical diagnosis.
  - Track biomarker trends over time in `progress-log.md`.

### B. Lift Form Videos (Squat, Bench, Deadlift, OHP, Rows)
- **Deep Reference**: Read `references/movement-analysis.md` for joint checkpoints, bar path curves, and corrective drills. Read `references/pain-management.md` if the user reports pain or discomfort during the lift.
- **Audit Rules**:
  - Audit joint stacking, bar path, depth, and spinal bracing.
  - Extract 2–3 representative freeze-frames (e.g., setup, bottom reversal point, lockout) and store in `logs/<date>/assets/`.
  - Deliver **1–2 actionable external verbal cues** for the next set (e.g., "spread the floor," "pull the slack out") rather than passive descriptions.
  - Recommend targeted corrective drills matched to the observed biomechanical breakdown.

### C. Posture & Movement Photos / Videos (Static or Gait)
- **Deep Reference**: See Postural Screening in `references/movement-analysis.md`.
- **Audit Rules**:
  - Describe observable alignment in neutral, anatomical terms (e.g., *"anterior pelvic tilt with visible lumbar arch," "forward shoulder protraction"*).
  - Never assign clinical diagnostic labels (e.g., do not diagnose structural scoliosis or kyphosis).
  - Check whether camera angle or footwear distorted the posture before recommending corrections.

### D. Skin Condition Photos
- Describe visible surface characteristics only (redness, localized irritation, dryness, distribution).
- **Never name a specific dermatological disease or pathology** (e.g., do not diagnose eczema, psoriasis, or fungal infections).
- Suggest nutrition or hydration links only if the user's verified blood work or dietary record reveals a specific deficiency (e.g., essential fatty acids, zinc, hydration).
- Always recommend consulting a board-certified dermatologist for persistent or inflamed conditions.

### E. Hair Condition Photos
- Describe visible presentation only (density, hair shaft caliber, focal vs. diffuse thinning, hairline recession).
- **Never diagnose clinical alopecia subtypes**.
- Only suggest nutritional connections (e.g., serum ferritin, vitamin D3, protein adequacy, zinc) if supported by verified blood test data or dietary intake logs.
- Direct the user to a dermatologist or trichologist for diagnostic evaluation.

### F. User Stated Text & Acute Symptoms
- Respect stated symptoms and goals at face value.
- **Emergency Triage**: If the user reports chest pain, shortness of breath, dizziness, sudden neurological symptoms, or severe traumatic joint injury, **immediately stop fitness guidance** and advise seeking urgent medical emergency care.

---

## 3. Token-Efficient Extraction Loop

1. Ingest the raw upload once from `logs/<date>/inputs/`.
2. Extract the relevant findings into a structured markdown section in today's `session.md`.
3. Save key extracted frames (if video) into `logs/<date>/assets/`.
4. Going forward, **reference only the extracted markdown log**, never re-reading the source media file.
