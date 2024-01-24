
# Code Component Fundamental

## 1. สร้างโปรเจค Code Component ด้วย Power Platform CLI

1. จากโฟลเดอร์ example1 ให้คลิกขวาบน Explorer View และเลือกคำสั่ง New Folder และตั้งชื่อว่า sliderInput

2. รันคำสั่งด้านล่างเพื่อสร้าง Template ของโปรเจค SliderInputControl
    ```bash
    pac pcf init --namespace SampleNamespace --name SliderInputControl --template field --run-npm-install
    ```

3. หลังจากสร้างเสร็จ ให้เปิดโฟลเดอร์ sliderInput เพื่อดูไฟล์ภายใน 
    

4. รันคำสั่งด้านล่างใน Terminal เพื่อทดสอบรัน component

    ```bash
    npm start
    ```

5.


7. จาก Terminal กดปุ่มลัด Ctrl + C เพื่อหยุดการทำงานของ npm start

## 2. แก้ไข Manifest ของ Code Component

Manifest มักจะถูกใช้ในการกำหนดค่าพื้นฐานของ Code Component ที่ระบบ Power Platform จะนำไปใช้

```xml
<?xml version="1.0" encoding="utf-8" ?>
<manifest>
   <control namespace="SampleNamespace"
      constructor="SliderInputControl"
      version="0.0.1"
      display-name-key="SliderInputControl"
      description-key="SliderInputControl description"
      control-type="standard">

      <!-- กำหนด type-group เพื่อเป็นค่า attribute สำหรับ map กับข้อมูลของ Power Platform -->
      <type-group name="numbers">
         <type>Whole.None</type>
         <type>Currency</type>
         <type>FP</type>
         <type>Decimal</type>
      </type-group>

        <!-- แก้ไขค่า property ด้วยรายละเอียดต่อไปนี้ -->
      <property name="controlValue"
         display-name-key="Control Value"
         description-key="Control value description."
         of-type-group="numbers"
         usage="bound"
         required="true" />

      <resources>
         <code path="index.ts"
            order="1" />

        <!-- กำหนดส่วนของ resource ให้สามารถอ้างอิงไฟล์ css ที่อยู่ใน component ได้ -->
         <css path="css/SliderInputControl.css"
            order="1" />
      </resources>
   </control>
</manifest>
```

## 3. สร้าง Manifest ในรูปแบบ Typescript 

รันคำสั่งด้านล่างเพื่อสร้างไฟล์ manifest ในรูปแบบ Typescript

```bash
npm run refreshTypes
```

หากสำเร็จ ข้อความ log จะแสดงข้อความจบประมาณดังรูป

```bash
[2:03:14 PM] [refreshTypes]  Generating design types...
[2:03:14 PM] [refreshTypes]  Succeeded
```