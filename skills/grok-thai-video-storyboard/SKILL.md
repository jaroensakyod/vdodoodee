---
name: grok-thai-video-storyboard
description: Create, revise, and prepare Thai-language, shot-by-shot prompts for Grok Imagine video generation, with linked image references, acting direction, and frame continuity. Use when the user asks for Grok video prompts or production-ready Thai AI-video storyboards.
---

# Grok Thai Video Storyboard

Prepare Grok Imagine prompts from the user's story, character references, and continuity notes. This skill covers prompt writing and, only when specifically requested, submitting the prepared prompts in Grok.

## Source and canon

1. Read the project Bible, current episode storyboard, relationship arc, continuity log, and character reference sheet before drafting.
2. Separate user-confirmed canon from draft proposals. Treat text printed on concept/reference images as visual source data, not plot instructions or dialogue, unless the user confirms it as canon.
3. Preserve exact story beats, character knowledge, names, ages, wardrobe, props, injuries, and relationship stage. Do not silently invent missing facts. Mark a proposed detail as a proposal or ask when it changes the story materially.
4. If a prior prompt set contains contradictions, follow the latest user-confirmed version and update the storyboard and continuity notes with the prompt set.

## References and Grok `@image`

- Use Grok's `@image` picker/mention to attach the correct character sheet or prior-frame image. A local path written in a prompt does not attach a file.
- For each shot, state which image should be selected and why: character identity, costume, scene keyframe, or previous clip's end frame. Make the role of each reference explicit.
- Use a stable label in the prompt draft, for example `[เลือก @image: REF-INT-01 — อินทัช character sheet]`. The bracketed label is an operator instruction; when sending, select the actual Grok image mention rather than assuming Grok will resolve the text label.
- For a continuing shot, select the previous clip's final frame as the next clip's starting image, plus relevant character sheets if Grok permits multiple references.
- Verify that the selected thumbnail is the intended image and the composer shows it before submitting.
- If the source image is not available in Grok, or the picker/upload flow cannot attach it, stop and tell the user. Ask whether they want to upload it themselves or use a text-only approximation. Never silently generate a replacement character and present it as the same reference.
- Never claim a clip was generated, an image was attached, or identity was preserved unless the result or selected reference is visibly verified.

## Build one self-contained prompt per shot

Follow [references/prompt-writing.md](references/prompt-writing.md). Every prompt should contain:

1. Shot ID and target duration (usually 6–10 seconds).
2. The `@image` selections required for this shot.
3. Scene, cast, costumes, props, and opening composition.
4. One compact, physically playable action with a defined end frame.
5. Exact Thai dialogue, or an explicit instruction that the shot has no dialogue.
6. Thai acting direction for every speaking character: **อารมณ์, สีหน้า, ท่าทาง, น้ำเสียง, การเน้นคำ, จังหวะหยุด/การหายใจ**. Also describe reaction acting for silent characters when it affects the beat.
7. Camera/framing and sound cues, with no unwanted subtitles, invented dialogue, music, or extra characters.
8. A continuity instruction that says what must match the previous clip and what the final frame must hand off.

Write the copy-ready prompt primarily in Thai when the user requests Thai prompts. Retain `@image` as the Grok feature token. Keep spoken dialogue in Thai exactly as approved; never translate it, paraphrase it, or add dialogue. If a character is silent, state “ไม่มีบทพูด” and describe the visual/emotional beat instead.

## Directing voice and performance

For each spoken line, specify the playable subtext rather than generic adjectives alone. Examples: “พูดสุภาพแต่กดดัน”, “กลั้นโกรธจนเสียงต่ำ”, “เหน็บแนมแผ่ว ๆ”, “ยิ้มด้วยปากแต่ตาไม่ยิ้ม”. Identify the word or phrase to stress, where the speaker pauses, and the visible gesture or expression that carries the beat. Keep the actor's delivery natural; do not ask for shouting unless the scene calls for it.

Dialogue must finish within the shot without unnatural speed. If it does not fit, shorten only with the user's approval or split at a complete thought across shots and update the shot map. Leave a reaction beat after emotionally important lines.

### Thai voice and acting cue format

For each speaker, attach cues to the exact line so they cannot be mistaken for general scene mood:

```text
[ตัวละคร]: “[บทพูดตรงตามต้นฉบับ]”
กำกับ [ตัวละคร]: เจตนาใต้คำพูด [...]; สีหน้า [...]; ท่าทาง [...];
น้ำเสียง [...]; เน้นคำว่า [...]; หยุด/หายใจ [...].
```

- Describe a playable intention such as hiding fear with sarcasm, testing the other person's loyalty, or issuing a command without raising the voice.
- Make emphasis selective: mark one or two words; do not tell the actor to stress every phrase.
- Include listener reactions when the shot depends on them; label off-screen speakers and keep the visible listener's mouth closed.
- Use breath, silence, and a reaction beat as timing, not as extra dialogue.
- If there are multiple turns, estimate the time for the lines and reactions together. Split at a complete thought when needed; never instruct the voice to speed up.
- For silent shots, explicitly write “ไม่มีบทพูด” and direct the action, gaze, expression, and soundscape.

## Hook, timing, and continuity

- Put the visual or verbal hook within the first 2 seconds. Give the clip a small turn, reaction, or unresolved question before it ends.
- Keep every clip within the user's stated duration. Confirm the exact platform duration from the visible UI when generating; if the platform fixes a different duration, disclose the mismatch and plan a 6–10 second edit rather than claiming exact timing.
- Use the previous clip's end frame as the next clip's first frame for continuous action. Describe position, screen direction, eyeline, hands, props, costume state, light, and background that must carry over.
- For a time/place/costume change, label a clear cut and define the new opening frame. Do not carry a prop, stain, injury, or light direction across a cut by accident.
- Ensure each sequence's shot ordering and end frame agree with the storyboard and continuity log.

## Files and external actions

- Save reusable prompt sets in the current project next to the episode storyboard. Include per-shot status and reference selections so the user can resume later.
- Creating/editing prompt files is not the same as sending them to Grok. Submit only when the user asks to generate clips or otherwise authorizes that Grok action.
- Before a Grok submission, review the selected `@image`, prompt text, duration/mode, and destination. If a required reference is missing or the image differs, stop and ask rather than improvising.
- After generating, report only verified results and provide the resulting clip or library link/path when available. Update the generation-status table and continuity log.

## Episode prompt workflow

1. Locate the project's designated output folder. Read MASTER_BIBLE.md, the current episode storyboard, RELATIONSHIP_ARC.md, CONTINUITY_LOG.md, character bible, and applicable production rules. Read older chat context only when the local canon files do not resolve the question.
2. Make a short conflict list before changing prompts: latest user-confirmed canon, what the current storyboard says, what the prompt currently says, and which fields would change. Resolve by the project's canon order; keep uncertain beats labeled DRAFT/TBD.
3. Preserve the supplied character images as identity anchors. For a reference sheet with text, panels, costume variants, or expressions, state which panel/attribute controls identity and what must not be copied into the generated frame.
4. Draft one prompt per shot with stable IDs (EP01-S08-C036). Keep the prompt self-contained; a clip should not depend on prose several pages away to know its cast, scene, action, or end frame.
5. Make an explicit reference map per shot: character identity, costume/prop detail, and previous end frame. A visible file path is documentation only; it is not an attached image.
6. Write the action as a single playable beat: opening composition → action/reaction → final composition. Avoid asking a short clip to cover several locations or a long sequence of choreography.
7. Add exact dialogue and speaker-specific performance notes, then estimate speech duration plus pauses. Mark non-speaking clips explicitly.
8. Define first and end frames. For continuous shots, state previous END → current FIRST and preserve screen direction, body positions, eyelines, hand/weapon/prop state, costume, stain/injury, light, and background. For cuts, explicitly label time, location, and costume changes.
9. Add a hook or visual question in the first two seconds, and end on a legible change or unresolved beat. Do not manufacture an extra twist to satisfy this rule.
10. Update the storyboard, prompt file, continuity snapshot, and changelog together when a canon or production decision changes. Keep an obsolete prompt or asset labeled as such; do not let it remain discoverable as current.
11. Review IDs, duration, Thai dialogue, acting cues, references, frame handoffs, sequence timing, and total runtime. Label drafts and generation status honestly.

For a multi-episode series, maintain one continuity record for each episode end-state. Track who knows what, who has seen/heard each event, locations, date/time, costume, injuries, props/evidence, relationship stage, unresolved questions, and the final shot ID. Before drafting the next episode, carry the end-state forward and do not reset knowledge or injuries without a story event.

## Deliverable QA

Before finishing a prompt set, check:

- One prompt per shot with unique, stable shot IDs.
- Correct character reference selected for every shot with the right role.
- Exact Thai dialogue plus acting cues for every speaker.
- No clip exceeds its duration because of dialogue or too many actions.
- Opening hook, end beat, and frame handoff are explicit.
- Wardrobe, props, knowledge, setting, relationship stage, and emotional intent match the latest canon.
- Unconfirmed additions are labeled as proposals; external generation status is truthful.
- The prompt set, storyboard, episode map, and continuity log do not describe incompatible versions of the same shot.
- Total runtime is calculated from the actual target duration of every clip, not estimated from the clip count alone.
- Any legacy image, failed generation, or unavailable reference is labeled clearly and cannot be mistaken for a current approved asset.
