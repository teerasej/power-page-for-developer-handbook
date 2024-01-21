
# สร้าง Table Product

1. หน้า Home Page ของ Power Page https://make.powerpages.microsoft.com/
2. จากรายการเว็บไซต์ ให้กดปุ่ม Edit ตามรูปด้านล่าง
<img width="595" alt="2024-01-18_14-39-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1ce41cc5-d7f8-4350-a21d-348960006cc0">

3. กดเลือกส่วน Data Menu ทางด้านซ้าย และกดปุ่ม **+ Table** ตามรูปด้านล่าง
<img width="640" alt="2024-01-21_13-23-03" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/8c3494bc-433e-4726-a3f0-43171ee0e2ba">


4. กำหนดข้อมูลชื่อ Table ตามรายละเอียดด้านล่าง และกดปุ่ม Save
    - Display Name: Product
    - Prural Name: Products
<img width="513" alt="2024-01-21_13-23-22" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/85b17b2c-3657-4b0d-b05b-883df3f65929">

5. จากเมนู Data ให้เลือก **Tables in this site > Product > Table data > + New Column** ตามรูปด้านล่าง เพื่อกรอกข้อมูลสร้าง Column ใหม่ เสร็จแล้วกดปุ่ม Save

   -  Display Name: Stock
   -  Data Type: เลือก Whole number
   -  Format: เลือก None 
   -  ส่วนอื่นๆ ไม่ต้องเปลี่ยนแปลงอะไร
<img width="1257" alt="2024-01-21_13-24-56" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/d48528b7-9976-4e35-8adc-93e93a18a428">


6. ทำการกรอกข้อมูลลงไปใน Product table ผ่านส่วน Table Data เฉพาะ Column ที่กำหนด ดังนี้

| name |  stock |
|------|--------|
|  Macbook   |  4    |
|  iPhone 13   |  0    |
|  iPhone 15 Pro   |  23    |


**-- เสร็จสมบูรณ์ เย้ --**