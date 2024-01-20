

# การสร้างและต่อยอด Custom Layout ใน Web Template

## 1. สังเกตการสร้าง Custom Layout

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง

<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

3. จากเมนูด้านซ้าย ให้เลือก **Content > Web Template** ตามรูปด้านล่าง

<img width="214" alt="2024-01-18_14-35-34" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/0c4e482d-047f-4ee2-ad9d-f66b8ff6b8c5">

4. จากรายการของ Active Web Template ให้เลือก **Layout 2 Column Wide Left**
5. ในส่วนของ Source ให้สังเกตบรรทัดที่ 3, 6, 12, 17 ที่มีการใช้ Liquid tag `{% block %}` และ `{% endblock %}` ในการกำหนด Layout ของ Web Template

```html
<div class="container">
 <div class="page-heading">
  {% block breadcrumbs %}
      {% include 'Breadcrumbs' %}
    {% endblock %}
  {% block title %}
    {% include 'Page Header' %}
  {% endblock %}
 </div>
 <div class="row">
  <div class="col-sm-8 col-lg-8 left-column">
   {% block main %}
    {% include 'Page Copy' %}
   {% endblock %}
  </div>
  <div class="col-sm-4 col-lg-4 right-column">
   {% block aside %}{% endblock %}
  </div>
 </div>
</div>
```

## 2. สร้าง Web Template ต่อเนื่องจาก Web Template อื่น

1. กด back กลับมาที่หน้า Web Template
2. จากเมนูด้านบนให้เลือก **New** 
3. กรอกข้อมูลต่างๆ ในส่วน **General** ตามข้อมูลด้านล่าง 
   1. **Name:** Directory Template
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Source:** 
   ```html
   {% extends "Layout 2 Column Wide Left" %}

   {% block aside %}
     <h2>Directory</h2>
   {% endblock %}
   ```

### คำอธิบาย

สังเกตการสร้าง Web Template ใหม่ ในส่วนของ Source จะมีการใช้ Liquid tag `{% extends %}` ในการกำหนด Layout ของ Web Template ใหม่

```html
{% extends "Layout 2 Column Wide Left" %}
```

และ Liquid tag `{% block %}` และ `{% endblock %}` ในการกำหนด Layout ของ Web Template ใหม่แทนที่ของเดิมที่ถูกระบุไว้ใน Web Template ต้นฉบับ  

```html
{% block aside %}
  <h2>Directory 1</h2>
{% endblock %}
```

4. กดปุ่ม Save & Close เมื่อเสร็จสิ้น

## 3. สร้าง Page Template ใน Power Page

1. จากเมนูด้านซ้าย ให้เลือก **Website > Page Template > กดปุ่ม New** ตามรูปด้านล่าง

<img width="510" alt="2024-01-18_14-38-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/ad5a1318-5f86-4d6f-94d0-390c1f151a85">

2. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามข้อมูลด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น 
   1. **Name:** Directory Page
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Type:** Web Template
   4. **Web Template:** ให้เลือก **Directory Template** ที่เราสร้างไว้
   5. **Use Website Header and Footer:** กดติ๊กเพื่อเลือก
   6. **Is Default:** ไม่ต้องกดติ๊ก
   7. **Table Name:**ให้กดเลือก Web Page (mspp_webpage) จากที่รายการทางขวา


## 4. วิธีเลือกใช้งาน Page Template ใน Power Page Portal

1. กลับมาที่หน้า Home Page ของ Power Page https://make.powerpages.microsoft.com/
2. จากเว็บไซต์ที่เราเข้าไปสร้าง Web Template ไว้ตอนแรก ให้กดปุ่ม Edit ตามรูปด้านล่าง

<img width="595" alt="2024-01-18_14-39-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1ce41cc5-d7f8-4350-a21d-348960006cc0">

3. จากเมนู Page ให้กดเลือก **+ Page** ตามรูปด้านล่าง

<img width="355" alt="2024-01-18_14-39-38" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/90553db5-460d-48e4-bdfd-d976ae781ac7">

4. กำหนดค่าตามรูปด้านล่าง และกดปุ่ม Add เมื่อเสร็จสิ้น
   1. **Page Name:**  Directory Page
   2. **Custom Layout:** Directory Page (นี่คือ Page template ที่เราสร้างไว้ก่อนหน้านี้)

> หากไม่มี Directory Page ให้เลือก กดปุ่ม Sync ที่อยู่ด้านบนขวาของหน้าจอเพื่อ sync การตั้งค่ารวมถึง Page template ที่เราสร้างไว้ก่อนหน้านี้

5. จะมี **Directory Page** แสดงขึ้นมาใหม่ใน Main Navigation ให้ทดสอบดูการทำงานโดยกดปุ่ม Preview 
6. ทดสอบดูผลการทำงานของ Directory Page ที่เราสร้างไว้จาก Web Template ที่ชื่อ Directory Template

## 5. การเรียกใช้ Web Template อื่นใน Template ของตัวเอง

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง

<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

3. จากเมนูด้านซ้าย ให้เลือก **Content > Web Template** ตามรูปด้านล่าง

<img width="214" alt="2024-01-18_14-35-34" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/0c4e482d-047f-4ee2-ad9d-f66b8ff6b8c5">

4. จากเมนูด้านบนให้เลือก **New** 
5. กรอกข้อมูลต่างๆ ในส่วน **General** ตามข้อมูลด้านล่าง เสร็จแล้วกดปุ่ม **Save & Close**
   1. **Name:**  Directory List
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Source:** 
   ```html
    <ul>
      <li>List item 1</li>
      <li>List item 2</li>
      <li>List item 3</li>
    </ul>
   ```

6. กลับมาที่หน้า Web Template และเลือก **Directory Template** ที่เราสร้างไว้ก่อนหน้านี้
7. แก้ไขในส่วนของ Source ก่อนให้เป็นตามด้านล่าง 

  ```html
  {% extends "Layout 2 Column Wide Left" %}

  {% block aside %}
    <h2>Directory 1</h2>
    {% include 'Directory List' %}
  {% endblock %}
  ```
  สังเกตว่าเราเพิ่ม Liquid tag `{% include %}` ในการเรียกใช้งาน Web Template ที่ชื่อว่า Directory List ที่เราสร้างไว้ก่อนหน้านี้

8. กดปุ่ม **Save & Close**
9. กลับไปที่ Power Page Portal และกดปุ่ม sync 
10. ทำการพรีวิวหน้าเว็บไซต์ และเลือก Directory Page ที่เราสร้างไว้ก่อนหน้านี้ 


**-- เสร็จสมบูรณ์ เย้ --**