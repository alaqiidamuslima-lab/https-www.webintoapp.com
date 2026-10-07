<!DOCTYPE html>
<html lang="om">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <!-- Google Site Verification - Mirkaneessa Google -->
  <meta name="google-site-verification" content="6TeWvCer_dvgOVp-iImBIH2m4OdwGKUYUN6x_C7T_1I" />
  <title>Wiirtu GabaaOromoo — Wiirtu Daldala Dijitaalaa Guutuu</title>
  
  <!-- CDN koodii kaffaltii fi bifa meesshaalee miidhagsuuf -->
  <script src="https://jsdelivr.net"></script>
  <script src="https://jsdelivr.net"></script> 
  
  <style>
    :root { 
        --primary: #da251d; 
        --secondary: #000000; 
        --light: #f4f4f9; 
        --text: #333333; 
        --success: #28a745;
        --gray: #6c757d;
        --white: #ffffff;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', system-ui, sans-serif; }
    body { background-color: var(--light); color: var(--text); padding-bottom: 60px; }
    
    /* Naannoo Gubbaa (Navigation Bar) */
    header { background-color: var(--secondary); color: var(--white); padding: 15px 20px; display: flex; justify-content: space-between; align-items: center; box-shadow: 0 4px 6px rgba(0,0,0,0.1); position: sticky; top: 0; z-index: 1000; }
    .logo { font-size: 24px; font-weight: bold; color: var(--primary); display: flex; align-items: center; gap: 8px; cursor: pointer; }
    .search-box { display: flex; align-items: center; background: var(--white); border-radius: 4px; padding: 5px 10px; width: 40%; max-width: 500px; }
    .search-box input { border: none; outline: none; width: 100%; padding: 5px; font-size: 14px; }
    .search-box i { color: var(--gray); cursor: pointer; }
    .nav-actions { display: flex; gap: 20px; align-items: center; }
    .cart-btn { position: relative; cursor: pointer; display: flex; align-items: center; gap: 5px; color: var(--white); text-decoration: none; }
    .cart-count { position: absolute; top: -8px; right: -12px; background: var(--primary); color: var(--white); font-size: 11px; padding: 2px 6px; border-radius: 50%; font-weight: bold; }
    
    /* Giddugala Beeksisaa (Hero Section) */
    .hero-banner { background: linear-gradient(135deg, #da251d 0%, #000000 100%); color: var(--white); text-align: center; padding: 50px 20px; margin-bottom: 30px; }
    .hero-banner h1 { font-size: 36px; margin-bottom: 10px; }
    .hero-banner p { font-size: 16px; opacity: 0.9; }

    /* Qoodiinsa Meeshaalee (Categories) */
    .categories-bar { display: flex; gap: 15px; overflow-x: auto; margin-bottom: 25px; padding-bottom: 5px; }
    .category-chip { background: var(--white); padding: 8px 16px; border-radius: 20px; font-size: 14px; font-weight: 600; cursor: pointer; border: 1px solid #ddd; white-space: nowrap; transition: 0.2s; }
    .category-chip.active, .category-chip:hover { background: var(--primary); color: var(--white); border-color: var(--primary); }

    /* Haala Teessuma Meeshaalee (Product Grid) */
    .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
    .section-title { margin-bottom: 20px; border-left: 5px solid var(--primary); padding-left: 10px; font-size: 22px; display: flex; justify-content: space-between; align-items: center; }
    .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 25px; }
    .card { background: var(--white); border-radius: 8px; padding: 20px; box-shadow: 0 4px 10px rgba(0,0,0,0.05); text-align: center; display: flex; flex-direction: column; justify-content: space-between; height: 360px; transition: transform 0.3s; position: relative; }
    .card:hover { transform: translateY(-5px); }
    .card-img { height: 160px; background: #eef2f3; border-radius: 6px; display: flex; align-items: center; justify-content: center; font-weight: bold; color: var(--gray); font-size: 18px; }
    .card-title { font-size: 18px; margin: 12px 0 6px 0; font-weight: bold; text-align: left; }
    .card-vendor { font-size: 12px; color: var(--gray); text-align: left; margin-bottom: 10px; display: flex; align-items: center; gap: 4px; }
    .card-price { color: var(--primary); font-size: 22px; font-weight: bold; text-align: left; margin-bottom: 15px; }
    .btn-buy { width: 100%; background: var(--success); color: var(--white); border: none; padding: 12px; border-radius: 4px; font-weight: bold; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 8px; transition: 0.2s; }
    .btn-buy:hover { background: #218838; }
    
    /* Cudhaanoo Meeshaa Itti Dabalan (Floating Action Button) */
    .fab-upload { position: fixed; bottom: 30px; right: 30px; background: var(--primary); color: var(--white); width: 60px; height: 60px; border-radius: 50%; display: flex; align-items: center; justify-content: center; box-shadow: 0 4px 15px rgba(0,0,0,0.3); cursor: pointer; z-index: 999; border: none; }
    .fab-upload:hover { transform: scale(1.05); }

    /* Modals Base Styling - Saanduqoota Bilbila irratti ba'an */
    .modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.6); justify-content: center; align-items: center; z-index: 2000; padding: 20px; }
    .modal-content { background: var(--white); padding: 30px; border-radius: 8px; max-width: 450px; width: 100%; box-shadow: 0 5px 15px rgba(0,0,0,0.3); max-height: 90vh; overflow-y: auto; }
    .modal-content h3 { color: var(--primary); margin-bottom: 15px; display: flex; align-items: center; gap: 8px; }
    .form-group { margin-bottom: 15px; text-align: left; }
    .form-group label { display: block; font-size: 14px; font-weight: 600; margin-bottom: 5px; }
    .form-group input, .form-group select, .form-group textarea { width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 4px; font-size: 14px; outline: none; }
    .payment-info { background: #f8f9fa; padding: 12px; border-radius: 6px; margin-bottom: 10px; border-left: 4px solid var(--primary); }
    .btn-submit { width: 100%; background: var(--secondary); color: var(--white); border: none; padding: 12px; border-radius: 4px; font-weight: bold; cursor: pointer; margin-top: 10px; }
    .btn-submit:hover { background: var(--primary); }
    .modal-close { background: #ddd; color: var(--text); border: none; padding: 10px; width: 100%; margin-top: 10px; cursor: pointer; border-radius: 4px; font-weight: bold; }
  </style>
</head>
<body>

    <!-- Sirna Naannoo Gubbaa (Top Navigation) -->
    <header>
        <div class="logo" onclick="window.location.reload()"><i data-feather="shopping-bag"></i> Wiirtu GabaaOromoo</div>
        <div class="search-box">
            <input type="text" id="searchInput" placeholder="Maal barbaaddan? (Fkn: Buna, Uffata...)" onkeyup="barbaadiMeesshaa()">
            <i data-feather="search"></i>
        </div>
        <div class="nav-actions">
            <div class="cart-btn" onclick="baniCartModal()">
                <i data-feather="shopping-cart"></i>
                <span class="cart-btn-text">Kaartii</span>
                <span class="cart-count" id="cartCount">0</span>
            </div>
        </div>
    </header>

    <!-- Beeksisa Giddugalaa -->
    <section class="hero-banner">
        <h1>Wiirtu GabaaOromoo</h1>
        <p>Gabaa dijitaalaa daldaltoota fi bittoota Oromoo walitti fidu!</p>
    </section>

    <!-- Qabiyyee Guddaa (Main Container) -->
    <main class="container">
        <!-- Kutaa Filtara Kategoriwwanii -->
        <div class="categories-bar">
            <div class="category-chip active" onclick="calaliKategori('Hunda', this)">Hunda</div>
            <div class="category-chip" onclick="calaliKategori('Aadaa', this)">Uffata Aadaa</div>
            <div class="category-chip" onclick="calaliKategori('Qonnaa', this)">Omisha Qonnaa</div>
            <div class="category-chip" onclick="calaliKategori('Teknoolojii', this)">Elektirooniksii</div>
        </div>

        <div class="section-title">
            <span>Meeshaalee Gabaa Irra Jiran</span>
        </div>
        
        <!-- Bakka Meeshaaleen Itti Mul'atan -->
        <div class="grid" id="productGrid">
            <!-- Koodiin Javascript armaan gadii ofumaan asitti fe'a -->
        </div>
    </main>

    <!-- Cudhaanoo Meeshaa Haaraa Gabaaf Galchu (+) -->
    <button class="fab-upload" onclick="baniUploadModal()" title="Meeshaa kee gabaaf galchi">
        <i data-feather="plus"></i>
    </button>

    <!-- 1. POPUP SAANDUQA KAFFALTII: Lakkoofsa Baankii fi Telebirr -->
    <div id="paymentModal" class="modal">
        <div class="modal-content">
            <h3><i data-feather="alert-circle"></i> Lakkoofsa Kaffaltii GabaaOromoo</h3>
            <p style="margin-bottom: 15px; font-size: 14px; color: var(--gray);">Kaffaltii keessan lakkoofsota daldalaa armaan gadii kanaan xumuraa:</p>
            
            <div class="payment-info"><p><strong>📱 Telebirr / CBE Birr:</strong> 0912XXXXXX</p></div>
            <div class="payment-info"><p><strong>🏦 Baankii Hojii Gamtaa Oromiyaa:</strong> 1000XXXXXXXXX</p></div>
            <div class="payment-info"><p><strong>🏦 Baankii Daldala Itoophiyaa (CBE):</strong> 1000XXXXXXXXX</p></div>
            
            <hr style="margin: 15px 0; border: 0; border-top: 1px solid #eee;">
            <p style="font-size: 12px; color: var(--gray); font-style: italic;">*Erga kaffaltanii booda Nagahee (Screenshot) gama Telegram ykn WhatsApp kanaan gurgurtaaf ergaa.</p>
            <button class="btn-submit" onclick="mirkaneessiBittaaManual()">Kaffalee Jira</button>
            <button class="modal-close" onclick="cufuModal('paymentModal')">Cufi</button>
        </div>
    </div>

    <!-- 2. POPUP SAANDUQA GALMEESSAA: Formii Meeshaa Haaraa Ittiin Galchan -->
    <div id="uploadModal" class="modal">
        <div class="modal-content">
            <h3><i data-feather="file-text"></i> Meeshaa Gabaa Galchi</h3>
            <form id="uploadForm" onsubmit="galmeessiMeeshaa(event)">
