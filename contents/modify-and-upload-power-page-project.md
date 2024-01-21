
# Modify and upload Power Page Project

## 1. การแก้ไข Power Page Website ใน Visual Studio Code

จากโฟลเดอร์โปรเจค Power Page Website ที่ดึงมาจาก Power Platform มาใช้งาน ให้ทำการแก้ไขไฟล์ `web-pages/home/content-pages/Home.en-US.webpage.copy.html` ตามคำสั่งด้านล่าง

```html
<!-- จากบรรทัดที่ 5 -->
<h1>Create an engaging headline, welcome, or call to action</h1>
```

เปลี่ยนเป็น

```html
<!-- จากบรรทัดที่ 5 -->
<h1>Hello World</h1>
```

## 2. การอัพโหลดไฟล์โปรเจค Power Page Website ที่แก้ไขแล้ว กลับไปที่ Power Platform

รันคำสั่งด้านล่าง ใน Terminal เพื่ออัพโหลดไฟล์โปรเจค Power Page Website ที่แก้ไขแล้ว กลับไปที่ Power Platform

- ให้แทนที่ `[project directory]` ด้วยชื่อโฟลเดอร์โปรเจคที่เราต้องการจะอัพโหลดกลับไปที่ Power Platform

```bash
pac powerpages upload --modelVersion 2 --path "[project directory]" 
```

## 3. การเปิดดู Power Page Website ที่แก้ไขแล้ว ใน Power Platform

1. กลับมาที่ Power Page https://make.powerpages.microsoft.com/
2. เลือก Edit Website ของ Power Page ที่เราต้องการ
3. กดเปิด **Pages** เมนูจากด้านซ้ายมือ
4. เลือก **Home** จากรายการ Page

<img width="354" alt="2024-01-18_14-22-42" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/c05156f4-ea9e-4bbd-93af-9645d57d64c0">


5. ถ้าไม่พบการเปลี่ยนแปลงบนส่วน Edit ให้กดปุ่ม **Sync** จากด้านบนขวามือ
<img width="490" alt="2024-01-18_14-25-41" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/4a4ab054-f6df-4256-846c-cba15c17bafc">

6. กดปุ่ม Preview เพื่อดูผลลัพธ์การทำงาน

**-- เสร็จสมบูรณ์ เย้ --**