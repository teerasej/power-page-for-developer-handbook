
# การใช้งาน Object Tag

## 1. สร้าง Web Template ใน Power Page

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง

<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

3. จากเมนูด้านซ้าย ให้เลือก **Content > Web Template** ตามรูปด้านล่าง

<img width="214" alt="2024-01-18_14-35-34" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/0c4e482d-047f-4ee2-ad9d-f66b8ff6b8c5">

4. จากนั้นในเมนูด้านบนให้เลือก **New** ตามรูปด้านล่าง

<img width="441" alt="2024-01-18_14-36-18" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/a8f7a5db-f972-4bbb-9e8e-f1db6b9d1357">

5. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามข้อมูลด้านล่าง และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น
   1. **Name:**  Object Tag Template
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Source:** 
   ```html
    <h2>Page Details</h2>
    <p><strong>Page Title:</strong> {{ page.title }}</p> 
    <p><strong>Page ID:</strong> {{ page.id }}</p>
   ```
    สังเกตการใช้ Liquid tag `{{ page.title }}` และ `{{ page.id }}` ในการแสดงข้อมูลของ Page ที่เรากำลังแสดงอยู่

<img width="598" alt="2024-01-19_13-01-44" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/f9d53dc1-e952-45c4-912c-9f532cf177d4">

## 2. สร้าง Page Template จาก Web Template


1. จากเมนูด้านซ้าย ให้เลือก **Website > Page Template > กดปุ่ม New** ตามรูปด้านล่าง

<img width="510" alt="2024-01-18_14-38-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/ad5a1318-5f86-4d6f-94d0-390c1f151a85">

2. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามรายละเอียดด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น 
   1. **Name:**  Page Information
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Type:** Web Template
   4. **Web Template:** ให้เลือก **Object Tag Template** ที่เราสร้างไว้
   5. **Use Website Header and Footer:** กดติ๊กเพื่อเลือก
   6. **Is Default:** ไม่ต้องกดติ๊ก
   7. **Table Name:** ให้กดเลือก Web Page (mspp_webpage) จากที่รายการทางขวา


## 3. วิธีเลือกใช้งาน Page Template ใน Power Page Portal

1. กลับมาที่หน้า Home Page ของ Power Page https://make.powerpages.microsoft.com/
2. จากเว็บไซต์ที่เราเข้าไปสร้าง Web Template ไว้ตอนแรก ให้กดปุ่ม Edit ตามรูปด้านล่าง

<img width="595" alt="2024-01-18_14-39-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1ce41cc5-d7f8-4350-a21d-348960006cc0">

3. จากเมนู Page ให้กดเลือก **+ Page** ตามรูปด้านล่าง

<img width="355" alt="2024-01-18_14-39-38" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/90553db5-460d-48e4-bdfd-d976ae781ac7">

4. กำหนดค่าตามรูปด้านล่าง และกดปุ่ม Add เมื่อเสร็จสิ้น
   1. **Page Name:**  Page Info
   2. **Custom Layout:** Page Information (นี่คือ Page template ที่เราสร้างไว้ก่อนหน้านี้)

> หากไม่มี ให้เลือก กดปุ่ม Sync ที่อยู่ด้านบนขวาของหน้าจอเพื่อ sync การตั้งค่ารวมถึง Page template ที่เราสร้างไว้ก่อนหน้านี้

<img width="643" alt="2024-01-18_14-39-58" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/8e5235ad-ff3b-45ff-b521-afa913600fbc">

5. จะมี Page แสดงขึ้นมาใหม่ใน Main Navigation ให้ทดสอบดูการทำงานโดยกดปุ่ม Preview 
6. ได้ผลลัพธ์ตามรูปด้านล่าง 

<img width="644" alt="2024-01-19_13-07-48" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/e0f19d92-bb50-48dd-852d-cdbe9a4b1c91">


**-- เสร็จสมบูรณ์ เย้ --**

## เพิ่มเติม 

https://learn.microsoft.com/en-us/power-pages/configure/liquid/liquid-objects 