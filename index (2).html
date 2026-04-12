<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Galactic Pixel Python</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap" rel="stylesheet">
  <style>
    :root {
      --neon-green: #39ff14;
      --neon-cyan: #00fff7;
      --neon-pink: #ff00a0;
      --neon-yellow: #ffe600;
      --neon-orange: #ff6a00;
      --bg-dark: #030310;
      --bg-panel: #07071a;
      --border-glow: #1a1a4a;
      --grid-color: rgba(0, 255, 247, 0.04);
      --scanline: rgba(0,0,0,0.18);
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background-color: transparent;
      color: #fff;
      font-family: 'Press Start 2P', monospace;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      padding: 24px 16px;
      overflow-x: hidden;
    }

    /* ── PAGE BACKGROUND CANVAS ── */
    #bgCanvas {
      position: fixed;
      inset: 0;
      width: 100%;
      height: 100%;
      z-index: 0;
      pointer-events: none;
    }
    /* Lift all content above bg canvas */
    .page-wrap, .modal-backdrop { position: relative; z-index: 1; }

    /* ── PAGE WRAPPER ── */
    .page-wrap {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
      max-width: 980px;
      margin: 0 auto;
    }

    /* ── TITLE ── */
    .title-wrap {
      text-align: center;
      margin-bottom: 20px;
      width: 100%;
    }
    .title-main {
      font-size: clamp(14px, 2.8vw, 26px);
      color: var(--neon-green);
      text-shadow:
        0 0 6px var(--neon-green),
        0 0 20px var(--neon-green),
        0 0 50px rgba(57,255,20,0.4);
      letter-spacing: 4px;
      animation: flicker 6s infinite;
    }
    .title-sub {
      font-size: 8px;
      color: var(--neon-cyan);
      letter-spacing: 8px;
      margin-top: 6px;
      opacity: 0.7;
    }

    @keyframes flicker {
      0%,96%,100% { opacity: 1; }
      97% { opacity: 0.85; }
      98% { opacity: 1; }
      99% { opacity: 0.6; }
    }

    /* ── MAIN LAYOUT ── */
    .game-layout {
      display: flex;
      gap: 22px;
      align-items: center;
      flex-wrap: wrap;
      justify-content: center;
      width: 100%;
    }

    /* ── ARCADE CABINET FRAME ── */
    .cabinet {
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .screen-bezel {
      background: #0a0a1e;
      border: 3px solid #1e1e5a;
      border-radius: 4px;
      padding: 12px;
      box-shadow:
        0 0 0 1px #000,
        0 0 30px rgba(0,255,247,0.12),
        inset 0 0 40px rgba(0,0,0,0.6);
      position: relative;
    }

    /* Scanlines overlay */
    .screen-bezel::after {
      content: '';
      position: absolute;
      inset: 12px;
      background: repeating-linear-gradient(
        0deg,
        transparent,
        transparent 2px,
        var(--scanline) 2px,
        var(--scanline) 4px
      );
      pointer-events: none;
      z-index: 10;
      border-radius: 2px;
    }

    /* CRT curvature vignette */
    .screen-bezel::before {
      content: '';
      position: absolute;
      inset: 12px;
      background: radial-gradient(ellipse at center, transparent 60%, rgba(0,0,0,0.55) 100%);
      pointer-events: none;
      z-index: 11;
      border-radius: 2px;
    }

    canvas {
      display: block;
      image-rendering: pixelated;
      image-rendering: crisp-edges;
      border: 2px solid #1a1a5a;
      box-shadow:
        inset 0 0 20px rgba(0,0,0,0.8),
        0 0 15px rgba(0,255,247,0.08);
    }

    /* ── HUD bar ── */
    .hud {
      display: flex;
      justify-content: space-between;
      width: 100%;
      padding: 8px 4px 4px;
      font-size: 8px;
      color: var(--neon-cyan);
    }
    .hud-val { color: var(--neon-yellow); }

    /* ── CONTROLS ── */
    .controls {
      display: flex;
      gap: 10px;
      margin-top: 14px;
    }

    .btn {
      font-family: 'Press Start 2P', monospace;
      font-size: 9px;
      padding: 10px 18px;
      border: 2px solid;
      cursor: pointer;
      text-transform: uppercase;
      letter-spacing: 1px;
      transition: all 0.1s;
      position: relative;
      background: transparent;
    }
    .btn-start {
      color: var(--neon-green);
      border-color: var(--neon-green);
      box-shadow: 0 0 10px rgba(57,255,20,0.3), inset 0 0 10px rgba(57,255,20,0.05);
      text-shadow: 0 0 8px var(--neon-green);
    }
    .btn-start:hover, .btn-start:active {
      background: rgba(57,255,20,0.15);
      box-shadow: 0 0 20px rgba(57,255,20,0.6), inset 0 0 15px rgba(57,255,20,0.15);
    }
    .btn-mute {
      color: var(--neon-pink);
      border-color: var(--neon-pink);
      box-shadow: 0 0 10px rgba(255,0,160,0.3), inset 0 0 10px rgba(255,0,160,0.05);
      text-shadow: 0 0 8px var(--neon-pink);
    }
    .btn-mute:hover, .btn-mute:active {
      background: rgba(255,0,160,0.15);
      box-shadow: 0 0 20px rgba(255,0,160,0.6);
    }

    /* D-pad for mobile */
    .dpad {
      display: none;
      flex-direction: column;
      align-items: center;
      gap: 4px;
      margin-top: 14px;
    }
    .dpad-row { display: flex; gap: 4px; }
    .dpad-btn {
      font-family: 'Press Start 2P', monospace;
      width: 44px; height: 44px;
      background: rgba(0,255,247,0.08);
      border: 2px solid rgba(0,255,247,0.3);
      color: var(--neon-cyan);
      font-size: 14px;
      cursor: pointer;
      border-radius: 4px;
      display: flex; align-items: center; justify-content: center;
      user-select: none;
      -webkit-user-select: none;
      touch-action: manipulation;
    }
    .dpad-btn:active { background: rgba(0,255,247,0.25); }
    @media (max-width: 680px) { .dpad { display: flex; } }

    .tip {
      font-size: 7px;
      color: rgba(255,255,255,0.3);
      margin-top: 10px;
      letter-spacing: 1px;
    }

    /* ── SIDE PANEL ── */
    .side-panel {
      display: flex;
      flex-direction: column;
      gap: 12px;
      width: 220px;
      flex-shrink: 0;
      align-self: stretch;
      justify-content: flex-start;
    }

    .panel-box {
      background: var(--bg-panel);
      border: 2px solid var(--border-glow);
      padding: 14px 12px;
      position: relative;
      box-shadow: 0 0 20px rgba(0,0,0,0.5);
    }
    .panel-box::before {
      content: '';
      position: absolute;
      top: -1px; left: 10px; right: 10px; height: 2px;
      background: linear-gradient(90deg, transparent, var(--neon-cyan), transparent);
      opacity: 0.6;
    }

    .panel-title {
      font-size: 8px;
      color: var(--neon-cyan);
      letter-spacing: 2px;
      margin-bottom: 12px;
      text-shadow: 0 0 8px var(--neon-cyan);
    }

    /* Leaderboard */
    .lb-entry {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 6px 4px;
      font-size: 7px;
      border-bottom: 1px solid rgba(255,255,255,0.05);
    }
    .lb-entry:last-child { border-bottom: none; }
    .lb-rank { color: rgba(255,255,255,0.35); width: 18px; }
    .lb-rank.gold { color: var(--neon-yellow); text-shadow: 0 0 6px var(--neon-yellow); }
    .lb-rank.silver { color: #aaa; }
    .lb-rank.bronze { color: #cd7f32; }
    .lb-name { flex: 1; padding: 0 6px; color: #ddd; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
    .lb-score { color: var(--neon-green); text-shadow: 0 0 6px var(--neon-green); }
    .lb-loading { font-size: 7px; color: rgba(255,255,255,0.3); text-align: center; padding: 10px 0; }

    /* Legend */
    .legend-item { display: flex; align-items: center; gap: 10px; margin-bottom: 8px; font-size: 7px; color: #bbb; }
    .legend-dot { width: 12px; height: 12px; border-radius: 50%; flex-shrink: 0; }

    /* How to play */
    .how-item { font-size: 7px; color: #aaa; margin-bottom: 8px; line-height: 1.8; }
    .how-item span { color: var(--neon-yellow); }

    /* ── OVERLAY ── */
    #overlay {
      position: absolute;
      inset: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background: rgba(3,3,16,0.82);
      z-index: 20;
      gap: 12px;
      text-align: center;
      padding: 20px;
    }
    #overlay.hidden { display: none; }
    .overlay-title { font-size: 13px; color: var(--neon-yellow); text-shadow: 0 0 15px var(--neon-yellow); letter-spacing: 2px; }
    .overlay-score { font-size: 9px; color: var(--neon-cyan); }
    .overlay-sub { font-size: 7px; color: rgba(255,255,255,0.4); line-height: 2; }

    /* ── MODAL ── */
    .modal-backdrop {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.85);
      z-index: 100;
      align-items: center;
      justify-content: center;
    }
    .modal-backdrop.active { display: flex; }
    .modal {
      background: var(--bg-panel);
      border: 2px solid var(--neon-cyan);
      box-shadow: 0 0 40px rgba(0,255,247,0.3);
      padding: 28px 24px;
      text-align: center;
      max-width: 340px;
      width: 90%;
    }
    .modal h3 { font-size: 11px; color: var(--neon-yellow); margin-bottom: 16px; letter-spacing: 2px; }
    .modal p { font-size: 8px; color: #aaa; margin-bottom: 16px; line-height: 2; }
    .modal input {
      font-family: 'Press Start 2P', monospace;
      font-size: 10px;
      width: 100%;
      padding: 10px;
      background: #0a0a1e;
      border: 2px solid var(--neon-cyan);
      color: var(--neon-green);
      text-align: center;
      margin-bottom: 14px;
      outline: none;
    }
    .modal input:focus { box-shadow: 0 0 15px rgba(0,255,247,0.4); }
    .modal-btns { display: flex; gap: 10px; justify-content: center; }
    .modal-btns .btn { font-size: 8px; padding: 10px 14px; }
  </style>
</head>
<body>

  <!-- Full-page animated background -->
  <canvas id="bgCanvas"></canvas>

  <div class="page-wrap">
  <div class="title-wrap">
    <div class="title-main">GALACTIC PIXEL PYTHON</div>
    <div class="title-sub">ARCADE EDITION</div>
  </div>

  <div class="game-layout">
    <!-- MAIN GAME -->
    <div class="cabinet">
      <div class="screen-bezel" style="position:relative;">
        <div class="hud">
          <div>SCORE&nbsp;<span class="hud-val" id="hudScore">0</span></div>
          <div>LEVEL&nbsp;<span class="hud-val" id="hudLevel">1</span></div>
          <div>BEST&nbsp;<span class="hud-val" id="hudBest">—</span></div>
        </div>
        <canvas id="gameCanvas" width="480" height="360"></canvas>
        <div id="overlay">
          <div class="overlay-title">GALACTIC PIXEL PYTHON</div>
          <div class="overlay-sub">
            PRESS START TO PLAY<br>
            ARROW KEYS / WASD TO STEER
          </div>
        </div>
      </div>

      <div class="controls">
        <button class="btn btn-start" id="startBtn">▶ START</button>
        <button class="btn btn-mute" id="muteBtn">♪ MUTE</button>
      </div>

      <!-- Mobile D-Pad -->
      <div class="dpad">
        <div class="dpad-row"><button class="dpad-btn" id="dUp">▲</button></div>
        <div class="dpad-row">
          <button class="dpad-btn" id="dLeft">◀</button>
          <button class="dpad-btn" id="dDown">▼</button>
          <button class="dpad-btn" id="dRight">▶</button>
        </div>
      </div>

      <div class="tip">ARROW KEYS / WASD · EAT FOOD · DON'T CRASH</div>
    </div>

    <!-- SIDE PANEL -->
    <div class="side-panel">
      <!-- Leaderboard -->
      <div class="panel-box">
        <div class="panel-title">🏆 HALL OF FAME</div>
        <div id="leaderboard"><div class="lb-loading">LOADING...</div></div>
      </div>

      <!-- Legend -->
      <div class="panel-box">
        <div class="panel-title">LEGEND</div>
        <div class="legend-item"><div class="legend-dot" style="background:#39ff14;box-shadow:0 0 8px #39ff14;"></div>HEAD</div>
        <div class="legend-item"><div class="legend-dot" style="background:#00fff7;box-shadow:0 0 8px #00fff7;"></div>BODY</div>
        <div class="legend-item"><div class="legend-dot" style="background:#ff00a0;box-shadow:0 0 8px #ff00a0;"></div>FOOD</div>
        <div class="legend-item"><div class="legend-dot" style="background:#ffe600;box-shadow:0 0 8px #ffe600;"></div>BONUS</div>
      </div>

      <!-- How to play -->
      <div class="panel-box">
        <div class="panel-title">HOW TO PLAY</div>
        <div class="how-item">· EAT <span>PINK FOOD</span> TO GROW</div>
        <div class="how-item">· YELLOW <span>BONUS</span> FADES FAST</div>
        <div class="how-item">· SPEED INCREASES EVERY <span>5 PTS</span></div>
        <div class="how-item">· HIT WALL OR SELF = <span>GAME OVER</span></div>
      </div>
      </div>
    </div>
  </div> <!-- /page-wrap -->

  <!-- Name Entry Modal -->
  <div class="modal-backdrop" id="nameModal">
    <div class="modal">
      <h3>🎉 HIGH SCORE!</h3>
      <p>YOU SCORED <span id="modalScore" style="color:var(--neon-green)">0</span> POINTS!<br>ENTER YOUR NAME:</p>
      <input type="text" id="nameInput" maxlength="12" placeholder="PLAYER" autocomplete="off" spellcheck="false" />
      <div class="modal-btns">
        <button class="btn btn-start" id="modalSubmit">SUBMIT</button>
        <button class="btn btn-mute" id="modalSkip">SKIP</button>
      </div>
    </div>
  </div>

  <!-- Game Over Modal -->
  <div class="modal-backdrop" id="gameOverModal">
    <div class="modal">
      <h3 id="goTitle">GAME OVER</h3>
      <p>FINAL SCORE: <span id="goScore" style="color:var(--neon-green)">0</span><br><br><span id="goSub" style="color:rgba(255,255,255,0.4);font-size:7px"></span></p>
      <div class="modal-btns">
        <button class="btn btn-start" id="goRestart">PLAY AGAIN</button>
      </div>
    </div>
  </div>

  <script>
  // ═══════════════════════════════════════════════
  //  LEADERBOARD — JSONBin.io (auto-setup, no manual bin needed)
  //  Bin is created automatically on first ever load.
  // ═══════════════════════════════════════════════
  const JSONBIN_API_KEY = "$2a$10$wA5baUqGf3Et0EAacPijH.sFn8p5RUclQShbql/qUwo2cd56Kq0nG";
  const JSONBIN_BASE    = "https://api.jsonbin.io/v3";
  const BIN_STORE_KEY   = "galactic_pixel_python_bin_id";

  let localScores = JSON.parse(localStorage.getItem("galactic_pixel_python_scores") || "[]");
  let _binId = localStorage.getItem(BIN_STORE_KEY) || null;

  // Auto-create the bin if we don't have one yet
  async function ensureBin() {
    if (_binId) return _binId;
    try {
      const res = await fetch(`${JSONBIN_BASE}/b`, {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
          "X-Master-Key": JSONBIN_API_KEY,
          "X-Bin-Name": "galactic-pixel-python",
          "X-Bin-Private": "false"
        },
        body: JSON.stringify({ scores: [] })
      });
      const data = await res.json();
      _binId = data.metadata?.id || data.metadata?.bin_id || null;
      if (_binId) localStorage.setItem(BIN_STORE_KEY, _binId);
    } catch (e) { console.warn("Could not create bin:", e); }
    return _binId;
  }

  async function fetchScores() {
    const binId = await ensureBin();
    if (!binId) return localScores.slice(0, 10);
    try {
      const res = await fetch(`${JSONBIN_BASE}/b/${binId}/latest`, {
        headers: { "X-Master-Key": JSONBIN_API_KEY }
      });
      const data = await res.json();
      return (data.record?.scores || []).slice(0, 10);
    } catch { return localScores.slice(0, 10); }
  }

  async function saveScore(name, score) {
    const entry = { name: name.toUpperCase().slice(0,12), score, date: new Date().toISOString().slice(0,10) };

    // Always save locally too
    localScores.push(entry);
    localScores.sort((a,b) => b.score - a.score);
    localScores = localScores.slice(0, 50);
    localStorage.setItem("galactic_pixel_python_scores", JSON.stringify(localScores));

    const binId = await ensureBin();
    if (!binId) { renderLeaderboard(localScores.slice(0,10)); return; }

    try {
      const current = await fetchScores();
      const merged = [...current, entry].sort((a,b) => b.score - a.score).slice(0, 50);
      await fetch(`${JSONBIN_BASE}/b/${binId}`, {
        method: "PUT",
        headers: { "Content-Type": "application/json", "X-Master-Key": JSONBIN_API_KEY },
        body: JSON.stringify({ scores: merged })
      });
      renderLeaderboard(merged.slice(0,10));
    } catch { renderLeaderboard(localScores.slice(0,10)); }
  }

  async function loadLeaderboard() {
    renderLeaderboard(null);
    const scores = await fetchScores();
    renderLeaderboard(scores);
  }

  function renderLeaderboard(scores) {
    const el = document.getElementById("leaderboard");
    if (!scores) { el.innerHTML = '<div class="lb-loading">LOADING...</div>'; return; }
    if (scores.length === 0) {
      el.innerHTML = '<div class="lb-loading">NO SCORES YET.<br>BE THE FIRST!</div>'; return;
    }
    const rankClass = i => i === 0 ? 'gold' : i === 1 ? 'silver' : i === 2 ? 'bronze' : '';
    const rankIcon  = i => i === 0 ? '🥇' : i === 1 ? '🥈' : i === 2 ? '🥉' : `${i+1}.`;
    el.innerHTML = scores.map((s,i) => `
      <div class="lb-entry">
        <div class="lb-rank ${rankClass(i)}">${rankIcon(i)}</div>
        <div class="lb-name">${s.name || 'PLAYER'}</div>
        <div class="lb-score">${s.score}</div>
      </div>
    `).join('');
  }

  // ═══════════════════════════════════════════════
  //  GAME ENGINE
  // ═══════════════════════════════════════════════
  const canvas = document.getElementById("gameCanvas");
  const ctx = canvas.getContext("2d");
  const W = canvas.width, H = canvas.height;
  const GRID = 20;
  const COLS = W / GRID, ROWS = H / GRID;

  let snake, food, bonus, dx, dy, score, level, speed;
  let changingDir, gameRunning, gameInterval, bonusTimer;
  let muted = false;

  // Stars (static for perf)
  const STARS = Array.from({length:80}, () => ({
    x: Math.random()*W, y: Math.random()*H,
    size: Math.random() < 0.15 ? 2 : 1,
    alpha: 0.2 + Math.random()*0.5
  }));

  // Particle system
  let particles = [];
  function spawnParticles(x, y, color, count=8) {
    for(let i=0; i<count; i++) {
      const angle = (Math.PI*2/count)*i + Math.random()*0.4;
      particles.push({
        x: x*GRID+GRID/2, y: y*GRID+GRID/2,
        vx: Math.cos(angle)*(1+Math.random()*3),
        vy: Math.sin(angle)*(1+Math.random()*3),
        life: 1, color, size: 2+Math.random()*3
      });
    }
  }
  function updateParticles() {
    particles = particles.filter(p => p.life > 0);
    particles.forEach(p => {
      p.x += p.vx; p.y += p.vy;
      p.vx *= 0.92; p.vy *= 0.92;
      p.life -= 0.045;
      ctx.globalAlpha = p.life;
      ctx.fillStyle = p.color;
      ctx.fillRect(p.x - p.size/2, p.y - p.size/2, p.size, p.size);
    });
    ctx.globalAlpha = 1;
  }

  // Drawing helpers
  function drawGlowCircle(gx, gy, color, glowColor, r=GRID*0.45) {
    const cx = gx*GRID + GRID/2, cy = gy*GRID + GRID/2;
    // outer glow
    ctx.save();
    ctx.shadowBlur = 14; ctx.shadowColor = glowColor || color;
    ctx.fillStyle = color;
    ctx.beginPath(); ctx.arc(cx, cy, r, 0, Math.PI*2); ctx.fill();
    ctx.restore();
    // inner highlight
    ctx.fillStyle = 'rgba(255,255,255,0.25)';
    ctx.beginPath(); ctx.arc(cx - r*0.2, cy - r*0.25, r*0.3, 0, Math.PI*2); ctx.fill();
  }

  function drawPixelGrid() {
    ctx.strokeStyle = 'rgba(0,255,247,0.04)';
    ctx.lineWidth = 0.5;
    for(let x=0; x<=W; x+=GRID) { ctx.beginPath(); ctx.moveTo(x,0); ctx.lineTo(x,H); ctx.stroke(); }
    for(let y=0; y<=H; y+=GRID) { ctx.beginPath(); ctx.moveTo(0,y); ctx.lineTo(W,y); ctx.stroke(); }
  }

  function drawBackground() {
    ctx.fillStyle = '#030310';
    ctx.fillRect(0,0,W,H);
    drawPixelGrid();
    // stars
    STARS.forEach(s => {
      ctx.globalAlpha = s.alpha;
      ctx.fillStyle = '#fff';
      ctx.fillRect(s.x, s.y, s.size, s.size);
    });
    ctx.globalAlpha = 1;
  }

  function drawSnake() {
    snake.forEach((seg, i) => {
      const t = i / snake.length;
      if (i === 0) {
        // head — bright green
        drawGlowCircle(seg.x, seg.y, '#39ff14', '#39ff14');
        // eyes
        const cx = seg.x*GRID + GRID/2, cy = seg.y*GRID + GRID/2;
        const eyeOff = 3;
        let ex1, ey1, ex2, ey2;
        if (dx===1)        { ex1=cx+3; ey1=cy-eyeOff; ex2=cx+3; ey2=cy+eyeOff; }
        else if (dx===-1)  { ex1=cx-3; ey1=cy-eyeOff; ex2=cx-3; ey2=cy+eyeOff; }
        else if (dy===-1)  { ex1=cx-eyeOff; ey1=cy-3; ex2=cx+eyeOff; ey2=cy-3; }
        else               { ex1=cx-eyeOff; ey1=cy+3; ex2=cx+eyeOff; ey2=cy+3; }
        ctx.fillStyle='#000';
        ctx.beginPath(); ctx.arc(ex1,ey1,2,0,Math.PI*2); ctx.fill();
        ctx.beginPath(); ctx.arc(ex2,ey2,2,0,Math.PI*2); ctx.fill();
      } else {
        // body — cyan fading
        const r = Math.floor(0 + t*0);
        const g = Math.floor(255 - t*100);
        const b = Math.floor(247 - t*50);
        const color = `rgb(${r},${g},${b})`;
        drawGlowCircle(seg.x, seg.y, color, '#00fff7', GRID*0.38);
      }
    });
  }

  function drawFood() {
    // pulsing
    const pulse = 0.85 + 0.15 * Math.sin(Date.now() / 180);
    drawGlowCircle(food.x, food.y, '#ff00a0', '#ff00a0', GRID*0.42*pulse);
    // plus sign on food
    ctx.fillStyle = 'rgba(255,255,255,0.5)';
    const cx = food.x*GRID+GRID/2, cy = food.y*GRID+GRID/2;
    ctx.fillRect(cx-4, cy-1, 8, 2);
    ctx.fillRect(cx-1, cy-4, 2, 8);
  }

  function drawBonus() {
    if (!bonus) return;
    const age = (Date.now() - bonus.born) / bonus.lifetime;
    if (age >= 1) { bonus = null; return; }
    ctx.globalAlpha = 1 - age*0.7;
    const pulse = 0.8 + 0.2 * Math.sin(Date.now() / 120);
    drawGlowCircle(bonus.x, bonus.y, '#ffe600', '#ffe600', GRID*0.44*pulse);
    // star shape
    ctx.fillStyle = 'rgba(255,255,255,0.6)';
    const cx = bonus.x*GRID+GRID/2, cy = bonus.y*GRID+GRID/2;
    for(let a=0; a<5; a++) {
      const angle = (a/5)*Math.PI*2 - Math.PI/2;
      const r2 = a%2===0?5:2;
      ctx.fillRect(cx+Math.cos(angle)*r2-1, cy+Math.sin(angle)*r2-1, 2, 2);
    }
    ctx.globalAlpha = 1;
  }

  function spawnFood() {
    let pos;
    do {
      pos = { x: Math.floor(Math.random()*COLS), y: Math.floor(Math.random()*ROWS) };
    } while (snake.some(s=>s.x===pos.x&&s.y===pos.y));
    return pos;
  }

  function spawnBonus() {
    if (bonus) return;
    let pos;
    do {
      pos = { x: Math.floor(Math.random()*COLS), y: Math.floor(Math.random()*ROWS) };
    } while (snake.some(s=>s.x===pos.x&&s.y===pos.y) || (pos.x===food.x&&pos.y===food.y));
    bonus = { ...pos, born: Date.now(), lifetime: 5000 };
  }

  function updateHUD() {
    document.getElementById("hudScore").textContent = score;
    document.getElementById("hudLevel").textContent = level;
    const top = localScores[0];
    document.getElementById("hudBest").textContent = top ? top.score : "—";
  }

  function startGame() {
    snake = [{x:12,y:9},{x:11,y:9},{x:10,y:9}];
    food = spawnFood(); bonus = null;
    dx=1; dy=0; score=0; level=1; speed=150;
    changingDir=false; particles=[];
    gameRunning=true;
    document.getElementById("overlay").classList.add("hidden");
    if(gameInterval) clearInterval(gameInterval);
    gameInterval = setInterval(gameLoop, speed);
    updateHUD();
  }

  function gameLoop() {
    const head = { x: snake[0].x + dx, y: snake[0].y + dy };
    changingDir = false;

    // collision
    if (head.x<0||head.x>=COLS||head.y<0||head.y>=ROWS||snake.some(s=>s.x===head.x&&s.y===head.y)) {
      endGame(); return;
    }

    snake.unshift(head);
    let grew = false;

    if (head.x===food.x && head.y===food.y) {
      score++; grew=true;
      spawnParticles(head.x, head.y, '#ff00a0');
      food = spawnFood();
      if (score % 5 === 0) {
        level++;
        speed = Math.max(60, 150 - (level-1)*12);
        clearInterval(gameInterval);
        gameInterval = setInterval(gameLoop, speed);
      }
      if (score % 3 === 0) spawnBonus();
      updateHUD();
    }

    if (bonus && head.x===bonus.x && head.y===bonus.y) {
      score += 3; grew=true;
      spawnParticles(head.x, head.y, '#ffe600', 14);
      bonus = null;
      updateHUD();
    }

    if (!grew) snake.pop();

    // remove expired bonus
    if (bonus && Date.now()-bonus.born > bonus.lifetime) bonus = null;

    render();
  }

  function render() {
    drawBackground();
    drawFood();
    drawBonus();
    drawSnake();
    updateParticles();
  }

  async function endGame() {
    gameRunning=false;
    clearInterval(gameInterval);

    const topScore = localScores[0]?.score || 0;
    const isHighScore = score > 0 && score >= topScore;

    if (isHighScore || score > 0) {
      // Show name entry if high score, else just game over
      if (isHighScore) {
        document.getElementById("modalScore").textContent = score;
        document.getElementById("nameInput").value = "";
        document.getElementById("nameModal").classList.add("active");
        document.getElementById("nameInput").focus();
      } else {
        showGameOver();
      }
    } else {
      showGameOver();
    }
  }

  function showGameOver(name) {
    if (name) {
      document.getElementById("goTitle").textContent = "HIGH SCORE!";
      document.getElementById("goSub").textContent = `SAVED AS: ${name}`;
    } else {
      document.getElementById("goTitle").textContent = "GAME OVER";
      document.getElementById("goSub").textContent = score > 0 ? "GOOD EFFORT, PILOT." : "";
    }
    document.getElementById("goScore").textContent = score;
    document.getElementById("gameOverModal").classList.add("active");
  }

  // Modal events
  document.getElementById("modalSubmit").addEventListener("click", async () => {
    const name = document.getElementById("nameInput").value.trim() || "PLAYER";
    document.getElementById("nameModal").classList.remove("active");
    await saveScore(name, score);
    showGameOver(name.toUpperCase());
  });
  document.getElementById("nameInput").addEventListener("keydown", e => {
    if (e.key === "Enter") document.getElementById("modalSubmit").click();
  });
  document.getElementById("modalSkip").addEventListener("click", () => {
    document.getElementById("nameModal").classList.remove("active");
    showGameOver();
  });
  document.getElementById("goRestart").addEventListener("click", () => {
    document.getElementById("gameOverModal").classList.remove("active");
    startGame();
  });
  document.getElementById("startBtn").addEventListener("click", () => {
    document.getElementById("gameOverModal").classList.remove("active");
    document.getElementById("nameModal").classList.remove("active");
    startGame();
  });

  // Controls
  function changeDir(dir) {
    if (changingDir) return; changingDir=true;
    if (dir==="up"    && dy===0) { dx=0; dy=-1; }
    if (dir==="down"  && dy===0) { dx=0; dy=1;  }
    if (dir==="left"  && dx===0) { dx=-1; dy=0; }
    if (dir==="right" && dx===0) { dx=1;  dy=0; }
  }
  document.addEventListener("keydown", e => {
    if (["ArrowUp","ArrowDown","ArrowLeft","ArrowRight"].includes(e.key)) e.preventDefault();
    switch(e.key) {
      case "ArrowUp": case "w": case "W": changeDir("up"); break;
      case "ArrowDown": case "s": case "S": changeDir("down"); break;
      case "ArrowLeft": case "a": case "A": changeDir("left"); break;
      case "ArrowRight": case "d": case "D": changeDir("right"); break;
    }
  });
  // D-pad
  document.getElementById("dUp").addEventListener("click", ()=>changeDir("up"));
  document.getElementById("dDown").addEventListener("click", ()=>changeDir("down"));
  document.getElementById("dLeft").addEventListener("click", ()=>changeDir("left"));
  document.getElementById("dRight").addEventListener("click", ()=>changeDir("right"));

  // ═══════════════════════════════════════════════
  //  SOUND ENGINE (Web Audio API — no files needed)
  //  Works on GitHub Pages, works everywhere.
  // ═══════════════════════════════════════════════
  let audioCtx = null;
  let bgGainNode = null;
  let bgOscillators = [];

  function getAudioCtx() {
    if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    return audioCtx;
  }

  function playTone(freq, type, duration, gainVal, startDelay=0, freqEnd=null) {
    if (muted) return;
    const ctx2 = getAudioCtx();
    const osc = ctx2.createOscillator();
    const gain = ctx2.createGain();
    osc.connect(gain); gain.connect(ctx2.destination);
    osc.type = type;
    osc.frequency.setValueAtTime(freq, ctx2.currentTime + startDelay);
    if (freqEnd) osc.frequency.exponentialRampToValueAtTime(freqEnd, ctx2.currentTime + startDelay + duration);
    gain.gain.setValueAtTime(gainVal, ctx2.currentTime + startDelay);
    gain.gain.exponentialRampToValueAtTime(0.001, ctx2.currentTime + startDelay + duration);
    osc.start(ctx2.currentTime + startDelay);
    osc.stop(ctx2.currentTime + startDelay + duration);
  }

  function soundEat() {
    // bright ascending blip
    playTone(440, 'square', 0.04, 0.18);
    playTone(880, 'square', 0.08, 0.12, 0.04);
  }

  function soundBonus() {
    // sparkly arpeggio
    [523, 659, 784, 1047].forEach((f, i) => playTone(f, 'square', 0.09, 0.15, i*0.07));
  }

  function soundLevelUp() {
    // fanfare sweep
    [262, 330, 392, 523, 659].forEach((f, i) => playTone(f, 'triangle', 0.12, 0.2, i*0.08));
  }

  function soundGameOver() {
    // descending doom
    playTone(330, 'sawtooth', 0.15, 0.3);
    playTone(220, 'sawtooth', 0.2, 0.3, 0.15);
    playTone(110, 'sawtooth', 0.4, 0.35, 0.35, 55);
  }

  function soundStart() {
    // ready beeps
    [220, 440, 880].forEach((f, i) => playTone(f, 'square', 0.06, 0.15, i*0.1));
  }

  // ── Background chiptune music — 3-voice arcade engine ──────────
  // Tempo: 140 BPM → 1 beat = ~0.4286s, 1 sixteenth = ~0.107s
  const BPM      = 175;
  const BEAT     = 60 / BPM;
  const S16      = BEAT / 4;   // sixteenth note duration

  // Note helper: note name → frequency
  const NOTE = (function(){
    const names = ['C','C#','D','D#','E','F','F#','G','G#','A','A#','B'];
    return function(n, oct) {
      const idx = names.indexOf(n);
      return 440 * Math.pow(2, (oct - 4) + (idx - 9) / 12);
    };
  })();

  // ── MELODY (square wave, lead) ───────────────────────────────
  // Two 16-bar phrases that loop. Each entry: [freq|0, beats]
  // 0 = rest
  const R = 0;
  const MEL = [
    // Phrase A — driving galactic theme
    [NOTE('E',5),1],[NOTE('E',5),1],[NOTE('G',5),1],[NOTE('A',5),2],
    [NOTE('G',5),1],[NOTE('E',5),1],[NOTE('D',5),2],
    [NOTE('C',5),1],[NOTE('D',5),1],[NOTE('E',5),1],[NOTE('G',5),2],
    [NOTE('A',5),1],[NOTE('G',5),1],[NOTE('E',5),4],

    [NOTE('D',5),1],[NOTE('D',5),1],[NOTE('F',5),1],[NOTE('G',5),2],
    [NOTE('F',5),1],[NOTE('D',5),1],[NOTE('C',5),2],
    [NOTE('B',4),1],[NOTE('C',5),1],[NOTE('D',5),1],[NOTE('F',5),2],
    [NOTE('G',5),1],[NOTE('F',5),1],[NOTE('D',5),4],

    // Phrase B — tension / run
    [NOTE('E',5),0.5],[NOTE('F',5),0.5],[NOTE('G',5),0.5],[NOTE('A',5),0.5],
    [NOTE('B',5),1],[NOTE('A',5),1],[NOTE('G',5),2],
    [NOTE('F',5),0.5],[NOTE('G',5),0.5],[NOTE('A',5),0.5],[NOTE('B',5),0.5],
    [NOTE('C',6),1],[NOTE('B',5),1],[NOTE('A',5),2],

    [NOTE('G',5),1],[NOTE('F',5),1],[NOTE('E',5),1],[NOTE('D',5),1],
    [NOTE('C',5),1],[NOTE('D',5),1],[NOTE('E',5),2],
    [NOTE('A',4),1],[NOTE('B',4),1],[NOTE('C',5),1],[NOTE('D',5),1],
    [NOTE('E',5),6],
  ];

  // ── BASS (sawtooth, one octave below root) ───────────────────
  const BASS = [
    // mirrors chord roots: Am / G / C / G  x2  then  Dm / C / G / C
    [NOTE('A',2),2],[NOTE('A',2),2],[NOTE('G',2),2],[NOTE('G',2),2],
    [NOTE('C',3),2],[NOTE('C',3),2],[NOTE('G',2),4],
    [NOTE('D',3),2],[NOTE('D',3),2],[NOTE('C',3),2],[NOTE('C',3),2],
    [NOTE('G',2),2],[NOTE('G',2),2],[NOTE('C',3),4],

    [NOTE('A',2),1],[R,1],[NOTE('A',2),1],[R,1],
    [NOTE('G',2),1],[R,1],[NOTE('G',2),1],[R,1],
    [NOTE('C',3),1],[R,1],[NOTE('C',3),1],[R,1],
    [NOTE('G',2),4],
    [NOTE('D',3),1],[R,1],[NOTE('D',3),1],[R,1],
    [NOTE('C',3),1],[R,1],[NOTE('C',3),1],[R,1],
    [NOTE('G',2),2],[NOTE('G',2),2],
    [NOTE('C',3),4],
  ];

  // ── PERCUSSION — noise-based kick + hihat pattern ────────────
  // Pattern repeats every bar (16 sixteenths).
  // K=kick, H=hihat, S=snare, _=rest
  // Pattern: K _ H _ S _ H _ K K H _ S _ H _
  const DRUM_PATTERN = ['K','_','H','_','S','_','H','_','K','K','H','_','S','_','H','_'];

  function playDrumHit(type, when) {
    if (muted) return;
    const ctx2 = getAudioCtx();

    if (type === 'K') {
      // Kick: sine with fast pitch drop
      const osc = ctx2.createOscillator();
      const gain = ctx2.createGain();
      osc.connect(gain); gain.connect(ctx2.destination);
      osc.type = 'sine';
      osc.frequency.setValueAtTime(160, when);
      osc.frequency.exponentialRampToValueAtTime(40, when + 0.12);
      gain.gain.setValueAtTime(0.55, when);
      gain.gain.exponentialRampToValueAtTime(0.001, when + 0.18);
      osc.start(when); osc.stop(when + 0.2);

    } else if (type === 'S') {
      // Snare: noise burst
      const bufSize = ctx2.sampleRate * 0.12;
      const buf = ctx2.createBuffer(1, bufSize, ctx2.sampleRate);
      const d = buf.getChannelData(0);
      for (let i = 0; i < bufSize; i++) d[i] = Math.random() * 2 - 1;
      const src = ctx2.createBufferSource();
      src.buffer = buf;
      const gain = ctx2.createGain();
      const filter = ctx2.createBiquadFilter();
      filter.type = 'bandpass'; filter.frequency.value = 3000; filter.Q.value = 0.7;
      src.connect(filter); filter.connect(gain); gain.connect(ctx2.destination);
      gain.gain.setValueAtTime(0.28, when);
      gain.gain.exponentialRampToValueAtTime(0.001, when + 0.1);
      src.start(when); src.stop(when + 0.13);

    } else if (type === 'H') {
      // Hi-hat: short filtered noise
      const bufSize = ctx2.sampleRate * 0.04;
      const buf = ctx2.createBuffer(1, bufSize, ctx2.sampleRate);
      const d = buf.getChannelData(0);
      for (let i = 0; i < bufSize; i++) d[i] = Math.random() * 2 - 1;
      const src = ctx2.createBufferSource();
      src.buffer = buf;
      const gain = ctx2.createGain();
      const filter = ctx2.createBiquadFilter();
      filter.type = 'highpass'; filter.frequency.value = 7000;
      src.connect(filter); filter.connect(gain); gain.connect(ctx2.destination);
      gain.gain.setValueAtTime(0.08, when);
      gain.gain.exponentialRampToValueAtTime(0.001, when + 0.03);
      src.start(when); src.stop(when + 0.05);
    }
  }

  function scheduleVoice(seq, noteIndex, nextTime, waveType, gainLevel, articulation=0.85) {
    const ctx2 = getAudioCtx();
    const [freq, beats] = seq[noteIndex % seq.length];
    const dur = beats * BEAT;
    if (freq > 0) {
      const osc = ctx2.createOscillator();
      const gain = ctx2.createGain();
      osc.connect(gain); gain.connect(ctx2.destination);
      osc.type = waveType;
      osc.frequency.setValueAtTime(freq, nextTime);
      gain.gain.setValueAtTime(gainLevel, nextTime);
      gain.gain.exponentialRampToValueAtTime(0.001, nextTime + dur * articulation);
      osc.start(nextTime); osc.stop(nextTime + dur);
    }
    return { nextTime: nextTime + dur, noteIndex: noteIndex + 1 };
  }

  let bgSchedulerTimer = null;
  let bgMelIdx = 0, bgBassIdx = 0, bgDrumStep = 0;
  let bgMelTime = 0, bgBassTime = 0, bgDrumTime = 0;

  function scheduleBgMusic() {
    if (muted || !gameRunning) return;
    const ctx2 = getAudioCtx();
    const horizon = ctx2.currentTime + 0.35;

    // Melody voice
    if (bgMelTime < ctx2.currentTime) bgMelTime = ctx2.currentTime;
    while (bgMelTime < horizon) {
      const r = scheduleVoice(MEL, bgMelIdx, bgMelTime, 'square', 0.07, 0.72);
      bgMelTime = r.nextTime; bgMelIdx = r.noteIndex;
    }

    // Bass voice
    if (bgBassTime < ctx2.currentTime) bgBassTime = ctx2.currentTime;
    while (bgBassTime < horizon) {
      const r = scheduleVoice(BASS, bgBassIdx, bgBassTime, 'sawtooth', 0.09, 0.55);
      bgBassTime = r.nextTime; bgBassIdx = r.noteIndex;
    }

    // Drums (sixteenth grid)
    if (bgDrumTime < ctx2.currentTime) bgDrumTime = ctx2.currentTime;
    while (bgDrumTime < horizon) {
      const hit = DRUM_PATTERN[bgDrumStep % DRUM_PATTERN.length];
      if (hit !== '_') playDrumHit(hit, bgDrumTime);
      bgDrumTime += S16;
      bgDrumStep++;
    }

    bgSchedulerTimer = setTimeout(scheduleBgMusic, 150);
  }

  function startBgMusic() {
    stopBgMusic();
    const ctx2 = getAudioCtx();
    bgMelIdx = 0; bgBassIdx = 0; bgDrumStep = 0;
    bgMelTime = ctx2.currentTime + 0.05;
    bgBassTime = bgMelTime;
    bgDrumTime = bgMelTime;
    scheduleBgMusic();
  }

  function stopBgMusic() {
    if (bgSchedulerTimer) clearTimeout(bgSchedulerTimer);
    bgSchedulerTimer = null;
  }

  // Mute toggle
  document.getElementById("muteBtn").addEventListener("click", () => {
    muted = !muted;
    document.getElementById("muteBtn").textContent = muted ? "♪ UNMUTE" : "♪ MUTE";
    if (!muted && gameRunning) startBgMusic();
    else stopBgMusic();
  });

  // Hook sounds into game events — patch into existing functions
  const _origStartGame = startGame;
  startGame = function() {
    _origStartGame();
    soundStart();
    startBgMusic();
  };

  const _origEndGame = endGame;
  endGame = async function() {
    stopBgMusic();
    soundGameOver();
    await _origEndGame();
  };

  // Patch eat & bonus sounds into gameLoop by overriding spawnParticles calls
  const _origSpawnParticles = spawnParticles;
  let _lastEat = 0, _lastBonus = 0;
  spawnParticles = function(x, y, color, count=8) {
    _origSpawnParticles(x, y, color, count);
    const now = Date.now();
    if (color === '#ff00a0' && now - _lastEat > 50) { soundEat(); _lastEat = now; }
    if (color === '#ffe600' && now - _lastBonus > 50) { soundBonus(); _lastBonus = now; }
  };

  // Level up sound hook — watch level changes
  let _lastLevel = 1;
  const _origUpdateHUD = updateHUD;
  updateHUD = function() {
    _origUpdateHUD();
    if (typeof level !== 'undefined' && level > _lastLevel) {
      _lastLevel = level;
      soundLevelUp();
    }
  };

  // Initial render & leaderboard
  drawBackground();
  loadLeaderboard();

  // ═══════════════════════════════════════════════
  (function() {
    const bgC = document.getElementById('bgCanvas');
    const bgCtx = bgC.getContext('2d');
    let W, H;

    function resize() {
      W = bgC.width  = window.innerWidth;
      H = bgC.height = window.innerHeight;
    }
    resize();
    window.addEventListener('resize', resize);

    // ── Star layers (parallax) ──────────────────
    function makeStar(speed) {
      return {
        x: Math.random() * 3000 - 1500,
        y: Math.random() * 2000 - 1000,
        size: Math.random() < 0.1 ? 2 : 1,
        alpha: 0.15 + Math.random() * 0.55,
        speed,
        twinkleOffset: Math.random() * Math.PI * 2
      };
    }
    const starLayers = [
      Array.from({length: 180}, () => makeStar(0.08)),  // distant, slow
      Array.from({length:  90}, () => makeStar(0.22)),  // mid
      Array.from({length:  35}, () => makeStar(0.55)),  // near, fast
    ];

    // ── Nebula clouds ───────────────────────────
    const NEBULA_COLORS = [
      'rgba(0,180,255,',
      'rgba(140,0,255,',
      'rgba(255,0,140,',
      'rgba(0,255,160,',
    ];
    const nebulae = Array.from({length: 7}, (_, i) => ({
      x: (i / 7) * 1.4 - 0.1,    // fractional screen position
      y: Math.random(),
      rx: 0.18 + Math.random() * 0.22,
      ry: 0.10 + Math.random() * 0.14,
      alpha: 0.025 + Math.random() * 0.04,
      color: NEBULA_COLORS[i % NEBULA_COLORS.length],
      drift: (Math.random() - 0.5) * 0.00006,
      driftY: (Math.random() - 0.5) * 0.00003,
      pulse: Math.random() * Math.PI * 2,
      pulseSpeed: 0.003 + Math.random() * 0.004,
    }));

    // ── Shooting stars ──────────────────────────
    let shooters = [];
    function spawnShooter() {
      shooters.push({
        x: Math.random() * W,
        y: Math.random() * H * 0.5,
        len: 60 + Math.random() * 100,
        speed: 8 + Math.random() * 10,
        alpha: 1,
        angle: Math.PI / 5 + (Math.random() - 0.5) * 0.3,
      });
    }
    setInterval(spawnShooter, 2800 + Math.random() * 2000);

    // ── Pixel grid scan-lines on page bg ───────
    function drawBgGrid() {
      const CELL = 40;
      bgCtx.strokeStyle = 'rgba(0,255,247,0.022)';
      bgCtx.lineWidth = 0.5;
      for (let x = 0; x < W; x += CELL) {
        bgCtx.beginPath(); bgCtx.moveTo(x, 0); bgCtx.lineTo(x, H); bgCtx.stroke();
      }
      for (let y = 0; y < H; y += CELL) {
        bgCtx.beginPath(); bgCtx.moveTo(0, y); bgCtx.lineTo(W, y); bgCtx.stroke();
      }
    }

    // ── Horizon glow lines (retro arcade floor) ─
    function drawHorizonLines() {
      const lineCount = 10;
      const baseY = H * 0.88;
      for (let i = 0; i < lineCount; i++) {
        const t = i / lineCount;
        const y = baseY + t * H * 0.15;
        const alpha = (1 - t) * 0.07;
        bgCtx.strokeStyle = `rgba(0,255,247,${alpha})`;
        bgCtx.lineWidth = 0.8;
        bgCtx.beginPath(); bgCtx.moveTo(0, y); bgCtx.lineTo(W, y); bgCtx.stroke();
      }
      // converging vertical lines (perspective)
      const vx = W / 2, vy = H * 0.72;
      for (let i = -8; i <= 8; i++) {
        const endX = vx + i * (W / 9);
        const alpha = 0.06 - Math.abs(i) * 0.004;
        if (alpha <= 0) continue;
        bgCtx.strokeStyle = `rgba(255,0,160,${alpha})`;
        bgCtx.lineWidth = 0.6;
        bgCtx.beginPath();
        bgCtx.moveTo(vx, vy);
        bgCtx.lineTo(endX, H);
        bgCtx.stroke();
      }
    }

    let t = 0;
    function bgFrame() {
      t++;
      bgCtx.clearRect(0, 0, W, H);

      // deep space base
      bgCtx.fillStyle = '#030310';
      bgCtx.fillRect(0, 0, W, H);

      // nebulae
      nebulae.forEach(n => {
        n.x += n.drift; n.y += n.driftY; n.pulse += n.pulseSpeed;
        if (n.x > 1.2) n.x = -0.2;
        if (n.x < -0.2) n.x = 1.2;
        const pulseFactor = 1 + 0.08 * Math.sin(n.pulse);
        const grad = bgCtx.createRadialGradient(
          n.x * W, n.y * H, 0,
          n.x * W, n.y * H, n.rx * W * pulseFactor
        );
        grad.addColorStop(0, n.color + (n.alpha * 1.6).toFixed(3) + ')');
        grad.addColorStop(0.5, n.color + (n.alpha * 0.6).toFixed(3) + ')');
        grad.addColorStop(1, n.color + '0)');
        bgCtx.fillStyle = grad;
        bgCtx.beginPath();
        bgCtx.ellipse(n.x*W, n.y*H, n.rx*W*pulseFactor, n.ry*H*pulseFactor, 0, 0, Math.PI*2);
        bgCtx.fill();
      });

      // pixel grid overlay
      drawBgGrid();

      // stars by layer
      starLayers.forEach((layer, li) => {
        layer.forEach(s => {
          s.x += s.speed;
          if (s.x > W + 10) { s.x = -10; s.y = Math.random() * H; }
          const twinkle = 0.7 + 0.3 * Math.sin(t * 0.04 + s.twinkleOffset);
          bgCtx.globalAlpha = s.alpha * twinkle;
          // Larger stars get a tiny cyan tint
          bgCtx.fillStyle = li === 2 ? '#aaffff' : '#ffffff';
          bgCtx.fillRect(Math.round(s.x), Math.round(s.y), s.size, s.size);
        });
      });
      bgCtx.globalAlpha = 1;

      // shooting stars
      shooters = shooters.filter(s => s.alpha > 0.02);
      shooters.forEach(s => {
        s.x += Math.cos(s.angle) * s.speed;
        s.y += Math.sin(s.angle) * s.speed;
        s.alpha -= 0.025;
        const grad = bgCtx.createLinearGradient(
          s.x, s.y,
          s.x - Math.cos(s.angle)*s.len, s.y - Math.sin(s.angle)*s.len
        );
        grad.addColorStop(0, `rgba(255,255,255,${s.alpha.toFixed(2)})`);
        grad.addColorStop(1, 'rgba(255,255,255,0)');
        bgCtx.strokeStyle = grad;
        bgCtx.lineWidth = 1.5;
        bgCtx.beginPath();
        bgCtx.moveTo(s.x, s.y);
        bgCtx.lineTo(s.x - Math.cos(s.angle)*s.len, s.y - Math.sin(s.angle)*s.len);
        bgCtx.stroke();
      });

      // retro horizon grid (bottom of page)
      drawHorizonLines();

      requestAnimationFrame(bgFrame);
    }
    bgFrame();
  })();
  </script>
</body>
</html>
