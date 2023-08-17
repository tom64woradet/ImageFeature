FROM python:3.9

# ตั้งค่าตัวแปรแวดวงพลิกแหลกสำหรับ Python (หากมีการแก้ไข)
ENV PYTHONUNBUFFERED 1

# สร้างและเปลี่ยนเป็นโฟลเดอร์ /app บน image
WORKDIR /app

# คัดลอก requirements.txt จากโฟลเดอร์โปรเจกต์ของคุณเข้าสู่ image
COPY requirements.txt /app/

# ติดตั้งแพ็กเกจ Python จาก requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# คัดลอกโค้ดของ FastAPI จากโฟลเดอร์โปรเจกต์ของคุณเข้าสู่ image
COPY . /app/

# กำหนด command เริ่มต้นเมื่อ image ถูกใช้ในการสร้าง container
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]