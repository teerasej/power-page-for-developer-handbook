
# Power Platform CLI

Power Platform CLI เป็นเครื่องมือที่ใช้ในการจัดการกับ Power Page โดยตรงผ่าน Command Line Interface (CLI) โดยสามารถใช้งานได้ทั้งบน Windows, Mac และ Linux สามารถติดตั้งได้จาก [Power Platform CLI](https://docs.microsoft.com/en-us/powerapps/developer/data-platform/powerapps-cli) 

## การ login เข้าใช้งาน Power Page ผ่าน Power Platform CLI

## การเช็ค Organization Profile

รันคำสั่ง 

```bash
pac org list
```

จะแสดงรายการ Organization ที่เราสามารถเข้าใช้งานได้

## 1. การแสดงรายการ Power Page Website ทั้งหมด

รันคำสั่ง 

```bash
pac powerpage list
```

จะแสดงรายการ Power Page Website ทั้งหมดที่เราสามารถเข้าใช้งานได้

> ในที่นี้ให้ทำการ copy websiteId ที่ต้องการจะดึงไฟล์โปรเจคมาใช้งานเอาไว้

## 2. การดึงไฟล์โปรเจค Power Page Website จาก Power Platform 

1. เปิดโปรแกรม Visual Studio Code 
2. เปิด `C:\Project\PowerPageForDev\Lab01` ขึ้นมาในโปรแกรม Visual Studio Code
3. และเปิด Terminal ขึ้นมา

รันคำสั่งด้านล่าง เพื่อดึงไฟล์โปรเจค Power Page Website จาก Power Platform มาใช้งาน

- ให้แทนที่ [id] ด้วย websiteId ที่ copy มาจากขั้นตอนที่แล้ว

```bash
pac powerpages download --path . --modelVersion 2 --webSiteId [id]
```

เช็คไฟล์โปรเจค Power Page Website ที่ดึงมาจาก Power Platform ว่ามีอะไรบ้าง

## 3. การแก้ไข Power Page Website ใน Visual Studio Code

จากโฟลเดอร์โปรเจค Power Page Website ที่ดึงมาจาก Power Platform มาใช้งาน ให้ทำการแก้ไขไฟล์ `web-pages/home/content-pages/Home.en-US.webpage.copy.html` ตามคำสั่งด้านล่าง

```html
<!-- จากบรรทัดที่ 5 -->
<h1>Create an engaging headline, welcome, or call to action</h1>
```

เปลี่ยนเป็น

```html
<!-- จากบรรทัดที่ 5 -->
<h1>Hello World</h1>
```

## 4. การอัพโหลดไฟล์โปรเจค Power Page Website ที่แก้ไขแล้ว กลับไปที่ Power Platform

รันคำสั่งด้านล่าง ใน Terminal เพื่ออัพโหลดไฟล์โปรเจค Power Page Website ที่แก้ไขแล้ว กลับไปที่ Power Platform

- ให้แทนที่ [ชื่อ directory folder ของโปรเจค] ด้วยชื่อโฟลเดอร์โปรเจคที่เราต้องการจะอัพโหลดกลับไปที่ Power Platform

```bash
pac powerpages upload --modelVersion 2 --path "[ชื่อ directory folder ของโปรเจค]" 
```

## 5. การเปิดดู Power Page Website ที่แก้ไขแล้ว ใน Power Platform


