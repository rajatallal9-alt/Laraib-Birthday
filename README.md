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
  background-repeat: no-repeat;
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
.quote {
  font-style: italic;
  margin-top: 15px;
  font-size: 20px;
  color: #fff;
}
#sec1 { background-image: url('https://i.ibb.co/ZxP8tLw/birthday1.jpg'); font-size: 36px; color:#4b2e83; }
#sec2 { background-image: url('https://i.ibb.co/tMJ3xB3/birthday2.jpg'); }
#sec3 { background-image: url('https://i.ibb.co/2h5S1Hc/birthday3.jpg'); }
#sec4 { background-image: url('https://i.ibb.co/3f5v0Yb/birthday4.jpg'); }
#sec5 { background-image: url('https://i.ibb.co/yYb5g0G/birthday5.jpg'); }
#sec6 { background-image: url('https://i.ibb.co/2tX1WQZ/birthday6.jpg'); color: #333; }
#sec7 { background-image: url('https://i.ibb.co/0fQ5W9Z/birthday7.jpg'); color: #4b2e83; font-size: 48px; display:flex; justify-content:center; align-items:center; flex-direction: column; }
#sec8 { background-image: url('https://i.ibb.co/kD7wY8Z/birthday8.jpg'); color: #fff; font-size: 48px; display:flex; justify-content:center; align-items:center; flex-direction: column; }
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
  <div class="quote">"Aaj ka din waqai bohot khaas hai."</div>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec2" class="section hidden">
  <h2>Aap Jaisi Khoobsurat Insaan</h2>
  <p>آپ کے اخلاق، آپ کی سچائی، آپ کی نرمی اور آپ کی باریک حسِ جمال-آپ اُن چند لوگوں میں سے ہیں جو چہرے سے زیادہ دل کے خوبصورت ہوتے ہیں۔ </p>
  <div class="quote">"Aap jaisi achi, pyari, seedhi aur sachi insaan ko hamesha duniya ki sab se behtareen cheezein milni chahiye. Aapka ikhlaq, lehja aur soch aap ko sab se alag banati hain"</div>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec3" class="section hidden">
  <h2>Yaadein Jo Reh Gayi</h2>
  <p>آپ ہمیشہ سب کے لیے اچھا سوچنے والی، ہر ایک کے کام آنے والی، اور دوسروں کی خوشی میں خوش ہونے والی لڑکی ہیں۔</p>
  <div class="quote">"Mujhe abhi tak woh din yaad hai jab hum shed se wapis aa rahe thay aur barish ho rahi thi… aur mere mana karne ke bawajood ap ne pani me jump kiya."
<br>"Aur phir aap ke haath ka banaya hua pulao aur custard — abhi tak uski khushboo yaad aati hai."</div>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec4" class="section hidden">
  <h2>Aap Ki Aankhein</h2>
  <p>آپ کی آنکھیں—وہ گہرا سیاہ رنگ جو عام نہیں، ایک ایسے راز کی طرح ہے جو صرف خوبصورتی نہیں… گہرائی بھی رکھتا ہے۔</p>
  <div class="quote">"Aap ki aankhein woh gehra kaala rang jo na sirf khoobsurat hain balkay puri kainat in ma samai hoi ha."
<br>"Aap ki aankhon me koi ajeeb si khamosh chamak hai jo dekhne wale ko rok leti hai."</div>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec5" class="section hidden">
  <h2>Duaen & Motivation</h2>
  <p>میں دعا کرتا ہوں کہ اللہ تعالیٰ آپ کی زندگی کو آسانیوں سے بھر دے۔</p>
  <div class="quote">"Main dua karta hoon ke Allah aap ke tamam goals aasaan kar de."
<br>"Aap jahan bhi jaayein, izzat, mohabbat aur achi niyat wale log milain. Aapka dil hamesha halka aur khush rahe. Laraib… aap intelligent aur sincere hain."
<br>"Jahan niyat saaf hoti hai, wahan raasta ban hi jaata hai."
<br>"Aap kamzor nahi — bas nazuk dil ki hain. Aur nazuk dil wale hi asli strong hote hain."</div>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec6" class="section hidden">
  <h2>End Note</h2>
  <p> اللہ آپ کو خوشیوں، مسکراہٹوں، کامیابیوں اور محبتوں سے نوازے۔ </p>
  <p>Happy Birthday once again, Laraib! Allah kare yeh saal aap ki zindagi ka sab se behtareen saal ho. Aap hamesha muskurayein, chamkain aur khush rahein.</p>
  <audio id="bgMusic" src="ma_agar_kahon_tum_sa_haseen.mp3" loop autoplay></audio>
  <button class="btn-next" onclick="nextSection()">Next</button>
</div>

<div id="sec7" class="section hidden">
  <div id="happyText">Happy Birthday Laraib!</div>
  <img id="cake" src="https://i.ibb.co/F5bT63F/cake.png" alt="cake">
  <audio id="finalMusic" src="happy_birthday_song.mp3"></audio>
</div>

<div id="sec8" class="section hidden">
  <div id="happyTextFinal">Happy Birthday Laraib!</div>
  <img id="cakeFinal" src="https://i.ibb.co/F5bT63F/cake.png" alt="cake">
  <audio id="finalMusicPlay" src="happy_birthday_song.mp3" autoplay></audio>
</div>

<script>
let current = 1;
function nextSection() {
  document.getElementById('sec' + current).classList.remove('active');
  document.getElementById('sec' + current).classList.add('hidden');
  current++;
  if(current <= 8){
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
    if(current === 8){
      const finalPlay = document.getElementById('finalMusicPlay');
      finalPlay.play();
      setTimeout(()=>{
        finalPlay.pause();
        document.getElementById('happyTextFinal').style.opacity = '0';
      }, 5000);
    }
  }
}
</script>

</body>
</html>
