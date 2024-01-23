
# Power Platform CLI

Power Platform CLI เป็นเครื่องมือที่ใช้ในการจัดการกับ Power Page โดยตรงผ่าน Command Line Interface (CLI) โดยสามารถใช้งานได้ทั้งบน Windows, Mac และ Linux สามารถติดตั้งได้จาก [Power Platform CLI](https://docs.microsoft.com/en-us/powerapps/developer/data-platform/powerapps-cli) 

## 1. การ login เข้าใช้งาน Power Page ผ่าน Power Platform CLI

1. เปิด Visual Studio Code
2. ไปที่ Menu > Terminal > New terminal 
3. รันคำสั่งด้านล่างเพื่อสร้าง Authentication Profile ของ Power Page
    ```bash
    pac auth create
    ```

4. Login ด้วย Username และ Password ที่ให้ไว้ในไฟล์ Excel หาก Login สำเร็จ ระบบจะแสดงข้อความ ประมาณด้านล่าง
   ```bash
    Validating connection...
    Authentication profile created
   ```


## 2. การตรวจสอบ และสลับใช้ Environment

1. กลับมาที่ Terminal ใน Visual Studio Code
2. รันคำสั่ง 
    ```bash
    pac org list
    ```

    ระบบจะแสดงรายการ Organization ที่เราสามารถเข้าใช้งานได้ คล้ายตัวอย่างด้านล่าง

    | Active Display Name | Environment ID | Environment URL |  Unique Name |
    | --- | --- | --- | --- |
    | PowerPagesDeveloper-XXXXX | XXXX-XXXX-XXXXX-XXXX |  https://XXXX.crm.dynamics.com | unqXXXXXX |

3. ให้คัดลอก Environment ID ของ Organization ที่ต้องการใช้งาน 
4. และรันคำสั่งด้านล่าง และแทนที่ `<Environment ID>` ด้วยค่า Environment ID ที่ได้มา
    ```bash
    pac org select --environment <Environment ID>
    ```

    ถ้าสำเร็จ ระบบจะแสดงข้อความประมาณด้านล่าง 

    ```bash
    Looking for environment 'XXXX-XXXX-XXXXX-XXXX'
    Selected org 'PowerPagesDeveloper-XXXXX' 'https://XXXX.crm.dynamics.com' for current authentication profile.
    ```

**-- เสร็จสมบูรณ์ เย้ --**

