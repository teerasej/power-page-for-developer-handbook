
# การนำข้อมูลจาก Dataverse มาแสดงผลใน Liquid tag

ส่วนนี้ต่อเนื่องจาก [การสร้างและต่อยอด Custom Layout ใน Web Template](contents/liquid-framework/custom-layout.md)

## 1. แก้ไข Web Template 'Directory List'

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง

<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

3. จากเมนูด้านซ้าย ให้เลือก **Content > Web Template** ตามรูปด้านล่าง

<img width="214" alt="2024-01-18_14-35-34" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/0c4e482d-047f-4ee2-ad9d-f66b8ff6b8c5">

4. จากนั้นให้เลือก Web Template ชื่อ 'Directory List' และแก้ไข Source Code ดังนี้
   
  ```html
  {% fetchxml accounts %}
  <fetch>
    <entity name="account">
      <attribute name="name" />
    </entity>
  </fetch>
  {% endfetchxml %}


    <ul>
      {% for account in accounts.results.entities %} 
      <li>{{ account.name }}</li>
      {%- endfor -%}
    </ul>
  ```

  สังเกตว่าเราได้เพิ่ม Liquid tag ที่เรียกข้อมูลจาก Dataverse มาแสดงผล ด้วย Liquid tag ชื่อ `{% fetchxml %}` ในรูปแบบของ List แล้ว
   
5. กดปุ่ม **Save & Close** เพื่อบันทึกการแก้ไข


## 3. ตั้งค่า Permission ให้กับ Table

1. กลับมาที่หน้า Home Page ของ Power Page https://make.powerpages.microsoft.com/
2. จากเว็บไซต์ที่เราเข้าไปสร้าง Web Template ไว้ตอนแรก ให้กดปุ่ม Edit ตามรูปด้านล่าง

<img width="595" alt="2024-01-18_14-39-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1ce41cc5-d7f8-4350-a21d-348960006cc0">

3. จากเมนูด้านซ้าย ให้เลือก **Set up > Security > Table Permission** และกดเลือก **New Permission** ตามรูปด้านล่าง 

<img width="1037" alt="2024-01-19_15-17-31" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/165a5af0-3f90-4cbd-bc3c-c0e7aa0b6966">


4. สร้าง Permission และกรอกข้อมูลตามด้านล่าง เสร็จแล้วกดปุ่ม Save
   1. Name: Account Directory
   2. Table: Account
   3. Access Type: Global Access
   4. Permission to: Read
   5. Roles
      1. Anonymous
      2. Authenticated Users
   6. เสร็จแล้วกดปุ่ม Save

<img width="594" alt="2024-01-19_15-20-58" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/e5ff4665-035b-4e1e-8cbb-311149e34c07">


## 4. ทดสอบการทำงาน

1. กดปุ่ม Sync ด้านบนขวาตามรูปด้านล่าง เพื่อให้แน่ใจว่าเราได้ทำการ Sync ข้อมูล Web template ล่าสุดมาแล้ว
   
<img width="579" alt="2024-01-19_15-05-44" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/18415567-5fb0-49e5-a78c-ad4cd533607c">

2. กดปุ่ม Preview เพื่อแสดงผล 

<img width="579" alt="2024-01-19_15-05-44 copy" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/f9262894-1ca1-45fc-9890-f1dfe4722a49">

3. ควรได้ผลลัพธ์ประมาณรูปด้านล่าง 

<img width="1212" alt="2024-01-19_15-12-02" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/2f65a022-b685-4025-b29d-409ceededcd0">
