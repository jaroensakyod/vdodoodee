# Canon Change Log

| วันที่ | เรื่องที่เปลี่ยน/เพิ่ม | แหล่งยืนยัน | ผลต่อไฟล์ |
|---|---|---|---|
| 2026-10-04 | ตั้งโปรเจกต์และบันทึกฐานเรื่อง EP01 9 ฉาก; ต่อมาเพิ่ม production draft EP01 38 คลิปจากคำตอบล่าสุดในแชตอ้างอิง โดยรายละเอียดที่ไม่ยืนยันยังเป็น draft | แชต “เขียน Prompt”, conversationId `6ac1184e-8464-83ec-bdd6-498faf39f224` | MASTER_BIBLE, CHARACTER_BIBLE, arc, episode map, EP01 storyboard, continuity |
| 2026-10-04 | EP02–EP10 ถูกบันทึกเป็น proposal เท่านั้น เพราะแชตไม่ได้ให้โครงครบ 10 ตอนของชื่อ/เวอร์ชันใหม่นี้ | สังเคราะห์จากข้อมูลที่ยืนยัน; ยังไม่ใช่ canon ผู้ใช้ | EPISODE_MAP |
| 2026-10-04 | ตอนตั้งโครงครั้งแรกยังไม่มีภาพแนบใน attachment/workspace; เพิ่มช่องทางเก็บ asset ไว้ ก่อนผู้ใช้ส่งภาพจริงในข้อความถัดมา | ตรวจ attachment/workspace ก่อนรับภาพ character sheet | CHARACTER_BIBLE |
| 2026-10-04 | ผู้ใช้ส่งภาพ character sheet ของรณภพ (ดำแดง) และอินทัช (ขาวทอง); เก็บไฟล์ต้นฉบับและอัปเดต prompt anchors/continuity | ภาพแนบจากผู้ใช้: `ChatGPT Image Oct 4, 2026, 07_09_44 AM.png` (รณภพ), `ChatGPT Image Oct 4, 2026, 07_10_02 AM.png` (อินทัช) | characters/references, CHARACTER_BIBLE, MASTER_BIBLE |
| 2026-10-04 | ตามคำขอผู้ใช้ ปรับ prompt 38 คลิปให้ยึด production draft ล่าสุดในแชต: เปิดคำสั่งลับในรถม้า/คงฉากโคลน, เพิ่ม acting cues และ @image roles, เรียงฉากระเบียง/ตำหนัก/แผนลอบสังหาร; raw runtime 300.5 วินาทีและตัด handle เงียบ 0.5 วินาทีให้ได้ 5:00; ชะตาผู้โจมตีคนที่สองเป็น TBD | คำขอผู้ใช้ “แก้ prompt 38”; บท 38 คลิปล่าสุดจากแชตอ้างอิงเป็น production draft ไม่ใช่การยืนยัน canon ใหม่ | GROK_VIDEO_PROMPTS, EP01_STORYBOARD, KEYFRAME_PROMPTS, MASTER_BIBLE, continuity |
| 2026-10-04 | ทำ skill รายละเอียดสำหรับ prompt Grok ภาษาไทย การกำกับเสียง/สีหน้า/ท่าทาง การเลือก @image และ continuity หลายตอน | คำขอผู้ใช้ “ทำ skill ไว้ให้ละเอียด” | `skills/grok-thai-video-storyboard/` |

เพิ่มแถวใหม่เมื่อผู้ใช้ยืนยัน เปลี่ยน หรือล็อกรายละเอียด ห้ามลบประวัติเดิม

