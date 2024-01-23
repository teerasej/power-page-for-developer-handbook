
# Fetching Power Page Project


## 1. แสดงรายการของ Website ใน Environment 

1. กลับมาที่ Terminal ใน Visual Studio Code
2. รันคำสั่งด้านล่างใน Terminal 
    ```bash
    pac powerpages list
    ```
    ระบบจะแสดงรายการ Website ที่เราสามารถเข้าใช้งานได้ คล้ายตัวอย่างด้านล่าง

    ```bash
    Index      Website Id                  Friendly Name                                 
    [1]        XXXX-XXXX-XXXX-XXXX-XXXX    Site 1 - site-XXXXX  
    ```

3. ให้เราคัดลอก Website Id เอาไว้

## 2. ดาวน์โหลด Source code ของ Power Page 

1. กลับมาที่ Terminal ใน Visual Studio Code
2. รันคำสั่งด้านล่างใน Terminal โดยให้แทนที่ `<Website ID>` ด้วยค่า Website ID ที่ได้มา
    ```bash
    pac powerpages download --path . --modelVersion 2 --webSiteId <Website ID> 
    ```
    
    ระบบจะดาวน์โหลด Source code ของ Power Page ลงในโฟลเดอร์ปัจจุบันที่เราอยู่ใน Terminal

3. ตรวจสอบโครงสร้าง และไฟล์ที่ได้มาจาก Power Page

**-- เสร็จสมบูรณ์ เย้ --**

