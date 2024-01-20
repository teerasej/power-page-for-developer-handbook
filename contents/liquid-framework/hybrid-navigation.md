
# การใช้งาน Hybrid Naivagation

- เป้าหมายของ Hybrid Navigation คือการสร้าง Web Template ในส่วน Navigation ที่ยืดหยุ่นมากขึ้น โดยสามารถกำหนดให้ Navigation แสดงผลได้หลายรูปแบบ ตามที่เราต้องการ

## 1. สร้าง Web Template ใหม่ ที่มีการสร้าง Hybrid Navigation

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง

<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

3. จากเมนูด้านซ้าย ให้เลือก **Content > Web Template** ตามรูปด้านล่าง

<img width="214" alt="2024-01-18_14-35-34" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/0c4e482d-047f-4ee2-ad9d-f66b8ff6b8c5">

4. จากนั้นในเมนูด้านบนให้เลือก **New** ตามรูปด้านล่าง

<img width="441" alt="2024-01-18_14-36-18" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/a8f7a5db-f972-4bbb-9e8e-f1db6b9d1357">

5. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น
   1. **Name:** Hybrid Nav
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Source:** 
   ```
   {% extends "Layout 2 Column Wide Left" %}

    {% block aside %}
    
        <h2>Child pages</h2>

        {% assign max_depth = 3 %}
        {% assign current_depth = 0 %}
        {% assign current_page = page %}

        {% if current_page.children.size > 0 %}
        
            <ul>
            {% for child in current_page.children %}
                <li><a href="{{ child.url }}">{{ child.title }}</a></li>
            {% endfor %}
            </ul>
            
        {% endif %}
    {% endblock %}
   ```

## 2. สร้าง Page Template ใน Power Page

1. จากเมนูด้านซ้าย ให้เลือก **Website > Page Template > กดปุ่ม New** ตามรูปด้านล่าง

<img width="510" alt="2024-01-18_14-38-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/ad5a1318-5f86-4d6f-94d0-390c1f151a85">

2. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น 
   1. **Name:** With Hybrid Navigation
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Type:** Web Template
   4. **Web Template:** ให้เลือก **Hybrid Nav** ที่เราสร้างไว้
   5. **Use Website Header and Footer:** กดติ๊กเพื่อเลือก
   6. **Is Default:** ไม่ต้องกดติ๊ก
   7. **Table Name:** ให้กดเลือก Web Page (mspp_webpage) จากที่รายการทางขวา

## 3. สร้าง Page ใหม่ ได้แก่ Level-0 และ Level-1

1. จากเมนูด้านซ้าย ให้เลือก **Content > Web Pages > กดปุ่ม New** 
2. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามรูปด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น 
   1. **Name:** Level 0
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Parent Page:** ให้ค้นหา และเลือก **Home**
   4. **Partial URL:** level-0
   5. **Page Template:** ค้นหา และเลือก **With Hybrid Navigation**
   6. **Publishing State:** ค้นหา และเลือก **Published**

<img width="613" alt="2024-01-20_17-51-19" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/85a56243-b3ac-44fe-becb-2f28dbf1bdeb">


6. กดปุ่ม New เพื่อสร้าง Web Page เพิ่มเป็นอันที่ 2
7. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามรูปด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น 
   1. **Name:** Level 1
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Parent Page:** ให้ค้นหา และเลือก **Level 0**
   4. **Partial URL:** level-1
   5. **Page Template:** ค้นหา และเลือก **With Hybrid Navigation**
   6. **Publishing State:** ค้นหา และเลือก **Published**

<img width="644" alt="2024-01-20_17-51-59" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/53bc9039-d302-4c25-b6c4-1dd45ec52f5f">


## 4. เพิ่ง Menu โดยใช้ Web Link 

โดยปกติเราจะใช้ Power Page Portal ในการสร้าง Menu และ Link ไปยัง Page ต่างๆ ที่เราสร้างไว้ แต่ในกรณีนี้เราจะใช้ Web Link Set ในการสร้าง Menu และ Link ไปยัง Page ต่างๆ ที่เราสร้างไว้

<img width="281" alt="2024-01-20_15-18-24" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/6b469777-c582-43c0-b684-0ddc56e4db9b">


1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง

<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

3. จากเมนูด้านซ้าย ให้เข้าไปที่ **Website > Web Link Set** และกดเลือก **Default** ตามรูปด้านล่าง

> Deault คือกลุ่มของ Web Link Set ที่ถูกกำหนดให้เป็นค่าเริ่มต้น และจะถูกนำไปใช้เป็น Navigation หลักของ Power Page Portal

<img width="572" alt="2024-01-20_15-41-03" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/fbb61246-8ed5-491a-9838-e1004863ded7">

4. ในส่วนของ Default Web Link set ที่เปิดขึ้นมา ให้เลือก Tab **Links** และกดปุ่ม **New Web Link** ตามรูปด้านล่าง

<img width="1181" alt="2024-01-20_15-40-33" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/f5ee772e-552c-4175-9a43-99298f97f73e">


5. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามรูปด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น 
   1. **Name:** Level 0
   2. **"Web Link Set":** ให้เลือก Default 
   3. **Publishing State:** ค้นหา และเลือก **Published**
   4. **Parent Web Link:** ไม่ใส่
   5. **Page:** ค้นหาและเลือก Level 0

<img width="588" alt="2024-01-20_17-45-08" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/77e4ccfd-a3d8-40cb-8f87-89601001276d">

6. กดปุ่ม New เพื่อสร้าง Link เพิ่มเป็นอันที่ 2
7. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามรูปด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น 
   1. **Name:** Level 1
   2. **"Web Link Set":** ให้เลือก Default 
   3. **Publishing State:** ค้นหา และเลือก **Published**
   4. **Parent Web Link:** ค้นหา และเลือก **Level 0**
   5. **Page:** ค้นหา และเลือก Level 1

<img width="553" alt="2024-01-20_17-45-18" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/fc4b7401-840a-49a0-8379-3460a4f5553c">

8. กดกลับมาที่ Power Page Portal และกดปุ่ม Sync ด้านบนขวา

<img width="579" alt="2024-01-19_15-05-44" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/18415567-5fb0-49e5-a78c-ad4cd533607c">

9.  จะสังเกตว่าส่วนของ Page > Main Navigation แสดงผลเป็นเมนูตามที่เราสร้างไว้ใน Web Link Set

<img width="334" alt="2024-01-20_18-00-02" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/99930075-d302-4d44-aa47-568ea2d3b82a">


10. ทดสอบ Preview หน้าเว็บ Level-0 จะเห็นส่วนเมนู Child Page แสดงขึ้นมา

<img width="858" alt="2024-01-20_18-10-10" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/3932a337-6fa5-4a24-8ac4-26daf25ba57e">


## 5. แสดงข้อมูล Parent Page เป็น Hybrid Navigation

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง

<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

3. จากเมนูด้านซ้าย ให้เลือก **Content > Web Template** ตามรูปด้านล่าง

<img width="214" alt="2024-01-18_14-35-34" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/0c4e482d-047f-4ee2-ad9d-f66b8ff6b8c5">

4. เลือกเปิด Web Template 'Hybrid Nav' และแทนที่โค้ดดังต่อไปนี้ และกด **Save & Close**

```html
{% extends "Layout 2 Column Wide Left" %}



{% block aside %}
  
<h2>Child pages</h2>

{% assign max_depth = 3 %}
{% assign current_depth = 0 %}
{% assign current_page = page %}

{% if current_page.children.size > 0 %}
   
    <ul>
    {% for child in current_page.children %}
        <li><a href="{{ child.url }}">{{ child.title }}</a></li>
    {% endfor %}
    </ul>
      
{% endif %}

<h2>Parent pages</h2>

{% assign current_page = page %}

{% for i in (1..max_depth) %}
    {% if current_page.parent %}
        <ul>
            <li><a href="{{ current_page.parent.url }}">{{ current_page.parent.title }}</a></li>
        </ul>
        {% assign current_page = current_page.parent %}
    {% endif %}
{% endfor %}

{% endblock %}
```

5. กดกลับมาที่ Power Page Portal และกดปุ่ม Sync ด้านบนขวา

<img width="579" alt="2024-01-19_15-05-44" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/18415567-5fb0-49e5-a78c-ad4cd533607c">

6. ทดสอบ Preview หน้าเว็บ Level-0 และ Level-1 จะเห็นเมนูส่วน Parent Page แสดงขึ้นมา

<img width="866" alt="2024-01-20_18-03-38" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/5bbc5093-0b47-438e-a76c-c82e83b4a60f">


**-- เสร็จสมบูรณ์ เย้ --**