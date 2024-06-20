
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
onebox push -s /path/to/source/file.txt -d upload/data
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

### อัปโหลดไฟล์โดยเปลี่ยนชื่อไฟล์และโฟลเดอร์ปลายทางโดยใช้รูปแบบ {datetime}
```bash
onebox push -s /path/to/source/file.txt -d /path/to/destination-{date}/{time}_file.txt -f
```
