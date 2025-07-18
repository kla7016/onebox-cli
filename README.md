# OneBox CLI (POC)

<p align="center">
  <img src="images/logo.png" alt="โลโก้" width="200">
</p>

OneBox CLI เป็น command-line tool ที่ออกแบบมาเพื่ออำนวนความสะดวกในการจัดการไฟล์ และการถ่ายโอนไฟล์ด้วย OneBox คู่มือนี้จะช่วยให้คุณดาวน์โหลด ติดตั้ง และใช้งาน OneBox CLI ได้อย่างมีประสิทธิภาพ

## สารบัญ
- [การติดตั้ง OneBoxCLI บน Linux](#การติดตั้ง-oneboxcli-บน-linux-ubuntu-debian-centos-mac-os)
- [การติดตั้ง OneBoxCLI บน windows](#การติดตั้ง-oneboxcli-บน-windows)
- [การล็อกอิน](#การล็อกอิน)
- [การเลือก Account](#การเลือก-account)
- [อัปโหลดไฟล์](#อัปโหลดไฟล์)
    - [อัปโหลดไฟล์โดยใช้ชื่อไฟล์ต้นฉบับ](#อัปโหลดไฟล์โดยใช้ชื่อไฟล์ต้นฉบับ)
    - [อัปโหลดไฟล์โดยเปลี่ยนชื่อไฟล์ปลายทาง](#อัปโหลดไฟล์โดยเปลี่ยนชื่อไฟล์ปลายทาง)
    - [อัปโหลดไฟล์โดยเปลี่ยนชื่อไฟล์ปลายทางโดยใช้รูปแบบ {datetime}](#อัปโหลดไฟล์โดยเปลี่ยนชื่อไฟล์ปลายทางโดยใช้รูปแบบ-datetime)
    - [วิธีตั้งค่าให้ลบไฟล์บน OneBox แบบอัตโนมัติกรณีพื้นที่จัดเก็บบน OneBox เต็ม](#วิธีตั้งค่าให้ลบไฟล์บน-OneBox-แบบอัตโนมัติกรณีพื้นที่จัดเก็บบน-OneBox-เต็ม)
    - [ให้ระบบค้นหา File ที่ถูกสร้างล่าสุดใน Folder](#ให้ระบบค้นหา-File-ที่ถูกสร้างล่าสุดใน-Folder)
    - [การกำหนด Path ที่ใช้เก็บ Chunk ไฟล์ระหว่าง Upload](#การกำหนด-Path-ที่ใช้เก็บ-Chunk-ไฟล์ระหว่าง-Upload)
- [อัปโหลดโฟลเดอร์](#อัปโหลดโฟลเดอร์)
  - [ระบุนามสกุลไฟล์ ที่ต้องการให้ระบบค้นหา](#ระบุนามสกุลไฟล์-ที่ต้องการให้ระบบค้นหา)
  - [ระบุวันที่ต้องการให้ระบบค้นหาไฟล์](#ระบุวันที่ต้องการให้ระบบค้นหาไฟล์)
  - [การกำหนด Path ที่ใช้เก็บ Chunk ไฟล์ระหว่าง Upload แบบทั้ง Folder](#การกำหนด-Path-ที่ใช้เก็บ-Chunk-ไฟล์ระหว่าง-Upload-แบบทั้ง-Folder)
- [เปิดใช้งานการเก็บ Log](#เปิดใช้งานการเก็บ-Log)
- [การตั้งค่าการแจ้งเตือน](#การตั้งค่าการแจ้งเตือน)
    - [การตั้งค่าการแจ้งเตือนสำหรับ Discord Webhook](#การตั้งค่าการแจ้งเตือนสำหรับ-Discord-Webhook)
    - [การตั้งค่าการแจ้งเตือนสำหรับ Telegram](#การตั้งค่าการแจ้งเตือนสำหรับ-Telegram)
- [การใช้งาน Crontab กับ OneBox](#การใช้งาน-Crontab-กับ-OneBox)


## การติดตั้ง OneBoxCLI บน Linux (ubuntu, debian, centos, mac os)

### 1. ดาวน์โหลดไฟล์ OneBox
```bash
sudo wget https://github.com/kla7016/onebox-cli/releases/latest/download/onebox -O /usr/local/bin/onebox
```

### 2. ให้สิทธิ์ในการรันไฟล์ OneBox
```bash
sudo chmod +x /usr/local/bin/onebox
```

## การติดตั้ง OneBoxCLI บน windows

### 1. download ไฟล์โปรแกรม onebox.exe 

[คลิกเพื่อ download onebox.exe](https://github.com/kla7016/onebox-cli/releases/latest/download/onebox.exe)

### 2. เปิดโฟลเดอร์ที่เก็บไฟล์ onebox.exe

<img src="images/setup/1_go_to_directory.png" alt="go_to_directory" width="500">

### 3. ที่แถบไดเรกทอรีด้านบน ลบ Path ออก พิมพ์ `cmd` แล้วกดปุ่ม enter

<img src="images/setup/2_type_cmd.png" alt="type_cmd" width="500">

### ตรวจสอบการติดตั้ง

โดยพิมพ์คำสั่ง `onebox version` แล้วกดปุ่ม Enter
```bash
onebox version
```
ถ้าระบบแสดงเลข version ของโปรแกรม หมายถึงระบบทำงานเป็นปกติ การติดตั้งสำเร็จ

## การล็อกอิน

สามารถเข้าสู่ระบบได้ผ่าน 2 ช่องทาง

### 1. เข้าสู่ระบบด้วย Username และ Password OneID:
```bash
onebox login
```
<img src="images/login/login-username.png" alt="login-username" width="500">

### 2. เข้าสู่ระบบด้วย OneBox Token:
```bash
onebox login-token
```

สามารถหา OneBox Token ได้จากหน้าเว็บ [https://box.one.th](https://box.one.th) หรือ [https://hosbox.id.th](https://hosbox.id.th)

โดยมีขั้นตอนดังนี้

1. หลังจากเข้าสู่ระบบ ให้ไปที่เมนู Profile อยู่มุมขวาบนของหน้าจอ

<img src="images/login/login-token-step1.png" alt="login-token-step1" width="500">

2. คลิกที่เมนู Onebox token

<img src="images/login/login-token-step2.png" alt="login-token-step2" width="300">

3. ระบบจะแสดง OneBox Token ให้คัดลอก และนำไปใช้ในการ Login โดย Token จะมีอายุ 5 นาที และใช้ Login ได้ 1 ครั้งต่อ 1 Token เท่านั้น

<img src="images/login/login-token-step3.png" alt="login-token-step3" width="500">

4. นำ Token ที่คัดลอกจากหน้าเว็บมาใส่ใน OneBox CLI เพื่อ Login

<img src="images/login/login-token.png" alt="login-token" width="500">


## การเลือก Account

หลังจาก Login กรณีบัญชีของคุณ มีทั้งบัญชีองค์กร และบัญชีส่วนบุคคล คุณจะต้องเลือกบัญชีที่ใช้ในการเก็บข้อมูล

<img src="images/login/select-account.png" alt="select-account" width="500">

กดปุ่ม Enter เพิ่มเลือก Account

<img src="images/login/choose-account.png" alt="choose-account" width="500">

คุณสามารถสลับ Account ได้ตลอดเวลาโดยใช้คำสั่ง
```bash
onebox select-account
```

## อัปโหลดไฟล์

### การใช้งานพารามิเตอร์
- `-s` หรือ `--source` คือ path ไฟล์ในเครื่องที่ต้องการอัปโหลด
- `-d` หรือ `--destination` คือ path ที่ต้องการเก็บไฟล์ใน OneBox

### อัปโหลดไฟล์โดยใช้ชื่อไฟล์ต้นฉบับ
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination
```

<img src="images/upload/upload.png" alt="upload" width="500">

### อัปโหลดไฟล์โดยเปลี่ยนชื่อไฟล์ปลายทาง
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination/new_file.txt
```

### อัปโหลดไฟล์โดยเปลี่ยนชื่อไฟล์ปลายทางโดยใช้รูปแบบ {datetime}
โดยเพิ่ม `-f` หรือ `--format`
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination/{datetime}_file.txt -f
```

### รูปแบบของ Format
- `{datetime}`: {ปี}{เดือน}{วัน}_{ชั่วโมง}{นาที}{วินาที} เช่น 20240617_134526
- `{date}`: {ปี}{เดือน}{วัน} เช่น 20240617
- `{time}`: {ชั่วโมง}{นาที}{วินาที} เช่น 134526

### อัปโหลดไฟล์โดยเปลี่ยนชื่อไฟล์ และโฟลเดอร์ปลายทางโดยใช้รูปแบบ {datetime}
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination-{date}/{time}_file.txt -f
```

### วิธีตั้งค่าให้ลบไฟล์บน OneBox แบบอัตโนมัติกรณีพื้นที่จัดเก็บบน OneBox เต็ม

ให้เพิ่มคำสั่ง `--auto-remove-files-in-folder` เข้าไปต่อท้ายในไฟล์ onebox-backup.bat

```
"C:\OneBox\onebox.exe" push -s "D:\BACKUP" -d "Test-Backup" --send-alerts --log --log-file "C:\OneBox\log" --hosxp --auto-remove-files-in-folder
```

เมื่อพื้นที่จัดเก็บไม่เพียงพอต่อการ Upload ระบบจะทำการลบไฟล์ที่เก่าที่สุดใน Folder ที่กำหนด ในตัวอย่างจะเป็น Folder ชื่อ HOSxP-Backup เพื่อให้การ Backup ทำได้ต่อเนื่อง

### ให้ระบบค้นหา File ที่ถูกสร้างล่าสุดใน Folder

เติม `--last-file` เข้าไปในคำสั่ง

```
"C:\OneBox\onebox.exe" push -s "D:\BACKUP" -d "Test-Backup" --send-alerts --log --log-file "C:\OneBox\log" --last-file
```

กรณีต้องหาค้นหาไฟล์ล่าสุด โดยกำหนดการค้นหาจากนามสกุลไฟล์

ให้เพิ่ม `--extensions ".zip,.7z"` ตัวอย่างนี้ระบบจะค้นหาเฉพาะไฟล์ .zip และ .7z เท่านั้น

```
"C:\OneBox\onebox.exe" push -s "D:\BACKUP" -d "Test-Backup" --send-alerts --log --log-file "C:\OneBox\log" --last-file --extensions ".zip,.7z"
```


### การกำหนด Path ที่ใช้เก็บ Chunk ไฟล์ระหว่าง Upload

ให้เพิ่ม `--chunk-dir "D:\OneBox\chunk-file"` สามารถเปลี่ยน path ที่ใช้จัดเก็บ chunk file ได้ตามต้องการ

```
"C:\OneBox\onebox.exe" push -s "D:\BACKUP\file.txt" -d "Test-Backup" --send-alerts --log --log-file "C:\OneBox\log" --chunk-dir "D:\OneBox\chunk-file"
```

กรณีไม่เปลี่ยน Chunk ไฟล์จะถูกจัดเก็บที่
```
C:\Users\<user>\AppData\Local\Temp
```

## อัปโหลดโฟลเดอร์

### การใช้งานพารามิเตอร์
- `-s` หรือ `--source` คือ path folder ในเครื่องที่ต้องการอัปโหลด
- `-d` หรือ `--destination` คือ path ที่ต้องการเก็บไฟล์ใน OneBox

```bash
onebox push-dir -s /path/to/source -d /path/to/destination
```

ตัวอย่างการใช้งาน

<img src="images/upload/upload-folder.png" alt="upload-folder" width="500">

### สามารถกำหนดชื่อ folder ที่ฝั่ง onebox ในรูปแบบ `{datetime}`, `{date}` หรือ `{time}` เหมือนกับการอัปโหลดไฟล์

```bash
onebox push-dir -s /path/to/source -d /path/to/destination-{datetime} -f
```

### ระบุนามสกุลไฟล์ ที่ต้องการให้ระบบค้นหา
ให้เพิ่ม `--extensions ".zip,.7z"` ตัวอย่างนี้ระบบจะค้นหาเฉพาะไฟล์ .zip และ .7z เท่านั้น

```
"C:\OneBox\onebox.exe" push-dir -s "D:\BACKUP" -d "Test-Backup" --extensions ".zip,.7z"
```

### ระบุวันที่ต้องการให้ระบบค้นหาไฟล์
ให้เพิ่ม `--date "today"` ตัวอย่างนี้ระบบจะค้นหาเฉพาะไฟล์ที่สร้างในวันนี้เท่านั้น
- ค่าที่รองรับ:
  - today
  - yesterday
  - YYYY-MM-DD เช่น 2024-05-23
  - ช่วงเวลา: YYYY-MM-DD..YYYY-MM-DD เช่น 2024-05-01..2024-05-31
```
"C:\OneBox\onebox.exe" push-dir -s "D:\BACKUP" -d "Test-Backup" --date "today"
```


### การกำหนด Path ที่ใช้เก็บ Chunk ไฟล์ระหว่าง Upload แบบทั้ง Folder
ให้เพิ่ม `--chunk-dir "D:\OneBox\chunk-file"` สามารถเปลี่ยน path ที่ใช้จัดเก็บ chunk file ได้ตามต้องการ

```
"C:\OneBox\onebox.exe" push-dir -s "D:\BACKUP" -d "Test-Backup" --send-alerts --log --log-file "C:\OneBox\log" --chunk-dir "D:\OneBox\chunk-file"
```


## เปิดใช้งานการเก็บ Log
สามารถเปิดการใช้งานการเก็บ Log โดยใช้พารามิเตอร์ต่อไปนี้:
- `--log`: เปิดการใช้งานการเก็บ Log
- `--log-file`: Path ที่ต้องการเก็บไฟล์ Log

หากไม่ได้กำหนด `--log-file` Log จะถูกจัดเก็บใน Default Folder ของแต่ละ OS:
- Linux: `/var/log/OneBoxCLI/onebox-cli.log`
- MacOS: `/Library/Logs/OneBoxCLI/onebox-cli.log\`
- Windows: `AppData\OneBoxCLI\logs\onebox-cli.log`

เปิดการใช้งาน log โดยเก็บ log ที่ Default Folder:
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination --log
```

กำหนด Path สำหรับเก็บ log เอง:
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination --log --log-file /path/to/save/log
```

กำหนด Path และชื่อไฟล์ log เอง:
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination --log --log-file /path/to/save/log/mydata.log
```

## การตั้งค่าการแจ้งเตือน
สามารถตั้งค่าให้ส่งแจ้งเตือนไปยัง Line Notify หรือ Webhook เพื่อแจ้งสถานะการ Upload File
```bash
onebox alert --set
```

`Alert ID` คือ id สำหรับอ้างอิงถึง Setting Alert แต่ละอัน ใช้สำหรับอ้างอิงตอนส่ง Alert กรณีต้องการส่งแบบเฉพาะเจาะจง และใช้อ้างอิงสำหรับการลบ Alert

การกำหนด `Alert ID` สามารถใช้ตัวหนังสือเหล่านี้ได้เท่านั้น 0-9, a-z, A-Z, - , _ 

ตัวอย่างการตั้งค่า Alert

<img src="images/alert/alert-select-new.png" alt="alert-select" width="500">

การตั้งค่า Webhook

<img src="images/alert/alert-set-webhook-new.png" alt="alert-set-webhook" width="500">

Email - กรอก Email ที่ต้องการส่งแจ้งเตือน Backup

<img src="images/alert/alert-set-email.png" alt="alert-set-email" width="500">
<br>

### การตั้งค่าการแจ้งเตือนสำหรับ Discord Webhook

#### การสร้างเซิร์ฟเวอร์และขอ Discord Webhook URL

กดเครื่องหมาย `+` สำหรับสร้างกลุ่มสำหรับแจ้งเตือน

<img src="images/alert/set-discord-1.png" alt="set-discord-1" width="500">

กด `สร้างของฉัน`

<img src="images/alert/set-discord-2.png" alt="set-discord-2" width="300">

กด `สำหรับฉันและเพื่อนๆ`

<img src="images/alert/set-discord-3.png" alt="set-discord-3" width="300">

ตั้งชื่อเซิร์ฟเวอร์ แล้วกด `สร้าง` แล้วกด `แก้ไขช่อง`

<img src="images/alert/set-discord-4.png" alt="set-discord-4" width="300">

คลิกขวาช่องข้อความที่ต้องการแจ้งเตือน เช่น `#ทั่วไป` แล้วกด `แก้ไขช่อง`

<img src="images/alert/set-discord-5.png" alt="set-discord-5" width="300">

กด `การรวม` และกด `สร้าง Webhook`

<img src="images/alert/set-discord-6.png" alt="set-discord-6" width="500">

กดที่ตัว bot เพิ่อแสดงรายละเอียด

<img src="images/alert/set-discord-7.png" alt="set-discord-7" width="500">

กด `คัดลอก URL เว็บฮุก` เพื่อนำไปใช้ตั้งค่าการแจ้งเตือน โดย Discord Webhook URL จะขึ้นต้นด้วย `https://discordapp.com/api/webhooks` หรือ `https://discord.com/api/webhooks`

<img src="images/alert/set-discord-8.png" alt="set-discord-8" width="500">

กรอก URL Discord Webhook ที่ต้องการส่งแจ้งเตือน Backup

<img src="images/alert/alert-set-discord.png" alt="alert-set-discord" width="500">

<br>

### การตั้งค่าการแจ้งเตือนสำหรับ Telegram

#### การสร้างกลุ่มและขอ Chat ID

เปิดโปรไฟล์แล้วกด `New Group` สำหรับสร้างกลุ่มสำหรับแจ้งเตือน

<img src="images/alert/set-telegram-1.png" alt="set-telegram-1" width="300">

ตั้งชื่อกลุ่มสำหรับการ backup แล้วกด `Next`

<img src="images/alert/set-telegram-2.png" alt="set-telegram-2" width="300">

เพิ่ม bot Hos Box Notify โดยพิมพ์ `@HosBox_notify_bot` กดที่ชื่อ bot แล้วกด `Create`

<img src="images/alert/set-telegram-3.png" alt="set-telegram-3" width="300">

เมื่อกลุ่มถูกสร้างให้พิมพ์ `/id` เพื่อแสดง Chat ID สำหรับนำไปใช้ตั้งค่าการแจ้งเตือน

<img src="images/alert/set-telegram-4.png" alt="set-telegram-4" width="300">

กรอก Chat ID ที่ต้องการส่งแจ้งเตือน Backup

<img src="images/alert/alert-set-telegram.png" alt="alert-set-telegram" width="500">

<br>

สามารถดูการตั้งค่าแจ้งเตือนทั้งหมดโดยใช้คำสั่ง
```bash
onebox alert --list
```

คำสั่งลบการตั้งค่า `--rm` ตามด้วย `alert_id`
```bash
onebox alert --rm {alert_id}
```

การใช้งานเมื่อต้องการส่งแจ้งเตือน โดยจะส่งแจ้งเตือนไปยัง server ทั้งหมดที่ตั้งค่าไว้
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination --send-alerts
```

กรณีมีการตั้งค่าแจ้งเตือนไว้หลายอัน สามารถเลือกส่งแจ้งเตือนแบบเฉพาะเจาะจงโดยใช้ `alert_id` เป็นตัวกำหนด
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination --send-alerts --alert-id alertId01,alertId02
```

### ตัวอย่าง Body Webhook

กรณี Upload สำเร็จ
```json
{
  "status": "success",
  "message": "Upload successful",
  "file_name": "test-pdf.pdf",
  "file_size": "1.93 MB",
  "file_size_byte": 2019837,
  "source": "/Users/korkla/Desktop/TestSyncFile/test-pdf.pdf",
  "destination": "upload/chunck",
  "start_time": "2024-06-24T08:35:14+07:00",
  "end_time": "2024-06-24T08:35:18+07:00",
  "duration": "4.001624584s",
  "transaction_id": "4cb39305903ed94ca6b42d97cad6c547",
  "account_name": "ทดสอบ ระบบ",
  "account_type": "Personal",
  "account_id": "123456708256",
  "total_storage": "500.00 GB",
  "used_storage": "52.76 GB",
  "remaining_storage": "447.24 GB",
  "total_storage_byte": 536870912000,
  "used_storage_byte": 56652495385,
  "remaining_storage_byte": 480218416615
}
```

กรณี Upload ไม่สำเร็จ
```json
{
  "status": "failed",
  "message": "Your space not enough",
  "file_name": "testfile_4GB.zip",
  "file_size": "4.00 GB",
  "file_size_byte": 4294967296,
  "source": "/Users/korkla/Desktop/TestBigFile/file01/testfile_4GB.zip",
  "destination": "upload/chunck",
  "start_time": "2024-06-24T09:34:25+07:00",
  "end_time": "2024-06-24T09:34:26+07:00",
  "duration": "1.067305166s",
  "transaction_id": "",
  "account_name": "ทดสอบ ระบบ",
  "account_type": "Personal",
  "account_id": "123456708256",
  "total_storage": "1.00 GB",
  "used_storage": "1.93 MB",
  "remaining_storage": "1022.07 MB",
  "total_storage_byte": 1073741824,
  "used_storage_byte": 2019837,
  "remaining_storage_byte": 1071721987
}
```

### ตัวอย่าง Alert ที่ส่งผ่าน Email

กรณี Upload สำเร็จ

<img src="images/alert/email-success.png" alt="email-success" width="300">

กรณี Upload ไม่สำเร็จ

<img src="images/alert/email-failed.png" alt="email-failed" width="300">

### ตัวอย่าง Alert ที่ส่งผ่าน Discord Webhook

กรณี Upload สำเร็จ

<img src="images/alert/discord-success.png" alt="discord-success" width="200">

กรณี Upload ไม่สำเร็จ

<img src="images/alert/discord-failed.png" alt="discord-failed" width="200">

### ตัวอย่าง Alert ที่ส่งผ่าน Telegram

กรณี Upload สำเร็จ

<img src="images/alert/telegram-success.png" alt="telegram-success" width="300">

กรณี Upload ไม่สำเร็จ

<img src="images/alert/telegram-failed.png" alt="telegram-failed" width="300">

## การใช้งาน Crontab กับ OneBox

### ตัวอย่างตั้งเวลาให้สำรองข้อมูลทุกเที่ยงคืนของทุกวัน
1. เปิดไฟล์ crontab ด้วยคำสั่ง:

```bash
crontab -e
```

2. เพิ่มบรรทัดนี้เข้าไปในไฟล์ crontab:

```bash
0 0 * * * /usr/local/bin/onebox push -s /path/to/source/folder -d /path/to/destination/folder --log --log-file /path/to/save/log/backup.log --send-alerts
```

บรรทัดนี้จะทำให้ระบบสำรองข้อมูลทุกเที่ยงคืนของทุกวันโดยอัตโนมัติ

### สรุปคำสั่งที่ใช้:
- `crontab -e`: เปิดไฟล์ crontab เพื่อแก้ไข
- `0 0 * * *`: ตั้งเวลาให้ทำงานทุกเที่ยงคืนของทุกวัน
- `/usr/local/bin/onebox push -s /path/to/source/folder -d /path/to/destination/folder --log --log-file /path/to/save/log/backup.log --send-alerts`: คำสั่งในการอัปโหลดข้อมูลพร้อมกับเก็บ log และส่งแจ้งเตือน