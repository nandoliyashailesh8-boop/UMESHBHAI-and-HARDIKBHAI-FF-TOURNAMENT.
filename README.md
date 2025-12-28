<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>UMESHBHAI & Hardik Tournament</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
/* ===== BASE ===== */
body{margin:0;font-family:Arial,sans-serif;background:#0b0b0b;color:#fff;line-height:1.5}
header{background:#ffb300;color:#000;padding:15px;text-align:center;font-size:22px;font-weight:bold}

/* ===== SECTION TITLES ===== */
.section-title{text-align:center;color:#ffb300;margin:25px 0 10px;font-size:20px}

/* ===== MATCH CARDS ===== */
.container{padding:15px;display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:20px}
.card{background:#111;border-radius:15px;box-shadow:0 0 15px #ffb300;overflow:hidden;text-align:center;transition:0.3s}
.card img{width:100%;height:auto;border-radius:10px;display:block}
.card h3{color:#ffb300;margin:10px 0}
.card p{font-size:14px}
.card .btn{margin-top:10px}

/* ===== BUTTONS ===== */
.btn{display:block;margin:10px;padding:12px;background:#ffb300;color:#000;text-decoration:none;border-radius:8px;font-weight:bold;text-align:center;transition:0.3s}
.btn:hover{background:#ffd54f}
.btn.disabled{background:#555;color:#ccc;pointer-events:none}

/* ===== TIMER ===== */
.timer{font-size:18px;margin:10px;color:#00ffcc;text-align:center}

/* ===== PAYMENT ===== */
.payment{background:#111;margin:20px;padding:15px;border-radius:15px;box-shadow:0 0 15px #ffb300;text-align:center}
.payment img{width:200px;margin:10px 0;display:block;margin-left:auto;margin-right:auto}
.pay-buttons a{margin:8px;display:block}

/* ===== GALLERY ===== */
.gallery{display:grid;grid-template-columns:repeat(auto-fit,minmax(140px,1fr));gap:10px;padding:15px}
.gallery img{width:100%;border-radius:10px;display:block}

/* ===== FOOTER ===== */
footer{text-align:center;padding:15px;font-size:13px;opacity:.8}

/* ===== RESPONSIVE ===== */
@media(max-width:600px){
  header{font-size:18px;padding:12px}
  .section-title{font-size:18px}
  .container{grid-template-columns:1fr}
  .payment img{width:150px}
}
</style>
</head>

<body>

<header>🔥 UMESHBHAI & Hardik Tournament 🔥</header>

<div class="section-title">⏳ Match Starts In</div>
<div class="timer" id="timer">Loading...</div>

<div class="section-title">🎮 Available Matches</div>
<div class="container">

<div class="card">
<img src="https://picsum.photos/seed/solo/600/400" alt="Solo Match">
<h3>SOLO MATCH</h3>
<p>Entry Fee: ₹30</p>
<p>Prize: ₹500</p>
<a href="#payment" class="btn match-btn" data-amount="30">JOIN NOW</a>
</div>

<div class="card">
<img src="https://picsum.photos/seed/duo/600/400" alt="Duo Match">
<h3>DUO MATCH</h3>
<p>Entry Fee: ₹50</p>
<p>Prize: ₹1000</p>
<a href="#payment" class="btn match-btn" data-amount="50">JOIN NOW</a>
</div>

<div class="card">
<img src="https://picsum.photos/seed/squad/600/400" alt="Squad Match">
<h3>SQUAD MATCH</h3>
<p>Entry Fee: ₹100</p>
<p>Prize: ₹3000</p>
<a href="#payment" class="btn match-btn" data-amount="100">JOIN NOW</a>
</div>

</div>

<div class="section-title">📜 Tournament Rules</div>
<div class="rules" style="background:#111;margin:20px;padding:15px;border-radius:15px;font-size:14px;line-height:1.6">
1️⃣ No hacks / cheats allowed<br>
2️⃣ Room ID WhatsApp par milegi<br>
3️⃣ Match start ke baad entry allow nahi<br>
4️⃣ Payment non-refundable<br>
5️⃣ Screenshot WhatsApp par bhejna compulsory
</div>

<div class="section-title">💰 Payment Options</div>
<div id="payment" class="payment">

<h3>UPI ID</h3>
<h2>Thakoru429@okicici</h2>
<img src="https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=upi://pay?pa=Thakoru429@okicici&pn=Tournament&cu=INR" alt="UPI QR">

<div class="pay-buttons">
<!-- Google Pay Buttons -->
<a class="btn" href="upi://pay?pa=Thakoru429@okicici&pn=SoloMatch&am=30&cu=INR">🟢 Google Pay – SOLO ₹30</a>
<a class="btn" href="upi://pay?pa=Thakoru429@okicici&pn=DuoMatch&am=50&cu=INR">🟢 Google Pay – DUO ₹50</a>
<a class="btn" href="upi://pay?pa=Thakoru429@okicici&pn=SquadMatch&am=100&cu=INR">🟢 Google Pay – SQUAD ₹100</a>

<!-- Razorpay -->
<a class="btn" href="https://rzp.io/l/your_razorpay_link">💳 Pay via Razorpay</a>
</div>

<p>Google Pay • PhonePe • Paytm • BHIM</p>
<p>Payment ke baad screenshot WhatsApp par bheje</p>
<a class="btn" href="https://wa.me/918487801647?text=Payment%20Done%20for%20Tournament">📲 Send Screenshot on WhatsApp</a>

</div>

<div class="section-title">📸 Tournament Gallery</div>
<div class="gallery">
<img src="https://picsum.photos/seed/1/300/200" alt="Gallery Image 1">
<img src="https://picsum.photos/seed/2/300/200" alt="Gallery Image 2">
<img src="https://picsum.photos/seed/3/300/200" alt="Gallery Image 3">
<img src="https://picsum.photos/seed/4/300/200" alt="Gallery Image 4">
</div>

<footer>© 2025 UMESHBHAI & Hardik Tournament | All Rights Reserved</footer>

<script>
// ===== TIMER WITH AUTO STOP & JOIN NOW DISABLE =====
let remainingTime = 60*60; // 1 hour
const timer = document.getElementById("timer");
const joinButtons = document.querySelectorAll(".match-btn");

const interval = setInterval(()=>{
  if(remainingTime < 0){
    clearInterval(interval);
    timer.innerHTML="⏰ Match Started!";
    joinButtons.forEach(btn=>{
      btn.classList.add("disabled");
      btn.innerHTML="Match Started";
    });
    return;
  }
  let m = Math.floor(remainingTime/60);
  let s = remainingTime % 60;
  s = s<10 ? "0"+s : s;
  timer.innerHTML = m+" Minutes "+s+" Seconds";
  remainingTime--;
},1000);
</script>

</body>
</html>
