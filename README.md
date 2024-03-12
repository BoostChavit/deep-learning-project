# สมาชิกกลุ่ม
1. 6410450842 นายชวิศ สิทธิธรรมจักษ์
2. 6410451393 นายวิทวัส พิณรัตน์

# Preparing data
Alphabet written dataset : https://www.kaggle.com/datasets/dhruvildave/english-handwritten-characters-dataset/data

หลังจากดาวน์โหลด dataset แล้ว unzip โฟลเดอร์หลังจาหนั้นให้เปลี่ยนชื่อโฟลเดอร์จาก 'archive' เป็น 'alphabets' แล้วนำโฟลเดอร์นี้ไปใส่ใน working directory
*Note: โครงสร้างของ dataset : english.csv จะประกอยด้วยคอลัมน์ image(path ไปที่ไฟล์รูป), label(ผลเฉลย)
          alphabets\
            │\
            └── Img\
            |    │\
            |    ├── images of alphabets\
            │\
            └── english.csv\

# Preprocessing data

1. โหลด english.csv เข้ามาเป็น pandas dataframe
2. สร้างคอมลัมน์ใหม่ใน dataframe ชื่อ img โดยจะข้อมูลของรูป
3. นำเข้ารูปแล้วใส่ในคอลัมน์ img โดยปรับขนาดรูปเป็น 64 x 64
4. นำชื่อ class ทั้งหมดใส่ในตัวแปร class_names
5. ทำการแบ่ง train_test_split ของที่ละ class เป็น x_train, y_train, x_test, y_test (ข้อมูลจะยังเรียงจาก class 0-9A-Za-z)
6. ทำการสุ่มลำดับของข้อมูล
7. ทำ one-hot-encode กับ y_train, y_test
