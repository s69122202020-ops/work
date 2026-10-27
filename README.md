/* <!DOCTYPE html> */
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>อบต.เมืองเก่า | บริการประชาชนทันสมัย</title>
<!-- Tailwind CSS for utility styling -->
<script src="https://cdn.tailwindcss.com"></script>
<!-- Font Awesome Icons -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<!-- Google Fonts Prompt & Sarabun -->
<link href="https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<style>
/* CSS Reset & Global Root Vars */
* {
  box-sizing: border-box;
}

:root {
  --base-font-size: 16px;
  --primary: #07583b;
  --primary-hover: #0b7650;
  --primary-light: #e5f2e9;
  --accent-gold: #d4af37;
  --text-main: #1f2937;
  --bg-main: #f4f7f4;
}

html {
  font-size: var(--base-font-size);
  scroll-behavior: smooth;
}

body {
  margin: 0;
  font-family: 'Prompt', sans-serif;
  background-color: var(--bg-main);
  color: var(--text-main);
  line-height: 1.7;
}

/* Sticky Header */
header {
  background: rgba(255, 255, 255, 0.98);
  backdrop-filter: blur(8px);
  padding: 12px 6%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  position: sticky;
  top: 0;
  z-index: 40;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
}

.logo-container {
  display: flex;
  align-items: center;
  gap: 12px;
}

.logo-img {
  width: 45px;
  height: 45px;
  object-fit: contain;
}

.logo-text {
  color: var(--primary);
  font-weight: 700;
  font-size: 1.25rem;
  line-height: 1.2;
}

.logo-sub {
  font-size: 0.75rem;
  color: #55665a;
  font-weight: 400;
}

.header-right {
  display: flex;
  align-items: center;
  gap: 15px;
  flex-wrap: wrap;
}

/* Accessibility Font Resizer */
.font-resizer {
  display: flex;
  align-items: center;
  background: var(--primary-light);
  border-radius: 9999px;
  padding: 4px 10px;
  gap: 4px;
  border: 1px solid #c2e2cc;
}

.font-resizer span {
  font-size: 0.8rem;
  color: var(--primary);
  font-weight: 600;
  margin-right: 4px;
}

.font-resizer button {
  border: 0;
  background: white;
  color: var(--primary);
  border-radius: 50%;
  width: 28px;
  height: 28px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  font-weight: bold;
  box-shadow: 0 1px 3px rgba(0,0,0,0.1);
  transition: all 0.2s;
}

.font-resizer button:hover {
  background: var(--primary);
  color: white;
}

/* Main Navigation */
nav {
  display: flex;
  gap: 6px;
  flex-wrap: wrap;
}

nav button {
  border: 0;
  background: transparent;
  padding: 8px 14px;
  cursor: pointer;
  border-radius: 8px;
  font-weight: 500;
  color: #374151;
  transition: all 0.2s;
  display: flex;
  align-items: center;
  gap: 6px;
}

nav button:hover,
nav button.active {
  background: var(--primary-light);
  color: var(--primary);
  font-weight: 600;
}

/* Page Section Animations */
.page {
  display: none;
}

.page.active {
  display: block;
  animation: fadeIn 0.35s ease-in-out;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(8px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Hero Banner Section */
.hero {
  padding: 90px 8%;
  color: white;
  background:
    linear-gradient(135deg, rgba(6, 60, 45, 0.88), rgba(7, 88, 59, 0.72)),
    url("https://images.unsplash.com/photo-1577495508048-b635879837f1?auto=format&fit=crop&w=1600&q=80")
    center/cover no-repeat;
  border-bottom-left-radius: 24px;
  border-bottom-right-radius: 24px;
  box-shadow: 0 10px 25px rgba(7, 88, 59, 0.15);
}

.hero h1 {
  font-size: clamp(32px, 5vw, 52px);
  line-height: 1.25;
  font-weight: 700;
  margin-top: 0;
  text-shadow: 0 2px 4px rgba(0,0,0,0.3);
}

.hero p {
  max-width: 600px;
  font-size: 1.1rem;
  margin-top: 15px;
  margin-bottom: 25px;
  color: #e2f1e7;
}

/* Layout Container */
.container {
  max-width: 1200px;
  margin: auto;
  padding: 35px 20px;
}

h2.section-title {
  color: var(--primary);
  font-size: 1.6rem;
  font-weight: 700;
  margin-top: 30px;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 10px;
}

h2.section-title::before {
  content: '';
  display: inline-block;
  width: 6px;
  height: 24px;
  background: var(--accent-gold);
  border-radius: 4px;
}

.btn {
  background: var(--primary);
  color: white;
  padding: 10px 20px;
  border: 0;
  border-radius: 10px;
  cursor: pointer;
  font-weight: 500;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  transition: all 0.2s;
  box-shadow: 0 2px 6px rgba(7, 88, 59, 0.2);
}

.btn:hover {
  background: var(--primary-hover);
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(7, 88, 59, 0.3);
}

.btn-secondary {
  background: #e2ece5;
  color: var(--primary);
  box-shadow: none;
}

.btn-secondary:hover {
  background: #d0e2d5;
}

/* Quick Action Grid */
.quick-grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 16px;
}

.quick-card {
  background: white;
  border: 1px solid #e1ebe3;
  border-radius: 16px;
  padding: 20px 12px;
  text-align: center;
  cursor: pointer;
  transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 12px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.02);
}

.quick-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 24px rgba(7, 88, 59, 0.12);
  border-color: var(--primary);
}

.icon-wrapper {
  width: 58px;
  height: 58px;
  border-radius: 50%;
  background: var(--primary-light);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--primary);
  font-size: 24px;
  transition: all 0.25s;
}

.quick-card:hover .icon-wrapper {
  background: var(--primary);
  color: white;
  transform: scale(1.1);
}

.quick-card span.title {
  font-weight: 600;
  color: var(--text-main);
  font-size: 0.95rem;
}

/* Service & News Cards Grid */
.cards-grid,
.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 22px;
}

.card {
  background: white;
  border: 1px solid #e1ebe3;
  border-radius: 16px;
  overflow: hidden;
  transition: all 0.25s;
  display: flex;
  flex-direction: column;
  box-shadow: 0 2px 10px rgba(0,0,0,0.03);
}

.card:hover {
  transform: translateY(-50px);
  transform: translateY(-5px);
  box-shadow: 0 12px 28px rgba(0,0,0,0.08);
}

.card-img-container {
  position: relative;
  height: 180px;
  overflow: hidden;
}

.card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s;
}

.card:hover img {
  transform: scale(1.06);
}

.category-tag {
  position: absolute;
  top: 12px;
  left: 12px;
  background: rgba(7, 88, 59, 0.85);
  backdrop-filter: blur(4px);
  color: white;
  padding: 4px 12px;
  border-radius: 9999px;
  font-size: 0.75rem;
  font-weight: 500;
}

.card-body {
  padding: 18px;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

.card-body h3 {
  font-size: 1.1rem;
  font-weight: 600;
  margin: 0 0 8px 0;
  color: var(--text-main);
  line-height: 1.4;
}

.card-body p {
  color: #64748b;
  font-size: 0.9rem;
  margin-bottom: 16px;
  flex-grow: 1;
}

/* Service Card Design */
.service-card {
  background: white;
  border: 1px solid #e1ebe3;
  border-radius: 16px;
  padding: 24px 20px;
  text-align: center;
  transition: all 0.25s;
  display: flex;
  flex-direction: column;
  align-items: center;
  box-shadow: 0 2px 10px rgba(0,0,0,0.02);
}

.service-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 25px rgba(7, 88, 59, 0.1);
  border-color: var(--primary);
}

.service-img {
  width: 70px;
  height: 70px;
  border-radius: 16px;
  object-fit: cover;
  margin-bottom: 14px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.08);
}

.service-card h3 {
  font-size: 1.15rem;
  font-weight: 600;
  margin: 4px 0 8px 0;
}

.service-card p {
  color: #64748b;
  font-size: 0.88rem;
  margin-bottom: 18px;
}

/* Header Banner Page Titles */
.page-title {
  background: linear-gradient(135deg, #e7f3e9 0%, #d5ebd9 100%);
  padding: 35px 8%;
  border-bottom: 1px solid #cce2d1;
}

.page-title h1 {
  margin: 0 0 6px 0;
  color: var(--primary);
  font-size: 1.8rem;
  font-weight: 700;
}

.page-title p {
  margin: 0;
  color: #4b6354;
}

/* Search Toolbar */
.toolbar {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin-bottom: 25px;
  background: white;
  padding: 12px;
  border-radius: 12px;
  border: 1px solid #e1ebe3;
  box-shadow: 0 2px 6px rgba(0,0,0,0.02);
}

.toolbar input,
.toolbar select {
  padding: 10px 14px;
  border: 1px solid #d7e3da;
  border-radius: 8px;
  background: white;
  outline: none;
  font-size: 0.95rem;
  transition: border-color 0.2s;
}

.toolbar input:focus,
.toolbar select:focus {
  border-color: var(--primary);
  box-shadow: 0 0 0 3px rgba(7, 88, 59, 0.1);
}

.toolbar input {
  flex: 1;
  min-width: 220px;
}

/* News Row Component */
.news-row {
  background: white;
  border: 1px solid #e1ebe3;
  padding: 16px;
  border-radius: 16px;
  margin-bottom: 16px;
  display: flex;
  gap: 20px;
  align-items: center;
  transition: all 0.2s;
}

.news-row:hover {
  border-color: var(--primary);
  box-shadow: 0 6px 18px rgba(0,0,0,0.05);
}

.news-row img {
  width: 150px;
  height: 110px;
  object-fit: cover;
  border-radius: 12px;
  flex-shrink: 0;
}

/* Footer Section */
footer {
  background: #053b28;
  color: white;
  padding: 45px 8% 25px;
  margin-top: 50px;
  border-top: 4px solid var(--accent-gold);
}

footer p {
  font-size: 0.9rem;
  color: #c0dec8;
  margin: 4px 0;
}

/* Modal Popup Window */
.modal-bg {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.6);
  backdrop-filter: blur(4px);
  z-index: 50;
  align-items: center;
  justify-content: center;
  padding: 20px;
}

.modal-bg.show {
  display: flex;
  animation: fadeIn 0.2s ease-out;
}

.modal {
  background: white;
  border-radius: 20px;
  padding: 30px;
  width: min(540px, 100%);
  max-height: 90vh;
  overflow-y: auto;
  position: relative;
  box-shadow: 0 20px 40px rgba(0,0,0,0.2);
}

.modal label {
  display: block;
  font-size: 0.9rem;
  margin-top: 12px;
  font-weight: 600;
  color: var(--text-main);
}

.modal input,
.modal textarea,
.modal select {
  width: 100%;
  padding: 10px 14px;
  margin: 6px 0 12px;
  border: 1px solid #d7e3da;
  border-radius: 8px;
  outline: none;
  transition: all 0.2s;
}

.modal input:focus,
.modal textarea:focus {
  border-color: var(--primary);
  box-shadow: 0 0 0 3px rgba(7, 88, 59, 0.1);
}

.modal textarea {
  min-height: 100px;
  resize: vertical;
}

.close-btn {
  position: absolute;
  top: 20px;
  right: 20px;
  border: 0;
  background: #f1f5f2;
  color: #555;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.2s;
}

.close-btn:hover {
  background: #e2ece5;
  color: #000;
}

/* Custom Notification Toast */
#toast {
  visibility: hidden;
  min-width: 280px;
  background-color: #07583b;
  color: #fff;
  text-align: center;
  border-radius: 10px;
  padding: 14px 20px;
  position: fixed;
  z-index: 60;
  left: 50%;
  bottom: 30px;
  transform: translateX(-50%);
  box-shadow: 0 8px 20px rgba(0,0,0,0.2);
}

#toast.show {
  visibility: visible;
  animation: fadeinout 3.5s;
}

@keyframes fadeinout {
  0% { bottom: 0; opacity: 0; }
  15% { bottom: 30px; opacity: 1; }
  85% { bottom: 30px; opacity: 1; }
  100% { bottom: 0; opacity: 0; }
}

/* Responsive Breakpoints */
@media (max-width: 950px) {
  .quick-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 768px) {
  header {
    padding: 12px 4%;
  }
  .cards-grid,
  .services-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  .quick-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 540px) {
  .cards-grid,
  .services-grid,
  .quick-grid {
    grid-template-columns: 1fr;
  }
  
  nav {
    width: 100%;
    order: 3;
    margin-top: 10px;
    justify-content: space-between;
  }

  nav button {
    padding: 6px 10px;
    font-size: 0.85rem;
  }

  .news-row {
    flex-direction: column;
    align-items: flex-start;
  }

  .news-row img {
    width: 100%;
    height: 160px;
  }

  .hero {
    padding: 50px 6%;
  }
}
</style>
</head>

<body>

<!-- Header / Navigation Bar -->
<header>
  <div class="logo-container">
    <svg class="logo-img" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
      <circle cx="50" cy="50" r="48" fill="#07583B"/>
      <path d="M50 15L20 35V42H80V35L50 15Z" fill="#D4AF37"/>
      <rect x="28" y="46" width="8" height="28" fill="white"/>
      <rect x="46" y="46" width="8" height="28" fill="white"/>
      <rect x="64" y="46" width="8" height="28" fill="white"/>
      <rect x="20" y="78" width="60" height="7" fill="#D4AF37"/>
    </svg>
    <div>
      <div class="logo-text">อบต.เมืองเก่า</div>
      <div class="logo-sub">องค์การบริหารส่วนตำบลเมืองเก่า</div>
    </div>
  </div>
  

    <!-- Main Navigation Menu -->
    <nav>
      <button class="active" onclick="showPage('home', this)">
        <i class="fa-solid fa-house"></i> หน้าแรก
      </button>
      <button onclick="showPage('news', this)">
        <i class="fa-solid fa-newspaper"></i> ข่าวสารและประกาศ
      </button>
      <button onclick="showPage('services', this)">
        <i class="fa-solid fa-handshake-angle"></i> บริการประชาชน
      </button>
      <button onclick="openModal('ติดต่อหน่วยงาน อบต.เมืองเก่า')">
        <i class="fa-solid fa-phone"></i> ติดต่อเรา
      </button>
    </nav>
  </div>
</header>

<main>

<!-- Page 1: Home -->
<section class="page active" id="home">
  <!-- Hero Section -->
  <div class="hero">
    <h1>อบต.เมืองเก่า<br><span style="color: #f1d368;">พัฒนาเมืองเก่า น่าอยู่ ยั่งยืน</span></h1>
    <p>ศูนย์รวมข้อมูลข่าวสารราชการ บริการประชาชนออนไลน์ สะดวกรวดเร็ว โปร่งใส และเข้าถึงได้ตลอด 24 ชั่วโมง</p>
    <button class="btn" onclick="showPageById('services')">
      สำรวจบริการประชาชน <i class="fa-solid fa-arrow-right"></i>
    </button>
  </div>

  <div class="container">
    <h2 class="section-title">บริการด่วนสำหรับประชาชน</h2>

    <!-- Quick Links Grid with SVGs/Icons -->
    <div class="quick-grid">
      <div class="quick-card" onclick="openModal('ยื่นแบบฟอร์มคำร้องออนไลน์')">
        <div class="icon-wrapper">
          <i class="fa-solid fa-file-pen"></i>
        </div>
        <span class="title">แบบฟอร์มคำร้อง</span>
      </div>

      <div class="quick-card" onclick="openModal('สอบถามข้อมูลภาษีและรายได้')">
        <div class="icon-wrapper">
          <i class="fa-solid fa-calculator"></i>
        </div>
        <span class="title">ภาษีและรายได้</span>
      </div>

      <div class="quick-card" onclick="openModal('ลงทะเบียนเบี้ยยังชีพผู้สูงอายุ')">
        <div class="icon-wrapper">
          <i class="fa-solid fa-person-cane"></i>
        </div>
        <span class="title">เบี้ยยังชีพผู้สูงอายุ</span>
      </div>

      <div class="quick-card" onclick="showPageById('news')">
        <div class="icon-wrapper">
          <i class="fa-solid fa-bullhorn"></i>
        </div>
        <span class="title">ข่าวประชาสัมพันธ์</span>
      </div>

      <div class="quick-card" onclick="openModal('ติดต่อสอบถามเจ้าหน้าที่')">
        <div class="icon-wrapper">
          <i class="fa-solid fa-headset"></i>
        </div>
        <span class="title">ติดต่อสอบถาม</span>
      </div>
    </div>

    <!-- Latest News -->
    <h2 class="section-title">ข่าวประชาสัมพันธ์ล่าสุด</h2>
    <div class="cards-grid" id="homeNews"></div>

    <!-- About Section -->
    <div class="bg-white rounded-2xl p-8 mt-10 border border-emerald-100 shadow-sm flex flex-col md:flex-row gap-8 items-center">
      <div class="md:w-1/3">
        <img src="https://images.unsplash.com/photo-1577495508048-b635879837f1?auto=format&fit=crop&w=800&q=80" alt="สำนักงาน อบต." class="rounded-xl shadow-md w-full h-52 object-cover">
      </div>
      <div class="md:w-2/3">
        <h3 class="text-xl font-bold text-emerald-900 mb-2">เกี่ยวกับ องค์การบริหารส่วนตำบลเมืองเก่า</h3>
        <p class="text-gray-600 mb-4">
          มุ่งเน้นการพัฒนาคุณภาพชีวิตของประชาชนในท้องถิ่น ส่งเสริมการอนามัย ยกระดับสิ่งแวดล้อม และยึดมั่นการบริหารงานอย่างมีธรรมาภิบาล พร้อมอำนวยความสะดวกในการให้บริการดิจิทัลแก่ประชาชนทุกกลุ่มอย่างทั่วถึงและเท่าเทียม
        </p>
        <div class="flex gap-4">
          <button class="btn btn-secondary" onclick="openModal('ข้อมูลวิสัยทัศน์และพันธกิจ')">
            <i class="fa-solid fa-compass"></i> วิสัยทัศน์และพันธกิจ
          </button>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Page 2: News -->
<section class="page" id="news">
  <div class="page-title">
    <h1>ข่าวสารและประกาศ</h1>
    <p>ติดตามข่าวประชาสัมพันธ์ กิจกรรมชุมชน และประกาศจัดซื้อจัดจ้าง</p>
  </div>

  <div class="container">
    <!-- Toolbar for Filters -->
    <div class="toolbar">
      <input id="searchNews"
             placeholder="🔎 ค้นหาข่าวสาร..."
             oninput="renderNews()">

      <select id="category" onchange="renderNews()">
        <option value="ทั้งหมด">หมวดหมู่ทั้งหมด</option>
        <option value="ข่าวประชาสัมพันธ์">ข่าวประชาสัมพันธ์</option>
        <option value="กิจกรรมชุมชน">กิจกรรมชุมชน</option>
        <option value="ประกาศทั่วไป">ประกาศทั่วไป</option>
      </select>
    </div>

    <div id="newsList"></div>
  </div>
</section>

<!-- Page 3: Public Services -->
<section class="page" id="services">
  <div class="page-title">
    <h1>บริการประชาชน</h1>
    <p>ศูนย์รวมช่องทางยื่นคำร้อง และบริการข้อมูลออนไลน์สำหรับประชาชน</p>
  </div>

  <div class="container">
    <div class="toolbar">
      <input id="searchService"
             placeholder="🔎 ค้นหาชื่อบริการ..."
             oninput="renderServices()">
    </div>

    <div class="services-grid" id="serviceList"></div>
  </div>
</section>

</main>

<!-- Footer -->
<footer>
  <div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-8 mb-6">
    <div>
      <h3 class="font-bold text-lg text-white mb-2 flex items-center gap-2">
        <i class="fa-solid fa-landmark text-amber-400"></i> อบต.เมืองเก่า
      </h3>
      <p class="text-xs">องค์การบริหารส่วนตำบลเมืองเก่า มุ่งมั่นพัฒนาชุมชนและบริการประชาชนด้วยความยั่งยืน โปร่งใส และเป็นธรรม</p>
    </div>
    <div>
      <h4 class="font-bold text-white mb-2">ช่องทางติดต่อ</h4>
      <p><i class="fa-solid fa-location-dot w-5 text-amber-400"></i> 123 หมู่ 4 ต.เมืองเก่า อ.เมือง จ.สุโขทัย 64000</p>
      <p><i class="fa-solid fa-phone w-5 text-amber-400"></i> 055-123-456, 055-123-457</p>
      <p><i class="fa-solid fa-envelope w-5 text-amber-400"></i> contact@muangkao.go.th</p>
    </div>
    <div>
      <h4 class="font-bold text-white mb-2">เวลาทำการ</h4>
      <p><i class="fa-solid fa-clock w-5 text-amber-400"></i> จันทร์ - ศุกร์: 08:30 - 16:30 น.</p>
      <p><i class="fa-solid fa-calendar-xmark w-5 text-amber-400"></i> ปิดทำการวันเสาร์ - อาทิตย์ และวันหยุดนักขัตฤกษ์</p>
    </div>
  </div>
  <div class="text-center border-t border-emerald-800 pt-4 text-xs text-emerald-300">
    © 2026 เว็บไซต์ต้นแบบ องค์การบริหารส่วนตำบลเมืองเก่า (อบต.เมืองเก่า) - สงวนลิขสิทธิ์
  </div>
</footer>

<!-- Dynamic Modal Popup Window -->
<div class="modal-bg" id="modalBg">
  <div class="modal">
    <button class="close-btn" onclick="closeModal()" aria-label="ปิดหน้าต่าง">
      <i class="fa-solid fa-xmark"></i>
    </button>
    <h2 id="modalTitle" class="text-xl font-bold text-emerald-900 mb-1"></h2>
    <div id="modalContent"></div>
  </div>
</div>

<!-- Notification Toast -->
<div id="toast">บันทึกข้อมูลเรียบร้อยแล้ว</div>

<script>
// Mock Data: News Articles with High Quality Unsplash Images
const newsData = [
  {
    title: "กิจกรรมพัฒนาชุมชนและทำความสะอาดพื้นที่สาธารณะ (Big Cleaning Day)",
    category: "กิจกรรมชุมชน",
    image: "https://images.unsplash.com/photo-1559027615-cd4628902d4a?auto=format&fit=crop&w=700&q=80",
    desc: "ขอเชิญชวนประชาชนร่วมมือร่วมใจปรับปรุงภูมิทัศน์และทำความสะอาดพื้นที่ส่วนรวมเพื่อสุขอนามัยที่ดีของชุมชน"
  },
  {
    title: "ประชาสัมพันธ์การลงทะเบียนรับสวัสดิการและเบี้ยยังชีพ",
    category: "ข่าวประชาสัมพันธ์",
    image: "https://images.unsplash.com/photo-1551836022-d5d88e9218df?auto=format&fit=crop&w=700&q=80",
    desc: "ตรวจสอบคุณสมบัติ เอกสารที่ต้องใช้ และขั้นตอนการยื่นเรื่องก่อนติดต่อเจ้าหน้าที่ ณ สำนักงาน"
  },
  {
    title: "ประกาศแผนการจัดซื้อจัดจ้าง ประจำปีงบประมาณ",
    category: "ประกาศทั่วไป",
    image: "https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?auto=format&fit=crop&w=700&q=80",
    desc: "เปิดเผยข้อมูลการดำเนินงานเพื่อสร้างความโปร่งใส ตรวจสอบได้ ตามหลักธรรมาภิบาล"
  }
];

// Mock Data: Public Services with High Quality Unsplash Thumbnail Icons
const serviceData = [
  {
    title: "แบบฟอร์มคำร้องทั่วไป",
    desc: "ยื่นคำร้องเรียน คำขอ หรือติดต่อเรื่องทั่วไปต่อหน่วยงาน",
    image: "https://images.unsplash.com/photo-1450133064473-71024230f91b?auto=format&fit=crop&w=300&q=80",
    icon: "fa-file-signature"
  },
  {
    title: "ภาษีและรายได้",
    desc: "บริการข้อมูลการชำระภาษีที่ดิน สิ่งปลูกสร้าง และภาษีป้าย",
    image: "https://images.unsplash.com/photo-1554224155-8d04cb21cd6c?auto=format&fit=crop&w=300&q=80",
    icon: "fa-receipt"
  },
  {
    title: "เบี้ยยังชีพผู้สูงอายุ",
    desc: "ตรวจสอบสิทธิและลงทะเบียนรับเบี้ยยังชีพรายเดือน",
    image: "https://images.unsplash.com/photo-1581579438747-1dc8d17bbce4?auto=format&fit=crop&w=300&q=80",
    icon: "fa-heart"
  },
  {
    title: "สวัสดิการผู้พิการ",
    desc: "ยื่นคำขอรับสิทธิสวัสดิการ และสิ่งอำนวยความสะดวก",
    image: "https://images.unsplash.com/photo-1576765608535-5f04d1e3f289?auto=format&fit=crop&w=300&q=80",
    icon: "fa-wheelchair"
  },
  {
    title: "แจ้งร้องเรียน / ร้องทุกข์",
    desc: "แจ้งปัญหาความเดือดร้อน ถนน ชำรุด ไฟฟ้า หรือน้ำประปา",
    image: "https://images.unsplash.com/photo-1585829365295-ab7cd400c167?auto=format&fit=crop&w=300&q=80",
    icon: "fa-triangle-exclamation"
  },
  {
    title: "จัดการสิ่งแวดล้อมและขยะ",
    desc: "บริการจัดเก็บขยะมูลฝอย และแจ้งดูแลสิ่งแวดล้อมในชุมชน",
    image: "https://images.unsplash.com/photo-1532996122724-e3c354a0b15b?auto=format&fit=crop&w=300&q=80",
    icon: "fa-recycle"
  },
  {
    title: "ข้อมูลข่าวสารราชการ",
    desc: "ขอเข้าถึงข้อมูลข่าวสารและการดำเนินงานของ อบต.",
    image: "https://images.unsplash.com/photo-1451187580459-43490279c0fa?auto=format&fit=crop&w=300&q=80",
    icon: "fa-database"
  },
  {
    title: "ติดต่อเจ้าหน้าที่",
    desc: "สอบถามเส้นทาง หมายเลขภายใน และเวลาทำการ",
    image: "https://images.unsplash.com/photo-1423666639041-f56000c27a9a?auto=format&fit=crop&w=300&q=80",
    icon: "fa-phone-volume"
  }
];

// Switch active page tab
function showPage(id, button) {
  document.querySelectorAll(".page").forEach(page => {
    page.classList.remove("active");
  });

  document.getElementById(id).classList.add("active");

  document.querySelectorAll("nav button").forEach(btn => {
    btn.classList.remove("active");
  });

  if (button) button.classList.add("active");

  window.scrollTo({ top: 0, behavior: "smooth" });
}

function showPageById(id) {
  const button = document.querySelector(`nav button[onclick*="'${id}'"]`);
  showPage(id, button);
}

// Senior-friendly Font Resizer
let currentFontSize = 16;
function changeFontSize(step) {
  if (step === 0) {
    currentFontSize = 16;
  } else {
    currentFontSize = Math.min(Math.max(currentFontSize + (step * 2), 14), 22);
  }
  document.documentElement.style.setProperty('--base-font-size', currentFontSize + 'px');
}

// Custom Toast Notification (Replaces alert)
function showToast(message) {
  const toast = document.getElementById("toast");
  toast.innerText = message;
  toast.className = "show";
  setTimeout(() => {
    toast.className = toast.className.replace("show", "");
  }, 3500);
}

// Generate News Card HTML
function makeNewsCard(item) {
  return `
    <article class="card">
      <div class="card-img-container">
        <img src="${item.image}" alt="${item.title}" loading="lazy">
        <span class="category-tag">${item.category}</span>
      </div>
      <div class="card-body">
        <h3>${item.title}</h3>
        <p>${item.desc}</p>
        <button class="btn" onclick="openModal('${item.title.replace(/'/g, "\\'")}')">
          อ่านรายละเอียด <i class="fa-solid fa-arrow-right text-xs"></i>
        </button>
      </div>
    </article>
  `;
}

// Render News on Homepage
document.getElementById("homeNews").innerHTML = newsData.map(makeNewsCard).join("");

// Search & Filter News on News Page
function renderNews() {
  const keyword = document.getElementById("searchNews").value.toLowerCase();
  const category = document.getElementById("category").value;

  const filtered = newsData.filter(item => {
    const matchCategory = category === "ทั้งหมด" || item.category === category;
    const matchText = item.title.toLowerCase().includes(keyword) || item.desc.toLowerCase().includes(keyword);
    return matchCategory && matchText;
  });

  const newsList = document.getElementById("newsList");
  if (filtered.length === 0) {
    newsList.innerHTML = `<div class="bg-white p-8 rounded-xl text-center text-gray-500">ไม่พบข้อมูลข่าวสารที่คุณค้นหา</div>`;
    return;
  }

  newsList.innerHTML = filtered.map(item => `
    <div class="news-row">
      <img src="${item.image}" alt="${item.title}">
      <div class="flex-1">
        <span class="text-xs font-bold text-emerald-700 bg-emerald-50 px-2.5 py-1 rounded-full border border-emerald-200">${item.category}</span>
        <h3 class="text-lg font-bold text-gray-800 mt-2 mb-1">${item.title}</h3>
        <p class="text-gray-600 text-sm mb-3">${item.desc}</p>
        <button class="btn text-sm py-1.5 px-3" onclick="openModal('${item.title.replace(/'/g, "\\'")}')">
          อ่านรายละเอียด <i class="fa-solid fa-angle-right"></i>
        </button>
      </div>
    </div>
  `).join("");
}

// Search & Render Services
function renderServices() {
  const keyword = document.getElementById("searchService").value.toLowerCase();
  const filtered = serviceData.filter(item => 
    item.title.toLowerCase().includes(keyword) || item.desc.toLowerCase().includes(keyword)
  );

  const serviceList = document.getElementById("serviceList");
  if (filtered.length === 0) {
    serviceList.innerHTML = `<div class="col-span-full bg-white p-8 rounded-xl text-center text-gray-500">ไม่พบบริการที่คุณค้นหา</div>`;
    return;
  }

  serviceList.innerHTML = filtered.map(item => `
    <div class="service-card">
      <img src="${item.image}" alt="${item.title}" class="service-img">
      <h3>${item.title}</h3>
      <p>${item.desc}</p>
      <button class="btn w-full justify-center" onclick="openModal('${item.title}')">
        <i class="fa-solid ${item.icon}"></i> ยื่นเรื่อง / ดูรายละเอียด
      </button>
    </div>
  `).join("");
}

// Open Dynamic Form Modal
function openModal(title) {
  document.getElementById("modalTitle").innerText = title;
  const modalContent = document.getElementById("modalContent");
  
  modalContent.innerHTML = `
    <p class="text-sm text-gray-600 mb-4">กรุณากรอกข้อมูลเพื่อยื่นเรื่องหรือติดต่อเจ้าหน้าที่เกี่ยวกับ <strong>${title}</strong></p>
    <form onsubmit="handleFormSubmit(event, '${title}')">
      <label><i class="fa-solid fa-user text-emerald-700"></i> ชื่อ-นามสกุลผู้ยื่นคำร้อง</label>
      <input type="text" required placeholder="ตัวอย่าง: นายสมชาย ใจดี">
      
      <label><i class="fa-solid fa-phone text-emerald-700"></i> เบอร์โทรศัพท์ติดต่อ</label>
      <input type="tel" required placeholder="ตัวอย่าง: 081-234-5678">

      <label><i class="fa-solid fa-envelope text-emerald-700"></i> อีเมล (ถ้ามี)</label>
      <input type="email" placeholder="example@email.com">
      
      <label><i class="fa-solid fa-message text-emerald-700"></i> รายละเอียดคำร้อง / ข้อสอบถาม</label>
      <textarea required placeholder="ระบุรายละเอียดเพิ่มเติม..."></textarea>
      
      <button type="submit" class="btn w-full justify-center mt-3 py-3">
        <i class="fa-solid fa-paper-plane"></i> ส่งข้อมูลคำร้อง
      </button>
    </form>
  `;

  document.getElementById("modalBg").classList.add("show");
}

// Close Modal Window
function closeModal() {
  document.getElementById("modalBg").classList.remove("show");
}

// Form Submission Event
function handleFormSubmit(event, title) {
  event.preventDefault();
  closeModal();
  showToast(`ระบบได้รับข้อมูล "${title}" เรียบร้อยแล้ว เจ้าหน้าที่จะดำเนินการโดยเร็วที่สุด`);
}

// Close Modal when clicking background overlay
document.getElementById("modalBg").addEventListener("click", function(e) {
  if (e.target === this) closeModal();
});

// Initial Load
renderNews();
renderServices();
</script>

</body>
</html>
