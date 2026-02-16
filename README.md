<!DOCTYPE html>
<html lang="fa">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dragon Roleplay</title>

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:tahoma;
  scroll-behavior:smooth;
}

body{
  color:#222;
  background: linear-gradient(135deg, #fdfbfb, #ebedee);
  overflow-x:hidden;
}

/* ===== Preloader ===== */
#preloader{
  position:fixed;
  width:100%;
  height:100%;
  background:#fff;
  display:flex;
  justify-content:center;
  align-items:center;
  z-index:9999;
}

.loader{
  width:60px;
  height:60px;
  border:6px solid #1E90FF;
  border-top:6px solid transparent;
  border-radius:50%;
  animation:spin 1s linear infinite;
}

@keyframes spin{
  100%{transform:rotate(360deg);}
}

/* ===== Navbar ===== */
.navbar{
  position:fixed;
  top:0;
  width:100%;
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:10px 20px;
  background: rgba(255,255,255,0.95);
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  z-index:1000;
  border-radius: 0 0 15px 15px;
}

/* Hamburger Menu */
.menu-toggle{
  display:flex;
  flex-direction:column;
  gap:5px;
  cursor:pointer;
}

.menu-toggle div{
  width:30px;
  height:4px;
  background:#1E90FF;
  border-radius:2px;
  transition:0.3s;
}

/* Navbar Links */
.navbar ul{
  display:flex;
  gap:20px;
  list-style:none;
  transition:0.3s;
}

.navbar a{
  color:#1E90FF;
  text-decoration:none;
  font-weight:bold;
  padding:8px 15px;
  border-radius:8px;
  transition:0.3s;
  position:relative;
}

.navbar a:hover{
  background:#1E90FF;
  color:white;
}

/* For Mobile Menu */
.navbar ul.show{
  display:flex;
  flex-direction:column;
  background: rgba(255,255,255,0.95);
  position:absolute;
  top:50px;
  right:20px;
  padding:10px 20px;
  border-radius:8px;
  box-shadow:0 0 15px rgba(0,0,0,0.2);
}

/* ===== Hero ===== */
.hero{
  height:100vh;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
  background: linear-gradient(135deg, #FFFAE3, #FFE0B2);
  border-radius: 15px;
  padding: 0 20px;
}

.logo{
  color:#1E90FF;
  font-size:50px;
  font-weight:bold;
  text-shadow: 0 0 10px #1E90FF;
}

.btn{
  margin-top:20px;
  padding:15px 35px;
  background:#1E90FF;
  color:white;
  text-decoration:none;
  border-radius:15px;
  font-weight:bold;
  font-size:18px;
  box-shadow:0 0 20px #1E90FF, 0 0 40px #00BFFF;
  transition:0.3s;
}

.btn:hover{
  background:#00BFFF;
  box-shadow:0 0 30px #1E90FF, 0 0 60px #00BFFF;
  transform:scale(1.05);
}

.players{
  margin-top:20px;
  font-size:20px;
  color:#555;
}

/* ===== Sections ===== */
.section{
  padding:80px 20px;
  text-align:center;
  border-radius: 15px;
  margin:20px auto;
}

/* ===== Cards ===== */
.cards{
  display:flex;
  flex-wrap:wrap;
  justify-content:center;
  gap:20px;
  margin-top:40px;
}

.card{
  padding:25px;
  border-radius:10px;
  width:250px;
  color:white;
  font-weight:bold;
  transition:0.3s;
  box-shadow: 0 0 15px rgba(0,0,0,0.1);
}

.card.owner{background:#FF4500;}      /* نارنجی قرمز */
.card.scripter{background:#32CD32;}   /* سبز */

.card:hover{
  transform:translateY(-5px);
  box-shadow:0 0 25px rgba(0,0,0,0.2);
}

/* ===== Gallery Section ===== */
#gallery {
  padding:60px 20px;
  text-align:center;
}

.gallery-scroll{
  display:flex;
  overflow-x:auto;
  gap:20px;
  padding:20px 0;
  scroll-behavior: smooth;
}

.gallery-card{
  flex: 0 0 auto;
  background: rgba(255,255,255,0.2);
  padding:10px;
  border-radius:12px;
  overflow:hidden;
  transition:0.3s;
  width:300px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

.gallery-card img{
  width:100%;
  height:auto;
  border-radius:10px;
  transition:0.3s;
}

.gallery-card:hover{
  transform:scale(1.05);
  box-shadow:0 0 25px rgba(0,0,0,0.2);
}

/* ===== Server IP Section ===== */
#server-ip{
  padding:60px 20px;
  text-align:center;
  background:#FFF5E1;
  border-radius:15px;
  margin:40px 0;
}

#server-ip h2{
  color:#1E90FF;
}

#server-ip span{
  display:block;
  font-size:22px;
  margin-top:15px;
  color:#32CD32;
  font-weight:bold;
}

/* Footer */
footer{
  background:#FFD580;
  padding:20px;
  text-align:center;
  font-weight:bold;
  color:#1E90FF;
}

/* Responsive */
@media(max-width:768px){
  .cards{
    flex-direction:column;
    align-items:center;
  }
  .gallery-card{
    width:80%;
  }
}
<style>
/* کلی استایل‌های قبلی سایتت اینجاست */

/* ===== Neon Effects ===== */
.neon {
  box-shadow: 0 0 10px #00f, 0 0 20px #00f, 0 0 40px #00f;
}

/* دکمه‌ها */
.btn, button {
  background: linear-gradient(90deg,#00f,#0ff,#00f);
  box-shadow: 0 0 10px #00f, 0 0 20px #0ff, 0 0 40px #00f;
  animation: glow 1.5s infinite alternate;
}

@keyframes glow {
  from { box-shadow: 0 0 5px #00f, 0 0 15px #0ff; }
  to   { box-shadow: 0 0 15px #0ff, 0 0 35px #00f; }
}

/* لینک‌های منو */
.navbar a {
  box-shadow: 0 0 5px #1E90FF, 0 0 15px #00BFFF;
}

.navbar a:hover {
  box-shadow: 0 0 15px #00BFFF, 0 0 40px #1E90FF;
}

/* کارت‌ها */
.card {
  box-shadow: 0 0 15px rgba(0,255,255,0.4);
}

.card:hover {
  box-shadow: 0 0 25px #00ffff, 0 0 50px #1E90FF;
}

/* همبرگری */
.menu-toggle div {
  box-shadow: 0 0 10px #1E90FF, 0 0 20px #00BFFF;
}

/* گالری */
.gallery-card {
  box-shadow: 0 0 10px #1E90FF, 0 0 25px #00BFFF;
}

.gallery-card:hover {
  box-shadow: 0 0 25px #00ffff, 0 0 60px #1E90FF;
}
</style>
</style>
</head>
<body>

<div id="preloader">
  <div class="loader"></div>
</div>

<nav class="navbar">
  <div class="menu-toggle" id="menu-toggle">
    <div></div>
    <div></div>
    <div></div>
  </div>
  <ul id="nav-links">
    <li><a href="#home">خانه</a></li>
    <li><a href="#features">ویژگی‌ها</a></li>
    <li><a href="#team">مدیریت</a></li>
    <li><a href="#gallery">گالری</a></li>
    <li><a href="#server-ip">IP سرور</a></li>
    <li><a href="Shop.html">شاپ</a></li>
    <!-- لینک انجمن اضافه شد -->
    <li><a href="Froum-DragonRp.html">انجمن</a></li>
  </ul>
</nav>

<section id="home" class="hero">
  <h1 class="logo">DRAGON ROLEPLAY</h1>
  <h2><span id="typing"></span></h2>
  <a href="samp://127.0.0.1:7777" class="btn">🎮 Connect To Server</a>
  <div class="players">👥 Players Online: <span id="playerCount">10</span></div>
</section>

<section id="features" class="section">
  <h2>ویژگی‌های سرور</h2>
  <div class="cards">
    <div class="card" style="background:#1E90FF;">🚓 سیستم پلیس حرفه‌ای</div>
    <div class="card" style="background:#32CD32;">🏢 گتو و مافیا</div>
    <div class="card" style="background:#FFD700;">💰 اقتصاد واقعی</div>
    <div class="card" style="background:#FF69B4;">🏎 ماشین‌های سفارشی</div>
  </div>
</section>

<section id="team" class="section">
  <h2>تیم مدیریت</h2>
  <div class="cards">
    <div class="card owner">👑 Owner: Mr_Taha</div>
    <div class="card scripter">🛡 Scripter: Kurdx</div>
  </div>
</section>

<section id="gallery" class="section">
  <h2>گالری سرور</h2>
  <div class="gallery-scroll">
    <div class="gallery-card"><img src="https://via.placeholder.com/400x250.png?text=Server+Image+1" alt=""></div>
    <div class="gallery-card"><img src="https://via.placeholder.com/400x250.png?text=Server+Image+2" alt=""></div>
    <div class="gallery-card"><img src="https://via.placeholder.com/400x250.png?text=Server+Image+3" alt=""></div>
    <div class="gallery-card"><img src="https://via.placeholder.com/400x250.png?text=Server+Image+4" alt=""></div>
  </div>
</section>

<section id="server-ip">
  <h2>IP سرور</h2>
  <span>-- فعلاً خالی --</span>
</section>

<footer>
  Tavsot Tim Dragon Rp
</footer>

<script>
// Preloader
window.addEventListener("load", function(){
  document.getElementById("preloader").style.display = "none";
});

// Typing Effect
const text = "به بهترین سرور رول‌پلی ایران خوش آمدید";
let i = 0;
function typing(){
  if(i < text.length){
    document.getElementById("typing").innerHTML += text.charAt(i);
    i++;
    setTimeout(typing, 60);
  }
}
typing();

// Hamburger Menu Toggle
const menuToggle = document.getElementById('menu-toggle');
const navLinks = document.getElementById('nav-links');
menuToggle.addEventListener('click', () => {
  navLinks.classList.toggle('show');
});
// ===== Auto Scroll Gallery =====
const gallery = document.querySelector('.gallery-scroll');

let scrollAmount = 0;

setInterval(() => {
  scrollAmount += 320; // عرض هر عکس + فاصله
  if (scrollAmount >= gallery.scrollWidth - gallery.clientWidth) {
    scrollAmount = 0;
  }
  
  gallery.scrollTo({
    left: scrollAmount,
    behavior: "smooth"
  });
  
}, 5000); // هر 5 ثانیه
</script>
<!-- Music Player -->
<div id="music-player">
  <button id="music-btn">🔊</button>
</div>

<audio id="bg-music" autoplay loop>
  <source src="https://uploadkon.ir/uploads/898c16_26Unknown-artist-GTA-Songs-320-.mp3" type="audio/mpeg">
</audio>

<style>
#music-player{
  position:fixed;
  bottom:20px;
  left:20px;
  z-index:9999;
}

#music-btn{
  width:55px;
  height:55px;
  border-radius:50%;
  border:none;
  background:linear-gradient(135deg,#ff9800,#ff5722);
  color:white;
  font-size:22px;
  box-shadow:0 0 15px #ff9800, 0 0 30px #ff5722;
  cursor:pointer;
  transition:0.3s;
}

#music-btn:hover{
  transform:scale(1.1);
  box-shadow:0 0 25px #ff9800, 0 0 50px #ff5722;
}
</style>

<script>
const music = document.getElementById("bg-music");
const btn = document.getElementById("music-btn");

btn.addEventListener("click", () => {
  if(music.paused){
    music.play();
    btn.innerHTML = "🔊";
  } else {
    music.pause();
    btn.innerHTML = "🔇";
  }
});

// autoplay fix for mobile
document.body.addEventListener("click", () => {
  music.play();
},{ once:true });
</script>
</body>
</html>
