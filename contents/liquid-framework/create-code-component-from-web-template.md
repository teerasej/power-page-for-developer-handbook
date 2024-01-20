
# การสร้าง Code Component จาก Web Template

## 1. สร้าง Web Template ใหม่

1. เปิด Power Page https://make.powerpages.microsoft.com/
2. จากตัวเลือก Website ให้เลือก (...) และเลือก **Power Page Management** ตามรูปด้านล่าง

<img width="902" alt="2024-01-18_14-33-16" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/68cb3fb7-e7ee-4b3d-bf08-c7cee47a6851">

3. จากเมนูด้านซ้าย ให้เลือก **Content > Web Template** ตามรูปด้านล่าง

<img width="214" alt="2024-01-18_14-35-34" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/0c4e482d-047f-4ee2-ad9d-f66b8ff6b8c5">

4. จากนั้นในเมนูด้านบนให้เลือก **New** ตามรูปด้านล่าง

<img width="441" alt="2024-01-18_14-36-18" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/a8f7a5db-f972-4bbb-9e8e-f1db6b9d1357">

## 2. สร้าง Code Component จาก Web Template

1. ให้กรอกข้อมูลต่างๆ ในส่วน **General** ตามด้านล่างดังนี้ และกดปุ่ม **Save & Close** เมื่อเสร็จสิ้น
   1. **Name:**  Greeting User
   2. **Website:** ให้เลือก Website ที่เราสร้างไว้
   3. **Source:** 
  
    ```html
    
    {% if user %}
        <p>Welcome, {{ user.fullname }}!</p>
    {% else %}
        <p>Welcome, Guest!</p>
    {% endif %}

    {% manifest %} 
        { 
        "type": "Functional", 
        "displayName": "Greeting User", 
        "description": "greeting user, if not greeting guest", 
        "params": [] 
        } 
    {% endmanifest %} 

    ```

## 3. วิธีเลือกใช้งาน Page Template ใน Power Page Portal

1. กลับมาที่หน้า Home Page ของ Power Page https://make.powerpages.microsoft.com/
2. จากเว็บไซต์ที่เราเข้าไปสร้าง Web Template ไว้ตอนแรก ให้กดปุ่ม Edit ตามรูปด้านล่าง

<img width="595" alt="2024-01-18_14-39-14" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1ce41cc5-d7f8-4350-a21d-348960006cc0">

3. จากเมนู Page ให้กดเลือก **Edit code** ทางด้านบนขวา ตามรูปด้านล่าง

<img width="1187" alt="2024-01-20_12-29-40" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/ed442f61-fc56-47f6-b895-2c0f9b049dc4">

4. กดปุ่ม **Open Visualt Studio Code** ตามรูปด้านล่าง

<img width="516" alt="2024-01-20_12-36-03" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/99ba723f-0297-4c1d-9315-5f2b9dae6e71">

5. จะเป็นการเปิด tab ใหม่ขึ้นมาเป็น Visual Studio Code โดยอัตโนมัติ และจะเปิดโฟลเดอร์ที่เก็บไฟล์ของ Web Template ขึ้นมาให้เราดังรูปด้านล่าง ให้สังเกตว่า เราอยู่ที่ **Site 1 > web-pages > Home > Home.en-US.webpage.html**

<img width="434" alt="2024-01-20_13-05-01" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/06387573-33c2-42f1-94f2-a9efa1492842">

6. เพิ่มโค้ดด้านล่างลงในส่วนของ Section แรก ประมาณบรรทัดที่ 8 ตามรูปด้านล่าง และ**บันทึกไฟล์**

```html
 {% include 'Greeting User' %}
```
<img width="511" alt="2024-01-20_13-41-45" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/d999335e-528b-4e59-b2fb-5b612ff66c52">


7. กลับมาที่หน้าจอ Power Page Portal ให้กดปุ่ม **Sync** บนหน้าต่างกลางหน้าเว็บ ตามรูปด้านล่าง

<img width="556" alt="2024-01-20_13-10-47" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/1de14fde-93a9-43ee-bb25-4ad1affcbde4">

8. จะสังเกตเห็นส่วนที่เราเพิ่มเข้ามา เรียกว่า Custom Component ดังรูปด้านล่าง

<img width="393" alt="2024-01-20_13-44-34" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/e23b2b73-6b6d-44b6-90f4-2383f0512e46">

9. ถ้าคลิกเลือก Custom Component จะสังเกตเห็นว่าเราสามารถกำหนดค่า parameter ต่างๆ ได้ แต่ตอนนี้ตัว component ไม่มีการรับค่าอะไรเลย เลยเห็นเป็นดังรูปด้านล่าง

> ⚠️ เราจะไม่กดปุ่ม **Open Power Pages Management** ในขั้นตอนนี้ เพราะถึงแม้ว่าเราจะกดปุ่มนี้ได้ แต่การเปิด Web Template ขึ้นมา จะมี bug ที่ทำให้ Source code เดิมถูกล้างออกไป

<img width="484" alt="2024-01-20_13-45-25" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/c1756952-370d-40f4-b6d7-2b2c639c4388">

10. ตอนนี้สามารถทดสอบ Preview ได้เลย โดยกดปุ่ม **Preview** ด้านบนขวาของหน้าเว็บ

## เพิ่ม Parameter ให้กับ Code Component

1. กลับมาที่หน้าเว็บ Visual Studio Code ให้ทำการเปิดไฟล์ **web-templates/Greeting User.html** 

- สังเกตว่านี่คือชื่อเดียวกับ Web template ที่เราทำไว้ใน Power Page Portal

<img width="291" alt="2024-01-20_14-10-12" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/7939ec2e-aa99-4b11-94c7-7015fb882e89">

2. แก้ไขโค้ดใน template เป็นแบบด้านล่าง

- สังเกตว่า เราเพิ่ม parameter 2 ตัว คือ **greetingMessage** และ **emoji** เข้ามาในส่วนของ manifest
- และในส่วนของ HTML เราก็ใช้ parameter ที่เราเพิ่มเข้ามาในส่วนของ manifest ในการแสดงผล โดยมีการกำหนดค่า default ให้กับ parameter ด้วย ผ่านการใช้ Liquid filter ชื่อว่า **default**  

```html

{% if user %}
    <p>{{ greetingMessage | default: 'Welcome' }}, {{ user.fullname }}{{ emoji | default: '' }}!</p>
{% else %}
    <p>{{ greetingMessage | default: 'Welcome' }}, Guest{{ emoji | default: '' }}!</p>
{% endif %}


{% manifest %} 
    { 
        "type": "Functional", 
        "displayName": "Greeting User", 
        "description": "greeting user, if not greeting guest", 
        "params": [
            {
                "id": "greetingMessage",
                "displayName": "Greeting Message",
                "description": "word in front of user's name"
            },
            {
                "id": "emoji",
                "displayName": "Emoji",
                "description": "Any emoji at the end of greeting message"
            }
        ] 
    } 
{% endmanifest %} 
```

3. เสร็จแล้วอย่าลืม Save
4. กลับมาที่หน้าจอ Power Page Portal ให้กดปุ่ม **Sync** ด้านบนขวาของหน้าเว็บ

<img width="579" alt="2024-01-19_15-05-44" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/8f0b87f1-30f6-4a49-9c81-dea8d01ba6e1">


5. ทดสอบกดเลือก Custom Component ใหม่อีกครั้ง จะสังเกตว่าเราสามารถกำหนดค่า parameter ต่างๆ ได้ โดย parameter ที่เราเพิ่มเข้ามา จะเป็นตัวเลือกใหม่ที่เราสามารถกำหนดค่าได้ ดังรูปด้านล่าง

> ⚠️ ถ้ายังไม่แสดงให้กลับไปดูโค้ดส่วน Manifest หรือกด sync อีกครั้ง

<img width="489" alt="2024-01-20_14-19-06" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/5b440ab7-d46a-4901-b8ca-dc123c3b58c9">

6. ทดสอบใส่ค่า Greeting Message และ Emoji แล้วกดปุ่ม **Preview** ด้านบนขวาของหน้าเว็บ ควรได้ผลลัพธ์ใกล้เคียงด้านล่าง 

<img width="638" alt="2024-01-20_14-22-54" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/02e6adbe-6ba7-4ee4-bb97-8862f35f7f40">

**-- เสร็จสมบูรณ์ เย้ --**

## เพิ่มเติม

https://learn.microsoft.com/en-us/power-pages/configure/web-templates-as-components