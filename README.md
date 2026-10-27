# Overnight Packprint — นามบัตรออนไลน์

นามบัตรของแพรว บริษัท โอเวอร์ไนท์ แพคพริ้นท์ จำกัด สร้างด้วย HTML, CSS และ JavaScript ไม่ต้องติดตั้ง dependencies หรือ build

## โครงสร้างไฟล์

```text
praew-basic-git/
├── .git/               # ใช้ Git repository หลักเพียงแห่งเดียว
├── .gitignore
├── .nojekyll           # ให้ GitHub Pages เสิร์ฟไฟล์ static โดยไม่ใช้ Jekyll
├── index.html          # หน้าเว็บและข้อมูลติดต่อ
├── style.css           # รูปแบบและ responsive layout
├── script.js           # รายการบริการ บันทึกผู้ติดต่อ และการแชร์
├── assets/
│   └── line-qr.png     # QR LINE จากนามบัตรต้นฉบับ
└── README.md
```

## เปิดดูบนเครื่อง

เปิด `index.html` ในเบราว์เซอร์ได้ทันที หรือรันจากโฟลเดอร์โปรเจกต์:

```sh
python3 -m http.server 8080
```

แล้วเปิด `http://localhost:8080` การแชร์ลิงก์ควรทดสอบจาก URL เว็บที่เผยแพร่แล้ว

## Deploy ด้วย GitHub Pages

1. สร้าง repository บน GitHub (เลือก Public หากใช้ GitHub Free)
2. จากโฟลเดอร์นี้ ให้ commit และ push โดยแทน `YOUR_USERNAME` และ `YOUR_REPOSITORY` ด้วยค่าจริง:

   ```sh
   git add .
   git commit -m "Add digital business card for GitHub Pages"
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
   git push -u origin main
   ```

   หากมี remote `origin` อยู่แล้ว ให้ตรวจด้วย `git remote -v` และใช้ remote เดิมที่ต้องการ

3. ใน GitHub ไปที่ **Settings → Pages → Build and deployment**
4. ตั้ง **Source: Deploy from a branch** เลือก **Branch: main** และ **Folder: / (root)** แล้วกด **Save**
5. รอ deployment เสร็จ แล้วเปิด URL ที่ GitHub แสดง โดยทั่วไปเป็น `https://YOUR_USERNAME.github.io/YOUR_REPOSITORY/`

หลังจากเปิด Pages แล้ว การ push เข้า `main` จะอัปเดตเว็บอัตโนมัติ ไม่ต้องใช้ GitHub Actions workflow เพิ่มเติม

ไฟล์ CSS, JavaScript และรูปภาพใช้ relative paths เพื่อรองรับ URL ที่มีชื่อ repository เป็น subpath

อ้างอิง: [การตั้งค่า publishing source ของ GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
