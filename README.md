<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Happy Birthday Laraib — Card</title>
<style>
  :root{
    --accent-1: #8b2eff;
    --accent-2: #4b2e83;
    --card-bg: #fff7ff;
  }

  html,body{
    height:100%;
    margin:0;
    font-family: "Segoe UI", Roboto, Arial, sans-serif;
    background: linear-gradient(180deg,#f8f0ff 0%, #fff 60%), url('assets/bg.jpg') center/cover no-repeat;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    color:#222;
    overflow:hidden;
  }

  /* Generic layout for full-screen sections */
  .section {
    position:absolute;
    inset:0;
    display:flex;
    justify-content:center;
    align-items:center;
    padding:20px;
    box-sizing:border-box;
    opacity:0;
    transform: translateY(24px);
    transition: opacity .6s ease, transform .6s ease;
    pointer-events:none;
  }
  .section.active{
    opacity:1;
    transform: translateY(0);
    pointer-events:auto;
    z-index:5;
  }

  /* Envelope container */
  .card-wrap{
    width:100%;
    max-width:760px;
    display:flex;
    flex-direction:column;
    align-items:center;
    gap:18px;
  }

  /* ENVELOPE (pure CSS) */
  .envelope {
    width: 360px;
    max-width: 86%;
    height: 220px;
    position: relative;
    perspective: 1200px;
  }

  /* Back of envelope / body */
  .envelope .body {
    position:absolute;
    inset:0;
    border-radius:10px;
    background: linear-gradient(180deg, #fff, #fff7fb);
    box-shadow: 0 12px 40px rgba(20,10,60,0.16);
    overflow:visible;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:18px;
    box-sizing:border-box;
  }

  /* Flap (front triangle) */
  .envelope .flap {
    position:absolute;
    top:0;
    left:0;
    width:100%;
    height:62%;
    transform-origin: top center;
    background: linear-gradient(180deg,#ffd7f6,#ffecff);
    border-top-left-radius:12px;
    border-top-right-radius:12px;
    box-shadow: 0 12px 30px rgba(120,60,160,0.12);
    transform-style: preserve-3d;
    transition: transform .8s cubic-bezier(.2,.9,.3,1);
    backface-visibility: hidden;
    z-index:8;
    display:flex;
    align-items:flex-end;
    justify-content:center;
  }

  /* Small decorative stripe on flap */
  .envelope .flap::after{
    content:"";
    display:block;
    width:80%;
    height:24px;
    margin-bottom:20px;
    background: linear-gradient(90deg, rgba(75,46,131,0.08), rgba(139,46,255,0.12));
    border-radius:6px;
    opacity:.9;
  }

  /* Letter inside envelope */
  .envelope .letter {
    position:absolute;
    left:8%;
    width:84%;
    height:78%;
    top:12%;
    background: linear-gradient(180deg,#fff,#fffefc);
    border-radius:6px;
    box-shadow: 0 6px 20px rgba(30,10,60,0.06);
    transform-origin: bottom center;
    transform: translateY(24px) scale(.98);
    opacity:0;
    transition: transform .8s cubic-bezier(.2,.9,.3,1), opacity .6s;
    padding:18px;
    box-sizing:border-box;
    z-index:6;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
  }

  /* When envelope is opened */
  .envelope.opened .flap {
    transform: rotateX(-180deg) translateY(-6%);
  }
  .envelope.opened .letter {
    transform: translateY(-6px) scale(1);
    opacity:1;
  }

  /* Message content inside the letter */
  .card-content{
    text-align:center;
    color:var(--accent-2);
  }
  .card-content h1{
    margin:0 0 6px 0;
    font-size:22px;
    letter-spacing:.2px;
  }
  .card-content p{
    margin:0;
    font-size:16px;
    line-height:1.45;
    color:#333;
  }

  /* Buttons */
  .controls{
    display:flex;
    gap:12px;
    margin-top:6px;
  }
  .btn{
    appearance:none;
    border:0;
    padding:10px 18px;
    border-radius:10px;
    background:linear-gradient(90deg,var(--accent-1), #5b18d6);
    color:#fff;
    cursor:pointer;
    font-size:16px;
    box-shadow: 0 6px 18px rgba(91,24,214,0.18);
  }
  .btn.secondary{
    background:transparent;
    color:var(--accent-2);
    box-shadow:none;
    border:1px solid rgba(75,46,131,0.08);
  }

  /* Small helpers for final section (cake & knife) */
  #cake { max-width:40%; width:260px; transition: transform .4s ease; border-radius:14px; }
  #knife { width:110px; position:absolute; left:-200px; top:46%; transform:rotate(-18deg); transition:left .7s, transform .4s; opacity:0; }

  /* Confetti pieces */
  .confetti { position:fixed; width:10px; height:14px; z-index:9999; pointer-events:none; }

  /* Responsive */
  @media (max-width:480px){
    .envelope{ height:200px; }
    .card-content h1{ font-size:18px; }
    .card-content p{font-size:15px;}
    #cake{ width:180px; }
    #knife{ width:70px; }
  }
</style>
</head>
<body>

<!-- Section 1 -->
<section id="sec1" class="section active" aria-label="Card 1">
  <div class="card-wrap">
    <div class="envelope" data-index="1" aria-hidden="false">
      <div class="flap" aria-hidden="true"></div>
      <div class="letter" role="article" aria-labelledby="title1">
        <div class="card-content">
          <h1 id="title1">✨ Happy Birthday, Laraib!</h1>
          <p>آج کا دن آپ کے لیے روشنیوں سے بھرا ہوا ہے — aaj ka din waqai bohot khaas hai.</p>
        </div>
      </div>
      <div class="body" aria-hidden="true"></div>
    </div>

    <div class="controls">
      <button class="btn" onclick="openEnvelope(1)">Open Card</button>
      <button class="btn secondary" onclick="skipOpen(1)">Skip</button>
    </div>
  </div>
</section>

<!-- Section 2 -->
<section id="sec2" class="section" aria-label="Card 2">
  <div class="card-wrap">
    <div class="envelope" data-index="2">
      <div class="flap"></div>
      <div class="letter" role="article" aria-labelledby="title2">
        <div class="card-content">
          <h1 id="title2">🌼 Aap Jaisi Khoobsurat Insaan</h1>
          <p>Aap jaisi achi, pyari, seedhi aur sachi insaan ko hamesha duniya ki sab se behtareen cheezein milni chahiye.</p>
        </div>
      </div>
      <div class="body"></div>
    </div>

    <div class="controls">
      <button class="btn" onclick="openEnvelope(2)">Open Card</button>
      <button class="btn secondary" onclick="skipOpen(2)">Skip</button>
    </div>
  </div>
</section>

<!-- Section 3 -->
<section id="sec3" class="section" aria-label="Card 3">
  <div class="card-wrap">
    <div class="envelope" data-index="3">
      <div class="flap"></div>
      <div class="letter" role="article" aria-labelledby="title3">
        <div class="card-content">
          <h1 id="title3">📸 Yaadein Jo Reh Gayi</h1>
          <p>Mujhe abhi tak woh din yaad hai jab hum shed se wapis aa rahe thay aur barish ho rahi thi. Aap ne paani me jump kiya — woh masoomiyat hamesha yaad rahegi.</p>
        </div>
      </div>
      <div class="body"></div>
    </div>

    <div class="controls">
      <button class="btn" onclick="openEnvelope(3)">Open Card</button>
      <button class="btn secondary" onclick="skipOpen(3)">Skip</button>
    </div>
  </div>
</section>

<!-- Section 4 -->
<section id="sec4" class="section" aria-label="Card 4">
  <div class="card-wrap">
    <div class="envelope" data-index="4">
      <div class="flap"></div>
      <div class="letter" role="article" aria-labelledby="title4">
        <div class="card-content">
          <h1 id="title4">✨ Aap Ki Aankhein</h1>
          <p>Aap ki aankhein gehra kaala rang rakhti hain — unme narmi aur kahaniyan hain jo dil ko chhoo jati hain.</p>
        </div>
      </div>
      <div class="body"></div>
    </div>

    <div class="controls">
      <button class="btn" onclick="openEnvelope(4)">Open Card</button>
      <button class="btn secondary" onclick="skipOpen(4)">Skip</button>
    </div>
  </div>
</section>

<!-- Section 5 -->
<section id="sec5" class="section" aria-label="Card 5">
  <div class="card-wrap">
    <div class="envelope" data-index="5">
      <div class="flap"></div>
      <div class="letter" role="article" aria-labelledby="title5">
        <div class="card-content">
          <h1 id="title5">🤲 Duaen & Motivation</h1>
          <p>Main dua karta hoon ke Allah aap ke tamam goals aasaan kare. Jahan niyat saaf hoti hai, wahan raasta ban hi jaata hai.</p>
        </div>
      </div>
      <div class="body"></div>
    </div>

    <div class="controls">
      <button class="btn" onclick="openEnvelope(5)">Open Card</button>
      <button class="btn secondary" onclick="skipOpen(5)">Skip</button>
    </div>
  </div>
</section>

<!-- Section 6 (End Note, will start bg music when opened) -->
<section id="sec6" class="section" aria-label="Card 6">
  <div class="card-wrap">
    <div class="envelope" data-index="6">
      <div class="flap"></div>
      <div class="letter" role="article" aria-labelledby="title6">
        <div class="card-content">
          <h1 id="title6">🎂 End Note</h1>
          <p>Happy Birthday once again, Laraib! Allah kare yeh saal aap ki zindagi ka sab se behtareen saal ho. Aap hamesha muskurayein.</p>
        </div>
      </div>
      <div class="body"></div>
    </div>

    <div class="controls">
      <button class="btn" onclick="openEnvelope(6, {startBg:true})">Open Card</button>
      <button class="btn secondary" onclick="skipOpen(6)">Skip</button>
    </div>
  </div>

  <audio id="bgMusic" src="assets/ma_agar_kahon_tum_sa_haseen.mp3" loop preload="auto" aria-hidden="true"></audio>
</section>

<!-- Final Section with cake & cut -->
<section id="sec7" class="section" aria-label="Final surprise">
  <div class="card-wrap" style="align-items:center">
    <div class="envelope" data-index="7">
      <div class="flap"></div>
      <div class="letter" role="article" aria-labelledby="title7">
        <div class="card-content">
          <h1 id="title7">🎉 Surprise!</h1>
          <p>Click <strong>Open</strong> and then press <strong>Cut Cake</strong> to celebrate 🎂</p>
        </div>
      </div>
      <div class="body"></div>
    </div>

    <div class="controls" style="margin-bottom:14px;">
      <button class="btn" onclick="openEnvelope(7)">Open Card</button>
      <button class="btn secondary" onclick="skipOpen(7)">Skip</button>
    </div>

    <div style="position:relative; width:100%; display:flex; justify-content:center; align-items:center; gap:18px;">
      <img id="knife" src="assets/knife.png" alt="" aria-hidden="true" />
      <img id="cake" src="assets/cake.png" alt="Birthday cake" />
    </div>

    <div style="margin-top:16px;">
      <button id="cutBtn" class="btn" onclick="cutCake()">Cut Cake 🎂</button>
    </div>

    <audio id="finalMusic" src="assets/happy_birthday_song.mp3" preload="auto" aria-hidden="true"></audio>
    <audio id="sliceSound" src="assets/cake_cut.mp3" preload="auto" aria-hidden="true"></audio>
  </div>
</section>

<script>
  // Section navigation + envelope logic
  const totalSections = 7;
  let current = 1;
  let bgStarted = false;

  // Show a section by index (1..totalSections)
  function showSection(i){
    for(let s=1;s<=totalSections;s++){
      const el = document.getElementById('sec'+s);
      if(!el) continue;
      if(s === i) el.classList.add('active');
      else el.classList.remove('active');
    }
    current = i;
  }

  // Called when user clicks "Open Card" for a section
  function openEnvelope(idx, opts = {}){
    const env = document.querySelector(`#sec${idx} .envelope`);
    if(!env) return;
    // start background music if requested
    if(opts.startBg && !bgStarted){
      const bg = document.getElementById('bgMusic');
      if(bg){
        bg.play().catch(()=>{}); // user gesture should allow play
        bgStarted = true;
      }
    }
    // animate: add 'opened' class
    env.classList.add('opened');

    // After opening, show Next button (we will replace "Open/Skip" with "Next")
    const controls = env.closest('.card-wrap').querySelector('.controls');
    if(controls){
      // replace controls with a Next button after a small delay so the letter appears first
      setTimeout(()=>{
        controls.innerHTML = `<div><button class="btn" onclick="goNext(${idx})">Next →</button></div>`;
      }, 700);
    }
  }

  // Skip opening - directly reveal content and go to Next controls
  function skipOpen(idx){
    const env = document.querySelector(`#sec${idx} .envelope`);
    if(env) env.classList.add('opened');
    const controls = env.closest('.card-wrap').querySelector('.controls');
    if(controls){
      controls.innerHTML = `<div><button class="btn" onclick="goNext(${idx})">Next →</button></div>`;
    }
  }

  // Go to next section (or finish)
  function goNext(fromIdx){
    let next = fromIdx + 1;
    if(next > totalSections) next = totalSections;
    showSection(next);
    // If landing page has bg music element and not started, we won't autoplay unless user opens
  }

  // Final section: cake cutting
  function cutCake(){
    const knife = document.getElementById('knife');
    const cake = document.getElementById('cake');
    const slice = document.getElementById('sliceSound');
    const final = document.getElementById('finalMusic');

    // animate knife in
    knife.style.opacity = '1';
    knife.style.left = '50%';
    knife.style.transform = 'translateX(-160px) rotate(-8deg)';

    setTimeout(()=>{
      // sound and cake swap
      if(slice){ slice.currentTime = 0; slice.play().catch(()=>{}); }
      cake.style.transform = 'scale(.96)';
      setTimeout(()=>{
        cake.src = 'assets/cake-sliced.png';
        cake.style.transform = 'scale(1)';
      }, 240);
    }, 700);

    // confetti & final music
    setTimeout(()=>{
      if(final){ final.currentTime = 0; final.play().catch(()=>{}); }
      launchConfetti(50);
    }, 1100);

    // hide knife after animation
    setTimeout(()=>{
      knife.style.opacity = '0';
      knife.style.left = '-200px';
    }, 2200);

    // disable cut button
    const btn = document.getElementById('cutBtn');
    if(btn){ btn.disabled = true; btn.style.opacity = .7; }
  }

  // Simple confetti generator
  function launchConfetti(n){
    const colors = ['#f94144','#f3722c','#f9c74f','#90be6d','#577590','#b983ff','#ffb3c6'];
    for(let i=0;i<n;i++){
      const el = document.createElement('div');
      el.className = 'confetti';
      el.style.left = (Math.random()*100)+'vw';
      el.style.background = colors[Math.floor(Math.random()*colors.length)];
      el.style.transform = `rotate(${Math.random()*360}deg)`;
      el.style.width = (6+Math.random()*18)+'px';
      el.style.height = (8+Math.random()*18)+'px';
      el.style.top = '-20px';
      el.style.opacity = 1;
      el.style.transition = `transform ${2+Math.random()*1.0}s cubic-bezier(.2,.9,.3,1), top ${2+Math.random()*1.0}s linear, opacity 1s ease`;
      document.body.appendChild(el);
      // animate by setting properties after append
      setTimeout(()=>{
        el.style.top = (70+Math.random()*35)+'vh';
        el.style.transform = `translateY(${120+Math.random()*60}vh) rotate(${Math.random()*720}deg)`;
      }, 30);
      // remove
      setTimeout(()=> el.remove(), 4200);
    }
  }

  // Keyboard navigation: when letter already opened, Next arrow moves forward
  document.addEventListener('keydown', (e)=>{
    if(e.key === 'ArrowRight' || e.key === ' '){
      // find if current section has a Next button visible
      const controls = document.querySelector(`#sec${current} .controls`);
      if(controls && controls.querySelector('button')){
        controls.querySelector('button').click();
      } else {
        // otherwise try to open envelope
        const openBtn = document.querySelector(`#sec${current} .controls .btn`);
        if(openBtn) openBtn.click();
      }
    }
    if(e.key === 'ArrowLeft'){
      // go previous
      const prev = Math.max(1, current-1);
      showSection(prev);
    }
  });

  // Ensure the first section's "Open" is ready (already visible by markup)
  // Helper: if the user reloads, ensure only one section active
  (function init(){
    showSection(1);
  })();
</script>
</body>
</html>
