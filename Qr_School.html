<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>QR Code Generator</title>
    
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=M+PLUS+Rounded+1c:wght@400;700&display=swap">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    
    <style>
        body {
            font-family: 'M PLUS Rounded 1c', sans-serif;
            background-color: #121212;
            color: #00ffcc;
            margin: 0;
            padding: 0;
            position: relative;
            text-align: center;
            background-image: url('nakom.jpg');
            background-size: cover;
            background-repeat: no-repeat;
            background-position: 270px center;
            height: 120vh;
            
            /* ป้องกันการคลุมดำ */
            -webkit-user-select: none;
            -ms-user-select: none;
            user-select: none;
        }

        #message {
            color: #ff5252;
            font-size: 24px;
            font-weight: bold;
        }

        #qrcodeContainer {
            width: 310px;
            height: 310px;
            border: 2px solid #ffffff;
            background-color: #ffffff;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 20px auto;
            border-radius: 8px;
        }

        #qrcode {
            width: 300px;
            height: 300px;
        }

        h1, h3, p, #timeDisplay { color: #00ffcc; }
        .hidden { display: none; }

        @media (min-width: 1200px) { body { background-position: calc(50% + 200px) center; } }
        @media (max-width: 1199px) and (min-width: 768px) { body { background-position: center; } }
        @media (max-width: 767px) { body { background-position: center; } }
    </style>
</head>
<body>
    <h1>QR Code Generator</h1>
    <h3>โรงเรียนกรมแผนที่ทหาร</h3>
    <h2>Donate: 0846795069</h2>
    <h4>Develop By: Chana.s</h4>
    <div id="timeDisplay"></div>
    <div id="qrcodeContainer">
        <div id="qrcode"></div>
        <div id="message" class="hidden">ระบบปิดให้บริการ</div>
    </div>

    <!-- ข้อมูลแสดงบนจอ -->
    <p id="ip"></p>
    <p id="region"></p>
    <p id="city"></p>
    <p id="country"></p>
    <p id="os-info"></p>
    <p id="browser-info"></p>

    <script>
        // ========================================================
        // CONFIGURATION: ใส่ MAC Address เครื่องที่คุณยืนยันแล้ว
        // ========================================================
        const TARGET_MAC_ADDRESS = "04:82:00:82:72:EA";

        // ป้องกันการคลิกขวาและ F12
        document.addEventListener('contextmenu', e => e.preventDefault());
        document.onkeydown = function(e) {
            if (event.keyCode == 123) return false;
            if (e.ctrlKey && e.shiftKey && e.keyCode == 'I'.charCodeAt(0)) return false;
            if (e.ctrlKey && e.shiftKey && e.keyCode == 'J'.charCodeAt(0)) return false;
            if (e.ctrlKey && e.shiftKey && e.keyCode == 'C'.charCodeAt(0)) return false;
            if (e.ctrlKey && e.keyCode == 'U'.charCodeAt(0)) return false;
        }

        // อัพเดทเวลาหน้าจอ
        function updateTime() {
            const now = new Date();
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric', hour: '2-digit', minute: '2-digit', second: '2-digit' };
            document.getElementById('timeDisplay').innerText = now.toLocaleDateString('th-TH', options);
        }
        updateTime();
        setInterval(updateTime, 1000);

        // --------------------------------------------------------
        // ฟังก์ชันเข้ารหัสที่จำลองมาจาก Java (JS ล้วน)
        // --------------------------------------------------------
        function stringXorEncode(dataStr, keyStr) {
            let resultBytes = [];
            let keyLen = keyStr.length;
            for (let i = 0; i < dataStr.length; i++) {
                let d = dataStr.charCodeAt(i);
                let k = keyStr.charCodeAt(i % keyLen);
                resultBytes.push(d ^ k);
            }
            let binaryString = "";
            for(let i = 0; i < resultBytes.length; i++) {
                binaryString += String.fromCharCode(resultBytes[i]);
            }
            return btoa(binaryString);
        }

        function hexToBin4(hexChar) {
            return parseInt(hexChar, 16).toString(2).padStart(4, '0');
        }

        function charToBinString(char) {
            return char.charCodeAt(0).toString(2);
        }

        // ฟังก์ชันสร้างลิงก์ QR Code 
        function generateQRCodeUrl() {
            const now = new Date();
            const year = now.getFullYear();
            const month = String(now.getMonth() + 1).padStart(2, '0');
            const day = String(now.getDate()).padStart(2, '0');
            const hour = String(now.getHours()).padStart(2, '0');
            const min = String(now.getMinutes()).padStart(2, '0');
            const sec = String(now.getSeconds()).padStart(2, '0');

            const dateStr = `${year}${month}${day}`;
            let sb2 = "";
            for (let i = 0; i < dateStr.length; i++) {
                sb2 += charToBinString(dateStr[i]);
            }
            sb2 += "111111111111";

            const secStr = sec;
            let sb4 = "";
            for (let i = 0; i < secStr.length; i++) {
                sb4 += charToBinString(secStr[i]);
            }

            const cleanMac = TARGET_MAC_ADDRESS.replace(/:/g, '').toUpperCase();
            let sb5 = "";
            for (let i = 0; i < cleanMac.length; i++) {
                sb5 += hexToBin4(cleanMac[i]);
            }

            const inputData = sb4 + sb5;
            const encodedSuffix = stringXorEncode(inputData, sb2);
            const prefix = `${year}${month}${day}${hour}${min}`;
            
            return "https://app.rtarf.mi.th/Qrcode/?qrcode=6" + prefix + encodedSuffix;
        }

        // สร้าง QR Code (แสดงตลอดเวลา)
        function drawQRCode() {
            $('#qrcode').show();
            $('#message').hide();
            $('#qrcode').empty();
            
            const finalUrl = generateQRCodeUrl();
            new QRCode(document.getElementById('qrcode'), {
                text: finalUrl,
                width: 300,
                height: 300
            });
        }

        $(document).ready(function() {
            drawQRCode();
            setInterval(drawQRCode, 5000); // อัพเดท QR Code ทุกๆ 5 วินาที
        });
    </script>

    <!-- Script สำหรับดึงข้อมูล Client IP / Device -->
    <script>
        fetch('https://ipinfo.io?token=ac65b6ea4beb43')
            .then(response => response.json())
            .then(data => {
                document.getElementById('ip').innerText = 'IP Address: ' + data.ip;
                document.getElementById('region').innerText = 'Region: ' + data.region;
                document.getElementById('city').innerText = 'City: ' + data.city;
                document.getElementById('country').innerText = 'Country: ' + data.country;
            })
            .catch(error => console.error('Error fetching IP:', error));

        function getOS() {
            let ua = window.navigator.userAgent;
            let pf = window.navigator?.userAgentData?.platform || window.navigator.platform;
            if (/Windows NT 10.0/.test(ua)) return "Windows 10";
            if (/Windows NT 6.3/.test(ua)) return "Windows 8.1";
            if (/Windows NT 6.2/.test(ua)) return "Windows 8";
            if (/Windows NT 6.1/.test(ua)) return "Windows 7";
            if (/Mac/.test(pf)) return "macOS";
            if (/Android/.test(ua)) return "Android";
            if (/like Mac/.test(ua)) return "iOS";
            return "Unknown";
        }

        function getBrowserInfo() {
            let ua = window.navigator.userAgent;
            let browser = "Unknown";
            if (/Edge|Edg/.test(ua)) browser = "Edge";
            else if (/Chrome/.test(ua)) browser = "Google Chrome";
            else if (/Safari/.test(ua)) browser = "Safari";
            else if (/Firefox/.test(ua)) browser = "Mozilla Firefox";
            
            let match = ua.match(/(?:Chrome|Firefox|Safari|Edg)\/(\d+(\.\d+)?)/);
            let version = match ? match[1] : "";
            return `${browser} ${version}`;
        }
        
        document.getElementById('os-info').innerText = 'OS : ' + getOS();
        document.getElementById('browser-info').innerText = 'Browser : ' + getBrowserInfo();

        if (/Mobile|Android|iP(hone|od|ad)/i.test(navigator.userAgent)) {
            document.body.insertAdjacentHTML('beforeend', '<p><center>คุณกำลังเข้าถึงเว็บไซต์จากอุปกรณ์มือถือ</center></p>');
        }
    </script>
</body>
</html>
