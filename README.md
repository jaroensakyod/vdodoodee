# เหนือบัลลังก์ มีเพียงเจ้า — Project files

เริ่มอ่านที่ [MASTER_BIBLE.md](MASTER_BIBLE.md). ไฟล์นั้นเป็น source of truth และชี้ไปยังเอกสารที่ต้องใช้อัปเดตต่อกัน

## โครงสร้าง

```text
outputs/
├── MASTER_BIBLE.md
├── EPISODE_MAP.md
├── RELATIONSHIP_ARC.md
├── characters/
│   ├── CHARACTER_BIBLE.md
│   └── references/        # วางภาพต้นฉบับรณภพและอินทัชที่นี่
├── continuity/
│   ├── CONTINUITY_LOG.md
│   └── CHANGELOG.md
├── production/PRODUCTION_RULES.md
└── episodes/
    ├── EPISODE_TEMPLATE.md
    ├── EP01/EP01_STORYBOARD.md
    └── EP02–EP10/          # โฟลเดอร์เตรียมไว้ต่อยอด
```

Skill สำหรับทำ prompt Grok ภาษาไทยโดยเฉพาะติดตั้งที่ `skills/grok-thai-video-storyboard/SKILL.md`; ใช้คู่กับ Bible และ continuity ในโฟลเดอร์นี้

## ใช้ต่ออย่างไร

1. อ่าน Bible, episode map, relationship arc และ continuity log ก่อนเขียนตอนถัดไป.
2. วางภาพ reference จริงไว้ใน `characters/references/` และบันทึกชื่อ/ตัวละครใน `CHARACTER_BIBLE.md`.
3. คัดลอก `EPISODE_TEMPLATE.md` ไปยังโฟลเดอร์ EP ที่ทำ; ใช้ shot ID เช่น `EP02-S03-C014`.
4. เมื่อผู้ใช้ยืนยัน canon ให้แก้เอกสารเกี่ยวข้องและเพิ่มรายการใน `continuity/CHANGELOG.md`.
5. ปิดท้ายแต่ละ EP ด้วย continuity snapshot ใหม่; ห้ามย้อน knowledge state โดยไม่มีเหตุการณ์รองรับ.

## สถานะต้นฉบับ

- EP01 ฐานเรื่องที่ยืนยันมี 9 ฉาก; production draft 38 คลิปล่าสุดจากแชตอ้างอิงอยู่ใน storyboard และ prompt แยกชัดจาก canon.
- โครง EP02–EP10 เป็น proposal ชั่วคราว ไม่ใช่ข้อมูลที่ผู้ใช้ยืนยัน.
- ภาพ reference จริงของทั้งสองตัวละครอยู่ใน `characters/references/` และลงทะเบียนใน Character Bible แล้ว.
- EP01 ยังเป็น DRAFT เพื่อให้ซ้อมอ่าน dialogue ต่อคลิปและปรับความยาวจริงก่อนล็อก.
- Prompt ทั้ง 38 คลิปอยู่ใน `episodes/EP01/GROK_VIDEO_PROMPTS.md`; ยังไม่ได้ส่งเข้า Grok. keyframe C001 เป็นภาพรถม้าและสอดคล้องกับฉากเปิดฉบับ 38 คลิป.

