# Grok prompt-writing guide for Thai story clips

Use this reference when drafting or revising a prompt set. Keep the actual prompt compact enough for Grok to follow, but detailed enough to direct the actor and preserve continuity.

## Shot prompt format

Use a separate copy-ready block for each shot:

```text
EP01-S01-C001 | เป้าหมาย 8 วินาที | โหมดวิดีโอ 9:16
ภาพอ้างอิง: [เลือก @image: REF-INT-01 — ใช้ล็อกใบหน้า/ผม/ชุดของอินทัช]
ภาพเริ่ม: [เลือก @image: keyframe หรือเฟรมจบของคลิปก่อน — ใช้ล็อกองค์ประกอบ]

ภาพและการกระทำ: [สถานที่ เวลา ใครอยู่ในเฟรม เสื้อผ้า/พร็อพ ภาพเริ่ม การกระทำหนึ่งชุด และภาพจบ]
บทพูด: [ชื่อผู้พูด]: “บทภาษาไทยที่ยืนยันแล้ว”
กำกับการแสดง: อารมณ์/เจตนา [...]; สีหน้า [...]; ท่าทาง [...]; น้ำเสียง [...]; เน้นคำ [...]; จังหวะ [...].
กล้องและเสียง: [...]; ไม่มีบทพูดเพิ่ม/ไม่มี subtitle/ไม่มีตัวอักษรลอย.
ต่อเนื่อง: เริ่มจาก [เฟรมก่อน]; คง [ตำแหน่ง มือ พร็อพ แสง ชุด]; จบด้วย [ภาพที่ส่งต่อคลิปหน้า].
```

The reference labels in brackets are for the operator to select the real Grok `@image` item. The label itself is not a working attachment. If a prompt needs two images, name each role separately (e.g. identity versus start-frame composition) so Grok does not merge costume or pose incorrectly.

## Acting cue checklist

For every speaking line, include cues from all six categories:

| Cue | What to specify | Example |
|---|---|---|
| อารมณ์/เจตนา | What the line is doing beneath its literal meaning | “ประชดเพื่อปิดบังความระแวง” |
| สีหน้า | A visible, restrained facial signal | “ยิ้มบาง แต่สายตายังจับผิด” |
| ท่าทาง | One concrete body/hand movement | “ก้มมองคราบโคลนก่อนเงยสบตา” |
| น้ำเสียง | Pitch, volume, texture, politeness | “เสียงต่ำ สุภาพแต่แข็ง” |
| เน้นคำ | One or two meaningful words, not the whole sentence | “เน้น ‘องค์ประกัน’ แล้วกดเสียงท้ายประโยค” |
| จังหวะ | Pause, breath, speed, or reaction timing | “หยุดครึ่งจังหวะก่อนคำว่า ‘แต่’” |

Do not use vague cues alone (“ดูเศร้า”, “เล่นให้มีอารมณ์”). Convert them into an observable action and an audible delivery. Do not over-direct every eyebrow movement when a shot is simple; include only cues that clarify subtext and continuity.

## Speech timing

- Estimate how many Thai words/syllables and speaker turns fit the target duration. A short 8-second clip commonly supports one sentence, or two brief exchanges with reaction time; long court dialogue may need separate clips.
- Keep each line complete within the shot. Do not ask Grok to cram a paragraph into a short clip, accelerate unnaturally, or cut off the last word.
- Preserve exact dialogue from canon. If the existing line is too long, offer a proposed trim in the project file and mark it for user approval; do not silently change meaning.
- State who speaks each line and who listens/reveals a reaction. Thai lip-sync can drift when several faces speak in one shot; use a clear close-up or shot/reverse-shot if needed.
- For off-screen dialogue, say that the speaker is off-screen and specify whose mouth must remain closed.
- If exact spoken Thai is unreliable in the platform, specify the performance and create a clean voiceover/subtitle plan for post, but do not claim Grok rendered exact dialogue until verified.

## `@image` and identity locking

For each shot, prepare an explicit reference checklist:

- **Character reference:** whose face, hair, body, signature jewelry, and base costume should stay fixed.
- **Shot-start reference:** what exact frame composition, pose, hand state, eyeline, and lighting the video begins from.
- **Prior end frame:** required for continuous action; do not substitute a random reference-sheet pose.
- **Supporting reference:** location, prop, or costume detail only when needed.

Recommended labels:

```text
[เลือก @image: REF-RAN-01 — identity/costume anchor ของรณภพ]
[เลือก @image: REF-INT-01 — identity/costume anchor ของอินทัช]
[เลือก @image: EP01-S04-C019-END — first-frame/continuity anchor]
```

Avoid ambiguous instructions such as “use the image” when multiple images are attached. State which person or property each image controls. If a reference sheet includes concept text or a quote, tell Grok not to reproduce that text; do not turn it into story dialogue unless canon confirms it.

If the Grok `@image` picker cannot select the local source asset, do not replace the face with a text-described lookalike without asking. Report the missing reference and ask whether the user wants to upload it manually or approve a text-only approximation.

## Continuity handoff

Write concrete start and end states rather than “continue seamlessly” alone:

```text
เริ่ม: อินทัชอยู่ขวาของเฟรม มือขวากำกระดาษที่ไหม้ครึ่งหนึ่ง สายตามองออกหน้าต่าง
คงเดิม: ชุดขาวทองยังมีคราบโคลนที่ชายผ้าซ้าย; ไฟตะเกียงอยู่ด้านซ้าย; ไม่มีตัวละครเพิ่ม
จบ: อินทัชหันหน้าไปทางหน้าต่างและสายตาหลุดจากกระดาษ — ใช้เฟรมนี้เปิด C002
```

For an attack/action beat, track every prop and body position in order (arrow flight/impact, fall direction, weapon hand, attacker position, injury state, dropped evidence). End the shot with a stable composition that can become the next first frame.

## Hook and clip ending

- Within the first two seconds, show a concrete visual anomaly, threat, pointed line, or reaction that raises a question.
- Before the cut, land a specific change: new information, a look that contradicts the line, an interrupted action, a visible consequence, or an unresolved question.
- Avoid adding an unapproved twist solely to make the ending feel dramatic.

## Example: dialogue-rich prompt

```text
EP01-S02-C007 | เป้าหมาย 8 วินาที | วิดีโอแนวตั้ง 9:16
ภาพอ้างอิง: [เลือก @image: REF-RAN-01 — หน้าตาและชุดรณภพ] [เลือก @image: REF-INT-01 — หน้าตาและชุดอินทัช]
ภาพเริ่ม: ต่อจาก C006 END; ทั้งคู่ยืนเผชิญหน้าที่ประตูวัง ทหารอยู่หลังรณภพ คราบโคลนอยู่ชายชุดอินทัช
ภาพและการกระทำ: รณภพก้มตาเห็นคราบโคลนก่อนมองหน้าอินทัช อินทัชยืนนิ่ง ไม่หลบตา
บทพูด: รณภพ: “ข้านึกว่าองค์ชายจันทรคีรีจะมาถึงก่อนตะวันตกดิน” อินทัช: “ข้าก็นึกว่าอโยธาราจะส่งขุนนางมาต้อนรับ”
กำกับการแสดง: รณภพพูดด้วยน้ำเสียงเรียบเย็นและประชดบาง ๆ เน้น “ก่อนตะวันตกดิน”; สายตาเหลือบคราบโคลนก่อนค่อยสบตา. อินทัชตอบสุภาพแต่เหน็บแนม เน้น “ขุนนาง”; ยกคางเล็กน้อยและยิ้มเพียงมุมปาก. เว้นช่วงหายใจหนึ่งจังหวะระหว่างผู้พูด; ไม่มีใครหัวเราะ
กล้องและเสียง: medium two-shot ที่เห็นสายตาทั้งคู่ เสียงฝนหยดจากชายคาเบา ๆ; lip-sync ไทย; ไม่มีผู้พูด/บทเพิ่ม ไม่มี subtitle
จบ/ต่อเนื่อง: จบที่ช่วงเงียบหลังคำตอบโดยทั้งคู่ยังสบตา; คงตำแหน่งซ้าย-ขวาเพื่อเปิด C008
```

## Example: silent action prompt

```text
EP01-S01-C005 | เป้าหมาย 8 วินาที | วิดีโอแนวตั้ง 9:16
ภาพอ้างอิง: [เลือก @image: REF-INT-01 — identity/costume ของอินทัช]
ภาพเริ่ม: ต่อจาก C004; คราบโคลนที่ชายผ้าขาวทองยังอยู่ เด็กยืนถอยหลัง
ภาพและการกระทำ: อินทัชก้มมองคราบโคลน เงยไปมองเด็ก แล้วยิ้มมุมปากก่อนเดินผ่านไป
บทพูด: อินทัช: “ปาแม่นดีนี่ คราวหน้าเล็งสูงกว่านี้อีกนิด”
กำกับการแสดง: อารมณ์ขบขันแบบแห้ง ๆ ไม่โกรธ; คิ้วยกนิดเดียว เน้น “สูงกว่านี้”; ชี้ชายผ้าตัวเองแล้วลดมือลง ไม่แตะเด็ก; น้ำเสียงเบาสบายเหมือนชมจริงแต่มีแววหยอก; เว้นจังหวะสั้นก่อน “อีกนิด”
กล้องและเสียง: medium tracking shot เสียงเมืองเปียกฝน; ไม่มีดนตรีตลก ไม่มี subtitle ไม่มีผู้พูดอื่น
จบ/ต่อเนื่อง: ชายผ้าที่เปื้อนโคลนเคลื่อนผ่าน foreground ไปทางประตูวัง ใช้ทิศทางนี้เปิด C006
```
