# Token-Efficient Handling

Read this whenever a query involves an uploaded video, PDF, or image, or whenever "read before acting" would otherwise mean pulling in a lot of log history. The goal: pay full processing cost for a piece of media **once**, then reuse the compact extracted result forever after — never the raw file.

## Core rule: extract once, store compact, never re-process

The first time any blood PDF, video, or photo is processed, convert it into a compact text artifact (a table, a short bullet list) in that day's `session.md`. That extracted text — not the original file — is the source of truth from then on.
- Never re-attach or re-analyze a previously processed file "just to double check" unless the user explicitly re-uploads a new one or asks you to re-examine it.
- When a later session needs a past result (e.g., "what was my vitamin D last time"), read the compact table from that session's log — do not re-open the original PDF/image/video.
- This also means: don't ask the user to re-send a file you've already processed. If you need more from the same document (a marker you didn't extract yet), ask them to confirm the specific value instead of re-uploading.

## Video specifically (the most expensive input type)

- Before processing, if the video is more than ~30-60 seconds or covers more than one movement/angle, ask the user to trim it to the specific rep or angle that matters, rather than processing the whole clip. One clean example rep beats ten.
- Extract observations from a handful of representative frames (e.g., top/bottom of a lift, or front/side/back for posture) rather than analyzing every frame — describe what's needed, not everything visible.
- Store only the resulting text description in `session.md`. Don't keep re-describing the same video across turns in the same session — refer back to what you already wrote.
- If the movement or angle is unclear from a few frames, ask for a specific short re-record rather than requesting the whole video be resent at higher quality/length.

## Images (skin, hair, posture photos)

- One clear photo per angle/area is enough — don't request multiple redundant shots "to be safe" unless the first is genuinely unusable (see `references/input-processing.md` for when to ask for a clearer photo).
- Describe once, store the description, and reuse it in the same way as video — later turns reference the stored text, not the image itself.

## Blood work PDFs

- Extract markers into a compact table (marker, value, range, flag) once, store that table in `session.md`, and treat it as the record from then on — don't re-parse or re-quote the source PDF in later turns.
- If the user pastes values as text instead of uploading a PDF, prefer that — it's already compact and skips file processing entirely. It's fine to say so if it would help: "You can also just paste the values directly if that's easier."

## Reading logs: default to the summary, drill down only when needed

- The default for "read before acting" is `progress-log.md` (the short, dated-entry summary) — not every full `session.md`. Only open a specific `logs/<date>/session.md` when:
  - the current query directly references something from that session (a past recommendation, a specific test result), or
  - `progress-log.md` flags an unresolved follow-up relevant to the current query.
- Don't open the last several `session.md` files "just in case" — `progress-log.md` exists specifically so you don't have to.

## Keeping `progress-log.md` itself from growing without bound

- Once `progress-log.md` holds more than ~10-15 dated entries, condense the older ones: replace the oldest entries with a single rolled-up summary block (e.g., "Sessions Jan-Mar 2026: goal was X, key findings were Y, plan evolved to Z") and keep only recent sessions in full per-entry detail.
- Do this consolidation as part of a normal session update, not as a separate cleanup task — fold it into step 6 of the workflow when you notice the file has grown large.
- Never summarize away a flag from Version History in `plan.md` or a still-open medical follow-up — carry those forward explicitly even when compressing older entries.
