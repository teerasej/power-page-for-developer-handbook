
# Fetching Power Page Project

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



