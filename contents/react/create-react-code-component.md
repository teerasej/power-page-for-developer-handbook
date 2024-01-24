
# การสร้าง React Code component

1. เปิดโปรแกรม Visual Studio Code 
2. เช็คว่าเราได้เปิดโฟลเดอร์ **example1** (c:\Users\student\Desktop\example1) ขึ้นมาแล้ว
3. คลิกขวาในส่วนของ Explorer view ในโปรแกรม Visual Studio Code และเลือกคำสั่ง **New folder**
4. ตั้งชื่อโฟลเดอร์ว่า **GreetingComponent** ขึ้นมา
5. คลิกว่าที่โฟลเดอร์ **GreetingComponent** และเลือกคำสั่ง Open in new terminal 
6. รันคำสั่งด้านล่าง เพื่อสร้างโปรเจค Code Component ด้วย Power Platform CLI
    ```bash
    pac pcf init --namespace MyCompanyPCFComponents --name Greeting --template field --framework react --run-npm-install
    ```
    - `--namespace`  กำหนดชื่อกลุ่ม namespace ของ component ที่จะสร้าง
    - `--name` กำหนดชื่อของ component ที่จะสร้าง
    - `--template` กำหนด template ของ component ที่จะสร้าง ในที่นี้เป็น field คือ component ที่จะใช้ในการแสดงผล
    - `--framework` กำหนด framework ที่จะใช้ในการสร้าง component ในที่นี้เป็น react
    - `--run-npm-install` กำหนดให้รันคำสั่ง npm install ให้อัตโนมัติเมื่อสร้าง component เสร็จ
7. หลังจากสร้างเสร็จ ให้เปิดโฟลเดอร์ **GreetingComponent** เพื่อดูไฟล์ภายใน (ตัวโปรเจคจะมีรายละเอียดคล้ายที่เห็นในภาพด้านล่าง)


    <img width="325" alt="2024-01-24_20-47-35" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/85eeb8b5-724a-4ad6-9dc5-78cd76079aae">

## 2. การรันทดสอบ Code component

1. รันคำสั่งด้านล่างใน Terminal เพื่อทดสอบรัน component
    ```bash
    npm start
    ```
2.  ถ้าเป็นการรันครั้งแรก จะมี pop up เพื่อขอรันระบบ Node.js ให้กด Allow Access 
<img width="547" alt="2024-01-24_20-22-32" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/b991cc03-1013-46dc-94b6-63199486bfa9">

3. ถ้าการรันสำเร็จ จะเห็นเว็บเบราเซอร์เปิดขึ้นมาเพื่อพรีวิวหน้าตาของ component (คล้ายในภาพด้านล่าง)
<img width="851" alt="2024-01-24_20-48-04" src="https://github.com/teerasej/power-page-for-developer-handbook/assets/85179/6de85080-238c-4a1e-82cd-d8b7e7f39eee">

## 2. การสร้าง Package ของ Code Component เป็น Solution

1. คลิกขวาที่โฟลเดอร์ **GreetingComponent** สร้าง folder `solutionGreeting`
2. คลิกขวาที่โฟลเดอร์ `solutionGreeting` และเลือกคำสั่ง **Open in new terminal**
3. รันคำสั่งด้านล่าง เพื่อสร้าง Solution ของ Code Component ด้วย Power Platform CLI โดยแทนค่า `<publisher name>` และ `<prefix>` ด้วยข้อมูลที่ต้องการ
   
    ```bash
    pac solution init --publisher-name <publisher name> --publisher-prefix <prefix>
    ```
   เช่น
   ```bash
    pac solution init --publisher-name DevTeam --publisher-prefix dtcp
    ```

    ถ้าสำเร็จจะแสดงข้อความประมาณด้านล่าง ที่บ่งบอกว่าสร้าง Solution สำเร็จแล้ว 

    ```bash
    Dataverse solution project with name 'solutionGreeting' created successfully in: 'C:\Users\student\Desktop\example1\GreetingComponent\solutionGreeting'
    Dataverse solution files were successfully created for this project in the sub-directory Other, using solution name solutionGreeting, publisher name DevTeam, and customization prefix dtcp.
    Please verify the publisher information and solution name found in the Solution.xml file.
    ```

4. กลับมาที่ Terminal รันคำสั่งด้านล่าง เพื่อเพิ่ม Code Component Project ลงใน Solution ที่สร้างขึ้นมา

    ```bash
    pac solution add-reference --path ../   
    ```

5. รันคำสั่งด้านล่าง เพื่อ build solution เป็นไฟล์ zip สำหรับนำไปใช้งาน

    ```bash
    msbuild /t:build /restore
    ```
6. การรันครั้งต่อไป สามารถรันแค่คำสั่งด้านล่างได้ ไม่ต้องใส่ `/restore`
    ```bash
    msbuild /t:build
    ```

7. จะได้ไฟล์ zip ในโฟลเดอร์ `solutionGreeting\bin\Debug` ที่สามารถนำไปใช้งานได้

## 3. Publish the code component

1. ใน Power Platform Portal กดเปิด Solution
2. กดปุ่ม Import Solution 
3. เลือกไฟล์ Solution ที่ต้องการนำเข้า และกด next
4. ตรวจสอบข้อมูลของ Solution และกด Import
5. รอจนการ import เสร็จสมบูรณ์
6. เข้าไปดู Code Component ที่นำเข้ามาใหม่ และสังเกตชื่อของ Code Component เราจะนำส่วนนี้ไปอ้างอิงใช้งานต่อ

## 4. การเรียกใช้งาน Code Component ใน Power Page

1. ใน Power Page Portal ให้เลือกเปิด Power Page Management จาก
2. เปิดเมนูด้านซ้ายมือ และเปิด Content > Web Template 
3. สร้าง Web Template ใหม่ โดยใช้ข้อมูลดังนี้
    - Name: `Test Component`
    - Website: เลือกเว็บไซต์ที่ต้องการใช้งาน
    - Source: 

    ```html
    {% codecomponent name: dtcp_MyCompanyPCFComponents.Greeting %}
    ```
    สังเกตว่า ชื่อของ Component จะต้องเป็นชื่อที่ได้จากการสร้าง Solution ข้างต้น และต้องมี prefix ของ publisher ด้วย
4. นำ Web Template ที่สร้างขึ้นมา ไปใช้งานใน Page Template 
5. ทดสอบแสดงผลการทำงาน โดยการสร้าง Web Page จาก Page Template และ Preview

**-- เสร็จสมบูรณ์ --**