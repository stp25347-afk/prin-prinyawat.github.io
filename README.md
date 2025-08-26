<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>โปรไฟล์: ไจ่ไจ๋</title>
    <!-- Google Fonts: Kanit for Thai text -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        /* CSS สำหรับธีม Makoto Shinkai */
        :root {
            --shinkai-blue: #a3c4f3;
            --shinkai-purple: #9080ff;
            --shinkai-pink: #ffafcc;
            --shinkai-orange: #ffc482;
            --shinkai-text: #fff;
            --shinkai-glow: 0 0 10px rgba(255, 255, 255, 0.5), 0 0 20px rgba(255, 255, 255, 0.3);
            --transition-speed: 0.8s ease-in-out;
        }

        body {
            font-family: 'Kanit', sans-serif;
            margin: 0;
            padding: 0;
            overflow: hidden;
            height: 100vh;
            color: var(--shinkai-text);
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* พื้นหลังแบบไล่สีเพื่อสร้างบรรยากาศท้องฟ้า */
        .background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--shinkai-blue) 0%, var(--shinkai-purple) 100%);
            z-index: -1;
            transition: transform var(--transition-speed);
        }

        /* เอฟเฟกต์เมฆและดาว (pseudo-elements) */
        .background::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 75% 25%, rgba(255, 255, 255, 0.1) 0%, transparent 40%),
                        radial-gradient(circle at 25% 75%, rgba(255, 255, 255, 0.1) 0%, transparent 40%);
            background-size: 150% 150%;
            animation: cloud-move 60s linear infinite;
        }

        @keyframes cloud-move {
            from { background-position: 0 0; }
            to { background-position: 100% 100%; }
        }

        .container {
            position: relative;
            width: 90%;
            max-width: 800px;
            height: 80vh;
            padding: 20px;
            box-sizing: border-box;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.2);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            transition: transform var(--transition-speed);
        }

        /* การจัดหน้าแต่ละหน้า */
        .page {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transform: scale(0.95);
            transition: opacity var(--transition-speed), transform var(--transition-speed);
            position: absolute;
            top: 0;
            left: 0;
            padding: 20px;
            box-sizing: border-box;
        }

        .page.active {
            opacity: 1;
            transform: scale(1);
            z-index: 10;
        }

        /* ส่วนหัวและข้อความ */
        h1, h2 {
            font-weight: 700;
            text-shadow: var(--shinkai-glow);
        }

        p {
            font-weight: 300;
            font-size: 1.2rem;
            max-width: 600px;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
        }

        /* แถบนำทาง */
        .navigation {
            position: absolute;
            bottom: 20px;
            display: flex;
            gap: 15px;
            z-index: 20;
        }

        .nav-btn {
            background: rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.5);
            color: var(--shinkai-text);
            font-family: 'Kanit', sans-serif;
            font-size: 1rem;
            padding: 10px 20px;
            border-radius: 50px;
            cursor: pointer;
            backdrop-filter: blur(5px);
            transition: background 0.3s ease, transform 0.3s ease;
        }

        .nav-btn:hover {
            background: rgba(255, 255, 255, 0.4);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .nav-btn.active {
            background: var(--shinkai-pink);
            border-color: var(--shinkai-pink);
            transform: scale(1.05);
        }

        /* สำหรับหน้าจอขนาดเล็ก */
        @media (max-width: 768px) {
            .container {
                width: 95%;
                height: 90vh;
            }

            h1 { font-size: 2.5rem; }
            h2 { font-size: 1.8rem; }
            p { font-size: 1rem; }
            .nav-btn {
                padding: 8px 15px;
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>

    <!-- พื้นหลังแบบ parallax -->
    <div class="background" id="background"></div>

    <!-- ส่วนหลักของเนื้อหา -->
    <div class="container">

        <!-- หน้าที่ 1: หน้าหลัก -->
        <div class="page active" id="page1">
            <h1>นายปฤณ ปริญญวัฒน์</h1>
            <p>เรียกผมว่า "ไจ่ไจ๋" ก็ได้ครับ</p>
            <p>ยินดีต้อนรับสู่โลกของผม...</p>
        </div>

        <!-- หน้าที่ 2: ความสนใจ -->
        <div class="page" id="page2">
            <h2>ความสนใจ</h2>
            <p>ผมมีความสนใจในเรื่องของกองทัพอากาศและเครื่องบินรบมาโดยตลอดครับ</p>
            <p>ความยิ่งใหญ่ของเทคโนโลยีทางอากาศเป็นสิ่งที่น่าหลงใหลสำหรับผม</p>
        </div>

        <!-- หน้าที่ 3: การศึกษา -->
        <div class="page" id="page3">
            <h2>การศึกษา</h2>
            <p>ปัจจุบันผมกำลังศึกษาอยู่ที่โรงเรียนสุรธรรมพิทักษ์ครับ</p>
            <p>ที่นี่มอบโอกาสให้ผมได้เรียนรู้และเติบโตในทุกๆ ด้าน</p>
        </div>

        <!-- หน้าที่ 4: งานอดิเรก -->
        <div class="page" id="page4">
            <h2>งานอดิเรก</h2>
            <p>ในเวลาว่าง ผมชอบเล่นเกมตระกูล Soul ครับ</p>
            <p>ความท้าทายและการต้องใช้ความพยายามอย่างมากเพื่อก้าวข้ามอุปสรรค เป็นสิ่งที่ผมชื่นชอบในเกมแนวนี้</p>
        </div>

        <!-- หน้าที่ 5: ติดต่อ/บทสรุป -->
        <div class="page" id="page5">
            <h2>สุดท้ายนี้...</h2>
            <p>ขอบคุณที่เข้ามาทำความรู้จักกันครับ</p>
            <p>หวังว่าจะได้พูดคุยกับคุณอีกในอนาคต</p>
        </div>

    </div>

    <!-- แถบนำทาง -->
    <nav class="navigation">
        <button class="nav-btn active" onclick="showPage('page1')">หน้าหลัก</button>
        <button class="nav-btn" onclick="showPage('page2')">ความสนใจ</button>
        <button class="nav-btn" onclick="showPage('page3')">การศึกษา</button>
        <button class="nav-btn" onclick="showPage('page4')">งานอดิเรก</button>
        <button class="nav-btn" onclick="showPage('page5')">ติดต่อ</button>
    </nav>

    <script>
        /**
         * JavaScript สำหรับการเปลี่ยนหน้าและเอฟเฟกต์
         */
        const pages = document.querySelectorAll('.page');
        const navButtons = document.querySelectorAll('.nav-btn');
        const background = document.getElementById('background');

        // ฟังก์ชันสำหรับแสดงหน้าเว็บที่เลือก
        function showPage(pageId) {
            // ซ่อนทุกหน้า
            pages.forEach(page => {
                page.classList.remove('active');
            });
            // เอาสถานะ active ออกจากปุ่มนำทางทั้งหมด
            navButtons.forEach(btn => {
                btn.classList.remove('active');
            });

            // แสดงหน้าที่ต้องการ
            const targetPage = document.getElementById(pageId);
            if (targetPage) {
                targetPage.classList.add('active');
            }

            // เพิ่มสถานะ active ให้กับปุ่มที่ถูกคลิก
            const activeButton = document.querySelector(`.nav-btn[onclick*="${pageId}"]`);
            if (activeButton) {
                activeButton.classList.add('active');
            }
        }

        // เพิ่มเอฟเฟกต์ parallax เบาๆ ตามการเคลื่อนที่ของเมาส์
        document.addEventListener('mousemove', (e) => {
            const parallaxIntensity = 10; // ค่าความเข้มของ parallax
            const x = (window.innerWidth - e.pageX * parallaxIntensity) / 100;
            const y = (window.innerHeight - e.pageY * parallaxIntensity) / 100;
            background.style.transform = `translate(${x}px, ${y}px)`;
        });

    </script>
</body>
</html>
