<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Happy Birthday — Open ❤️</title>
  <style>
    :root{--bg:#0f172a;--card:#0b1220;--accent:#ff6b81;--accent2:#ffd166}
    *{box-sizing:border-box}
    body{margin:0;font-family:system-ui,-apple-system,Segoe UI,Roboto,'Helvetica Neue',Arial;background:linear-gradient(180deg,#061021 0%,#0b1a2b 100%);color:#fff;min-height:100vh;display:flex;align-items:center;justify-content:center;padding:20px}
    .card{width:100%;max-width:920px;background:linear-gradient(180deg,rgba(255,255,255,0.04),rgba(255,255,255,0.02));border-radius:18px;padding:28px;box-shadow:0 10px 30px rgba(2,6,23,0.6);position:relative;overflow:hidden}
    header{display:flex;gap:18px;align-items:center}
    .photo{width:120px;height:120px;border-radius:14px;flex:0 0 120px;background:linear-gradient(135deg,var(--accent),var(--accent2));display:grid;place-items:center;font-weight:700;font-size:18px;color:#071022}
    .content{flex:1}
    h1{margin:0;font-size:30px;letter-spacing:0.4px}
    p.lead{margin:8px 0 18px;color:#d6e7ffcc}
    .message{background:linear-gradient(180deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));padding:16px;border-radius:12px;border:1px solid rgba(255,255,255,0.03)}
    .message p{margin:0;font-size:16px}
    .controls{display:flex;gap:8px;margin-top:14px}
    .btn{background:transparent;border:1px solid rgba(255,255,255,0.06);padding:8px 12px;border-radius:10px;color:#fff;cursor:pointer}
    .btn.primary{background:linear-gradient(90deg,var(--accent),#ff8aa6);border:none;color:#071022;font-weight:700}
    .small{font-size:13px;color:#a8c5ffcc}

    /* balloons */
    .balloon{position:absolute;bottom:-120px;width:60px;height:80px;border-radius:30px;opacity:0.95}
    .balloon:after{content:'';position:absolute;left:50%;transform:translateX(-50%);bottom:-18px;width:2px;height:26px;background:linear-gradient(180deg,rgba(255,255,255,0.3),transparent);}
    .b1{left:8%;background:linear-gradient(180deg,#ffd166,#ff6b81);animation:float 9s ease-in-out infinite}
    .b2{left:22%;background:linear-gradient(180deg,#8bf5ff,#6b8cff);animation:float 11s ease-in-out -2s infinite}
    .b3{right:18%;background:linear-gradient(180deg,#d6ffb3,#66e0aa);animation:float 10s ease-in-out -1s infinite}
    .b4{right:6%;background:linear-gradient(180deg,#ff9bd6,#ffd166);animation:float 12s ease-in-out -3s infinite}
    @keyframes float{0%{transform:translateY(0) }50%{transform:translateY(-220px) rotate(-6deg)}100%{transform:translateY(0) rotate(0deg)}}

    /* confetti */
    .confetti-piece{position:absolute;will-change:transform,opacity;opacity:0}

    /* responsive */
    @media (max-width:640px){header{flex-direction:column;align-items:flex-start}.photo{width:96px;height:96px}h1{font-size:22px}}
  </style>
</head>
<body>
  <div class="card" id="card">
    <div class="balloon b1"></div>
    <div class="balloon b2"></div>
    <div class="balloon b3"></div>
    <div class="balloon b4"></div>

    <header>
      <div class="photo" id="photo"> <img src="kuttiya.jpeg" width="120" height="150">
      </div>
      <div class="content">
        <h1 id="title">Happy Birthday, <span id="name">kuttiya😊</span> 🎉</h1>
        <p class="lead" id="subtitle">Wishing you a day full of love, laughter and your favourite cake.</p>
        <div class="message" id="message">
          <p>To my dearest <strong id="name2">kuttiya😊</strong>,<br>I hope this year brings you all the joy you bring me every day. Love you forever.</p>
        </div>
        <div class="controls">
          <button class="btn primary" id="playBtn">Play tune & confetti</button>
          <button class="btn" id="downloadBtn">Download as image</button>
          
        </div>
        
      </div>
    </header>
  </div>

  <template id="confetti-template">
    <div class="confetti-piece"></div>
  </template>

  <div style="display:none" id="editor">
    <label>Name: <input id="inpName" value="kuttiya😊"></label>
        `<svg xmlns='http://www.w3.org/2000/svg' width='900' height='600'><foreignObject width='100%' height='100%'>`+
          document.getElementById('card').outerHTML+
          `</foreignObject></svg>`);
        const img = new Image();
        img.onload = ()=>{
          const c = document.createElement('canvas'); c.width=img.width; c.height=img.height; const ctx=c.getContext('2d'); ctx.fillStyle='#061021'; ctx.fillRect(0,0,c.width,c.height); ctx.drawImage(img,0,0);
          const a = document.createElement('a'); a.href = c.toDataURL('image/png'); a.download = `happy-birthday.png`; a.click();
        };
        img.src = svg;
      }catch(err){ alert('Download failed — try taking a screenshot.'); }
    });

    // small accessibility: keyboard trigger
    document.addEventListener('keydown',(e)=>{ if(e.key==='Enter'){ document.getElementById('playBtn').click(); } });

  </script>
</body>
</html>    <label>Short message: <input id="inpShort" value="Wishing you a day full of love, laughter and your favourite cake."></label>
    <label>Long message:<br><textarea id="inpLong">To my dearest Angel,\nI hope this year brings you all the joy you bring me every day. Love you forever.</textarea></label>
    <label>Upload photo: <input id="inpFile" type="file" accept="image/*"></label>
  </div>

  <script>
    // Simple confetti generator
    const card = document.getElementById('card');
    const confettiTpl = document.getElementById('confetti-template');
    function spawnConfetti(count=40){
      for(let i=0;i<count;i++){
        const el = confettiTpl.content.firstElementChild.cloneNode(true);
        const size = Math.random()*10+6;
        el.style.width = size + 'px';
        el.style.height = size + 'px';
        el.style.left = (Math.random()*90) + '%';
        el.style.top = '-20px';
        el.style.background = `linear-gradient(180deg, hsl(${Math.random()*360} 90% 60%), hsl(${Math.random()*360} 70% 40%))`;
        el.style.transform = `rotate(${Math.random()*360}deg)`;
        el.style.opacity = 1;
        el.style.transition = 'transform 3s ease-out, top 3s ease-in, opacity 1s 2s';
        card.appendChild(el);
        requestAnimationFrame(()=>{
          el.style.top = (80 + Math.random()*40) + '%';
          el.style.transform = `translateY(${200+Math.random()*200}px) rotate(${Math.random()*720}deg) scale(${0.6+Math.random()*1.2})`;
        });
        setTimeout(()=>{ el.style.opacity=0; el.remove(); },4500);
      }
    }

    // Tiny "Happy Birthday" tune using WebAudio
    function playSimpleTune(){
      const ctx = new (window.AudioContext || window.webkitAudioContext)();
      const notes = [  660,660,0,660,0,520,660,0,780,0,390 ]; // simplified motif
      let t = ctx.currentTime + 0.05;
      for(let i=0;i<notes.length;i++){
        const n = notes[i];
        const dur = (n===0)?0.12:0.24;
        if(n>0){
          const o = ctx.createOscillator();
          const g = ctx.createGain();
          o.type='sine'; o.frequency.value = n;
          g.gain.value = 0.0001;
          o.connect(g); g.connect(ctx.destination);
          o.start(t);
          g.gain.exponentialRampToValueAtTime(0.12,t+0.02);
          g.gain.exponentialRampToValueAtTime(0.0001,t+dur);
          o.stop(t+dur+0.02);
        }
        t += dur;
      }
    }

    document.getElementById('playBtn').addEventListener('click', ()=>{ spawnConfetti(60); playSimpleTune(); });

    // Simple customize dialog
    document.getElementById('customizeBtn').addEventListener('click', ()=>{
      const name = prompt('Name for the birthday wish (e.g. Angel):', document.getElementById('name').textContent) || 'Angel';
      const shortMsg = prompt('Short subtitle text:', document.getElementById('subtitle').textContent) || '';
      const longMsg = prompt('Long message (\n for new lines):', document.getElementById('message').innerText.replace(/\n/g,'\\n')) || '';
      if(name){ document.getElementById('name').textContent = name; document.getElementById('name2').textContent = name; }
      if(shortMsg) document.getElementById('subtitle').textContent = shortMsg;
      if(longMsg) document.getElementById('message').innerHTML = '<p>'+longMsg.replace(/\\n/g,'<br>')+'</p>';
      // ask to upload photo
      if(confirm('Would you like to add a photo from your computer?')){
        document.getElementById('inpFile').click();
      }
    });

    // handle file input to replace photo
    const inpFile = document.getElementById('inpFile');
    inpFile.addEventListener('change', (e)=>{
      const f = e.target.files[0];
      if(!f) return;
      const r = new FileReader();
      r.onload = ()=>{ document.getElementById('photo').style.background = `url(${r.result}) center/cover`; document.getElementById('photo').textContent=''; };
      r.readAsDataURL(f);
    });

    // download as image using html2canvas-like approach (minimal)
    document.getElementById('downloadBtn').addEventListener('click', async ()=>{
      try{
        // use SVG foreignObject trick
        const svg = `data:image/svg+xml;charset=utf-8,` + encodeURIComponent(
  
