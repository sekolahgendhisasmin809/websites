
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>SMK - Demo Website Sekolah (Soft Ungu)</title>

  <!-- OPTIONAL: gunakan Google Fonts jika online -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg-1: #f6f3fb;          /* very soft lavender base */
      --purple-1: #6e55a3;      /* primary purple */
      --purple-2: #9a7fc9;      /* lighter purple */
      --accent: #ffffff;
      --muted: #6b5b7a;
      --card: rgba(255,255,255,0.85);
      --glass: rgba(255,255,255,0.06);
      --radius: 12px;
      --max-width: 1100px;
      font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }

    /* Page background */
    html,body{
      height:100%;
      margin:0;
      background: linear-gradient(180deg, var(--bg-1), #efeaf8 60%);
      color: #2b2350;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    /* Layout container */
    .wrap{
      max-width: var(--max-width);
      margin: 28px auto;
      padding: 20px;
    }

    /* Header / nav */
    header {
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:16px;
      margin-bottom:18px;
    }
    .brand {
      display:flex;
      gap:12px;
      align-items:center;
    }
    .logo {
      width:64px;
      height:64px;
      border-radius:12px;
      background: linear-gradient(135deg,var(--purple-2), var(--purple-1));
      color: white;
      display:flex;
      align-items:center;
      justify-content:center;
      font-weight:700;
      font-size:18px;
      box-shadow: 0 8px 22px rgba(110,85,163,0.14);
    }
    .brand h1{ margin:0; font-size:18px; color:var(--purple-1); }
    nav a{
      color:var(--muted);
      text-decoration:none;
      margin-left:14px;
      font-weight:600;
      padding:8px 10px;
      border-radius:8px;
    }
    nav a:hover{ background: rgba(106,84,173,0.06); color:var(--purple-1); }

    /* HERO */
    .hero{
      display:flex;
      gap:20px;
      background: linear-gradient(90deg, rgba(153,127,201,0.07), rgba(170,143,209,0.04));
      border-radius: var(--radius);
      padding:22px;
      align-items:center;
      box-shadow: 0 8px 26px rgba(80,64,128,0.06);
      border: 1px solid rgba(110,85,163,0.06);
    }
    .hero-left{ flex:1; }
    .hero h2{ margin:0 0 8px 0; color:var(--purple-1); }
    .hero p{ margin:0 0 14px 0; color:#4a4065; line-height:1.5; }
    .btn{
      display:inline-block;
      padding:10px 14px;
      border-radius:10px;
      background: linear-gradient(90deg,var(--purple-1), var(--purple-2));
      color:white;
      border:none;
      cursor:pointer;
      font-weight:700;
      text-decoration:none;
    }

    .hero-right{
      width:220px;
      text-align:center;
    }
    .school-card{
      background:var(--card);
      border-radius:10px;
      padding:10px;
      box-shadow: 0 6px 18px rgba(80,64,128,0.06);
      border:1px solid rgba(0,0,0,0.04);
    }
    .school-card img{ width:100%; border-radius:8px; display:block; }

    /* Main grid */
    .grid{
      margin-top:18px;
      display:grid;
      grid-template-columns: 1fr 340px;
      gap:18px;
    }
    main .card, aside .card {
      background: white;
      border-radius:10px;
      padding:16px;
      box-shadow: 0 10px 30px rgba(97,81,142,0.04);
      border:1px solid rgba(0,0,0,0.04);
    }

    .section-head{
      display:flex;
      justify-content:space-between;
      align-items:center;
      margin-bottom:12px;
    }
    .section-head h3{ margin:0; color:var(--purple-1); }

    /* Profile layout */
    .profile{
      display:flex;
      gap:18px;
      align-items:flex-start;
    }
    .profile img{
      width:160px;
      height:110px;
      object-fit:cover;
      border-radius:8px;
      border:1px solid rgba(0,0,0,0.04);
    }

    /* Table (siswa) */
    table {
      width:100%;
      border-collapse:collapse;
      font-size:14px;
      color:#3b3455;
    }
    th, td {
      padding:10px 8px;
      border-bottom:1px solid rgba(0,0,0,0.04);
      text-align:left;
    }
    thead th {
      background: linear-gradient(90deg, rgba(106,84,173,0.04), rgba(153,127,201,0.02));
      color:var(--purple-1);
      font-weight:700;
    }

    /* Kejuruan cards */
    .majors{
      display:flex;
      gap:12px;
      flex-wrap:wrap;
    }
    .major {
      flex: 1 1 260px;
      background: linear-gradient(180deg, rgba(154,127,201,0.06), rgba(255,255,255,0.9));
      border-radius:8px;
      padding:12px;
      border:1px solid rgba(0,0,0,0.04);
      color:#2b2350;
    }

    /* Sidebar widgets */
    .widget { margin-bottom:12px; }

    /* Floating login button (opens modal) */
    .login-btn {
      position:fixed;
      right:20px;
      bottom:20px;
      background:var(--purple-1);
      color:white;
      border:none;
      padding:12px 14px;
      border-radius:14px;
      box-shadow: 0 10px 30px rgba(110,85,163,0.18);
      cursor:pointer;
      z-index:60;
    }

    /* Modal */
    .modal-backdrop{
      position:fixed;
      inset:0;
      background: rgba(20,16,40,0.45);
      display:none;
      align-items:center;
      justify-content:center;
      z-index:80;
    }
    .modal{
      width:360px;
      border-radius:12px;
      padding:18px;
      background: white;
      color: #2b2350;
      box-shadow: 0 20px 50px rgba(30,20,60,0.4);
      border:1px solid rgba(0,0,0,0.06);
    }
    .modal h4{ margin:0 0 8px 0; color:var(--purple-1); }
    .modal input{
      width:100%;
      padding:10px 12px;
      margin-bottom:10px;
      border-radius:8px;
      border:1px solid rgba(0,0,0,0.07);
      font-size:14px;
    }
    .modal .actions{ display:flex; gap:10px; align-items:center; justify-content:space-between; margin-top:6px; }

    footer{ text-align:center; color:#6b5b7a; margin:28px 0; font-size:14px; }

    /* Responsive */
    @media (max-width:980px){
      .grid{ grid-template-columns: 1fr; }
      .hero{ flex-direction:column; }
      .hero-right{ width:100%; }
    }
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="brand">
        <div class="logo" aria-hidden>SMK</div>
        <div>
          <h1>SMK Negeri 100 Batam</h1>
          <div style="font-size:13px; color:#7b6a8c;">Inovatif dan Berbudaya</div>
        </div>
      </div>

      <nav aria-label="Navigasi utama">
        <a href="#home">Home</a>
        <a href="#profile">Profil</a>
        <a href="#siswa">Nama Siswa</a>
        <a href="#kejuruan">Kejuruan</a>
        <a href="#" id="loginNav">Login</a>
      </nav>
    </header>

    <!-- HERO -->
    <section id="home" class="hero" aria-label="Halaman utama">
      <div class="hero-left">
        <h2>Selamat Datang di SMK Negeri 100 Batam</h2>
        <p>
          halaman ini menampilkan profil sekolah, daftar siswa, program kejuruan, serta form login.
        </p>
        <a class="btn" href="#profile">Lihat Profil</a>
      </div>

      <div class="hero-right">
        <div class="school-card" aria-hidden>
          <div style="margin-top:10px; font-weight:700; color:var(--purple-1);">SMK Negeri 100 Batam</div>
          <div style="font-size:13px; color:#6b5b7a;">Jl.No.20.Batam</div>
        </div>
      </div>
    </section>

    <!-- GRID -->
    <div class="grid">
      <main>
        <!-- Profil -->
        <section id="profile" class="card" aria-label="Profil sekolah">
          <div class="section-head">
            <h3>Profil Sekolah</h3>
            <small style="color:#7b6a8c;">Tentang Sekolah</small>
          </div>

          <div class="profile">
            <img src="https://uploads.onecompiler.io/43w7h5fjp/43xrc6f2j/sekolah.jpeg">
            <div>
              <h4 style="margin:0 0 6px 0; color:var(--purple-1);">SMK Negeri 100 Batam</h4>
              <p style="margin:0 0 8px 0; color:#4a4065;">
                SMK Negeri 100 berfokus pada penguatan berpikir kritis dalam pemecahan masalah serta mendukung oppa oppa korea
                yang susah digapai.
              </p>

              <strong>Visi</strong>
              <p style="margin:6px 0 8px 0;">Menjadi SMK unggulan dalam pengembangan keahlian vokasi dan teknologi.</p>

              <strong>Misi</strong>
              <ol style="margin:6px 0 0 18px; color:#4a4065;">
                <li>Menyelenggarakan pendidikan berorientasi kompetensi di dunia teknologi.</li>
                <li>Meningkatkan kualitas pendidik.</li>
                <li>Memfasilitasi kerja sama dengan dunia usaha/industri.</li>
              </ol>
            </div>
          </div>
        </section>

        <!-- Daftar Siswa -->
        <section id="siswa" class="card" aria-label="Daftar siswa" style="margin-top:16px;">
          <div class="section-head">
            <h3>Daftar Nama Siswa</h3>
            <div style="display:flex; gap:10px; align-items:center;">
              <small style="color:#7b6a8c;">data statis</small>
              <input id="searchSiswa" placeholder="Cari nama / nis" style="padding:8px 10px; border-radius:8px; border:1px solid rgba(0,0,0,0.06);">
            </div>
          </div>

          <div style="overflow:auto;">
            <table id="tblSiswa" aria-label="Tabel siswa">
              <thead>
                <tr><th>No</th><th>NIS</th><th>Nama</th><th>Kelas</th><th>Kejuruan</th></tr>
              </thead>
              <tbody>
                <tr><td>1</td><td>2019001</td><td>NAYZILA FITRIA</td><td>RPL 1</td><td>RPL</td></tr>
                <tr><td>2</td><td>2019002</td><td>WINIE TRI</td><td>RPL 1</td><td>RPL</td></tr>
                <tr><td>3</td><td>2019003</td><td>LIDYA STAR</td><td>RPL 1</td><td>RPL</td></tr>
                <tr><td>4</td><td>2019004</td><td>BUNGA RAMADHANI</td><td>RPL 1</td><td>RPL</td></tr>
                <tr><td>5</td><td>2019005</td><td>GENDHIS NOOR</td><td>RPL 1</td><td>RPL</td></tr>
              </tbody>
            </table>
          </div>

        <!-- Kejuruan -->
        <section id="kejuruan" class="card" aria-label="Kejuruan" style="margin-top:16px;">
          <div class="section-head">
            <h3>Kejuruan / Program Keahlian</h3>
            <small style="color:#7b6a8c;">Program unggulan</small>
          </div>

          <div class="majors">
            <div class="major">
              <h4 style="margin:0 0 6px 0; color:var(--purple-1);">Rekayasa Perangkat Lunak (RPL)</h4>
              <p style="margin:0; color:#4a4065;">Pembelajaran pemrograman, database, aplikasi web & mobile.</p>
            </div>

            <div class="major">
              <h4 style="margin:0 0 6px 0; color:var(--purple-1);">Teknik Komputer & Jaringan (TKJ)</h4>
              <p style="margin:0; color:#4a4065;">Jaringan komputer, instalasi, dan administrasi jaringan.</p>
            </div>

            <div class="major">
              <h4 style="margin:0 0 6px 0; color:var(--purple-1);">Teknik Audio Video (TAV)</h4>
              <p style="margin:0; color:#4a4065;">Produksi multimedia, editing audio & video.</p>
            </div>

            <div class="major">
              <h4 style="margin:0 0 6px 0; color:var(--purple-1);">Manejemen Perkantoran</h4>
              <p style="margin:0; color:#4a4065;">Keterampilan administrasi, manajemen, dan komunikasi bisnis.</p>
            </div>
          </div>
        </section>

      <!-- SIDEBAR -->
      <aside>
        <div class="card widget" aria-label="Berita singkat">
          <div class="section-head"><h3>Berita Singkat</h3><small style="color:#7b6a8c;">Update</small></div>
          <article style="margin-bottom:10px;">
            <strong>Workshop Industri</strong>
            <div style="font-size:13px; color:#4a4065; margin-top:6px;">Siswa RPL mengikuti workshop pembuatan aplikasi bersama mitra lokal.</div>
            <div style="font-size:12px; color:#7b6a8c; margin-top:8px;">10 Sep 2025</div>
          </article>
          <article>
            <strong>Pelatihan TKJ</strong>
            <div style="font-size:13px; color:#4a4065; margin-top:6px;">Pembelajaran instalasi server dan keamanan jaringan.</div>
            <div style="font-size:12px; color:#7b6a8c; margin-top:8px;">2 Sep 2025</div>
          </article>
        </div>

        <div class="card widget" aria-label="Kontak">
          <h4 style="margin:0 0 8px 0; color:var(--purple-1);">Kontak Sekolah</h4>
          <div style="color:#4a4065;">Jl. Contoh No.20 Batam</div>
          <div style="color:#4a4065; margin-top:6px;">Telp: (0778) 123456</div>
          <div style="color:#4a4065; margin-top:6px;">Email: info@smkn100batam.sch.id</div>
        </div>
      </aside>

    <footer>
      © <span id="year"></span> SMK Negeri 100 Batam.
    </footer>

  <!-- Floating login button -->
  <button class="login-btn" id="openLogin" aria-haspopup="dialog" aria-controls="loginModal">Login</button>

  <!-- Modal backdrop -->
  <div class="modal-backdrop" id="backdrop" role="dialog" aria-modal="true" aria-hidden="true">
    <div class="modal" id="loginModal" aria-labelledby="modalTitle">
      <h4 id="modalTitle">Login Admin</h4>
      <p style="margin:6px 0 12px 0; color:#6b5b7a; font-size:14px;">Masuk menggunakan akun admin (demo).</p>
      <form id="frmLogin" onsubmit="handleLogin(event)">
        <label class="sr-only" for="u">Username</label>
        <input id="u" type="text" placeholder="Username" required>
        <label class="sr-only" for="p">Password</label>
        <input id="p" type="password" placeholder="Password" required>
        <div class="actions">
          <div style="font-size:13px; color:#7b6a8c;">Demo: admin / admin123</div>
          <div style="display:flex; gap:8px;">
            <button type="button" onclick="closeModal()" style="padding:8px 10px; border-radius:8px; border:1px solid rgba(0,0,0,0.06); background:transparent; cursor:pointer;">Batal</button>
            <button class="btn" type="submit">Masuk</button>
          </div>
        </div>
      </form>
    </div>
  </div>

  <script>
    // utilities
    document.getElementById('year').textContent = new Date().getFullYear();

    // open modal
    const openLogin = document.getElementById('openLogin');
    const backdrop = document.getElementById('backdrop');
    const loginNav = document.getElementById('loginNav');

    function openModal(){
      backdrop.style.display = 'flex';
      backdrop.setAttribute('aria-hidden','false');
      document.getElementById('u').focus();
    }
    function closeModal(){
      backdrop.style.display = 'none';
      backdrop.setAttribute('aria-hidden','true');
    }

    openLogin.addEventListener('click', openModal);
    loginNav.addEventListener('click', function(e){ e.preventDefault(); openModal(); });

    backdrop.addEventListener('click', function(e){
      if(e.target === backdrop) closeModal();
    });

    // demo login (client-only)
    function handleLogin(e){
      e.preventDefault();
      const u = document.getElementById('u').value.trim();
      const p = document.getElementById('p').value.trim();

      // DEMO: hanya client-side. Ganti dengan POST ke server untuk autentikasi nyata.
      if(u === 'admin' && p === 'admin123'){
        alert('Login berhasil (demo). Anda seharusnya diarahkan ke dashboard admin.');
        closeModal();
        // contoh redirect: window.location.href = '/admin/dashboard.php';
      } else {
        alert('Login gagal: username/password salah (demo).');
      }
    }

    // Simple search/filter siswa table
    const search = document.getElementById('searchSiswa');
    search.addEventListener('input', function(){
      const q = this.value.toLowerCase();
      const trs = document.querySelectorAll('#tblSiswa tbody tr');
      trs.forEach(tr => {
        const text = tr.textContent.toLowerCase();
        tr.style.display = text.includes(q) ? '' : 'none';
      });
    });

    // Accessibility helper: close modal with ESC
    document.addEventListener('keydown', function(e){
      if(e.key === 'Escape'){
        closeModal();
      }
    });

    // Notes: Untuk menghubungkan ke backend (PHP/MySQL)
    // - Ganti rows <tbody> tabel siswa dengan loop PHP yang mengambil data dari DB.
    // - Ubah form login untuk POST ke /admin/index.php dan verifikasi dirserver dengan password_verify.
    // - Simpan gambar/logo di folder uploads dan tampilkan src sesuai nama file di DB.
  </script>
