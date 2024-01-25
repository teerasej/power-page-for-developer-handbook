
# การใช้งาน Liquid Tag ต่างๆ


## 1. การเตรียมข้อมูลใน Dataverse 

ส่วนนี้จะเป็นการใช้ Product Table ที่สร้างไว้ตอนแรก [ตามขั้นตอนนี้](../create-table-product.md) 

### 1.1 จดชื่อ Table และ Column ที่ต้องการใช้งาน

เราจะทำการจดข้อมูลดังต่อไปนี้ เพื่อนำไปอ้างอิงใน Web Template

> ให้แน่ใจว่าเป็นค่า Name ไม่ใช่ Display Name

1. Name ของ Table
2. Name ของ Column ชื่อ Name
3. Name ของ Column ชื่อ stock
4. Name ของ Column ชื่อ tags

### 1.2 เปิดดูข้อมูล Table และ Column ที่ต้องการใช้งาน

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. เลือกเว็บไซต์ที่ต้องการ และให้กดปุ่ม Edit ตามรูปด้านล่าง
<img width="595" alt="2024-01-18_14-39-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1ce41cc5-d7f8-4350-a21d-348960006cc0"> 

3. จากเมนูด้านซ้าย ให้เลือก **Data > Tables in this site > Product > ... > Edit in Power Apps** ตามรูปด้านล่าง จะเป็นการเปิดหน้าเว็บใหม่ขึ้นมา
   <img width="511" alt="2024-01-21_13-26-00" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/3f1bae6b-4266-4ebf-bea9-376c5aef2124">

4. ในส่วนของ** Tables > Product** ให้เลือกเปิด **Schema > Column** ตามรูปด้านล่าง
<img width="1066" alt="2024-01-21_13-26-21" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/f3febe40-d143-4e62-b4cf-09dde9de80bb">

5. จดค่า Name ของ Column ชื่อ Name และ stock โดยใช้รูปด้านล่างเป็นตัวอ้างอิง **ข้อมูลจริงจะไม่ตรงกับในรูป ให้ใช้ค่าที่เห็นบน Environment ของตัวเอง**
<img width="492" alt="2024-01-19_16-49-44" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/5e3acb83-522e-4352-a48d-0066b04d1e96">
<img width="631" alt="2024-01-19_16-51-04" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/61762393-101e-408d-89ef-d34ae9e8549b">


6. กดเมนู Table จากทางด้านซ้าย และจดค่า Name Column ของ **Product** โดยใช้รูปด้านล่างเป็นตัวอ้างอิง **ข้อมูลจริงจะไม่ตรงกับในรูป ให้ใช้ค่าที่เห็นบน Environment ของตัวเอง**
<img width="1017" alt="2024-01-21_13-52-45" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/aa97b7b9-a9c4-440e-a8b1-9104139a53da">


## 2. กำหนด Table Permission ใน Website 

1. กลับมาที่หน้า Home Page ของ Power Page https://make.powerpages.microsoft.com/
2. จากเว็บไซต์ที่เราเข้าไปสร้าง Web Template ไว้ตอนแรก ให้กดปุ่ม Edit ตามรูปด้านล่าง
<img width="595" alt="2024-01-18_14-39-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1ce41cc5-d7f8-4350-a21d-348960006cc0">

3. จากเมนูด้านซ้าย ให้เลือก **Set up > Security > Table Permission** และกดเลือก **New Permission** ตามรูปด้านล่าง 
<img width="1037" alt="2024-01-19_15-17-31" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/165a5af0-3f90-4cbd-bc3c-c0e7aa0b6966">


4. สร้าง Permission และกรอกข้อมูลตามด้านล่าง เสร็จแล้วกดปุ่ม Save
   1. **Name:** Product List
   2. Table: เลือก Table Product ที่สร้างไว้
   3. **Access Type:**  Global Access
   4. Permission to: Read
   5. Roles
      1. Anonymous
      2. Authenticated Users
   6. เสร็จแล้วกดปุ่ม Save
<img width="586" alt="2024-01-19_16-36-23" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/a187bde4-1b3f-4759-a199-6bb5bb1da3b8">


## 3. การใช้ Filter

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง
<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

3. จากเมนูด้านซ้าย ให้เลือก **Content > Web Template** ตามรูปด้านล่าง
<img width="214" alt="2024-01-18_14-35-34" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/0c4e482d-047f-4ee2-ad9d-f66b8ff6b8c5">

4. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามรูปด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น
   1. **Name:** Product List Template
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Source:** โดยให้แทนที่ name ใน `<entity>` ด้วยชื่อ Table ที่จดไว้ในตอนแรก
    ```html
    <h1>Title: {{ page.title }}</h1>

    {% fetchxml products %}
    <fetch>
        <entity name="ponnf_product">
        <all-attributes />
        </entity>
    </fetch>
    {% endfetchxml %}

    <p> fetched {{ products.results.entities | size }} products.</p>
    ```

    สังเกตว่าเรามีการเรียกใช้ `products.results.entities` และใช้ filter ชื่อ `size` ซึ่งเป็น filter ที่ใช้นับจำนวนข้อมูลที่ได้จากการ fetch มา


## 4. สร้าง Page Template และนำมาแสดงใน Web site

1. จากเมนูด้านซ้าย ให้เลือก **Website > Page Template > กดปุ่ม New** ตามรูปด้านล่าง
<img width="510" alt="2024-01-18_14-38-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/ad5a1318-5f86-4d6f-94d0-390c1f151a85">

2. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น 
   1. **Name:**  Product List Page
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Type:** Web Template
   4. **Web Template:** ให้เลือก **Product List Template** ที่เราสร้างไว้
   5. **Use Website Header and Footer:** กดติ๊กเพื่อเลือก
   6. **Is Default:** ไม่ต้องกดติ๊ก
   7. **Table Name:** ให้กดเลือก Web Page (mspp_webpage) จากที่รายการทางขวา


## 5. วิธีเลือกใช้งาน Page Template ใน Power Page Portal

1. กลับมาที่หน้า Home Page ของ Power Page https://make.powerpages.microsoft.com/
2. จากเว็บไซต์ที่เราเข้าไปสร้าง Web Template ไว้ตอนแรก ให้กดปุ่ม Edit ตามรูปด้านล่าง
<img width="595" alt="2024-01-18_14-39-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1ce41cc5-d7f8-4350-a21d-348960006cc0">

3. จากเมนู Page ให้กดเลือก **+ Page** ตามรูปด้านล่าง
<img width="355" alt="2024-01-18_14-39-38" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/90553db5-460d-48e4-bdfd-d976ae781ac7">

4. กำหนดค่าตามด้านล่าง และกดปุ่ม Add เมื่อเสร็จสิ้น
   1. **Page name:** Product Catalog
   2. **Custom Layout:** Product List Page (นี่คือ Page template ที่เราสร้างไว้ก่อนหน้านี้)

> หากไม่มี Greeting Page ให้เลือก กดปุ่ม Sync ที่อยู่ด้านบนขวาของหน้าจอเพื่อ sync การตั้งค่ารวมถึง Page template ที่เราสร้างไว้ก่อนหน้านี้


5. จะมี Page แสดงขึ้นมาใหม่ใน Main Navigation ให้ทดสอบดูการทำงานโดยกดปุ่ม Preview 

## 6. การใช้งาน Liquid Tag ใน Web Template 

1. แก้ไข Web Template '**Product List Template**' ที่เราสร้างไว้ก่อนหน้านี้ โดยให้แทนที่ด้วย code ตามด้านล่างนี้
2. ให้แทนที่ name ของ Entity, attribute ด้วยค่า Name ที่จดเอาไว้จาก Table ใน Dataverse ตอนแรก

```html
<h1>Title: {{ page.title }}</h1>

{% fetchxml products %}
  <fetch>
    <entity name="ponnf_product">
      <attribute name="ponnf_stock" />
      <attribute name="ponnf_name" />
    </entity>
  </fetch>
{% endfetchxml %}

<p> fetched {{ products.results.entities | size }} products.</p>

<ul>
  {% for product in products.results.entities %} 
      {% if product.ponnf_stock > 0 %}
         <li>{{ product.ponnf_name }}, {{ product.ponnf_stock }}</li>
      {% endif %}
  {%- endfor -%}
</ul>

```

   - สังเกตว่าเรามีการกำหนดชื่อ attribute `ponnf_stock` และ `ponnf_name` โดยตรง ซึ่งเป็นชื่อของ Column ที่เราสร้างไว้ใน Dataverse เพื่อดึงข้อมูลมาจาก table ชื่อ `ponnf_product` 
   - เรามีการใช้ `{% if %}` tag ในการกรองข้อมูล โดยใช้ `product.ponnf_stock` ซึ่งเป็นชื่อของ Column ที่เราสร้างไว้ใน Dataverse

2. เสร็จแล้วกดปุ่ม **Save & Close** และให้ทดสอบการทำงาน
3. ควรได้ผลลัพธ์ใกล้เคียงรูปด้านล่าง 
<img width="777" alt="2024-01-19_17-16-38" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/a42b9e91-3dd1-4f27-b058-7ee7bd1d3546">

**-- เสร็จสมบูรณ์ เย้ --** 