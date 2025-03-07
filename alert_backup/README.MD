# การตั้งค่า Notify OneBox CLI (เวอร์ชั่น 1.2.2 ขึ้นไป)

## 1. ดาวน์โหลดไฟล์โปรแกรมเวอร์ชั่นล่าสุด

ดาวน์โหลดไฟล์ OneBox สำหรับ Windows

[คลิกเพื่อ download สำหรับ Windows](https://github.com/kla7016/onebox-cli/releases/latest/download/onebox.exe)

ดาวน์โหลดไฟล์ OneBox สำหรับ Linux
```bash
sudo wget https://github.com/kla7016/onebox-cli/releases/latest/download/onebox -O /usr/local/bin/onebox
```

ให้สิทธิ์ในการรันไฟล์ OneBox สำหรับ Linux
```bash
sudo chmod +x /usr/local/bin/onebox
```



## 2. เปิดโฟลเดอร์ที่เก็บไฟล์ onebox.exe เดิม

<img src="images/1_folder_program.png" alt="folder_program" width="500">

## 3. ลบไฟล์โปรแกรมเดิม แล้วแทนที่ด้วยโปรแกรมเวอร์ชั่นล่าสุด

<img src="images/2_move_prgram.png" alt="move_prgram" width="500">

## 4.เปิด command prompt และตรวจสอบเวอร์ชั่นโปรแกรม

```bash
onebox version
```
โปรแกรมต้อง version เท่ากับหรือมากกว่า 1.2.2

<img src="images/3_onebox_version.png" alt="onebox_version" width="500">

## 5. ตรวจสอบการตั้งค่า Notify
### 5.1 พิมพ์คำสั่งสำหรับตรวจสอบการตั้งค่า Notify ทั้งหมด
```bash
onebox alert --list
```
ระบบจะแสดง Notify ที่เราตั้งค่าทั้งหมด

<img src="images/4_onebox_alert_list.png" alt="alert_list" width="500"> <br>

### 5.2 ลบ Notify ประเภท line-notify ด้วย Alert ID (หากมี)

<img src="images/5_remove_alert.png" alt="remove_alert" width="500">

### 5.3 พิมพ์คำสั่งสำหรับตั้งค่า Notify

```bash
onebox alert --set
```
<br>
Notify ที่เพิ่มมาจะมี Email, Discord Webhook และ Telegram
<br>
<img src="images/6_alert_set.png" alt="alert_set" width="500">
<br><br>
Email - กรอก Email ที่ต้องการส่งแจ้งเตือน Backup
<br>
<img src="images/6_alert_set_email.png" alt="alert_set_email" width="500">
<br><br>
Discord Webhook - กรอก URL Discord Webhook ที่ต้องการส่งแจ้งเตือน Backup

<img src="images/6_alert_set_discord.png" alt="alert_set_discord" width="500">

สามารถตรวจสอบ URL Discord Webhook ผ่าน [คู่มือการตั้งค่าการแจ้งเตือนสำหรับ Discord Webhook](https://github.com/kla7016/onebox-cli?tab=readme-ov-file#%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%81%E0%B8%88%E0%B9%89%E0%B8%87%E0%B9%80%E0%B8%95%E0%B8%B7%E0%B8%AD%E0%B8%99%E0%B8%AA%E0%B8%B3%E0%B8%AB%E0%B8%A3%E0%B8%B1%E0%B8%9A-Discord-Webhook)

<br>
Telegram - กรอก Chat ID ที่ต้องการส่งแจ้งเตือน Backup<br>
<img src="images/6_alert_set_telegram.png" alt="get_token_4" width="500">

สามารถตรวจสอบ Chat ID ผ่าน [คู่มือการตั้งค่าการแจ้งเตือนสำหรับ Telegram](https://github.com/kla7016/onebox-cli?tab=readme-ov-file#%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%81%E0%B8%88%E0%B9%89%E0%B8%87%E0%B9%80%E0%B8%95%E0%B8%B7%E0%B8%AD%E0%B8%99%E0%B8%AA%E0%B8%B3%E0%B8%AB%E0%B8%A3%E0%B8%B1%E0%B8%9A-Telegram)


### 5.4 พิมพ์คำสั่งสำหรับตรวจสอบการตั้งค่า Notify ทั้งหมดอีกครั้ง
```bash
onebox alert --list
```

<img src="images/7_alert_list.png" alt="7_alert_list" width="500">

หากข้อมูลถูกต้องแล้วถือว่าการตั้งค่าการแจ้งเตือนเสร็จสิ้น