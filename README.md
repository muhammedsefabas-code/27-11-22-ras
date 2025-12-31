# 27-11-22-ras
https://kullaniciadi.github.io/27-11-22-rase
[yeni_yil_surprizi (1).html](https://github.com/user-attachments/files/24394570/yeni_yil_surprizi.1.html)
<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mutlu Yıllar ❤️</title>
<style>
body{
  margin:0;
  font-family:Arial,Helvetica,sans-serif;
  background:linear-gradient(135deg,#ff758c,#ff7eb3);
  color:white;
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  overflow:hidden;
}
.card{
  background:rgba(0,0,0,0.25);
  padding:35px;
  border-radius:20px;
  text-align:center;
  max-width:420px;
  z-index:2;
}
.heart{font-size:3rem;animation:pulse 1.5s infinite;}
@keyframes pulse{0%{transform:scale(1)}50%{transform:scale(1.2)}100%{transform:scale(1)}}
button{
  margin-top:20px;
  padding:12px 25px;
  border:none;
  border-radius:30px;
  cursor:pointer;
  font-size:1rem;
  background:#fff;
  color:#ff4f7a;
}
#countdown{margin-top:15px;font-size:1.1rem;}
.snow{
  position:fixed;
  top:-10px;
  color:white;
  animation:fall linear infinite;
}
@keyframes fall{to{transform:translateY(110vh)}}
.modal{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,0.7);
  display:none;
  justify-content:center;
  align-items:center;
  z-index:5;
}
.modal-content{
  background:#fff;
  color:#333;
  padding:20px;
  border-radius:20px;
  max-width:300px;
  text-align:center;
}
.modal-content img{width:100%;border-radius:15px;margin-bottom:10px}
</style>
</head>
<body>
<div class="card">
  <h1>Mutlu Yıllar ❤️</h1>
  <div class="heart">❤️</div>
  <p>
    Nice beraber uzun yıllara sevgilim.<br>
    İnşallah 2026 bize çok iyi gelir.<br>
    Senin için her şeyimi, her an, her zaman veririm.<br>
    Tek mutluluğum sensin.<br>
    Seni çok seviyorum.<br>
    Mutlu yıllar 🎆
  </p>
  <div id="countdown"></div>
  <button onclick="openSurprise()">Bana Tıkla</button>
</div>

<div class="modal" id="modal">
  <div class="modal-content">
    <img src="photo.jpg" alt="Biz">
    <p>Seni çok seviyorum ❤️<br>İyi ki varsın, hep benimle ol.</p>
    <button onclick="closeSurprise()">Kapat</button>
  </div>
</div>

<audio id="music" loop>
  <source src="music.mp3" type="audio/mpeg">
</audio>

<script>
// geri sayım
const target=new Date('2026-01-01T00:00:00');
const cd=document.getElementById('countdown');
setInterval(()=>{
  const now=new Date();
  const d=target-now;
  if(d<=0){cd.innerHTML='🎉 MUTLU YILLAR 2026 🎉';return;}
  const g=Math.floor(d/86400000);
  const s=Math.floor(d/3600000)%24;
  const dk=Math.floor(d/60000)%60;
  const sn=Math.floor(d/1000)%60;
  cd.innerHTML=`${g}g ${s}s ${dk}d ${sn}s`;
},1000);

// kar yağışı
setInterval(()=>{
  const snow=document.createElement('div');
  snow.className='snow';
  snow.innerHTML='❄️';
  snow.style.left=Math.random()*100+'vw';
  snow.style.animationDuration=2+Math.random()*3+'s';
  document.body.appendChild(snow);
  setTimeout(()=>snow.remove(),5000);
},200);

// sürpriz
function openSurprise(){
  document.getElementById('modal').style.display='flex';
  document.getElementById('music').play();
}
function closeSurprise(){
  document.getElementById('modal').style.display='none';
}
</script>
</body>
</html>
