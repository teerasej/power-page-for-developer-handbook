
# Modify and upload Power Page Project


## 1. แก้ไขโค้ด ในหน้า Home Page และอัพโหลดคืนระบบ 

1. ในส่วนของ Explorer View ใน Visual Studio Code ให้เราเปิดไฟล์ **my-site---site-0f1f4/web-pages/home/content-pages/Home.en-US.webpage.copy.html**

2. แก้ไขโค้ดในบรรทัดที่ 5 จาก

    ```jsx
    <h1>Create an engaging headline, welcome, or call to action</h1>
    ```
    ให้เป็น 
    ```jsx
    <h1>Hello World</h1>
    ```
3. บันทึกไฟล์
4. คลิกขวาที่โฟลเดอร์โปรเจคที่ได้มา และเลือกคำสั่ง **Open in integrated terminal** แบบรูปด้านล่าง
   <img width="430" alt="2024-01-23_21-32-17" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/099cd809-06e5-4beb-9dcc-7e2521912d93">

5. รันคำสั่งด้านล่าง เพื่ออัพโหลด Source code ของ Power Page กลับไปยังระบบ
    ```bash
    pac powerpages upload --path . --modelVersion 2 
    ```
    หากการทำงานเสร็จสิ้น ระบบจะแสดงข้อความประมาณด้านล่าง
    ```bash
    ...
    Power Pages website upload succeeded in 11.93 secs.
    ```

6. กลับไปที่ Power Page Portal เพื่อเช็คการเปลี่ยนแปลง โดยการกดปุ่ม **Sync** 



## 2. การเปิดดู Power Page Website ที่แก้ไขแล้ว ใน Power Platform

1. กลับมาที่ Power Page https://make.powerpages.microsoft.com/
2. เลือก Edit Website ของ Power Page ที่เราต้องการ
3. กดเปิด **Pages** เมนูจากด้านซ้ายมือ
4. เลือก **Home** จากรายการ Page

<img width="354" alt="2024-01-18_14-22-42" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/c05156f4-ea9e-4bbd-93af-9645d57d64c0">


5. ถ้าไม่พบการเปลี่ยนแปลงบนส่วน Edit ให้กดปุ่ม **Sync** จากด้านบนขวามือ
<img width="490" alt="2024-01-18_14-25-41" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/4a4ab054-f6df-4256-846c-cba15c17bafc">

6. กดปุ่ม Preview เพื่อดูผลลัพธ์การทำงาน

**-- เสร็จสมบูรณ์ เย้ --**