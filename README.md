🏢 Apartment Management System
ระบบบริหารจัดการหอพักพัฒนาด้วย Django 5 + SQLite รองรับการจัดการห้องพัก ผู้เช่า ค่าเช่า มิเตอร์น้ำ-ไฟ พัสดุ และแจ้งซ่อม

📋 Features
Moduleคำอธิบาย🏠 Roomsจัดการห้องพัก สถานะ ราคา แผนผังชั้น👤 Tenantsข้อมูลผู้เช่า สัญญาเช่า เลือกห้อง💰 Paymentsค่าเช่า ค่าน้ำ ค่าไฟ ยืนยันการชำระ📊 Metersบันทึกมิเตอร์น้ำ-ไฟประจำเดือน📦 Parcelsจัดการพัสดุ แจ้งเตือนผู้เช่า🔧 Repairsแจ้งซ่อม ติดตามสถานะ🧾 Invoicesออกบิล ส่งออก PDF📅 DashboardAdmin / Tenant แยกตาม role

🛠 Tech Stack

Backend: Django 5.0.4
Database: SQLite
Frontend: Bootstrap 5 + Font Awesome 6
อื่นๆ: Whitenoise, django-crispy-forms, Pillow, django-environ


⚙️ Requirements

Python 3.10+
pip
Git (optional)


🚀 การติดตั้ง (Step by Step)
1. ติดตั้ง Python
ดาวน์โหลด Python 3.10+ จาก https://www.python.org/downloads/

✅ ติ๊กช่อง "Add Python to PATH" ตอนติดตั้ง

ตรวจสอบว่าติดตั้งสำเร็จ:
cmdpython --version

2. ดาวน์โหลดโปรเจกต์
แตก zip แล้วเปิด Terminal หรือ VS Code ที่โฟลเดอร์โปรเจกต์:
cmdcd path\to\project

3. สร้าง Virtual Environment
cmdpython -m venv venv
เปิดใช้งาน venv:
cmd# Windows
venv\Scripts\activate

source venv/bin/activate

เมื่อ activate สำเร็จจะเห็น (venv) ข้างหน้า prompt

4. ติดตั้ง Package ทั้งหมด
cmdpip install django
pip install -r requirements.txt
ตรวจสอบว่าติดตั้งครบ:
cmdpip list

5. ตั้งค่าไฟล์ .env
คัดลอกไฟล์ตัวอย่าง:
cmd# Windows
copy .env.example .env

cp .env.example .env
เปิดไฟล์ .env แล้วแก้ไข:
envDEBUG=True
SECRET_KEY=your-secret-key-here
สร้าง Secret Key ใหม่:
cmdpython -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"

6. Migrate ฐานข้อมูล
cmdpython manage.py migrate

✅ ถ้าเห็น OK ทุกบรรทัด แปลว่าสำเร็จ


7. สร้าง Admin (Superuser)
cmdpython manage.py createsuperuser
กรอกข้อมูล:

Username: ชื่อ admin (เช่น admin)
Email: อีเมล (กด Enter ข้ามได้)
Password: รหัสผ่าน (ไม่แสดงตัวอักษรขณะพิมพ์)


8. เปิดเซิร์ฟเวอร์
cmdpython manage.py runserver
เปิด browser ไปที่:

🌐 หน้าเว็บหลัก: http://127.0.0.1:8000
🔧 หน้า Admin: http://127.0.0.1:8000/admin


👥 Role และสิทธิ์การใช้งาน
Roleการเข้าถึงAdmin / Superuserจัดการทุกอย่าง ดู dashboard ภาพรวมStaffจัดการห้อง ผู้เช่า มิเตอร์ พัสดุTenantดูข้อมูลห้องตัวเอง ชำระเงิน แจ้งซ่อม
สร้าง Tenant User
Admin เพิ่มผู้เช่าได้ที่ /tenants/add/ ระบบจะสร้าง account อัตโนมัติ:

Username: อีเมลของผู้เช่า
Password: 1234 


📁 โครงสร้างโปรเจกต์
project/
├── apartment_project/       # Settings, URLs, Middleware
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── apps/
│   ├── accounts/            # Login, Register, Logout
│   ├── dashboard/           # Dashboard แยกตาม role
│   ├── rooms/               # จัดการห้องพัก
│   ├── tenants/             # ข้อมูลผู้เช่า
│   ├── payments/            # การชำระเงิน
│   ├── meters/              # บันทึกมิเตอร์
│   ├── invoices/            # ใบแจ้งหนี้
│   ├── bookings/            # การจอง
│   ├── parcels/             # พัสดุ
│   └── repairs/             # แจ้งซ่อม
├── templates/               # HTML templates
├── static/                  # CSS, JS, Images
├── db.sqlite3               # ฐานข้อมูล SQLite
├── manage.py
└── requirements.txt


https://drive.google.com/drive/folders/1pxpjingEhOHhMG_6QrMyE8HhMXDequTn?usp=sharing #(link ส่ง อ.จีระวรรณ)
