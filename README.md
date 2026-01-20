# Translator — quick ping‑pong phrase translator for travelers

[Live demo](https://parawee66.github.io/translator/) · แบบหน้าเดียว (single‑page HTML) · ไม่มีการเก็บข้อมูล (privacy‑first)

Short description: เว็บแอพแปลประโยคสไตล์ phrasebook สำหรับนักท่องเที่ยว — สนทนาแบบสั้น ๆ (ping‑pong) เพื่อใช้ในสนามบิน ร้านอาหาร และการเดินทางทั่วไป

---

## Who this is for / กลุ่มเป้าหมาย
- นักท่องเที่ยวที่ต้องการสื่อสารแบบสั้น กระชับ และรวดเร็ว
- ผู้ใช้มือถือที่ต้องการประโยคสำเร็จรูปแทนการพิมพ์ยาว ๆ
- คนที่กังวลเรื่องความเป็นส่วนตัว — แอพนี้ทำงานทั้งหมดในเบราว์เซอร์ ไม่มีการส่งหรือเก็บข้อความไปยังเซิร์ฟเวอร์
- ผู้ที่ต้องการตัวอย่างประโยคในสถานการณ์จริง: สนามบิน, โรงแรม, ร้านอาหาร, ขอยา/ความช่วยเหลือฉุกเฉิน

## Core features / คุณสมบัติหลัก
- สนทนาแบบ ping‑pong: พิมพ์/เลือกประโยคแล้วจะตอบกลับทันทีในรูปแบบคู่สนทนา
- Single static HTML: ทำงานฝั่งลูกค้า (client‑side) เท่านั้น — ไม่มี backend ไม่มีฐานข้อมูล
- ความเป็นส่วนตัวสูง: ข้อความและประวัติการพูดคุยไม่ถูกส่งออกหรือเก็บบนเซิร์ฟเวอร์ (ดูรายละเอียดด้านล่าง)
- เบาและเร็ว: เหมาะสำหรับการใช้งานบนมือถือและเครือข่ายช้า
- ง่ายต่อการ fork และปรับแต่ง phrase packs

## Demo / ตัวอย่างการใช้งาน (quick examples)
- Airport: "Where is the check‑in counter?" → คำแนะนำประโยคสำเร็จรูป
- Restaurant: "Can I have the bill, please?"
- Directions: "How do I get to the train station?"
- Emergency: "I need a doctor" / "Call the police"

ตัวอย่างที่ใช้บ่อย:
- ภาษาอังกฤษ → ไทย (หรือสลับทิศทางตามที่มี)
- ปุ่มเลือกประโยค (preset) เพื่อใช้งานเร็ว

## Privacy & Data handling / นโยบายความเป็นส่วนตัว (สรุป)
- ไม่มีการส่งข้อความไปยังเซิร์ฟเวอร์ของโปรเจคนี้
- ประวัติการสนทนาอยู่ในหน่วยความจำของเบราว์เซอร์เท่านั้น (หากหน้ารีเฟรช ข้อมูลอาจหาย — ไม่มี persistent storage)
- ไม่มีการเก็บ log ผู้ใช้หรือการวิเคราะห์ (ถ้าต้องการเพิ่ม analytics ให้ระบุชัดเจนใน README และใน code)

## How to run locally / รันบนเครื่องของคุณ
1. คลอน repo:
   - git clone https://github.com/parawee66/translator.git
2. เปิดไฟล์ `index.html` โดยตรงด้วยเบราว์เซอร์ หรือเสิร์ฟแบบง่าย:
   - Python 3: `python -m http.server 8000` แล้วเปิด `http://localhost:8000/`
   - หรือใช้ Live Server ใน VS Code
3. หน้าเว็บเป็นไฟล์ statics ทั้งหมด (HTML/CSS/JS) — ไม่ต้องติดตั้ง backend

## Project structure (ตัวอย่าง)
- index.html — หน้าเดียว (UI + logic)
- assets/ — รูปภาพ, ไอคอน, GIF ตัวอย่าง
- js/phrases.json — (ถ้ามี) คลังประโยคแบบ JSON
- README.md — ไฟล์นี้

(ปรับโครงสร้างตาม repository จริงของคุณ)

## How to customize phrases / เพิ่มชุดประโยค (example)
ถ้าประโยคเก็บใน JSON ตัวอย่างโครงสร้าง:
[
  {
    "id": "airport_01",
    "source": "Where is the check-in counter?",
    "target": "เคาน์เตอร์เช็คอินอยู่ที่ไหน",
    "tags": ["airport", "travel"]
  },
  {
    "id": "restaurant_01",
    "source": "Can I have the bill, please?",
    "target": "ขอบิลทีครับ/ค่ะ",
    "tags": ["restaurant", "payment"]
  }
]
- เพิ่มไฟล์ phrase pack ใหม่หรือแก้ `js/phrases.json` แล้วรีเฟรชหน้าเว็บ

## Contribution / การร่วมพัฒนา
- หากต้องการเพิ่มภาษา ชุดประโยค หรือ UI improvements โปรดเปิด Issue หรือ PR
- แนะนำ labels ที่ใช้: `feature:phrasepack`, `bug`, `enhancement`, `i18n`
- Contribution flow:
  1. Fork repo
  2. สร้าง branch ใหม่ (เช่น `add-th-phrases`)
  3. แก้ไข/เพิ่มไฟล์
  4. เปิด Pull Request พร้อมคำอธิบาย use case ของชุดประโยคใหม่

ถ้าต้องการ ฉันช่วยเขียน issue templates / labels ให้ได้

## Deployment (GitHub Pages)
- ถ้าใช้ branch `main` ให้ไฟล์อยู่ที่ root หรือ `docs/` แล้วตั้งค่า GitHub Pages เป็น source
- ตัวอย่างการ deploy แบบง่าย:
  - Push โค้ดไปยัง `main` → Settings → Pages → เลือก branch `main` และ root
- Live demo ของโปรเจคนี้: https://parawee66.github.io/translator/

## Accessibility & Mobile tips
- ทำให้ปุ่มใหญ่พอแตะได้ (touch targets)
- ใช้ contrast ที่ชัดเจนสำหรับข้อความสำคัญ
- ให้รองรับการใช้คีย์บอร์ดและ screen readers หากต้องการเข้าถึงกลุ่มผู้สูงอายุหรือผู้ที่ต้องการ accessibility

## Troubleshooting / ปัญหาที่พบบ่อย
- หน้าไม่โหลด / 404 → ตรวจสอบว่าไฟล์อยู่ใน branch ที่เป็น source ของ GitHub Pages
- เสียง/Voice input ไม่ทำงาน → ต้องใช้ HTTPS และอนุญาตไมโครโฟนในเบราว์เซอร์
- การแปลไม่แม่น → เพิ่มประโยคเฉพาะสถานการณ์ (phrase pack) แทน reliance กับโมเดลทั่วไป

## Roadmap ideas (ไอเดียพัฒนา)
- เพิ่ม voice input / TTS (option)
- เพิ่ม offline JSON phrase packs สำหรับดาวน์โหลด
- เพิ่มฟังก์ชันหมวดหมู่ (airport, food, emergency) และปุ่ม favorite
- เพิ่มระบบ community contributed phrase packs (ผ่าน PR)

## License / ใบอนุญาต
- ใส่ license ที่ต้องการ เช่น MIT (เปลี่ยนได้ตามต้องการ)
- ตัวอย่าง: `LICENSE` — MIT License

## Contact / ติดต่อ
- เจ้าของ: parawee66 (GitHub) — https://github.com/parawee66
- เปิด issue หรือ PR ใน repo เพื่อเสนอชุดประโยคหรือรายงานบั๊ก

---

ขอบคุณที่แชร์โปรเจค! ถ้าต้องการ ฉันช่วย:
- สร้างไฟล์ README.md นี้ใน repo ให้ (push/create PR)
- สร้าง issue templates, labels, หรือตัวอย่าง phrase JSON
- เขียน README เวอร์ชันภาษาอังกฤษเพิ่มเติม

บอกฉันว่าต้องการให้ฉันทำขั้นตอนไหนต่อ (เช่น "สร้าง README ใน repo" หรือ "ส่ง README ให้เป็นไฟล์เท่านั้น") — ฉันจะทำให้ตามนั้นทันที