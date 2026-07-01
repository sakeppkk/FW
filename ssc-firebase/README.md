# SSC Firebase Camera

กล้องนี้ใช้เฉพาะโปรเจกต์ SSC บน Firebase Hosting

- URL เป้าหมาย: `https://sakeppkk.github.io/FW/ssc-firebase/ssc-camera.html`
- Firebase return URL: `https://ssc-fw.web.app/idcard.html`
- ส่งภาพเข้า Apps Script API ใหม่ด้วย `saveCameraCapture`
- ภาพเป็น JPEG ครอปสัดส่วน 1.586:1
- ไม่มี OCR, Tesseract หรือ Auto-fill
- ไม่ใช้และไม่แก้ Service Worker/cache กลาง

## ห้ามกระทบระบบเดิม

ไฟล์ `../ssc-camera.html` เป็นกล้องของโปรเจกต์ Apps Script เดิม ห้ามแก้ ย้าย ลบ หรือเขียนทับ กล้องสองชุดต้องเผยแพร่เป็นคนละ URL

## ลำดับเผยแพร่

1. อัปโหลดเฉพาะโฟลเดอร์ `ssc-firebase/` ขึ้น repository `FW`
2. ตรวจว่า URL กล้องใหม่ตอบ HTTP 200
3. Deploy Firebase Hosting ที่อัปเดต `public/config.js` และ `public/idcard.html`
4. ทดสอบการถ่าย ครอป ส่งภาพ และกลับหน้า Firebase
5. ตรวจ hash และทดสอบกล้อง Apps Script เดิมซ้ำ
