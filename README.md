# PostgreSQL_6510110198
# PSU Note

ระบบจดโน้ตและแท็ก (Note & Tag) ด้วย Flask + SQLAlchemy

## ฟีเจอร์

- สร้าง/แก้ไข/ลบ โน้ต
- สร้าง/แก้ไข/ลบ Tag
- โน้ตแต่ละรายการสามารถมีหลายแท็ก
- ค้นหาโน้ตตามแท็ก
- ใช้ Bootstrap 5 สำหรับ UI

## วิธีติดตั้ง

**ติดตั้ง Python packages**
   ```
   pip install -r requirements.txt
   ```

**ตั้งค่าฐานข้อมูล**
   - ตรวจสอบว่า PostgreSQL ทำงานอยู่
   - สร้าง database ชื่อ `coedb` และ user/password ให้ตรงกับในไฟล์ `noteapp.py`
   - ตัวอย่างคำสั่ง:
     ```sql
     CREATE DATABASE coedb;
     CREATE USER coe WITH PASSWORD 'CoEpasswd';
     GRANT ALL PRIVILEGES ON DATABASE coedb TO coe;
     ```
**รันแอป**
   ```
   python -m psunote.noteapp
   ```
   หรือ
   ```
   python psunote/noteapp.py
   ```
**เปิดเว็บเบราว์เซอร์**
   - ไปที่ http://127.0.0.1:5000

## โครงสร้างโปรเจกต์

```
psunote/
├── noteapp.py         # main Flask app
├── models.py          # SQLAlchemy models
├── forms.py           # WTForms
├── templates/
│   ├── base.html
│   ├── index.html
│   ├── notes-create.html
│   ├── tags-view.html
│   └── tag-edit.html
└── ...
```

## หมายเหตุ

- หากต้องการเปลี่ยนการเชื่อมต่อฐานข้อมูล ให้แก้ไข `SQLALCHEMY_DATABASE_URI` ใน `noteapp.py`
- หากมีปัญหาเกี่ยวกับการ migrate schema ให้ลบไฟล์ฐานข้อมูลหรือ drop table แล้วรันใหม่

---

**ผู้พัฒนา:**  
Aj.Boat
