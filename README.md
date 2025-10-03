<!doctype html>
<html lang="az">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Xidmətim.az — Demo Landing</title>
  <style>
    :root{
      --bg:#ffffff; 
      --text:#0f172a;      /* əsas text rəngi */
      --muted:#6b7280;     /* açıq rejimdə boz */
      --accent:#0ea5a4; 
      --accent-dark:#0b8c88; 
      --gold:#d4af37;
      --card:#f8fafc; 
      --radius:14px; 
      --shadow:0 6px 18px rgba(2,6,23,0.08);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    
    body.dark .mock-screen {
  background: #1e293b; /* tünd göy-boz rəng */
  border: 1px solid #334155; /* daha tünd sərhəd */
  color: #f8fafc; /* yazılar ağ olsun */
}

body.dark .mock-screen input {
  background: #0f172a;
  border: 1px solid #334155;
  color: #f8fafc;
}

body.dark .mock-screen div {
  color: #f8fafc; /* içindəki yazılar oxunsun */
}

    body{
      margin:0;
      background:linear-gradient(180deg,#f7f9fb 0%, #ffffff 100%);
      color:var(--text);
      transition: all 0.3s ease;
    }
    body.dark{
      --bg:#0f172a;        /* fon rəngi */
      --text:#f8fafc;      /* əsas yazılar */
      --muted:#cbd5e1;     /* muted yazılar üçün açıq boz */
      --card:#1e293b;      /* kartların fonu */
      background:var(--bg);
      color:var(--text);
    }
    *{box-sizing:border-box}
    .container{max-width:980px;margin:28px auto;padding:0 18px}

    /* Header */
    header{display:flex;align-items:center;justify-content:space-between;padding:18px 0}
    .brand{display:flex;align-items:center;gap:12px}
    .logo{
      width:56px;
      height:56px;
      border-radius:12px;
      display:flex;
      align-items:center;
      justify-content:center;
      box-shadow:var(--shadow);
      background:linear-gradient(135deg,var(--accent),var(--accent-dark));
    }
    .logo img{
      width:70%;
      height:70%;
      object-fit:contain;
      border-radius:12px;
    }
    .brand h1{margin:0;font-size:18px}
    .nav{display:flex;gap:12px;align-items:center}
    .btn{background:var(--accent);color:white;padding:10px 14px;border-radius:10px;border:none;cursor:pointer;font-weight:600}
    .btn.ghost{background:transparent;color:var(--accent);border:1px solid rgba(14,165,164,0.12)}
    .btn-toggle{margin-left:10px;}

    /* Hero */
    .hero{display:grid;grid-template-columns:1fr 380px;gap:22px;align-items:center;margin-top:18px}
    .hero h2{font-size:28px;margin:0 0 10px}
    .hero p{color:var(--muted);margin:0 0 18px}
    .search{display:flex;gap:8px;margin-top:8px}
    .search input{flex:1;padding:12px 14px;border-radius:10px;border:1px solid #e6eef0}
    .search button{padding:12px 16px;border-radius:10px;border:none;background:var(--gold);color:#072020;font-weight:700}

    .phone-mock{background:linear-gradient(180deg,#fff 0,#f3f8f9 100%);padding:18px;border-radius:18px;box-shadow:var(--shadow);}
    .mock-screen{width:320px;height:560px;border-radius:12px;background:white;border:1px solid #eef6f7;overflow:hidden}

    /* categories */
    .cats{display:flex;gap:10px;flex-wrap:wrap;margin-top:16px}
    .cat{flex:0 0 20%;min-width:110px;background:var(--card);padding:12px;border-radius:12px;text-align:center;box-shadow:0 4px 14px rgba(2,6,23,0.04);cursor:pointer}
    .cat span{display:block;font-size:22px}
    .cat small{display:block;color:var(--muted);margin-top:6px}

    /* service cards */
    .services{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-top:22px}
    .card{background:var(--card);border-radius:12px;padding:12px;box-shadow:var(--shadow);display:flex;gap:12px;align-items:center}
    .card img{width:68px;height:68px;border-radius:10px;object-fit:cover}
    .card .meta{flex:1}
    .meta h4{margin:0 0 6px}
    .meta p{margin:0;color:var(--muted);font-size:13px}
    .meta .row{display:flex;gap:8px;align-items:center;margin-top:8px}
    .price{font-weight:700;color:var(--text)}

    /* footer */
    footer{margin-top:30px;padding:14px 0;border-top:1px solid #f0f4f5;color:var(--muted);display:flex;justify-content:space-between}

    /* responsive */
    @media (max-width:900px){
      .hero{grid-template-columns:1fr;}
      .services{grid-template-columns:1fr;}
      .cat{flex:1 1 30%}
      .mock-screen{width:280px;height:520px}
    }

    /* Modal */
    .modal-back{position:fixed;inset:0;background:rgba(2,6,23,0.45);display:none;align-items:center;justify-content:center;padding:16px}
    .modal{background:var(--card);padding:20px;border-radius:12px;max-width:420px;width:100%;box-shadow:0 10px 30px rgba(2,6,23,0.25)}
    .modal h3{margin:0 0 12px}
    .field{margin-bottom:10px}
    .field input{width:100%;padding:11px;border-radius:8px;border:1px solid #e6eef0}
    .small{font-size:13px;color:var(--muted)}
    .badge{background:linear-gradient(90deg,var(--accent),var(--accent-dark));color:white;padding:6px 10px;border-radius:999px;font-weight:700}

    /* düzəlişlər muted üçün */
    p, .small, .meta p, .meta span, footer {
      color:var(--muted);
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">
          <img src="https://i.postimg.cc/TPb5Yxx7/file-00000000fe0061f4885624bf1ab5f132.png" alt="Xidmətim.az" />
        </div>
        <div>
          <h1>Xidmətim.az</h1>
          <div class="small">Xidmət bir toxunuş uzağında</div>
        </div>
      </div>
      <div class="nav">
        <button class="btn ghost" id="demo-login">Giriş et</button>
        <button class="btn" id="book-now">Sifariş et</button>
        <button class="btn btn-toggle" id="toggleDark">🌙</button>
      </div>
    </header>

    <main>
      <section class="hero">
        <div>
          <h2>Ev xidmətlərini daha asan sifariş et</h2>
          <p>Soyuducu, paltaryuyan, kondisioner, təmizlik və digər xidmətlər — bir app-da. Etibarlı ustalar, şəffaf qiymətlər və sürətli xidmət.</p>

          <div class="search">
            <input id="searchInput" placeholder="Məsələn: Soyuducu ustası" />
            <button id="searchBtn">Axtar</button>
          </div>

          <div class="cats">
            <div class="cat"> <span>🧊</span><small>Soyuducu</small></div>
            <div class="cat"> <span>🧺</span><small>Paltar yuyan</small></div>
            <div class="cat"> <span>❄</span><small>Kondisioner</small></div>
            <div class="cat"> <span>🧹</span><small>Təmizlik</small></div>
            <div class="cat"> <span>🔌</span><small>Elektrikçi</small></div>
          </div>

          <div class="services">
            <div class="card">
              <img src="https://tezbazar.az/uploads/news/product_9326832366960625.jpg" alt="" />
              <div class="meta">
                <h4>Rəşad Usta <span style="font-size:13px;color:var(--muted)">• ⭐ 4.9</span></h4>
                <p class="small">Soyuducu təmiri • 15-30 dəq</p>
                <div class="row">
                  <div class="price">10-15 AZN</div>
                  <div class="badge">Tez</div>
                </div>
              </div>
            </div>

            <div class="card">
              <img src="https://st5.depositphotos.com/76785014/66493/i/950/depositphotos_664932152-stock-photo-happy-woman-cleaning-house-housekeeping.jpg" alt="" />
              <div class="meta">
                <h4>Aysel Xanim <span style="font-size:13px;color:var(--muted)">• ⭐ 4.8</span></h4>
                <p class="small">Temizlik xidmeti • 30-45 dəq</p>
                <div class="row">
                  <div class="price">50-60 AZN</div>
                </div>
              </div>
            </div>

            <div class="card">
              <img src="https://upload.wikimedia.org/wikipedia/commons/6/6d/Mehmet_Usta.jpg" alt="" />
              <div class="meta">
                <h4>Nicat Usta <span style="font-size:13px;color:var(--muted)">• ⭐ 4.7</span></h4>
                <p class="small">Elektrik işləri • 10-20 dəq</p>
                <div class="row">
                  <div class="price">5-15 AZN</div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="phone-mock">
          <div class="mock-screen" id="mockScreen">
            <div style="padding:14px">
              <div style="display:flex;align-items:center;justify-content:space-between">
                <strong>Xidmətim</strong>
                <div style="font-size:14px;color:var(--muted)">12:41</div>
              </div>
              <div style="margin-top:12px">
                <input id="miniSearch" placeholder="Xidmət axtar..." style="width:100%;padding:10px;border-radius:10px;border:1px solid #eef6f7" />
              </div>
              <div style="margin-top:12px;display:flex;gap:8px;flex-wrap:wrap">
                <div style="background:#f1fbfa;padding:8px;border-radius:10px">🧊 Soyuducu</div>
                <div style="background:#fff6f0;padding:8px;border-radius:10px">🧺 Təmizlik</div>
                <div style="background:#f8f6ff;padding:8px;border-radius:10px">🔌 Elektrikçi</div>
              </div>

              <div style="margin-top:18px;background:var(--card);padding:8px;border-radius:10px;border:1px solid #eef6f7">
                <div style="display:flex;align-items:center;gap:8px">
                  <img src="https://tezbazar.az/uploads/news/product_9326832366960625.jpg" style="width:54px;height:54px;border-radius:8px;object-fit:cover" />
                  <div style="flex:1">
                    <div style="font-weight:700">Rəşad Usta</div>
                    <div style="font-size:12px;color:var(--muted)">15-25 dəq • 10-15 AZN</div>
                  </div>
                  <button style="background:var(--accent);color:white;padding:8px 10px;border-radius:10px;border:none">Çağır</button>
                </div>
              </div>
            </div>
          </div>
        </div>

      </section>
    </main>

    <footer>
      <div>© 2025 Xidmətim.az</div>
      <div>Əlaqə: info@xidmetim.az</div>
    </footer>
  </div>

  <!-- Modal: Login -->
  <div class="modal-back" id="modalBack">
    <div class="modal" role="dialog" aria-modal="true">
      <h3>Giriş et</h3>
      <div class="field"><input id="email" placeholder="Email və ya telefon" /></div>
      <div class="field"><input id="password" type="password" placeholder="Şifrə" /></div>
      <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:12px">
        <button class="btn ghost" id="closeModal">Bağla</button>
        <button class="btn" id="doLogin">Daxil ol</button>
      </div>
      <div style="margin-top:8px;" class="small">Demo: hər hansı email və şifrə ilə daxil ola bilərsiniz.</div>
    </div>
  </div>

  <!-- Modal: Booking confirmation -->
  <div class="modal-back" id="bookBack">
    <div class="modal">
      <h3>Sifariş təsdiqi</h3>
      <p class="small">Xidmət: <strong id="bkService">Soyuducu ustası</strong></p>
      <div class="field"><input id="bkAddress" placeholder="Ünvan (məs: Nərimanov r.)" /></div>
      <div class="field"><input id="bkTime" placeholder="Vaxt (məs: 14:00)" /></div>
      <div style="display:flex;gap:8px;justify-content:flex-end;margin-top:8px">
        <button class="btn ghost" id="closeBook">Ləğv et</button>
        <button class="btn" id="confirmBook">Təsdiqlə</button>
      </div>
    </div>
  </div>

  <script>
    // Modal handlers
    const modalBack = document.getElementById('modalBack')
    const bookBack = document.getElementById('bookBack')
    document.getElementById('demo-login').addEventListener('click', ()=> modalBack.style.display='flex')
    document.getElementById('closeModal').addEventListener('click', ()=> modalBack.style.display='none')
    document.getElementById('book-now').addEventListener('click', ()=> bookBack.style.display='flex')
    document.getElementById('closeBook').addEventListener('click', ()=> bookBack.style.display='none')

    document.getElementById('doLogin').addEventListener('click', ()=>{
      const email = document.getElementById('email').value || 'demo@x';
      modalBack.style.display='none'
      alert('Daxil oldunuz: '+email)
    })

    document.getElementById('confirmBook').addEventListener('click', ()=>{
      const addr = document.getElementById('bkAddress').value || 'Seçilmiş ünvan';
      const time = document.getElementById('bkTime').value || 'Tezliklə';
      bookBack.style.display='none'
      setTimeout(()=> alert('Sifariş uğurla yaradıldı!\nÜnvan: '+addr+'\nVaxt: '+time),200)
    })

    // quick search -> open booking with selected text
    document.getElementById('searchBtn').addEventListener('click', ()=>{
      const q = document.getElementById('searchInput').value || 'Soyuducu ustası'
      document.getElementById('bkService').innerText = q
      bookBack.style.display='flex'
    })

    // mock "Çağır" in phone mock
    document.querySelectorAll('.mock-screen button').forEach(btn=> btn.addEventListener('click', ()=>{
      document.getElementById('bkService').innerText = 'Rəşad Usta'
      bookBack.style.display='flex'
    }))
  </script>
    <script>
    const toggleBtn = document.getElementById('toggleDark');
    toggleBtn.addEventListener('click', ()=>{
      document.body.classList.toggle('dark');
      // Buton simvolunu dəyişmək
      if(document.body.classList.contains('dark')){
        toggleBtn.textContent = '☀️';
      } else {
        toggleBtn.textContent = '🌙';
      }
    });
  </script>
  
</body>
</html>
