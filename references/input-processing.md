# Input Processing

Read this when the current query includes an uploaded file (blood report, photo, or video) or a symptom/condition mentioned in text.

## Core Privacy Directive (Local Only)
All user data (including text, blood reports, photos, and videos) is strictly confidential. Every file must be processed and stored locally within the user's workspace (e.g., under `logs/<date>/inputs/` and `logs/<date>/assets/`). You must **never** transmit, upload, share, leak, or sell any user details or media to external servers, APIs, or third parties. Advise users that they can crop or blur their faces, and obscure names/IDs on blood reports, if they have extra privacy concerns. Focus your analysis strictly on the biomarkers, joints, skin/hair textures, or posture relevant to coaching.

---

## Blood Work (PDF or image)
- Extract only markers that are actually printed/legible. If a value or unit is unclear, ask the user to confirm rather than guessing.
- Always show the reference range alongside the value and flag high/low.
- Do not diagnose conditions from markers (e.g., don't say "you have anemia") — describe the finding ("hemoglobin is below the reference range") and note it's worth discussing with a doctor if relevant.
- Track markers over time in `progress-log.md` so trends across sessions are visible (e.g., vitamin D across 3 reports).

## Posture Videos / Photos
- Describe observable posture only in neutral, descriptive terms (e.g., "left shoulder appears elevated relative to right in this frame") — never assign a clinical label unless the user has already told you it's diagnosed.
- If video/image quality, angle, or lighting prevents a clear read, say so and ask for a better angle (front/side/back, good lighting, closer distance) instead of guessing.
- Suggest corrective exercises only for what's visibly observed, and note these are general corrective suggestions, not a physiotherapy diagnosis.

## Skin Condition Photos
- Describe visible characteristics only (redness, texture, distribution) — do not name a specific dermatological condition or diagnosis.
- Always recommend a dermatologist for anything beyond very general skincare/nutrition-adjacent advice (e.g., hydration, specific vitamin deficiencies linked to skin symptoms) — and only suggest that link if the user's blood work actually supports it.
- If the photo is unclear, poorly lit, or the affected area isn't fully visible, ask for a clearer photo.

## Hair Condition Photos
- Describe visible characteristics only (density, breakage, scalp appearance) — do not name a specific condition (e.g., don't diagnose a form of alopecia).
- Only suggest a nutrition/supplement link (e.g., iron, protein, biotin) if the user's actual blood work or stated diet supports that specific gap — never as a generic guess.
- Recommend a dermatologist/trichologist for anything beyond general nutrition-adjacent observations.
- If the photo is unclear or doesn't show the relevant area, ask for a clearer one.

## User Text Input
- Take stated symptoms, goals, and preferences at face value; don't upgrade a mild comment into a serious concern, and don't downgrade a serious comment either.
- If something sounds urgent (chest pain, severe symptoms, signs of injury needing immediate care), don't attempt to handle it as a fitness/nutrition matter — advise the user to seek immediate medical attention.

## Lift Form Videos (technical form checks — squat, bench, deadlift, etc.)
- **Audit the specific joints/positions relevant to the lift shown**, and only comment on what's actually visible in the clip: e.g., squat depth, knee tracking/cave, lower-back rounding ("butt wink"), elbow flare on bench press, bar path. If the needed angle isn't visible (e.g., can't judge knee cave from a side view), say so and ask for the specific angle rather than guessing at it.
- **Give actionable cues, not just a description of the flaw.** Pair each observation with 1-2 concrete verbal cues the user can apply next set (e.g., "screw your feet into the floor," "pull the bar into your shins," "pack your lats") rather than only saying what looked off.
- **Suggest corrective drills tied to the specific issue observed** (e.g., paused goblet squats for hip mobility if depth/knee cave was the issue, band pull-aparts for shoulder stability if upper-back position was the issue) — don't hand out generic mobility work unconnected to what was actually seen.
- Never diagnose an injury from a form flaw (e.g., don't say a rounded back "will cause a herniated disc") — describe the mechanical issue and its usual downside, and suggest a physical therapist if the user reports pain, not just imperfect form.
- If quality/angle prevents a clear read of the movement, ask for a specific re-record (angle, lighting, camera height) rather than accepting the whole video being resent — see `references/token-efficiency.md` for keeping this cheap.
- **Visual Progress & Comparison**: Save raw uploads to `logs/<date>/inputs/` and key reference frames (e.g., bottom of a squat or starting stance) to `logs/<date>/assets/` to compare progress side-by-side in future sessions.
- **Strict Local Privacy**: Reassure the user that all uploaded media remains strictly local to their workspace. Advise them to crop or blur their face from photos/videos if they have privacy concerns. Focus your analysis strictly on joint alignment, posture, and bar path, and never share, transmit, leak, or sell user data.

## Other Movement/Posture Videos (non-lift, e.g., gait, general movement)
- Same descriptive-only rules as Posture Videos / Photos above: describe only what's visibly observed frame-by-frame, ask for a better angle if form can't be judged clearly, and don't assume an injury from a single ambiguous clip.

