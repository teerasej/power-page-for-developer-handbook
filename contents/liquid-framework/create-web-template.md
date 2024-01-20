
# การสร้าง Web Template และ Page Template รวมถึงวิธีใช้งานใน Power Page Portal

## 1. สร้าง Web Template ใน Power Page

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง

<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

3. จากเมนูด้านซ้าย ให้เลือก **Content > Web Template** ตามรูปด้านล่าง

<img width="214" alt="2024-01-18_14-35-34" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/0c4e482d-047f-4ee2-ad9d-f66b8ff6b8c5">

4. จากนั้นในเมนูด้านบนให้เลือก **New** ตามรูปด้านล่าง

<img width="441" alt="2024-01-18_14-36-18" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/a8f7a5db-f972-4bbb-9e8e-f1db6b9d1357">

5. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามรูปด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น
   1. **Name:**  Greeting
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Source:** 
   ```
    <h1>สวัสดี</h1>
   ```

<img width="618" alt="2024-01-18_14-37-28" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/d10683b7-5b22-4ef7-8e17-f6bf40ff0cd6">

6. สังเกตในส่วน Active Web Template จะมี Greeting ที่เราสร้างไว้แสดงอยู่ในรายการ
   
<img width="646" alt="2024-01-18_14-37-54" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/159d3e85-4379-48c4-afe0-b9e05474c20d">


## 2. สร้าง Page Template ใน Power Page

1. จากเมนูด้านซ้าย ให้เลือก **Website > Page Template > กดปุ่ม New** ตามรูปด้านล่าง

<img width="510" alt="2024-01-18_14-38-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/ad5a1318-5f86-4d6f-94d0-390c1f151a85">

2. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามรูปด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น 
   1. **Name:** Greeting Page
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Type:** Web Template
   4. **Web Template:** ให้เลือก **Greeting** ที่เราสร้างไว้
   5. **Use Website Header and Footer:** กดติ๊กเพื่อเลือก
   6. **Is Default:** ไม่ต้องกดติ๊ก
   7. **Table Name:**ให้กดเลือก Web Page (mspp_webpage) จากที่รายการทางขวา

<img width="1053" alt="2024-01-18_14-38-55" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/6b6a344d-697f-47fd-ab8a-462543cca9f5">


## 3. วิธีเลือกใช้งาน Page Template ใน Power Page Portal

1. กลับมาที่หน้า Home Page ของ Power Page https://make.powerpages.microsoft.com/
2. จากเว็บไซต์ที่เราเข้าไปสร้าง Web Template ไว้ตอนแรก ให้กดปุ่ม Edit ตามรูปด้านล่าง

<img width="595" alt="2024-01-18_14-39-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1ce41cc5-d7f8-4350-a21d-348960006cc0">

3. จากเมนู Page ให้กดเลือก **+ Page** ตามรูปด้านล่าง

<img width="355" alt="2024-01-18_14-39-38" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/90553db5-460d-48e4-bdfd-d976ae781ac7">

4. กำหนดค่าตามรูปด้านล่าง และกดปุ่ม Add เมื่อเสร็จสิ้น
   1. **Page Name:**  Say Hi
   2. **Custom Layout:** Greeting Page (นี่คือ Page template ที่เราสร้างไว้ก่อนหน้านี้)

> หากไม่มี Greeting Page ให้เลือก กดปุ่ม Sync ที่อยู่ด้านบนขวาของหน้าจอเพื่อ sync การตั้งค่ารวมถึง Page template ที่เราสร้างไว้ก่อนหน้านี้

<img width="643" alt="2024-01-18_14-39-58" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/8e5235ad-ff3b-45ff-b521-afa913600fbc">

5. จะมี Page แสดงขึ้นมาใหม่ใน Main Navigation ให้ทดสอบดูการทำงานโดยกดปุ่ม Preview ตามรูปด้านล่าง 
      
<img width="1167" alt="2024-01-18_14-40-22" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/afc7b377-1a72-4a3f-96c2-48cb494d82b3">

**-- เสร็จสมบูรณ์ เย้ --**