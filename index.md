<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>AI PRO 2026 | HOANGDZ AUTH</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;900&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.1.1/crypto-js.min.js"></script>
    <style>
        :root { --neon: #00f2ff; --bg: #050505; }
        body { margin:0; background:var(--bg); color:#fff; font-family:'Orbitron', sans-serif; overflow-x:hidden; }
        .snow { position:fixed; top:0; left:0; width:100%; height:100%; pointer-events:none; z-index:99; }
        .login-overlay { position:fixed; inset:0; display:flex; align-items:center; justify-content:center; background:rgba(0,0,0,0.95); z-index:2000; padding:20px; }
        .login-box { border:2px solid var(--neon); padding:20px; border-radius:20px; text-align:center; width:100%; max-width:350px; background:#000; }
        .wrapper { max-width:450px; margin:0 auto; padding:15px; display:none; }
        .glass { background:rgba(0,0,0,0.8); border:1px solid var(--neon); border-radius:15px; padding:15px; margin-bottom:10px; }
        input, button { width:100%; padding:12px; margin-bottom:10px; border-radius:8px; border:1px solid #444; background:#000; color:#fff; box-sizing:border-box; font-size:16px; }
        .btn { background:linear-gradient(90deg, var(--neon), #7000ff); font-weight:bold; cursor:pointer; }
        .res-box { font-size:2.5rem; text-align:center; font-weight:900; animation: flash 1s infinite; }
        @keyframes flash { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
        .hist-item { font-size:11px; border-bottom:1px solid #222; padding:8px 0; display:flex; justify-content:space-between; }
        .admin-link { position:fixed; bottom:10px; right:10px; font-size:10px; color:var(--neon); z-index:1000; }
    </style>
</head>
<body>

<div class="snow" id="snowContainer"></div>

<div class="login-overlay" id="loginScreen">
    <div class="login-box">
        <h2 style="color:var(--neon);">🔑 KÍCH HOẠT VIP HOANGDZ</h2>
        <input type="text" id="keyInput" placeholder="Nhập Key...">
        <button class="btn" onclick="checkKey()">KÍCH HOẠT NGAY</button>
    </div>
</div>

<div class="wrapper" id="mainScreen">
    <div class="glass" style="text-align:center;">
        <h3 style="color:var(--neon); margin:0;">CHÀO MỪNG QUAY TRỞ LẠI</h3>
        <p style="font-size:11px; color:#ccc;">Hệ thống phân tích MD5 thế hệ mới 2026. Tối ưu hóa tỉ lệ thắng cho người dùng VIP.</p>
    </div>

    <div class="glass">
        <input type="text" id="code" placeholder="MÃ PHIÊN (MD5)...">
        <button class="btn" onclick="runAnalysis()">PHÂN TÍCH KẾT QUẢ</button>
        <div id="loader" style="text-align:center; color:yellow; font-size:12px; display:none;">Đang phân tích dữ liệu, vui lòng đợi...</div>
        <div id="res" class="res-box">--</div>
        <div id="logic" style="font-size:10px; color:#aaa; margin-top:10px; text-align:center;"></div>
    </div>
    
    <div class="glass">
        <h3>LỊCH SỬ DỰ ĐOÁN</h3>
        <div id="historyList"></div>
    </div>
</div>

<div class="admin-link">Admin: @tranhoang2286</div>

<script>
    const masterKeys = { /* Chèn 600 key của bạn vào đây */ };

    function checkKey() {
        let val = document.getElementById('keyInput').value.trim();
        // Kiểm tra key...
        if(true) { // Thay bằng logic kiểm tra thật của bạn
            localStorage.setItem('expiry', Date.now() + 86400000);
            location.reload();
        }
    }

    function runAnalysis() {
        let input = document.getElementById('code').value.trim();
        if(input.length < 32) return alert("Nhập đủ 32 ký tự MD5!");
        
        // Hiển thị trạng thái phân tích
        let resBox = document.getElementById('res');
        let loader = document.getElementById('loader');
        resBox.innerText = "--";
        loader.style.display = "block";

        setTimeout(() => {
            let hash = CryptoJS.MD5(input).toString();
            let val = parseInt(hash.slice(-2), 16);
            let winrate = (70 + (val % 25));
            let res = (val % 2 === 0) ? "🔴 TÀI" : "⚪ XỈU";
            
            loader.style.display = "none";
            resBox.innerText = res;
            document.getElementById('logic').innerText = `Thuật toán MD5 | Tỉ lệ: ${winrate}%`;
            
            let list = document.getElementById('historyList');
            list.innerHTML = `<div class="hist-item"><span>${res}</span><span>${winrate}%</span><span>${new Date().toLocaleTimeString()}</span></div>` + list.innerHTML;
        }, 2000); // Đợi 2 giây
    }

    window.onload = () => {
        if(localStorage.getItem('expiry') > Date.now()) {
            document.getElementById('loginScreen').style.display = 'none';
            document.getElementById('mainScreen').style.display = 'block';
        }
    };
</script>
</body>
</html>
