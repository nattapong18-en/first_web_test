# history-of-c.html

## สถานะ: Vibe Coding

ไฟล์นี้เป็นผลจากการ prompt ตรง ๆ ให้ Claude สร้างหน้าเว็บนำเสนอประวัติ C — ไม่มีการรีวิวโค้ดทีละบรรทัด ไม่มีการออกแบบ architecture เอง ไม่มีการทดสอบ cross-browser หรือ accessibility audit จริงจัง เป็นการ generate-and-accept ล้วน ๆ ตามนิยาม vibe coding: ได้ผลลัพธ์ที่ "ดูใช้ได้" โดยไม่เข้าใจ/ตรวจสอบทุกส่วนที่ถูกสร้างขึ้น

**สิ่งที่ยังไม่ได้ทำ (และควรทำก่อนใช้จริง):**

- ไม่ได้ตรวจ semantic HTML / accessibility (aria-label, heading hierarchy, contrast ratio ของสี amber-on-dark ยังไม่ได้วัดจริงว่าผ่าน WCAG AA หรือไม่)
- ไม่ได้ทดสอบบน browser ที่ไม่รองรับ `IntersectionObserver` หรือ `prefers-reduced-motion` (fallback มีให้แต่ไม่ได้ verify)
- เนื้อหาประวัติศาสตร์ (วันที่, ชื่อ, ฟีเจอร์ของแต่ละ C standard) เขียนจากความรู้ทั่วไปของโมเดล ไม่ได้ web search cross-check แหล่งอ้างอิงปฐมภูมิ — ก่อนเอาไปอ้างอิงในงานวิชาการต้องเช็คกับ ISO/IEC 9899 spec หรือแหล่งที่เชื่อถือได้เอง
- CSS ไม่ได้ตรวจ specificity conflict อย่างเป็นระบบ แค่เขียนแล้วดูว่า render ถูก
- ไม่มี build step / bundler / minification — เป็น static file เดี่ยว โหลด Google Fonts จาก CDN ตรง ๆ (ต้องมีเน็ตตอนเปิด ไม่งั้น fallback เป็น monospace/serif ของระบบ)

**ทำไมถึงบอกไว้ตรงนี้:** เพื่อไม่ให้ตัวเองหรือคนอื่นเข้าใจผิดว่านี่คือ production-ready deliverable ที่ผ่านการ engineer จริง — มันคือ prototype ที่ได้จากการบรรยาย requirement แล้วปล่อยให้ AI ตัดสินใจ implementation detail เกือบทั้งหมด ถ้าจะเอาไปใช้จริงต้องมานั่งอ่านโค้ดเองอย่างน้อยหนึ่งรอบเต็ม ไม่ใช่แค่เปิดดูว่าหน้าตาโอเคก็จบ
