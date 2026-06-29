<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>Semanggi Engineering - README Blueprint</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#0D1117;--s1:#161B22;--s2:#1F2937;--s3:#21262D;
  --br:#30363D;--acc:#3FB950; /* Aksen utama diubah menjadi Hijau Semanggi */
  --grn:#2EA043;--orn:#F0883E;--pur:#BC8CFF;--red:#FF7B72;--ylw:#E3B341;
  --wht:#F0F6FC;--mut:#8B949E;
  --r:10px;--ff:'Segoe UI',system-ui,sans-serif;--mono:'Courier New',monospace
}
body{background:var(--bg);color:var(--wht);font-family:var(--ff);font-size:14px;line-height:1.6}
.wrap{max-width:820px;margin:0 auto;padding:20px 16px 48px}

/* ─── STEP NAV ─── */
.stepnav{display:flex;align-items:center;margin-bottom:28px;gap:0;overflow-x:auto;padding-bottom:4px}
.step{display:flex;align-items:center;gap:8px;padding:8px 14px 8px 10px;border-radius:var(--r);
  cursor:pointer;transition:background .15s;white-space:nowrap;position:relative;flex-shrink:0}
.step:hover .step-label{color:var(--wht)}
.step-num{width:26px;height:26px;border-radius:50%;display:flex;align-items:center;justify-content:center;
  font-size:11px;font-weight:700;flex-shrink:0;transition:all .2s}
.step-label{font-size:12px;font-weight:500;color:var(--mut);transition:color .15s}
.step.active .step-label{color:var(--wht);font-weight:600}
.step-arrow{color:var(--br);font-size:14px;margin:0 2px;flex-shrink:0}
.step.done .step-num{background:var(--grn);color:#000}
.step.active .step-num{background:var(--acc);color:#000}
.step.pending .step-num{background:var(--s2);color:var(--mut);border:1px solid var(--br)}

/* ─── PANES ─── */
.pane{display:none}.pane.active{display:block}

/* ─── CARDS ─── */
.card{background:var(--s1);border:1px solid var(--br);border-radius:var(--r);padding:18px;margin-bottom:14px}
.card-h{font-size:11px;font-weight:600;color:var(--mut);text-transform:uppercase;letter-spacing:.06em;margin-bottom:10px}

/* ─── HERO ─── */
.hero{background:linear-gradient(135deg,#0D2818 0%,#11291B 60%,#0D1117 100%);
  border:1px solid #1F4025;border-radius:var(--r);padding:24px 22px;margin-bottom:20px;position:relative;overflow:hidden}
.hero::before{content:'';position:absolute;top:-40px;right:-40px;width:160px;height:160px;
  border-radius:50%;background:#3FB9500A;border:1px solid #3FB95015}
.hero-tag{font-size:11px;font-weight:600;color:var(--acc);text-transform:uppercase;letter-spacing:.08em;margin-bottom:6px}
.hero-title{font-size:22px;font-weight:700;color:var(--wht);margin-bottom:6px;line-height:1.3}
.hero-sub{font-size:13px;color:var(--mut);margin-bottom:16px}
.chips{display:flex;flex-wrap:wrap;gap:6px}
.chip{background:var(--s2);border:1px solid var(--br);border-radius:20px;padding:4px 12px;font-size:11px;
  display:flex;align-items:center;gap:5px;color:var(--mut)}
.chip b{color:var(--wht)}

/* ─── ALERT ─── */
.alert{border-radius:8px;padding:11px 14px;font-size:12px;margin-bottom:14px;line-height:1.5}
.alert-blue{background:#0D2818;border:1px solid #2D5A36;color:var(--acc)} /* Diubah menjadi nuansa hijau */
.alert-green{background:#0D2818;border:1px solid #2D5A36;color:var(--grn)}
.alert-orange{background:#2E1F0D;border:1px solid #5A3A1A;color:var(--orn)}
.alert-red{background:#2E1313;border:1px solid #5A2A2A;color:var(--red)}

/* ─── CHECKLIST ─── */
.cl-section{margin-bottom:10px}
.cl-head{display:flex;align-items:center;justify-content:space-between;
  padding:11px 14px;background:var(--s2);border:1px solid var(--br);
  border-radius:var(--r);cursor:pointer;margin-bottom:2px;transition:border-color .15s}
.cl-head:hover{border-color:var(--acc)}
.cl-head-left{display:flex;align-items:center;gap:10px}
.cl-head-icon{width:28px;height:28px;border-radius:6px;display:flex;align-items:center;
  justify-content:center;font-size:14px;flex-shrink:0}
.cl-head-title{font-size:13px;font-weight:600}
.cl-head-prog{font-size:11px;color:var(--mut);display:flex;align-items:center;gap:6px}
.cl-mini-bar{width:48px;height:4px;background:var(--br);border-radius:2px;overflow:hidden}
.cl-mini-fill{height:4px;border-radius:2px;background:var(--grn);transition:width .3s}
.cl-items{display:flex;flex-direction:column;gap:2px;padding:2px 0 6px}
.cl-item{display:flex;align-items:flex-start;gap:10px;padding:10px 14px;
  background:var(--s3);border-radius:8px;cursor:pointer;transition:background .1s;
  border:1px solid transparent}
.cl-item:hover{background:var(--s2);border-color:var(--br)}
.cl-item.done{background:#0D1E12;border-color:#1F4025}
.cl-box{flex-shrink:0;width:18px;height:18px;border-radius:4px;
  border:2px solid var(--br);display:flex;align-items:center;justify-content:center;
  margin-top:1px;transition:all .15s}
.cl-item.done .cl-box{background:var(--grn);border-color:var(--grn)}
.cl-tick{color:#000;font-size:10px;font-weight:900;display:none}
.cl-item.done .cl-tick{display:block}
.cl-text{font-size:13px;line-height:1.45}
.cl-item.done .cl-text{color:var(--mut)}
.cl-hint{font-size:11px;color:var(--mut);margin-top:2px;font-style:italic}
.cl-item.done .cl-hint{opacity:.5}

/* ─── PROGRESS HERO ─── */
.prog-hero{background:var(--s1);border:1px solid var(--br);border-radius:var(--r);
  padding:16px 18px;display:flex;align-items:center;gap:16px;margin-bottom:20px}
.prog-ring-wrap{position:relative;flex-shrink:0;width:60px;height:60px}
.prog-ring-wrap svg{transform:rotate(-90deg)}
.prog-ring-pct{position:absolute;inset:0;display:flex;align-items:center;
  justify-content:center;font-size:13px;font-weight:700}
.prog-info{flex:1}
.prog-title{font-size:13px;font-weight:600;color:var(--wht);margin-bottom:2px}
.prog-sub{font-size:11px;color:var(--mut)}
.prog-bar-bg{height:6px;background:var(--br);border-radius:3px;margin-top:8px;overflow:hidden}
.prog-bar-fill{height:6px;border-radius:3px;background:var(--grn);transition:width .4s}

/* ─── SUBMIT FORM ─── */
.field{margin-bottom:14px}
.field label{display:block;font-size:11px;font-weight:600;color:var(--mut);
  text-transform:uppercase;letter-spacing:.05em;margin-bottom:6px}
.input{width:100%;background:var(--s2);border:1px solid var(--br);border-radius:8px;
  padding:10px 13px;color:var(--wht);font-size:13px;font-family:var(--mono);
  outline:none;transition:border-color .15s}
.input:focus{border-color:var(--acc)}
.input::placeholder{color:var(--mut)}
textarea.input{resize:vertical;font-family:var(--ff)}

/* ─── BUTTONS ─── */
.btn{display:inline-flex;align-items:center;gap:7px;padding:10px 20px;border-radius:8px;
  font-size:13px;font-weight:700;cursor:pointer;border:none;transition:opacity .15s}
.btn:disabled{opacity:.35;cursor:not-allowed}
.btn-primary{background:var(--acc);color:#0D1117}
.btn-primary:hover:not(:disabled){opacity:.85}
.btn-ghost{background:transparent;color:var(--mut);border:1px solid var(--br)}
.btn-ghost:hover:not(:disabled){color:var(--wht);border-color:var(--mut)}
.btn-green{background:var(--grn);color:#0D1117}
.btn-green:hover:not(:disabled){opacity:.85}

/* ─── SUCCESS ─── */
.success-box{background:#0D2818;border:2px solid var(--grn);border-radius:var(--r);
  padding:28px;text-align:center;margin-bottom:16px}
.success-icon{font-size:48px;margin-bottom:12px}
.success-title{font-size:20px;font-weight:700;color:var(--grn);margin-bottom:6px}
.success-sub{font-size:13px;color:var(--mut)}

/* ─── MISC ─── */
.h2{font-size:15px;font-weight:600;color:var(--wht);margin:18px 0 10px;
  padding-bottom:8px;border-bottom:1px solid var(--br)}
.gate-block{border-radius:8px;padding:12px 14px;font-size:12px;margin:12px 0;display:none}
.gate-block.show{display:block}
.tag-list{display:flex;flex-wrap:wrap;gap:6px;}
.tag-item{background:var(--s3);border:1px solid var(--br);padding:3px 8px;border-radius:4px;font-size:12px;color:var(--acc);font-family:var(--mono)}

/* ─── REPO CARD ─── */
.repo-card{background:var(--s2);border:1px solid var(--br);border-radius:8px;padding:14px;
  display:flex;gap:12px;align-items:flex-start;margin-bottom:10px}
.repo-icon{width:36px;height:36px;border-radius:8px;display:flex;align-items:center;
  justify-content:center;font-size:18px;flex-shrink:0}
.repo-name{font-size:13px;font-weight:700;font-family:var(--mono);margin-bottom:2px}
.repo-desc{font-size:11px;color:var(--mut)}
</style>
</head>
<body>
<div class="wrap">

<div class="hero">
  <div class="hero-tag">🍀 Design Brief · Master Prompt</div>
  <div class="hero-title">README Profile Blueprint</div>
  <div class="hero-sub">Panduan pembuatan GitHub Profile README yang bersifat premium, modern, interaktif, dan memiliki identitas kuat. Jangan membuat README yang terlihat seperti template GitHub pada umumnya.</div>
  <div class="chips">
    <div class="chip"><span>👤</span><span><b>Sri Irsa Ramayani (Irsa)</b></span></div>
    <div class="chip"><span>🎓</span><span><b>Teknik Komputer</b></span></div>
    <div class="chip"><span>🏛️</span><span><b>Univ. Amikom Yogyakarta</b></span></div>
    <div class="chip"><span>🍀</span><span>Tema: <b>Semanggi Engineering</b></span></div>
  </div>
</div>

<div class="stepnav">
  <div class="step active" id="sn-1" onclick="goStep(1)">
    <div class="step-num" id="snum-1">1</div>
    <div class="step-label">Identitas Profil</div>
  </div>
  <div class="step-arrow">›</div>
  <div class="step pending" id="sn-2" onclick="goStep(2)">
    <div class="step-num" id="snum-2">2</div>
    <div class="step-label">Checklist Desain</div>
  </div>
  <div class="step-arrow">›</div>
  <div class="step pending" id="sn-3" onclick="goStep(3)">
    <div class="step-num" id="snum-3">3</div>
    <div class="step-label">Finalisasi Brief</div>
  </div>
</div>

<div class="pane active" id="pane-1">

  <div class="h2">📌 Informasi Pribadi & Fokus Utama</div>
  <div class="alert alert-blue">
    🍀 Gunakan data berikut sebagai variabel wajib saat AI / Model merancang isi (teks dan badge) pada README profil saya.
  </div>

  <div style="display:flex;flex-direction:column;gap:10px;margin-bottom:20px">
    <div class="repo-card">
      <div class="repo-icon" style="background:#0D2818">🎯</div>
      <div style="flex:1">
        <div class="repo-name" style="color:var(--acc)">Area Fokus Utama</div>
        <div class="repo-desc" style="margin-bottom:6px">Bidang spesialisasi yang sedang didalami saat ini:</div>
        <div class="tag-list">
          <span class="tag-item">Cybersecurity</span>
          <span class="tag-item">Blockchain</span>
          <span class="tag-item">Cryptography</span>
        </div>
      </div>
    </div>
    <div class="repo-card">
      <div class="repo-icon" style="background:#0D2818">📚</div>
      <div style="flex:1">
        <div class="repo-name" style="color:var(--acc)">Topik Favorit</div>
        <div class="repo-desc" style="margin-bottom:6px">Hal-hal yang paling sering saya pelajari dan riset:</div>
        <div class="tag-list">
          <span class="tag-item">Operating System</span>
          <span class="tag-item">Linux</span>
          <span class="tag-item">Computer Network</span>
          <span class="tag-item">Vulnerability Research</span>
          <span class="tag-item">Secure Architecture</span>
          <span class="tag-item">Reverse Engineering</span>
          <span class="tag-item">AI for Cybersecurity</span>
        </div>
      </div>
    </div>
    <div class="repo-card">
      <div class="repo-icon" style="background:#0D2818">⚙️</div>
      <div style="flex:1">
        <div class="repo-name" style="color:var(--acc)">Tech Stack & Tools</div>
        <div class="repo-desc" style="margin-bottom:6px">Bahasa, Framework, dan Environment yang biasa digunakan:</div>
        <div class="tag-list">
          <span class="tag-item">Python</span>
          <span class="tag-item">Flask</span>
          <span class="tag-item">MySQL</span>
          <span class="tag-item">Azure</span>
          <span class="tag-item">Wireshark</span>
          <span class="tag-item">Git</span>
          <span class="tag-item">Docker</span>
          <span class="tag-item">Arch Linux</span>
          <span class="tag-item">Debian</span>
        </div>
      </div>
    </div>
  </div>

  <div style="display:flex;justify-content:flex-end;margin-top:6px">
    <button class="btn btn-primary" onclick="goStep(2)">Lanjut ke Checklist Desain →</button>
  </div>
</div>

<div class="pane" id="pane-2">

  <div class="prog-hero">
    <div class="prog-ring-wrap">
      <svg width="60" height="60" viewBox="0 0 60 60">
        <circle cx="30" cy="30" r="24" fill="none" stroke="#30363D" stroke-width="5"/>
        <circle cx="30" cy="30" r="24" fill="none" stroke="#3FB950" stroke-width="5"
          stroke-dasharray="150.8" id="ring-dash" stroke-dashoffset="150.8"
          stroke-linecap="round" style="transition:stroke-dashoffset .5s ease"/>
      </svg>
      <div class="prog-ring-pct" id="ring-pct" style="color:var(--mut)">0%</div>
    </div>
    <div class="prog-info">
      <div class="prog-title" id="prog-title">Belum ada syarat yang disetujui</div>
      <div class="prog-sub" id="prog-sub">Centang semua aturan filosofi desain sebelum memproses prompt</div>
      <div class="prog-bar-bg"><div class="prog-bar-fill" id="pbar" style="width:0%"></div></div>
    </div>
    <div id="prog-count-big" style="font-size:22px;font-weight:700;color:var(--mut);flex-shrink:0">0<span style="font-size:13px;color:var(--br)">/12</span></div>
  </div>

  <div class="cl-section">
    <div class="cl-head" onclick="toggleSec('a')">
      <div class="cl-head-left">
        <div class="cl-head-icon" style="background:#0D2818">✅</div>
        <div>
          <div class="cl-head-title" style="color:var(--acc)">Syarat Wajib (DO)</div>
          <div style="font-size:10px;color:var(--mut)">Elemen estetika dan tema yang diizinkan</div>
        </div>
      </div>
      <div class="cl-head-prog">
        <div class="cl-mini-bar"><div class="cl-mini-fill" id="mbar-a" style="width:0%"></div></div>
        <span id="sprog-a" style="color:var(--acc)">0/6</span>
      </div>
    </div>
    <div class="cl-body" id="cl-a">
      <div class="cl-items">
        <div class="cl-item" onclick="tick(this,'a')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">Gunakan tema sentral: <strong>Semanggi Engineering</strong></div><div class="cl-hint">Harus mencerminkan estetika daun semanggi dan pertumbuhan.</div></div>
        </div>
        <div class="cl-item" onclick="tick(this,'a')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">Gunakan palet warna: <strong>Light Green, Soft Green, White</strong></div><div class="cl-hint">Warna-warna ini harus diterapkan pada shield/badge atau teks dekoratif.</div></div>
        </div>
        <div class="cl-item" onclick="tick(this,'a')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">Seluruh ikon/emoji awan diubah menjadi <strong>Semanggi (🍀)</strong></div><div class="cl-hint">Termasuk mengganti kata 'Sky' atau 'Cloud' menjadi Semanggi/Clover.</div></div>
        </div>
        <div class="cl-item" onclick="tick(this,'a')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">Gaya desain: <strong>Clean, Minimal, Professional, Friendly</strong></div><div class="cl-hint">Tampilan harus modern, bersih, dan enak dilihat (bukan berantakan).</div></div>
        </div>
        <div class="cl-item" onclick="tick(this,'a')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">Gaya pendekatan teks: <strong>Anime Slice of Life</strong></div><div class="cl-hint">Penyampaian teks naratif yang tenang, segar, ramah, layaknya slice of life.</div></div>
        </div>
        <div class="cl-item" onclick="tick(this,'a')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">Harus bersifat interaktif dan memiliki <strong>identitas kuat (Irsa)</strong></div><div class="cl-hint">Bukan sekadar template GitHub pada umumnya.</div></div>
        </div>
      </div>
    </div>
  </div>

  <div class="cl-section">
    <div class="cl-head" onclick="toggleSec('b')">
      <div class="cl-head-left">
        <div class="cl-head-icon" style="background:#2E1313">❌</div>
        <div>
          <div class="cl-head-title" style="color:var(--red)">Daftar Larangan (DON'T)</div>
          <div style="font-size:10px;color:var(--mut)">Hal yang pantang dimasukkan ke dalam README</div>
        </div>
      </div>
      <div class="cl-head-prog">
        <div class="cl-mini-bar"><div class="cl-mini-fill" id="mbar-b" style="width:0%;background:var(--red)"></div></div>
        <span id="sprog-b" style="color:var(--red)">0/6</span>
      </div>
    </div>
    <div class="cl-body" id="cl-b">
      <div class="cl-items">
        <div class="cl-item" onclick="tick(this,'b')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">DILARANG menggunakan tema <strong>Hacker / Anonymous</strong></div><div class="cl-hint">Kesan "edgy" hacker harus dihilangkan total.</div></div>
        </div>
        <div class="cl-item" onclick="tick(this,'b')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">DILARANG menggunakan tema <strong>Matrix / Green Terminal</strong></div><div class="cl-hint">Bukan terminal hijau klasik retro.</div></div>
        </div>
        <div class="cl-item" onclick="tick(this,'b')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">DILARANG menggunakan palet warna <strong>Dark Red</strong></div><div class="cl-hint">Fokus pada warna hijau semanggi yang menenangkan.</div></div>
        </div>
        <div class="cl-item" onclick="tick(this,'b')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">DILARANG menggunakan ornamen <strong>Skull (Tengkorak)</strong></div><div class="cl-hint">Gunakan elemen yang merepresentasikan pertumbuhan/daun.</div></div>
        </div>
        <div class="cl-item" onclick="tick(this,'b')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">DILARANG menggunakan vibes <strong>Neon Hacker</strong></div><div class="cl-hint">Hindari warna neon mencolok yang menyakitkan mata.</div></div>
        </div>
        <div class="cl-item" onclick="tick(this,'b')">
          <div class="cl-box"><span class="cl-tick">✓</span></div>
          <div><div class="cl-text">DILARANG menggunakan template <strong>pasaran GitHub</strong></div><div class="cl-hint">Layout harus unik dan menonjolkan spesialisasi Irsa.</div></div>
        </div>
      </div>
    </div>
  </div>

  <div id="gate-warn" class="gate-block alert-orange" style="display:block;margin-top:8px">
    ⚠️ Kamu perlu menyetujui (mencentang) <strong>100% aturan checklist</strong> sebelum mengunci Master Prompt ini.
  </div>
  <div id="gate-ok" class="gate-block alert-green" style="display:none;margin-top:8px">
    ✅ Keren Irsa! Aturan filosofi desain sudah disetujui 100%. Lanjutkan ke tahap finalisasi.
  </div>

  <div style="display:flex;justify-content:space-between;margin-top:16px;gap:8px">
    <button class="btn btn-ghost" onclick="goStep(1)">← Kembali</button>
    <button class="btn btn-primary" id="btn-next-submit" disabled onclick="goStep(3)">Kunci & Finalisasi →</button>
  </div>
</div>

<div class="pane" id="pane-3">

  <div id="submit-form">
    <div class="alert alert-blue">
      🍀 Konfirmasi terakhir untuk menyimpan pengaturan ini sebagai <strong>Master Prompt</strong>.
    </div>

    <div class="card">
      <div class="card-h">Tanda Tangan Digital Profil</div>

      <div class="field">
        <label>Nama Pemilik README</label>
        <input class="input" type="text" id="inp-nama" value="Sri Irsa Ramayani" disabled style="opacity:0.8">
      </div>

      <div class="field">
        <label>Tema yang Diterapkan</label>
        <input class="input" type="text" value="🍀 Semanggi Engineering" disabled style="opacity:0.8; color:var(--acc)">
      </div>

      <div class="field">
        <label>Status Kepatuhan Desain</label>
        <div class="input" style="background:var(--s3);cursor:default;color:var(--mut)" id="cl-status-field">
          Menunggu persetujuan checklist...
        </div>
      </div>
    </div>

    <div style="display:flex;justify-content:space-between;align-items:center;margin-top:4px;gap:8px;flex-wrap:wrap">
      <button class="btn btn-ghost" onclick="goStep(2)">← Kembali Edit Aturan</button>
      <button class="btn btn-green" id="btn-submit" onclick="doSubmit()">✓ Selesai & Generate Brief</button>
    </div>
  </div>

  <div id="submit-success" style="display:none">
    <div class="success-box">
      <div class="success-icon">🍀</div>
      <div class="success-title">Blueprint Siap Digunakan!</div>
      <div class="success-sub">Halo Irsa, Master Prompt kamu sudah dikunci dan siap diberikan ke AI.</div>
    </div>

    <div class="card">
      <div class="card-h">Tindakan Selanjutnya</div>
      <ul class="ul" style="list-style:none;padding:0;display:flex;flex-direction:column;gap:5px">
        <li style="font-size:12.5px;color:var(--wht);padding-left:16px;position:relative"><span style="position:absolute;left:0;color:var(--acc);font-size:11px;top:1px">→</span> Salin seluruh instruksi yang kita buat ini.</li>
        <li style="font-size:12.5px;color:var(--wht);padding-left:16px;position:relative"><span style="position:absolute;left:0;color:var(--acc);font-size:11px;top:1px">→</span> Simpan instruksi di <strong>Notion</strong> atau buat file bernama <code>README_BLUEPRINT.md</code> di komputermu.</li>
        <li style="font-size:12.5px;color:var(--wht);padding-left:16px;position:relative"><span style="position:absolute;left:0;color:var(--acc);font-size:11px;top:1px">→</span> Berikan prompt ini kapan saja kamu meminta bantuan AI untuk merancang komponen GitHub milikmu!</li>
      </ul>
    </div>
  </div>

</div>

</div><script>
// ── DATA ─────────────────────────────────
const SECS = {
  a:{total:6,color:'var(--acc)'},
  b:{total:6,color:'var(--red)'}
};
const TOTAL = 12;
let clPct = 0;

// ── STEP NAV ─────────────────────────────
let curStep = 1;
function goStep(n) {
  document.querySelectorAll('.pane').forEach(p => p.classList.remove('active'));
  document.getElementById('pane-'+n).classList.add('active');
  
  [1,2,3].forEach(i => {
    const sn = document.getElementById('sn-'+i);
    const num = document.getElementById('snum-'+i);
    sn.classList.remove('active','done','pending');
    if (i < n) { sn.classList.add('done'); num.textContent = '✓'; }
    else if (i === n) { sn.classList.add('active'); num.textContent = i; }
    else { sn.classList.add('pending'); num.textContent = i; }
  });
  curStep = n;
  window.scrollTo({top:0,behavior:'smooth'});
  if (n === 3) updateSubmitStatus();
}

// ── CHECKLIST ────────────────────────────
function tick(el, sec) {
  el.classList.toggle('done');
  updateSec(sec);
  updateTotal();
}
function toggleSec(id) {
  const body = document.getElementById('cl-'+id);
  body.style.display = body.style.display === 'none' ? '' : '';
}
function updateSec(sec) {
  const items = document.querySelectorAll('#cl-'+sec+' .cl-item');
  const done = document.querySelectorAll('#cl-'+sec+' .cl-item.done').length;
  const total = items.length;
  const pct = total > 0 ? Math.round(done/total*100) : 0;
  document.getElementById('mbar-'+sec).style.width = pct+'%';
  document.getElementById('sprog-'+sec).textContent = done+'/'+total;
}
function updateTotal() {
  const done = document.querySelectorAll('.cl-item.done').length;
  clPct = Math.round(done/TOTAL*100);
  const circ = 2 * Math.PI * 24; 
  const offset = circ - (clPct/100)*circ;
  document.getElementById('ring-dash').style.strokeDashoffset = offset;
  document.getElementById('ring-pct').textContent = clPct+'%';
  document.getElementById('ring-pct').style.color = clPct >= 100 ? 'var(--grn)' : 'var(--mut)';
  document.getElementById('pbar').style.width = clPct+'%';
  document.getElementById('pbar').style.background = clPct >= 100 ? 'var(--grn)' : 'var(--ylw)';
  document.getElementById('prog-count-big').innerHTML = done+'<span style="font-size:13px;color:var(--br)">/'+TOTAL+'</span>';
  document.getElementById('prog-count-big').style.color = clPct >= 100 ? 'var(--grn)' : 'var(--mut)';

  let title, sub;
  if (clPct === 0) { title = 'Belum ada syarat yang disetujui'; sub = 'Centang semua aturan filosofi desain'; }
  else if (clPct < 100) { title = 'Hampir selesai!'; sub = 'Setujui sisa poin checklist sebelum lanjut'; }
  else { title = 'Blueprint 100% Disetujui! 🍀'; sub = 'Semua visi desain sudah siap'; }
  
  document.getElementById('prog-title').textContent = title;
  document.getElementById('prog-sub').textContent = sub;

  const ok = clPct === 100; // Harus 100% untuk lanjut
  document.getElementById('gate-warn').style.display = ok ? 'none' : 'block';
  document.getElementById('gate-ok').style.display = ok ? 'block' : 'none';
  document.getElementById('btn-next-submit').disabled = !ok;
  updateSubmitStatus();
}

function updateSubmitStatus() {
  const clf = document.getElementById('cl-status-field');
  if(clf){
    if (clPct >= 100) { clf.style.color='var(--grn)'; clf.textContent='✓ Checklist '+clPct+'% — Semua aturan desain telah dikunci'; }
    else { clf.style.color='var(--red)'; clf.textContent='✗ Checklist '+clPct+'% — Mohon setujui semua poin aturan (Tab 2)'; }
  }
}

function doSubmit() {
  document.getElementById('submit-form').style.display = 'none';
  document.getElementById('submit-success').style.display = 'block';
  document.getElementById('sn-3').classList.remove('active');
  document.getElementById('sn-3').classList.add('done');
  document.getElementById('snum-3').textContent = '✓';
  window.scrollTo({top:0,behavior:'smooth'});
}

// Init
Object.keys(SECS).forEach(s => updateSec(s));
updateTotal();
goStep(1);
</script>
</body>
</html>
