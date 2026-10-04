# EP01 keyframe prompts

> **สถานะไฟล์ภาพ:** `keyframes/EP01-S01-C001-FIRST.png` เป็น keyframe ฉากเปิดรถม้าของ C001 ปัจจุบัน สร้างโดยอ้างอิงภาพ character sheet อินทัชต้นฉบับในโปรเจกต์ เมื่อนำเข้า Grok ให้แนบ keyframe นี้พร้อม REF-INT-01 หาก Grok รับหลายภาพ และตรวจ thumbnail ว่าเป็นภาพถูกต้อง

## EP01-S01-C001-FIRST — imagegen prompt

**Tool:** Codex imagegen (built-in); generated image saved as `keyframes/EP01-S01-C001-FIRST.png`.

```text
Use case: stylized-concept
Asset type: EP01-S01-C001 cinematic video keyframe for a Thai fantasy BL series
Input image: Inthach's locked character reference sheet; use only its main portrait to preserve his adult male face, long black half-up hair, elegant gold headpiece with white floral ornaments, amber-brown eyes, and white-and-gold Thai-inspired royal clothing. Do not reproduce the reference sheet layout, text, or extra views.
Scene: inside a dim, moving royal carriage entering Ayothara at dusk after rain.
Subject: extreme close-up of Inthach's adult hand gripping a small folded secret order beneath a white sleeve; his focused amber-brown eyes are visible just above it.
Composition: vertical 9:16 cinematic close-up, shallow depth of field, foreground paper and hand sharp, one eye catching warm lantern light; only a partial glimpse of his face, no establishing shot.
Lighting/mood: tense, intimate, mysterious; warm oil-lamp glow against cool dusk shadows.
Materials: silk sleeve with fine gold embroidery, rumpled handmade paper, realistic skin and jewelry, rain-dark carriage wood.
Constraints: preserve Inthach's adult male identity and reference appearance; no other characters visible; no legible writing or typography in the image; no watermark, logos, collage, panels, or character-sheet layout.
```

The user-supplied source reference is stored at `../../characters/references/REF-INT-01 อินทัช.png`. Codex imagegen used that file as an identity reference. The generated frame has no legible note text; add the readable order in video/audio or editorial graphics later.

## Prompt ภาพเริ่มสำหรับ Grok (ต้องแนบ REF-INT-01 เป็น @image)

ใช้ข้อความนี้เฉพาะเมื่อเลือกภาพ REF-INT-01 จริงเป็น @image เพื่อคุมตัวตนอินทัช ห้ามส่งเป็น prompt ล้วนโดยไม่มีภาพอ้างอิง และห้ามอ้างว่าภาพที่ได้ตรงกับ reference จนกว่าจะตรวจผลจริง

```text
Create a vertical 9:16 cinematic live-action Thai fantasy drama still. Extreme close-up inside a dim moving royal carriage at dusk after rain: an elegant adult Thai-inspired male prince with long black half-up hair, amber-brown eyes, a delicate gold crown with white floral ornaments, and a white silk sleeve richly embroidered in gold grips a folded secret order. Show his focused eyes just above the paper, warm lantern light in one eye, cool dusk shadows and rain on the carriage window. Tense, intimate, mysterious, realistic skin and jewelry, shallow depth of field. The paper has ink marks but no readable text. One person only. No collage, reference-sheet layout, subtitles, watermark, or logo.
```
