<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Laraib</title>
<style>
html, body {
  margin: 0;
  padding: 0;
  height: 100%;
  font-family: 'Arial', sans-serif;
  overflow: hidden;
  background: #f0e6f7;
}
.section {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: #333;
  padding: 20px;
  position: absolute;
  top: 0;
  left: 0;
  opacity: 0;
  transition: opacity 1s, transform 1s;
  font-size: 24px;
  background-size: cover;
  background-position: center;
}
.active {
  opacity: 1;
  transform: translateY(0);
  z-index: 2;
}
.hidden {
  transform: translateY(50px);
}
.btn-next {
  margin-top: 40px;
  padding: 14px 28px;
  border: none;
  border-radius: 8px;
  background: #8b2eff;
  color: #fff;
  font-size: 18px;
  cursor: pointer;
}
#sec1 { background-color: #ffccf9; font-size: 36px; color:#4b2e83; }
#sec2 { background-color: #ffb3c6; color: #fff; }
#sec3 { background-color: #ffd6a5; color: #fff; }
#sec4 { background-color: #a0e7e5; color: #fff; }
#sec5 { background-color: #b4f8c8; color: #fff; }
#sec6 { background-color: #fef9c3; color: #333; }
#sec7 { background-color: #ffedbc; color: #4b2e83; font-size: 48px; display:flex; justify-content:center; align-items:center; }
#happyText {
  animation: fadeText 5s forwards;
}
@keyframes fadeText {
  0% {opacity: 1;}
  100% {opacity: 0;}
}
#cake {
  width: 200px;
  animation: cakeCut 2s ease-in-out infinite alternate;
  margin-top: 20px;
}
@keyframes cakeCut {
  0% { transform: scale(1); }
  50% { transform: scale(0.9) rotate(-5deg); }
  100% { transform: scale(1); }
}
</style>
</head>
<body>

<div id="sec1" class="section active">
  <h1>✨ Happy Birthday, Laraib! ✨</h1>
  <p>آج کا دن آپ کے لیے روشنیوں سے بھرا ہوا ہے، Laraib—</p>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec2" class="section hidden">
  <h2>Aap Jaisi Khoobsurat Insaan</h2>
  <p>آپ اُن چند لوگوں میں سے ہیں جو چہرے سے زیادہ دل کے خوبصورت ہوتے ہیں۔</p>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec3" class="section hidden">
  <h2>Yaadein Jo Reh Gayi</h2>
  <p>آپ کے اخلاق، آپ کی سچائی، آپ کی نرمی اور آپ کی باریک حسِ جمال…</p>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec4" class="section hidden">
  <h2>Aap Ki Aankhein</h2>
  <p>آپ کی آنکھیں—وہ گہرا سیاہ رنگ جو عام نہیں، ایک ایسے راز کی طرح ہے جو صرف خوبصورتی نہیں… گہرائی بھی رکھتا ہے۔</p>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec5" class="section hidden">
  <h2>Duaen & Motivation</h2>
  <p>میں دعا کرتا ہوں کہ اللہ تعالیٰ آپ کی زندگی کو آسانیوں سے بھر دے۔</p>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec6" class="section hidden">
  <h2>End Note</h2>
  <p>Happy Birthday once again, Laraib! اللہ آپ کو خوشیوں، مسکراہٹوں، کامیابیوں اور محبتوں سے نوازے۔</p>
  <audio id="bgMusic" src="ma_agar_kahon_tum_sa_haseen.mp3" loop autoplay></audio>
</div>

<div id="sec7" class="section hidden">
  <div id="happyText">Happy Birthday Laraib!</div>
  <img id="cake" src="https://i.ibb.co/F5bT63F/cake.png" alt="cake">
  <audio id="finalMusic" src="happy_birthday_song.mp3"></audio>
</div>

<script>
let current = 1;
function nextSection() {
  document.getElementById('sec' + current).classList.remove('active');
  document.getElementById('sec' + current).classList.add('hidden');
  current++;
  if(current <= 7){
    document.getElementById('sec' + current).classList.add('active');
    document.getElementById('sec' + current).classList.remove('hidden');
    if(current === 7){
      const finalMusic = document.getElementById('finalMusic');
      finalMusic.play();
      document.getElementById('happyText').style.opacity = '1';
      setTimeout(()=>{
        finalMusic.pause();
        document.getElementById('happyText').style.opacity = '0';
      }, 5000);
    }
  }
}
</script>

</body>
</html>
