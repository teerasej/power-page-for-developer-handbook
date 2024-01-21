
# Permission และ Liquid tag

ส่วนนี้ต่อเนื่องจากแบบฝึกหัด [การนำข้อมูลจาก Dataverse มาแสดงผลใน Liquid tag](contents/liquid-framework/liquid-tag-with-dataverse.md) โดยเราจะมาเรียนรู้การใช้งาน Permission ในการแสดงผลข้อมูลใน Liquid tag ต่อไป


## 1. แก้ไข Web Template 'Directory List'

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

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

{% if accounts.global_permission_granted %}
  <ul>
    {% for account in accounts.results.entities %} 
    <li>{{ account.name }}</li>
    {%- endfor -%}
  </ul>
{% else %}
  <div class="alert alert-warning">You do not have permissions to access the directory.</div>
{% endif %}
```

  สังเกตว่าเราได้เพิ่ม Liquid tag ที่มีการเช็ค Permission ก่อนที่จะแสดงผลข้อมูล ด้วย Liquid tag ชื่อ `{% if %}` ในรูปแบบของ List แล้ว
   
5. กดปุ่ม **Save & Close** เพื่อบันทึกการแก้ไข

## 2. ทดสอบการทำงาน

1. กลับมาที่หน้า Home Page ของ Power Page https://make.powerpages.microsoft.com/
2. จากเว็บไซต์ที่เราเข้าไปสร้าง Web Template ไว้ตอนแรก ให้กดปุ่ม Edit ตามรูปด้านล่าง
<img width="595" alt="2024-01-18_14-39-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1ce41cc5-d7f8-4350-a21d-348960006cc0">

3. กดปุ่ม Sync ด้านบนขวาตามรูปด้านล่าง เพื่อให้แน่ใจว่าเราได้ทำการ Sync ข้อมูล Web template ล่าสุดมาแล้ว
<img width="579" alt="2024-01-19_15-05-44" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/18415567-5fb0-49e5-a78c-ad4cd533607c">

4. กดปุ่ม Preview เพื่อแสดงผล 
<img width="579" alt="2024-01-19_15-05-44 copy" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/f9262894-1ca1-45fc-9890-f1dfe4722a49">

5. ควรได้ผลลัพธ์ประมาณรูปด้านล่าง 
<img width="1212" alt="2024-01-19_15-12-02" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/2f65a022-b685-4025-b29d-409ceededcd0">


## 3. ทดสอบยกเลิก Anonymous Permission


1. กลับมาที่หน้า Power Page Portal ของ Power Page https://make.powerpages.microsoft.com/

2. จากเมนูด้านซ้าย ให้เลือก **Set up > Security > Table Permission** และกดเลือก Permission ชื่อ **Account Directory** ตามรูปด้านล่าง 
<img width="1037" alt="2024-01-19_15-17-31" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/4dbc0af7-f323-4814-9775-94f9cb398099">

3. จาก Roles ให้เลือก **Anonymous** และกดปุ่ม **Remove** เพื่อลบ Permission ของ **Anonymous** ออก
<img width="581" alt="2024-01-19_15-41-49" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/111847c1-ab1d-4e93-99a5-90898d82a3f2">

4. กดปุ่ม **Save**
5. ทดสอบพรีวิวหน้าเว็บ **Directory Page** อีกครั้ง ควรได้ผลลัพธ์ใกล้เคียงด้านล่าง
<img width="1274" alt="2024-01-19_15-43-46" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/35a0735c-cb68-43ba-8094-1150804ca42a">

**-- เสร็จสมบูรณ์ เย้ --**