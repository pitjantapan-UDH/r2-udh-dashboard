# ค้นหายา R2 และแบบฟอร์ม

Dashboard กลุ่มงานเภสัชกรรม โรงพยาบาลอุดรธานี

โหลดข้อมูลล่าสุดจาก Google Sheets ทุกครั้งที่เปิดหน้าเว็บ มีปุ่มอัปเดตข้อมูล และค้นหาจากชื่อยา ชื่อแบบฟอร์ม หรือโรค

## นำขึ้น Cloudflare Workers Free

เชื่อม repository นี้กับ Worker `r2-udh` ที่สร้างไว้แล้วใน Cloudflare

- Production branch: `main`
- Root directory: `/`
- Build command: เว้นว่าง
- Deploy command: `npx wrangler deploy`

ชื่อ Worker ใน Cloudflare ต้องตรงกับ `name` ใน wrangler.jsonc
ใช้ Workers Free และที่อยู่ workers.dev โดยไม่ต้องซื้อโดเมน

## พัฒนาบนคอมพิวเตอร์

```sh
npx wrangler dev
```

```sh
npx wrangler login
npx wrangler deploy
```

โค้ดเป็น Worker แบบ standalone ไม่ต้องใช้บัญชี ChatGPT เมื่อเผยแพร่บน Cloudflare แล้ว

## ข้อมูลต้นฉบับ

https://docs.google.com/spreadsheets/d/1n_L-ZQDhsAtsUGmRs1s3KAHGZQ4gVd0K20p6nyYr45o/edit

ชีทต้องเปิดให้ส่งออก XLSX ได้เช่นเดียวกับเว็บต้นฉบับ การเปิดแบบฟอร์มขึ้นกับสิทธิ์ไฟล์ Google Drive

## License

รวม pako ภายใต้ MIT license ดู pako-LICENSE

## เริ่ม build หลังเชื่อม GitHub

เมื่อหน้า Settings → Builds แจ้งให้ push commit เพื่อเริ่ม build แรก ให้ส่ง commit ใหม่ไปที่ main แล้วตรวจสถานะที่แท็บ Deployments หลัง deploy สำเร็จ เปิด https://r2-udh.pit-jantapan.workers.dev
