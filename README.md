# การพัฒนาเว็บแอปพลิเคชันสำหรับบริหารจัดการคลินิกผิวหนังและความงาม
การพัฒนาเว็บแอปพลิเคชันสำหรับบริหารจัดการคลินิกผิวหนังและความงามเป็นการพัฒนาเว็บแอปพลิเคชันเพื่อยกระดับการทำงานของคลินกผิวหนังและความงาม
## คำอธิบายโครงการ
วัตถุประสงค์
1. เพื่อเปลี่ยนให้คลินิกมีระบบการจัดการข้อมูลในระบบดิจิตอล
2. เพื่อรองรับการขยายตัวของผู้ป่วยในอนาคต
3. เพื่อลดความซับซ้อนของระบบจากรูปแบบเดิม
4. เพื่อเพิ่มความพึงพอใจของผู้ใช้
## ความต้องการของระบบ
1. Python==3.11
2. XAMPP==3.3.0
3. Node.js==18.17.0
## ทดสอบแล้วบน
Edition	Windows 11 Pro
Version	22H2
OS build	22621.1992
Experience	Windows Feature Experience Pack 1000.22644.1000.0
## วิธีการติดตั้งและใช้งาน
### ขั้นตอนการติดตั้งแอปพลิเคชันในการใช้งานระบบ
1.	ทำการดาวน์โหลดไฟล์ “Clinic.zip” ไปยังไดเรคทอรี่ ที่ต้องการเก็บ
2.	เมื่อทำการดาวน์โหลดไฟล์เสร็จเรียบร้อยแล้ว ให้ทำการแตกไฟล์สำหรับการใช้งาน
3.	ติดตั้ง Node.js,Python,XAMPP ไปยังเครื่องคอมพิวเตอร์ที่ต้องการใช้งาน
4.	ทำการเปิด terminal ที่มีเก็บไฟล์ requirements.txt ไว้แล้วใช้คำสั่ง pip install -r requirements.txt ดังรูป
   ![image](https://cdn.discordapp.com/attachments/938092515884662805/1136908889456132198/image.png)
5.	เมื่อ ติดตั้ง XAMPP สำเร็จ ให้ไปเปิดใช้งาน Apache และ MySQL
   ![image](https://cdn.discordapp.com/attachments/938092515884662805/1136909239001043016/image.png)
7.	เมื่อทำการติดตั้ง สำเร็จตามข้อ 4 ทำการพิมคำสั่ง py manage.py makemigrations เพื่อให้ Django ทำการตรวจสอบและอัปเดตฐานข้อมูลของแอปพลิเคชันของคุณเมื่อคุณทำการเปลี่ยนแปลงโครงสร้างฐานข้อมูล (models) หรือเพิ่ม-ลบ-แก้ไขตารางใน Django โดยใช้ Python code แทนการใช้ SQL โดยตรง
   ใช้คำสั่ง py.manage.py migrate เพื่อทำการอัปเดตฐานข้อมูลตาม migrations ที่ได้สร้างขึ้นในข้อ 5
   ใช้คำสั่ง py.manage.py createsuperuser เพื่อสร้างผู้ใช้งานเริ่มต้นโดยผู้ใช้
    
1. ID : admin Password : admin (ผู้ช่วยคุณหมอ)
2. ID : doctor Password : 1234 (คุณหมอ)
9.	เข้าไปเปลี่ยน status ในฐานข้อมูล clinic_app_clinic_user เพื่อระบุว่าผู้ใช้คือใครโดย 1 คือ ผู้ช่วยคุณหมอและ 2 คือ คุณหมอ ดังรูป
  ![image](https://cdn.discordapp.com/attachments/938092515884662805/1136909461068455976/image.png)
### ขั้นตอนการใช้งานระบบ
1.	เปิดการใช้งาน XAMPP และ ใช้งาน Apache,MySQLดังภาพ
   ![image](https://cdn.discordapp.com/attachments/938092515884662805/1136909828980211763/image.png)
2.	ทำการเปิดใช้งาน python Django โดยใช้คำสั่ง py manage.py runserver
 ![image](https://cdn.discordapp.com/attachments/938092515884662805/1136910424290361464/image.png)
3.	ทำการเปิดใช้คำสั่ง npm run dev เป็นคำสั่งที่ใช้ในการรัน "script" ที่กำหนดไว้ในไฟล์ package.json ของโปรเจกต์ Node.js หรือ JavaScript ที่ใช้ npm (Node Package Manager) เป็นตัวจัดการแพ็กเกจในโปรเจกต์นั้นๆ
 ![image](https://cdn.discordapp.com/attachments/938092515884662805/1136910544348135485/image.png)
4.	เมื่อเปิดใช้งาน node.js,MySQLและ Python Django สำเร็จ ให้เข้าใช้งานผ่าน web browser เช่น google chrome แล้วพิมพ์ http://localhost:5173/ แล้วจะนำไปสู้หน้าล็อคอินจากนั้นเข้าสู่ระบบโดยใช้ ID และ Password ที่ตั้งไว้ในตอนติดตั้งระบบ ดังรูป

![image](https://cdn.discordapp.com/attachments/938092515884662805/1136910634525667338/image.png)
# การจัดวางโครงสร้างโฟลเดอร์ย่อย
โครงสร้างไดเรกทอรีของโปรเจกต์
'code/'
├── backend/
│   └── clinic_site/
│      ├── clinic_app/
│      ├── clinic_site/
│      ├── media/
│      ├── db.sqlite3
│      ├── manage.py
│      ├── Procfile
│      ├── requirements
│      └── .env
└── frontend/
   └── Clinic_front/
      ├── node_modules/
      ├── public/
      ├── src/
      ├── .gitignore
      ├── index.html
      ├── package.json
      ├── package-lock.json
      ├── postcss.config.js
      ├── tailwind.config.js
      ├── vite.config.js
      └── yarn.lock




# แหล่งอ้างอิง
* [1] Siritongtaworn, S., & Siengthai, S. (2019). The importance of healthcare service quality in Thailand: A literature review. In Proceedings of the 14th International Conference on Knowledge, Information and Creativity Support Systems (KICSS).
* [2] Kaptelinin, V., & Nardi, B. A. (2018). Affordances in HCI: Toward a Mediated Action Perspective. In Proceedings of the 2018 CHI Conference on Human Factors in Computing Systems (p. 7).
* [3] Shneiderman, B., Plaisant, C., Cohen, M., Jacobs, S., & Elmqvist, N. (2016). Designing the User Interface: Strategies for Effective Human-Computer Interaction. Pearson.
* [4] Froont. (2017). Responsive Web Design Techniques, Tools and Design Strategies.
* [5] ณัฐพงศ์ ศิริสรรค์. (2017). สร้างเว็บแอปพลิเคชันด้วย MySQL, PHP, และ Laravel Framework. สำนักพิมพ์ สำนักพิมพ์มหาวิทยาลัยธรรมศาสตร์.
* [6] Ross, J. W., Beath, C. M., & Mocker, M. (2019). Designed for Digital: How to Architect Your Business for Sustained Success. MIT Press.Westerman, G., Bonnet, D., & McAfee, A. (2014). Leading Digital: Turning Technology into Business Transformation. Harvard Business Review Press.
* [7] Tarhan, A., & Salleh, N. (2019). Flexibility-Awareness in Process-Aware Information Systems. In Proceedings of the International Conference on Information Systems (ICIS).
* [8] Iqbal, S., & Alzahrani, A. (2020). Visual Studio Code as a Tool for Teaching and Learning. In 2020 3rd International Conference on Education and E-Learning (ICEEL) (pp. 35-40). IEEE.
* [9] Banks, A., & Porcello, E. (2020). Learning React: Functional Web Development with React and Redux. O'Reilly Media.
* [10] Aydin, M. E., & Oztemel, E. (2018). Designing a Django-based web application for online assessment. Journal of Educational Technology & Society, 21(1), 61-72.
* [11] Waris Limtoprasert, & Nuutthapachr Sethasathien. (2564). เคล็ดไม่ลับการใช้ Postman. bigdata.go.th. ค้นเมื่อ 10 กรกฎาคม 2566. https://bigdata.go.th/big-data-101/เคล็ดไม่ลับการใช้-postman/
* [12] Mindphp Developer. (2560). What is Navicat Query? Mindphp.com. ค้นเมื่อ 10 กรกฎาคม 2566. https://www.mindphp.com/developer/21-sql-mysql/4070-what-is-navicat-query.html
* [13] DEMETER ADMIN. (2560). Google Chrome คืออะไร. support.dmit.co.th. ค้นเมื่อ 10 กรกฎาคม 2023. https://support.dmit.co.th/hc/th/articles/115015461708-Google-Chrome-คืออะไร
* [14] apsth. (2023).โปรแกรมคลินิก Cloud Platform สืบค้นเมื่อ 12 กรกฎาคม 2566 สืบค้นจาก https://www.apsth.com/index.html
* [15] บริษัท ละมุนภัณฑ์ ไอที จำกัด. (2022). โปรแกรมคลินิกความงาม|JERA Cloud. สืบค้นเมื่อ 14 พฤษภาคม 2566. สืบค้นจาก https://www.jeracloud.com/?fbclid=IwAR2DZ4zcYED2zQZO1230XW1iyZ26_5QaEY37epo7VyoViomvOXLFa_I7xgs
* [16] OpenEMR Foundation, Inc.. (2020). Openemr. สืบค้นเมื่อ 14 พฤษภาคม 2566. สืบค้นจาก https://www.open-emr.org/enlandscape.cloud/
* [17] doctorease. (2023). CRM services ที่มาพร้อมกับโปรแกรมคลินิก doctorease. สืบค้นเมื่อ 14 พฤษภาคม 2566. สืบค้นจาก https://www.doctorease.co/crm-services/
* [18] cliniclive. (2023). ระบบบริหารงานคลินิก ออนไลน์ clinic live. สืบค้นเมื่อ 10 กรกฎาคม 2566. https://cliniclive.com

# ขอบคุณ
 ด้วยความร่วมมือและความสนับสนุนของทุกคน โครงการนี้ได้ก้าวไปข้างหน้าได้ด้วยความสำเร็จ
