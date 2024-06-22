# OneBox CLI

<p align="center">
  <img src="images/logo.png" alt="โลโก้" width="200">
</p>

OneBox CLI เป็น command-line tool ที่ออกแบบมาเพื่ออำนวนความสะดวกในการจัดการไฟล์ และการถ่ายโอนไฟล์ด้วย OneBox คู่มือนี้จะช่วยให้คุณดาวน์โหลด ติดตั้ง และใช้งาน OneBox CLI ได้อย่างมีประสิทธิภาพ

## ดาวน์โหลดและติดตั้ง OneBox

### ดาวน์โหลดไฟล์ OneBox
```bash
sudo wget https://github.com/kla7016/onebox-cli/releases/latest/download/onebox -O /usr/local/bin/onebox
```

### ให้สิทธิ์ในการรันไฟล์ OneBox
```bash
sudo chmod +x /usr/local/bin/onebox
```

### ตรวจสอบการติดตั้ง
```bash
onebox version
```

## การล็อกอิน
ใช้คำสั่งต่อไปนี้เพื่อเข้าสู่ระบบด้วย Username และ Password ของคุณ:
```bash
onebox login
```
กรณีมีบัญชีองค์กร คุณจะต้องเลือกบัญชีที่ใช้ในการเก็บข้อมูลระหว่างบัญชีส่วนบุคคลและบัญชีองค์กร

## อัปโหลดไฟล์

### การใช้งานพารามิเตอร์
- `-s` หรือ `--source` คือ path ในเครื่องที่ต้องการอัปโหลด
- `-d` หรือ `--destination` คือ path ที่ต้องการเก็บไฟล์ใน OneBox

### อัปโหลดไฟล์โดยใช้ชื่อไฟล์ต้นฉบับ
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination
```

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

## การใช้งาน Crontab กับ OneBox

### ตัวอย่างตั้งเวลาให้สำรองข้อมูลทุกเที่ยงคืนของทุกวัน
1. เปิดไฟล์ crontab ด้วยคำสั่ง:

```bash
crontab -e
```

2. เพิ่มบรรทัดนี้เข้าไปในไฟล์ crontab:

```bash
0 0 * * * /usr/local/bin/onebox push -s /path/to/source/folder -d /path/to/destination/folder --log --log-file /path/to/save/log/backup.log
```

บรรทัดนี้จะทำให้ระบบสำรองข้อมูลทุกเที่ยงคืนของทุกวันโดยอัตโนมัติ

### สรุปคำสั่งที่ใช้:
- `crontab -e`: เปิดไฟล์ crontab เพื่อแก้ไข
- `0 0 * * *`: ตั้งเวลาให้ทำงานทุกเที่ยงคืนของทุกวัน
- `/usr/local/bin/onebox push -s /path/to/source/folder -d /path/to/destination/folder --log --log-file /path/to/save/log/backup.log`: คำสั่งในการสำรองข้อมูลพร้อมกับเก็บ log