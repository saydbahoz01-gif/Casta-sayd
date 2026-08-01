
<html lang="ku" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Castalica</title>
<script src="https://cdn.tailwindcss.com"></script>
<script src="https://code.iconify.design/3/3.1.0/iconify.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Arabic:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<script>
tailwind.config={theme:{extend:{fontFamily:{kurdish:['Noto Sans Arabic','sans-serif']}}}}
</script>
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{height:100%;width:100%;overflow:hidden;font-family:'Noto Sans Arabic',sans-serif}

.welcome-splash{position:fixed;inset:0;z-index:999;display:flex;flex-direction:column;align-items:center;justify-content:center;transition:opacity 0.7s ease,transform 0.7s ease}
.welcome-splash.hide{opacity:0;transform:scale(1.05);pointer-events:none}
.welcome-splash .logo-anim{animation:logoFloat 2.5s ease-in-out infinite}
@keyframes logoFloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-10px)}}
.welcome-splash .wt{animation:fadeUp 0.7s ease forwards;opacity:0}
@keyframes fadeUp{0%{opacity:0;transform:translateY(18px)}100%{opacity:1;transform:translateY(0)}}

.bg-anim{position:fixed;inset:0;z-index:0;overflow:hidden;transition:background 0.8s ease}
.bg-anim.light{background:#ffe699}
.bg-anim.dark{background:#732626}
.bg-anim .blob{position:absolute;border-radius:50%;filter:blur(100px);opacity:0.18;animation:blobF 20s ease-in-out infinite}
.light .blob{background:rgba(115,38,38,0.1)}
.dark .blob{background:rgba(255,230,153,0.1)}
.blob:nth-child(1){width:350px;height:350px;top:-10%;left:-5%;animation-duration:18s}
.blob:nth-child(2){width:300px;height:300px;top:40%;right:-8%;animation-delay:-5s;animation-duration:22s}
.blob:nth-child(3){width:250px;height:250px;bottom:-5%;left:30%;animation-delay:-10s;animation-duration:25s}
@keyframes blobF{0%,100%{transform:translate(0,0) scale(1)}25%{transform:translate(50px,-30px) scale(1.1)}50%{transform:translate(-20px,50px) scale(0.9)}75%{transform:translate(-40px,-15px) scale(1.05)}}

.light .text-main{color:#732626}
.dark .text-main{color:#ffe699}
.light .text-sub{color:#5a1e1e}
.dark .text-sub{color:#e0cc80}
.light .text-soft{color:#8a4040}
.dark .text-soft{color:#b8a060}

.glass{backdrop-filter:blur(24px) saturate(1.5);-webkit-backdrop-filter:blur(24px) saturate(1.5);border:1px solid rgba(255,255,255,0.18);box-shadow:0 8px 32px rgba(0,0,0,0.06),inset 0 1px 0 rgba(255,255,255,0.2)}
.light .glass{background:rgba(255,255,255,0.4);border-color:rgba(255,255,255,0.55)}
.dark .glass{background:rgba(0,0,0,0.2);border-color:rgba(255,230,153,0.08);box-shadow:0 8px 32px rgba(0,0,0,0.3),inset 0 1px 0 rgba(255,230,153,0.05)}
.glass-strong{backdrop-filter:blur(30px) saturate(1.8);-webkit-backdrop-filter:blur(30px) saturate(1.8);border:1px solid rgba(255,255,255,0.2);box-shadow:0 12px 40px rgba(0,0,0,0.08),inset 0 2px 0 rgba(255,255,255,0.25)}
.light .glass-strong{background:rgba(255,255,255,0.55);border-color:rgba(255,255,255,0.65)}
.dark .glass-strong{background:rgba(0,0,0,0.3);border-color:rgba(255,230,153,0.1);box-shadow:0 12px 40px rgba(0,0,0,0.4),inset 0 2px 0 rgba(255,230,153,0.06)}

.header-bar{position:fixed;top:0;left:0;right:0;z-index:90;padding:12px 16px;display:flex;align-items:center;justify-content:space-between}

.liquid-nav{position:fixed;bottom:24px;left:50%;transform:translateX(-50%);z-index:100;display:flex;gap:4px;padding:6px;border-radius:28px;transition:all 0.5s cubic-bezier(0.34,1.56,0.64,1)}
.nav-item{position:relative;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:8px 20px;border-radius:22px;cursor:pointer;transition:all 0.4s cubic-bezier(0.34,1.56,0.64,1);font-size:10px;font-weight:600;gap:3px;min-width:64px;z-index:1}
.light .nav-item{color:rgba(115,38,38,0.4)}
.dark .nav-item{color:rgba(255,230,153,0.4)}
.nav-item:hover{color:rgba(115,38,38,0.7)}
.dark .nav-item:hover{color:rgba(255,230,153,0.7)}
.nav-item.active{color:#732626}
.dark .nav-item.active{color:#ffe699}
.nav-item .nav-icon{font-size:22px;transition:transform 0.4s cubic-bezier(0.34,1.56,0.64,1)}
.nav-item.active .nav-icon{transform:scale(1.15)}
.nav-pill{position:absolute;top:6px;height:calc(100% - 12px);border-radius:22px;transition:all 0.5s cubic-bezier(0.34,1.56,0.64,1);pointer-events:none;z-index:0}
.light .nav-pill{background:rgba(255,255,255,0.6);border:1px solid rgba(255,255,255,0.7);box-shadow:0 4px 20px rgba(0,0,0,0.06)}
.dark .nav-pill{background:rgba(0,0,0,0.25);border:1px solid rgba(255,230,153,0.1);box-shadow:0 4px 20px rgba(0,0,0,0.3)}

.page{position:fixed;top:0;left:0;right:0;bottom:0;z-index:1;display:none;flex-direction:column;opacity:0;transition:opacity 0.4s ease,transform 0.5s cubic-bezier(0.34,1.56,0.64,1);transform:scale(0.96) translateY(10px);overflow-y:auto;overflow-x:hidden;scrollbar-width:none;padding-bottom:100px}
.page::-webkit-scrollbar{display:none}
.page.active{display:flex;opacity:1;transform:scale(1) translateY(0)}

.table-card{border-radius:20px;cursor:pointer;transition:all 0.5s cubic-bezier(0.34,1.56,0.64,1);overflow:hidden}
.table-card:hover{transform:scale(1.05)}
.table-card:active{transform:scale(0.95)}

.menu-item{border-radius:18px;transition:all 0.4s cubic-bezier(0.34,1.56,0.64,1);overflow:hidden}
.menu-item:hover{transform:translateY(-2px)}
.menu-item:active{transform:scale(0.98)}
.menu-img-wrap{width:72px;height:72px;border-radius:14px;overflow:hidden;flex-shrink:0;background:rgba(128,128,128,0.08)}
.menu-img-wrap img{width:100%;height:100%;object-fit:cover}

.cat-tab{padding:10px 18px;border-radius:16px;font-size:12px;font-weight:600;cursor:pointer;transition:all 0.4s cubic-bezier(0.34,1.56,0.64,1);white-space:nowrap;border:1px solid transparent}
.light .cat-tab{color:rgba(115,38,38,0.45)}
.dark .cat-tab{color:rgba(255,230,153,0.45)}
.light .cat-tab.active{color:#732626;background:rgba(255,255,255,0.5);border-color:rgba(255,255,255,0.6)}
.dark .cat-tab.active{color:#ffe699;background:rgba(0,0,0,0.25);border-color:rgba(255,230,153,0.1)}

.qty-ctrl{display:flex;align-items:center;gap:6px}
.qty-ctrl button{width:30px;height:30px;border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:all 0.3s cubic-bezier(0.34,1.56,0.64,1);font-size:16px;font-weight:700}
.qty-ctrl button:hover{transform:scale(1.12)}
.qty-ctrl button:active{transform:scale(0.88)}

.gallery-img{border-radius:18px;overflow:hidden;cursor:pointer;transition:all 0.5s cubic-bezier(0.34,1.56,0.64,1);position:relative}
.gallery-img:hover{transform:scale(1.03)}
.gallery-img:active{transform:scale(0.97)}
.gallery-img img{width:100%;height:100%;object-fit:cover;transition:transform 0.5s ease}
.gallery-img:hover img{transform:scale(1.08)}
.gallery-img .dl-overlay{position:absolute;inset:0;background:rgba(0,0,0,0.4);display:flex;align-items:center;justify-content:center;opacity:0;transition:opacity 0.3s ease;border-radius:18px}
.gallery-img:hover .dl-overlay{opacity:1}

.badge{position:absolute;top:-6px;right:-6px;min-width:20px;height:20px;border-radius:10px;background:linear-gradient(135deg,#ff6b6b,#ee5a24);color:#fff;font-size:11px;font-weight:700;display:flex;align-items:center;justify-content:center;padding:0 6px;animation:badgePop 0.4s cubic-bezier(0.34,1.56,0.64,1)}
@keyframes badgePop{0%{transform:scale(0)}100%{transform:scale(1)}}

.toast{position:fixed;top:80px;left:50%;transform:translateX(-50%) translateY(-20px);z-index:200;padding:14px 28px;border-radius:18px;font-size:14px;font-weight:600;opacity:0;transition:all 0.5s cubic-bezier(0.34,1.56,0.64,1);pointer-events:none}
.toast.show{opacity:1;transform:translateX(-50%) translateY(0)}

.modal-overlay{position:fixed;inset:0;z-index:150;background:rgba(0,0,0,0.4);backdrop-filter:blur(8px);-webkit-backdrop-filter:blur(8px);display:none;align-items:center;justify-content:center;opacity:0;transition:opacity 0.3s ease}
.modal-overlay.show{display:flex;opacity:1}
.modal-box{border-radius:28px;padding:32px;max-width:400px;width:90%;max-height:80vh;overflow-y:auto;transform:scale(0.9);transition:transform 0.4s cubic-bezier(0.34,1.56,0.64,1)}
.modal-overlay.show .modal-box{transform:scale(1)}

.admin-order{border-radius:16px;padding:16px;margin-bottom:12px;transition:all 0.3s ease}
.admin-order:hover{transform:translateY(-1px)}

.avail-dot{width:8px;height:8px;border-radius:50%;display:inline-block;flex-shrink:0}
.avail-yes{background:#00c853;box-shadow:0 0 6px rgba(0,200,83,0.5)}
.avail-no{background:#ff5252;box-shadow:0 0 6px rgba(255,82,82,0.5)}

.send-btn{padding:14px 28px;border-radius:18px;font-weight:700;font-size:15px;cursor:pointer;transition:all 0.4s cubic-bezier(0.34,1.56,0.64,1);border:none;display:inline-flex;align-items:center;gap:8px;color:#fff}
.send-btn:hover{transform:scale(1.03)}
.send-btn:active{transform:scale(0.97)}
.send-wa{background:linear-gradient(135deg,#25d366,#128c7e);box-shadow:0 8px 24px rgba(37,211,102,0.3)}
.send-admin{background:linear-gradient(135deg,#732626,#a03030);box-shadow:0 8px 24px rgba(115,38,38,0.4)}

.status-tag{padding:4px 12px;border-radius:10px;font-size:11px;font-weight:700}
.light .status-new{background:rgba(0,200,83,0.15);color:#00802b}
.dark .status-new{background:rgba(0,200,83,0.15);color:#66ff99}
.light .status-sent{background:rgba(230,137,0,0.12);color:#b35900}
.dark .status-sent{background:rgba(255,152,0,0.15);color:#ffcc66}

.back-btn{width:40px;height:40px;border-radius:14px;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:all 0.3s cubic-bezier(0.34,1.56,0.64,1)}
.back-btn:hover{transform:scale(1.1)}
.back-btn:active{transform:scale(0.9)}

@keyframes animUp{0%{opacity:0;transform:translateY(20px)}100%{opacity:1;transform:translateY(0)}}
.anim-up{animation:animUp 0.6s cubic-bezier(0.34,1.56,0.64,1) forwards;opacity:0}

.hide-scroll{scrollbar-width:none;-ms-overflow-style:none}
.hide-scroll::-webkit-scrollbar{display:none}

.light .icon-glass{color:rgba(115,38,38,0.55)}
.dark .icon-glass{color:rgba(255,230,153,0.6)}

.send-main-btn{width:100%;padding:16px;border-radius:22px;font-weight:800;font-size:15px;cursor:pointer;transition:all 0.4s cubic-bezier(0.34,1.56,0.64,1);border:none;color:#fff;display:flex;align-items:center;justify-content:center;gap:8px}
.light .send-main-btn{background:linear-gradient(135deg,#732626,#a03030);box-shadow:0 8px 32px rgba(115,38,38,0.25)}
.dark .send-main-btn{background:linear-gradient(135deg,#ffe699,#e0cc80);color:#732626;box-shadow:0 8px 32px rgba(255,230,153,0.2)}
.send-main-btn:hover{transform:scale(1.02)}
.send-main-btn:active{transform:scale(0.97)}

.light input::placeholder{color:rgba(115,38,38,0.35)}
.dark input::placeholder{color:rgba(255,230,153,0.3)}
.light input{color:#732626}
.dark input{color:#ffe699}
</style>
</head>
<body class="font-kurdish">

<!-- WELCOME SPLASH -->
<div id="welcomeSplash" class="welcome-splash" style="background:#ffe699">
  <div class="logo-anim mb-6">
    <span class="iconify" data-icon="lucide:coffee" style="font-size:72px;color:#732626"></span>
  </div>
  <h1 class="text-3xl font-black mb-3" style="color:#732626;letter-spacing:3px">CASTALICA</h1>
  <p class="wt text-xl font-bold mb-1" id="welcomeKu" style="color:#732626;animation-delay:0.2s">بەخێربێیت</p>
  <p class="wt text-base font-semibold mb-1" id="welcomeEn" style="color:#8a4040;animation-delay:0.5s">Welcome</p>
  <p class="wt text-base font-semibold" id="welcomeAr" style="color:#8a4040;animation-delay:0.8s">أهلاً وسهلاً</p>
</div>

<!-- BACKGROUND -->
<div id="bgAnim" class="bg-anim light">
  <div class="blob"></div><div class="blob"></div><div class="blob"></div>
</div>

<!-- TOAST -->
<div id="toast" class="toast glass-strong"></div>

<!-- HEADER -->
<header class="header-bar">
  <div class="flex items-center gap-2">
    <span class="iconify icon-glass" data-icon="lucide:coffee" style="font-size:22px"></span>
    <h1 class="text-main text-lg font-extrabold tracking-wider" style="letter-spacing:2px">CASTALICA</h1>
  </div>
  <div class="flex items-center gap-2">
    <button onclick="toggleTheme()" class="back-btn glass">
      <span id="themeIcon" class="iconify icon-glass" data-icon="lucide:sun" style="font-size:18px"></span>
    </button>
    <div class="relative">
      <button onclick="toggleLangMenu()" class="back-btn glass">
        <span class="iconify icon-glass" data-icon="lucide:globe" style="font-size:18px"></span>
      </button>
      <div id="langMenu" class="absolute top-full left-0 mt-2 glass-strong rounded-2xl p-2 min-w-[150px] z-50" style="display:none">
        <div onclick="setLang('ku')" class="px-4 py-2.5 rounded-xl cursor-pointer text-main text-sm font-medium transition-all hover:opacity-70">کوردی سۆرانی</div>
        <div onclick="setLang('ku-b')" class="px-4 py-2.5 rounded-xl cursor-pointer text-main text-sm font-medium transition-all hover:opacity-70">کوردی بادینی</div>
        <div onclick="setLang('en')" class="px-4 py-2.5 rounded-xl cursor-pointer text-main text-sm font-medium transition-all hover:opacity-70">English</div>
        <div onclick="setLang('ar')" class="px-4 py-2.5 rounded-xl cursor-pointer text-main text-sm font-medium transition-all hover:opacity-70">العربية</div>
      </div>
    </div>
    <button onclick="showAdminLogin()" class="back-btn glass">
      <span class="iconify icon-glass" data-icon="lucide:shield-check" style="font-size:18px"></span>
    </button>
  </div>
</header>

<!-- PAGE: TABLES -->
<div id="page-tables" class="page active" style="padding-top:70px">
  <div class="px-4 mb-5">
    <h2 class="text-main text-2xl font-extrabold mb-1" data-i18n="tables_title">مێزەکان</h2>
    <p class="text-sub text-sm" data-i18n="tables_sub">مێزێک هەڵبژێرە بۆ داواکاری</p>
  </div>
  <div class="px-4 grid grid-cols-4 gap-3" id="tablesGrid"></div>
</div>

<!-- PAGE: MENU -->
<div id="page-menu" class="page" style="padding-top:70px">
  <div class="px-4 mb-4 flex items-center gap-3">
    <button onclick="goTo('tables')" class="back-btn glass">
      <span class="iconify icon-glass" data-icon="lucide:arrow-right" style="font-size:18px"></span>
    </button>
    <div>
      <h2 class="text-main text-lg font-bold" data-i18n="menu_for">مێنیۆ بۆ</h2>
      <p class="text-sub text-sm" id="menuTableName">مێز ١</p>
    </div>
  </div>
  <div class="px-4 flex gap-2 mb-4 overflow-x-auto hide-scroll pb-2" id="catTabs"></div>
  <div class="px-4 grid grid-cols-1 gap-3" id="menuGrid"></div>
</div>

<!-- PAGE: ORDERS -->
<div id="page-orders" class="page" style="padding-top:70px">
  <div class="px-4 mb-5">
    <h2 class="text-main text-2xl font-extrabold mb-1" data-i18n="orders_title">داواکاریەکانم</h2>
    <p class="text-sub text-sm" data-i18n="orders_sub">سەرجەم داواکاریەکانی تۆ</p>
  </div>
  <div class="px-4" id="ordersList"></div>
</div>

<!-- PAGE: GALLERY -->
<div id="page-gallery" class="page" style="padding-top:70px">
  <div class="px-4 mb-5">
    <h2 class="text-main text-2xl font-extrabold mb-1" data-i18n="gallery_title">گالێری</h2>
    <p class="text-sub text-sm" data-i18n="gallery_sub">وێنەکانی کاستالیکا</p>
  </div>
  <div class="px-4 grid grid-cols-2 gap-3" id="galleryGrid"></div>
</div>

<!-- PAGE: ADMIN -->
<div id="page-admin" class="page" style="padding-top:70px">
  <div class="px-4 mb-5 flex items-center justify-between">
    <div>
      <h2 class="text-main text-2xl font-extrabold mb-1" data-i18n="admin_title">بەڕێوبەر</h2>
      <p class="text-sub text-sm" data-i18n="admin_sub">سەرجەم داواکاریەکان</p>
    </div>
    <button onclick="goTo('tables');adminLoggedIn=false" class="back-btn glass">
      <span class="iconify icon-glass" data-icon="lucide:log-out" style="font-size:18px"></span>
    </button>
  </div>
  <div class="px-4" id="adminOrdersList"></div>
</div>

<!-- LIQUID NAVBAR -->
<nav class="liquid-nav glass-strong" id="mainNav">
  <div class="nav-pill" id="navPill"></div>
  <div class="nav-item active" data-page="tables" onclick="goTo('tables')">
    <span class="iconify nav-icon" data-icon="lucide:layout-grid"></span>
    <span data-i18n="nav_tables">مێزەکان</span>
  </div>
  <div class="nav-item" data-page="orders" onclick="goTo('orders')">
    <span class="iconify nav-icon" data-icon="lucide:shopping-bag"></span>
    <span data-i18n="nav_orders">داواکاری</span>
    <div class="badge" id="orderBadge" style="display:none">0</div>
  </div>
  <div class="nav-item" data-page="gallery" onclick="goTo('gallery')">
    <span class="iconify nav-icon" data-icon="lucide:image"></span>
    <span data-i18n="nav_gallery">گالێری</span>
  </div>
</nav>

<!-- ADMIN LOGIN MODAL -->
<div id="adminLoginModal" class="modal-overlay" onclick="if(event.target===this)closeAdminLogin()">
  <div class="modal-box glass-strong">
    <div class="text-center mb-6">
      <div class="w-16 h-16 rounded-2xl glass mx-auto flex items-center justify-center mb-3">
        <span class="iconify icon-glass" data-icon="lucide:shield-check" style="font-size:28px"></span>
      </div>
      <h3 class="text-main text-xl font-bold" data-i18n="admin_login">چوونەژوورەوەی بەڕێوبەر</h3>
      <p class="text-sub text-sm mt-1" data-i18n="admin_pass_hint">تکایە پاسۆرد بنووسە</p>
    </div>
    <input id="adminPassInput" type="password" placeholder="پاسۆرد..." class="w-full px-5 py-3.5 rounded-2xl glass text-sm outline-none mb-4" style="background:transparent">
    <div class="flex gap-3">
      <button onclick="closeAdminLogin()" class="flex-1 py-3 rounded-2xl glass text-main text-sm font-bold cursor-pointer transition-all hover:scale-[1.02] active:scale-95" data-i18n="cancel">هەڵوەشاندنەوە</button>
      <button onclick="tryAdminLogin()" class="flex-1 py-3 rounded-2xl text-white text-sm font-bold cursor-pointer transition-all hover:scale-[1.02] active:scale-95" style="background:linear-gradient(135deg,#732626,#a03030)" data-i18n="login">چوونەژوورەوە</button>
    </div>
    <p id="adminError" class="text-center mt-3 text-sm font-bold" style="color:#ff5252;display:none" data-i18n="pass_wrong">پاسۆرد هەڵەیە!</p>
  </div>
</div>

<!-- SEND MODAL -->
<div id="sendModal" class="modal-overlay" onclick="if(event.target===this)closeSendModal()">
  <div class="modal-box glass-strong">
    <div class="text-center mb-6">
      <div class="w-16 h-16 rounded-2xl glass mx-auto flex items-center justify-center mb-3">
        <span class="iconify icon-glass" data-icon="lucide:send" style="font-size:28px"></span>
      </div>
      <h3 class="text-main text-lg font-bold" data-i18n="send_to">دایبەنێرە بۆ</h3>
    </div>
    <div class="flex flex-col gap-3">
      <button onclick="sendWhatsApp()" class="send-btn send-wa justify-center">
        <span class="iconify" data-icon="lucide:message-circle" style="font-size:20px"></span>
        <span>WhatsApp</span>
      </button>
      <button onclick="sendToAdmin()" class="send-btn send-admin justify-center">
        <span class="iconify" data-icon="lucide:shield-check" style="font-size:20px"></span>
        <span data-i18n="send_admin">بنێرە بۆ بەڕێوبەر</span>
      </button>
    </div>
    <button onclick="closeSendModal()" class="w-full mt-4 py-3 rounded-2xl glass text-main text-sm font-bold cursor-pointer transition-all hover:scale-[1.02] active:scale-95" data-i18n="cancel">هەڵوەشاندنەوە</button>
  </div>
</div>

<script>
let currentTheme='light',currentLang='ku',currentPage='tables',selectedTable=null,selectedCategory='dessert',adminLoggedIn=false;
let orders=JSON.parse(localStorage.getItem('castalica_orders')||'[]');
let cart={};

const tables=Array.from({length:20},(_,i)=>({id:i+1,num:i+1}));

// ===== MENU DATA WITH REAL FOOD IMAGES =====
const menuData={
  dessert:[
    {id:'d1',name:'تیرامیسو',price:5000,available:true,img:'https://images.unsplash.com/photo-1571877227200-a0d98ea607e9?w=200&h=200&fit=crop'},
    {id:'d2',name:'چیزکەیک',price:4500,available:true,img:'https://images.unsplash.com/photo-1565958011703-44f9829ba187?w=200&h=200&fit=crop'},
    {id:'d3',name:'پاناکۆتا',price:4000,available:false,img:'https://images.unsplash.com/photo-1488477181946-6428a0291777?w=200&h=200&fit=crop'},
    {id:'d4',name:'براونی شۆکلاتی',price:3500,available:true,img:'https://images.unsplash.com/photo-1606313564200-e75d5e30476c?w=200&h=200&fit=crop'},
    {id:'d5',name:'کرێپ فەڕەنسی',price:4000,available:true,img:'https://images.unsplash.com/photo-1519676867240-f03562e64548?w=200&h=200&fit=crop'},
    {id:'d6',name:'مۆفین توتفرۆکە',price:2500,available:true,img:'https://images.unsplash.com/photo-1607958996333-41aef7caefaa?w=200&h=200&fit=crop'},
    {id:'d7',name:'باسکووتە شۆکلات',price:3000,available:true,img:'https://images.unsplash.com/photo-1499636136210-6f4ee915583e?w=200&h=200&fit=crop'},
    {id:'d8',name:'ئایسکریم سێ بۆن',price:3000,available:false,img:'https://images.unsplash.com/photo-1501443762994-82bd5dace89a?w=200&h=200&fit=crop'},
    {id:'d9',name:'ماکارۆن',price:3500,available:true,img:'https://images.unsplash.com/photo-1569864358642-9d1684040f43?w=200&h=200&fit=crop'},
    {id:'d10',name:'کولاکانتە',price:2800,available:true,img:'https://images.unsplash.com/photo-1558326567-98ae2405596b?w=200&h=200&fit=crop'}
  ],
  cake:[
    {id:'c1',name:'کێکی شکلاتی',price:8000,available:true,img:'https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=200&h=200&fit=crop'},
    {id:'c2',name:'کێکی توتفرۆکە',price:7500,available:true,img:'https://images.unsplash.com/photo-1565958011703-44f9829ba187?w=200&h=200&fit=crop'},
    {id:'c3',name:'کێکی وەنێڵ',price:7000,available:false,img:'https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?w=200&h=200&fit=crop'},
    {id:'c4',name:'کێکی کارۆت',price:6500,available:true,img:'https://images.unsplash.com/photo-1621303837174-89787a7d4729?w=200&h=200&fit=crop'},
    {id:'c5',name:'کێکی لیمۆ',price:6500,available:true,img:'https://images.unsplash.com/photo-1519915028121-7d3463d20b13?w=200&h=200&fit=crop'},
    {id:'c6',name:'کێکی رێدڤێڵڤەت',price:8500,available:true,img:'https://images.unsplash.com/photo-1616541823729-00fe0aacd32c?w=200&h=200&fit=crop'},
    {id:'c7',name:'کێکی پێستەکە',price:7000,available:true,img:'https://images.unsplash.com/photo-1621303837174-89787a7d4729?w=200&h=200&fit=crop'},
    {id:'c8',name:'کێکی کاکاو',price:6000,available:true,img:'https://images.unsplash.com/photo-1606890737304-57a1ca8a5b62?w=200&h=200&fit=crop'}
  ],
  hot:[
    {id:'h1',name:'ئەسپرێسۆ',price:2500,available:true,img:'https://images.unsplash.com/photo-1510707577719-ae7c14805e3a?w=200&h=200&fit=crop'},
    {id:'h2',name:'کاپوچینۆ',price:3500,available:true,img:'https://images.unsplash.com/photo-1572442388796-11668a67e53d?w=200&h=200&fit=crop'},
    {id:'h3',name:'لاتە',price:3500,available:true,img:'https://images.unsplash.com/photo-1461023058943-07fcbe16d735?w=200&h=200&fit=crop'},
    {id:'h4',name:'مۆکا',price:4000,available:true,img:'https://images.unsplash.com/photo-1578314675249-a6910f80cc4e?w=200&h=200&fit=crop'},
    {id:'h5',name:'تەرکیش کافی',price:3000,available:false,img:'https://images.unsplash.com/photo-1514432324607-a09d9b4aefda?w=200&h=200&fit=crop'},
    {id:'h6',name:'هۆت کاکاو',price:3000,available:true,img:'https://images.unsplash.com/photo-1542990253-0d0f5be5f0ed?w=200&h=200&fit=crop'},
    {id:'h7',name:'چای سەوز',price:2000,available:true,img:'https://images.unsplash.com/photo-1556881286-fc6915169721?w=200&h=200&fit=crop'},
    {id:'h8',name:'ماچا لاتە',price:2500,available:true,img:'https://images.unsplash.com/photo-1536256263959-770b48d82b0a?w=200&h=200&fit=crop'},
    {id:'h9',name:'ئەمریکانۆ',price:2000,available:true,img:'https://images.unsplash.com/photo-1551030173-122aabc4489c?w=200&h=200&fit=crop'},
    {id:'h10',name:'فلات وایت',price:3000,available:true,img:'https://images.unsplash.com/photo-1587735243615-c03f25aaff15?w=200&h=200&fit=crop'}
  ],
  cold:[
    {id:'cl1',name:'ئایس لاتە',price:4000,available:true,img:'https://images.unsplash.com/photo-1461023058943-07fcbe16d735?w=200&h=200&fit=crop'},
    {id:'cl2',name:'فراپەچینۆ',price:4500,available:true,img:'https://images.unsplash.com/photo-1572490122747-3968b75cc699?w=200&h=200&fit=crop'},
    {id:'cl3',name:'سمووزی توت',price:5000,available:true,img:'https://images.unsplash.com/photo-1553530666-ba11a7da3888?w=200&h=200&fit=crop'},
    {id:'cl4',name:'مۆهیتۆ',price:4000,available:true,img:'https://images.unsplash.com/photo-1551538827-9c037cb4f32a?w=200&h=200&fit=crop'},
    {id:'cl5',name:'لیمۆناد تازە',price:3000,available:false,img:'https://images.unsplash.com/photo-1621263764928-df1444c5e859?w=200&h=200&fit=crop'},
    {id:'cl6',name:'جووسی ئاپڵ',price:2500,available:true,img:'https://images.unsplash.com/photo-1568902438335-15a8d4bb2972?w=200&h=200&fit=crop'},
    {id:'cl7',name:'شەیک شۆکلاتی',price:4500,available:true,img:'https://images.unsplash.com/photo-1572490122747-3968b75cc699?w=200&h=200&fit=crop'},
    {id:'cl8',name:'آیس شیکەلاد',price:4000,available:true,img:'https://images.unsplash.com/photo-1577805947697-89e18249d767?w=200&h=200&fit=crop'},
    {id:'cl9',name:'کوکتەیل میوە',price:5000,available:true,img:'https://images.unsplash.com/photo-1546171753-97d7676e4602?w=200&h=200&fit=crop'},
    {id:'cl10',name:'ئاوەکانی مینەرال',price:1000,available:true,img:'https://images.unsplash.com/photo-1548839140-29a749e1cf4d?w=200&h=200&fit=crop'}
  ]
};

const categories=[
  {id:'dessert',icon:'lucide:cake-slice',label:'dessert'},
  {id:'cake',icon:'lucide:cake',label:'cake'},
  {id:'hot',icon:'lucide:coffee',label:'hot'},
  {id:'cold',icon:'lucide:cup-soda',label:'cold'}
];

const galleryImages=[
  {id:'g1',src:'https://picsum.photos/seed/castcafe1/400/500',title:'کاستالیکا ١'},
  {id:'g2',src:'https://picsum.photos/seed/castcafe2/400/500',title:'کاستالیکا ٢'},
  {id:'g3',src:'https://picsum.photos/seed/castcafe3/400/500',title:'کاستالیکا ٣'},
  {id:'g4',src:'https://picsum.photos/seed/castcafe4/400/500',title:'کاستالیکا ٤'},
  {id:'g5',src:'https://picsum.photos/seed/castcafe5/400/500',title:'کاستالیکا ٥'},
  {id:'g6',src:'https://picsum.photos/seed/castcafe6/400/500',title:'کاستالیکا ٦'},
  {id:'g7',src:'https://picsum.photos/seed/castcafe7/400/500',title:'کاستالیکا ٧'},
  {id:'g8',src:'https://picsum.photos/seed/castcafe8/400/500',title:'کاستالیکا ٨'},
  {id:'g9',src:'https://picsum.photos/seed/castcafe9/400/500',title:'کاستالیکا ٩'},
  {id:'g10',src:'https://picsum.photos/seed/castcafe10/400/500',title:'کاستالیکا ١٠'},
  {id:'g11',src:'https://picsum.photos/seed/castcafe11/400/500',title:'کاستالیکا ١١'},
  {id:'g12',src:'https://picsum.photos/seed/castcafe12/400/500',title:'کاستالیکا ١٢'}
];

// ===== i18n =====
const i18n={
  ku:{tables_title:'مێزەکان',tables_sub:'مێزێک هەڵبژێرە بۆ داواکاری',menu_for:'مێنیۆ بۆ',nav_tables:'مێزەکان',nav_orders:'داواکاری',nav_gallery:'گالێری',orders_title:'داواکاریەکانم',orders_sub:'سەرجەم داواکاریەکانی تۆ',no_orders:'هیچ داواکارییەکێک نییە',gallery_title:'گالێری',gallery_sub:'وێنەکانی کاستالیکا',download:'داگرتن',admin_title:'بەڕێوبەر',admin_sub:'سەرجەم داواکاریەکان',admin_login:'چوونەژوورەوەی بەڕێوبەر',admin_pass_hint:'تکایە پاسۆرد بنووسە',cancel:'هەڵوەشاندنەوە',login:'چوونەژوورەوە',send_to:'دایبەنێرە بۆ',send_admin:'بنێرە بۆ بەڕێوبەر',table:'مێز',total:'کۆی گشتی',items:'بابەت',dinar:'دینار',available:'بەردەست',unavailable:'نەبەردەست',new:'نوێ',sent:'نێردراو',no_orders_admin:'هیچ داواکارییەکێک نییە',order_sent:'داواکاریەکە نێردرا!',order_saved:'داواکاریەکە پاشەکەوت کرا!',pass_wrong:'پاسۆرد هەڵەیە!',send_order:'ناردنی داواکاری',empty_cart:'سەبەتەکە بەتاڵە',dessert:'شیرینی',cake:'کێک',hot:'قاوەی گەرم',cold:'خواردنەوەی سارد'},
  'ku-b':{tables_title:'مێزەکان',tables_sub:'مێزێک هەڵبژێرە بۆ داواکاری',menu_for:'مێنیۆ بۆ',nav_tables:'مێزەکان',nav_orders:'داواکاری',nav_gallery:'گالێری',orders_title:'داواکاریەکانم',orders_sub:'سەرجەم داواکاریەکانی تۆ',no_orders:'هیچ داواکارییەکێک نییە',gallery_title:'گالێری',gallery_sub:'وێنەکانی کاستالیکا',download:'داگرتن',admin_title:'بەڕێوبەر',admin_sub:'سەرجەم داواکاریەکان',admin_login:'چوونەژوورەوەی بەڕێوبەر',admin_pass_hint:'تکایە پاسۆرد بنووسە',cancel:'هەڵوەشاندنەوە',login:'چوونەژوورەوە',send_to:'دایبەنێرە بۆ',send_admin:'بنێرە بۆ بەڕێوبەر',table:'مێز',total:'کۆی گشتی',items:'بابەت',dinar:'دینار',available:'بەردەست',unavailable:'نەبەردەست',new:'نوێ',sent:'نێردراو',no_orders_admin:'هیچ داواکارییەکێک نییە',order_sent:'داواکاریەکە نێردرا!',order_saved:'داواکاریەکە پاشەکەوت کرا!',pass_wrong:'پاسۆرد هەڵەیە!',send_order:'ناردنی داواکاری',empty_cart:'سەبەتەکە بەتاڵە',dessert:'شیرینی',cake:'کێک',hot:'قاوەی گەرم',cold:'خواردنەوەی سارد'},
  en:{tables_title:'Tables',tables_sub:'Select a table to order',menu_for:'Menu for',nav_tables:'Tables',nav_orders:'Orders',nav_gallery:'Gallery',orders_title:'My Orders',orders_sub:'All your orders',no_orders:'No orders yet',gallery_title:'Gallery',gallery_sub:'Castalica Photos',download:'Download',admin_title:'Admin',admin_sub:'All orders',admin_login:'Admin Login',admin_pass_hint:'Please enter password',cancel:'Cancel',login:'Login',send_to:'Send to',send_admin:'Send to Admin',table:'Table',total:'Total',items:'Items',dinar:'IQD',available:'Available',unavailable:'Unavailable',new:'New',sent:'Sent',no_orders_admin:'No orders yet',order_sent:'Order sent!',order_saved:'Order saved!',pass_wrong:'Wrong password!',send_order:'Send Order',empty_cart:'Cart is empty',dessert:'Desserts',cake:'Cakes',hot:'Hot Coffee',cold:'Cold Drinks'},
  ar:{tables_title:'الطاولات',tables_sub:'اختر طاولة للطلب',menu_for:'قائمة لـ',nav_tables:'الطاولات',nav_orders:'الطلبات',nav_gallery:'المعرض',orders_title:'طلباتي',orders_sub:'جميع طلباتك',no_orders:'لا توجد طلبات بعد',gallery_title:'المعرض',gallery_sub:'صور كاستاليكا',download:'تحميل',admin_title:'المدير',admin_sub:'جميع الطلبات',admin_login:'تسجيل دخول المدير',admin_pass_hint:'يرجى إدخال كلمة المرور',cancel:'إلغاء',login:'تسجيل الدخول',send_to:'أرسل إلى',send_admin:'أرسل للمدير',table:'طاولة',total:'المجموع',items:'عناصر',dinar:'دينار',available:'متوفر',unavailable:'غير متوفر',new:'جديد',sent:'تم الإرسال',no_orders_admin:'لا توجد طلبات بعد',order_sent:'تم إرسال الطلب!',order_saved:'تم حفظ الطلب!',pass_wrong:'كلمة مرور خاطئة!',send_order:'إرسال الطلب',empty_cart:'السلة فارغة',dessert:'حلويات',cake:'كعك',hot:'قهوة ساخنة',cold:'مشروبات باردة'}
};
function t(key){return(i18n[currentLang]&&i18n[currentLang][key])||i18n.ku[key]||key}

// ===== RENDER FUNCTIONS =====
function renderTables(){
  document.getElementById('tablesGrid').innerHTML=tables.map((tb,i)=>`
    <div class="table-card glass p-3 flex flex-col items-center justify-center gap-1 anim-up" style="animation-delay:${i*35}ms;min-height:95px" onclick="selectTable(${tb.id})">
      <span class="iconify icon-glass" data-icon="lucide:armchair" style="font-size:24px;opacity:0.45"></span>
      <span class="text-main text-2xl font-black">${tb.num}</span>
    </div>`).join('');
  applyI18n();
}

function renderCatTabs(){
  document.getElementById('catTabs').innerHTML=categories.map(cat=>`
    <div class="cat-tab ${selectedCategory===cat.id?'active':''}" onclick="selectCategory('${cat.id}')">
      <span class="iconify inline-block" data-icon="${cat.icon}" style="font-size:13px;vertical-align:middle;margin-left:4px"></span>
      ${t(cat.label)}
    </div>`).join('');
}

function renderMenu(){
  const items=menuData[selectedCategory]||[];
  document.getElementById('menuGrid').innerHTML=items.map((item,i)=>{
    const qty=cart[item.id]||0;
    return`
    <div class="menu-item glass p-3 flex gap-3 items-center anim-up" style="animation-delay:${i*40}ms">
      <div class="menu-img-wrap">
        <img src="${item.img}" alt="${item.name}" loading="lazy" onerror="this.style.display='none'">
      </div>
      <div class="flex-1 min-w-0">
        <div class="flex items-center gap-2 mb-0.5">
          <span class="avail-dot ${item.available?'avail-yes':'avail-no'}"></span>
          <h3 class="text-main text-sm font-bold truncate">${item.name}</h3>
        </div>
        <p class="text-sub text-xs font-semibold">${item.price.toLocaleString()} ${t('dinar')}</p>
        <p class="text-xs mt-0.5 font-medium" style="color:${item.available?'':'#ff5252'}">${item.available?t('available'):t('unavailable')}</p>
      </div>
      <div class="qty-ctrl">
        ${qty>0?`<button class="glass" onclick="event.stopPropagation();changeQty('${item.id}',-1)">−</button><span class="text-main text-sm font-bold w-5 text-center">${qty}</span>`:''}
        <button class="glass" style="${!item.available?'opacity:0.2;pointer-events:none':''}" onclick="event.stopPropagation();changeQty('${item.id}',1)">+</button>
      </div>
    </div>`}).join('');

  const totalItems=Object.values(cart).reduce((a,b)=>a+b,0);
  if(totalItems>0){
    document.getElementById('menuGrid').innerHTML+=`
    <div class="mt-4 mb-8 anim-up" style="animation-delay:${items.length*40}ms">
      <button onclick="openSendModal()" class="send-main-btn">
        <span class="iconify" data-icon="lucide:send" style="font-size:18px"></span>
        ${t('send_order')} (${totalItems} ${t('items')})
      </button>
    </div>`;
  }
}

function renderOrders(){
  const c=document.getElementById('ordersList');
  if(!orders.length){c.innerHTML=`<div class="text-center py-16"><span class="iconify text-soft" data-icon="lucide:shopping-bag" style="font-size:48px"></span><p class="text-soft mt-3">${t('no_orders')}</p></div>`;return}
  c.innerHTML=orders.slice().reverse().map((o,i)=>`
    <div class="admin-order glass anim-up" style="animation-delay:${i*50}ms">
      <div class="flex items-center justify-between mb-3">
        <div class="flex items-center gap-2"><span class="iconify text-sub" data-icon="lucide:armchair" style="font-size:16px"></span><span class="text-main font-bold text-sm">${t('table')} ${o.table}</span></div>
        <span class="status-tag ${o.status==='new'?'status-new':'status-sent'}">${t(o.status)}</span>
      </div>
      <div class="space-y-2 mb-3">${o.items.map(it=>`
        <div class="flex items-center justify-between">
          <div class="flex items-center gap-2"><span class="avail-dot ${it.available?'avail-yes':'avail-no'}"></span><span class="text-sub text-xs">${it.name}</span></div>
          <div class="flex items-center gap-3"><span class="text-soft text-xs">×${it.qty}</span><span class="text-main text-xs font-bold">${(it.price*it.qty).toLocaleString()}</span></div>
        </div>`).join('')}</div>
      <div class="flex items-center justify-between pt-3" style="border-top:1px solid rgba(128,128,128,0.15)">
        <span class="text-soft text-xs">${o.time}</span>
        <span class="text-main font-extrabold">${t('total')}: ${o.total.toLocaleString()} ${t('dinar')}</span>
      </div>
    </div>`).join('');
}

function renderGallery(){
  document.getElementById('galleryGrid').innerHTML=galleryImages.map((img,i)=>`
    <div class="gallery-img anim-up" style="animation-delay:${i*50}ms;aspect-ratio:4/5">
      <img src="${img.src}" alt="${img.title}" loading="lazy">
      <div class="dl-overlay" onclick="downloadImage('${img.src}','${img.title}')">
        <div class="glass-strong px-4 py-2 rounded-xl flex items-center gap-2">
          <span class="iconify" data-icon="lucide:download" style="font-size:18px;color:#fff"></span>
          <span class="text-white text-sm font-bold">${t('download')}</span>
        </div>
      </div>
    </div>`).join('');
}

function renderAdminOrders(){
  const c=document.getElementById('adminOrdersList');
  if(!orders.length){c.innerHTML=`<div class="text-center py-16"><span class="iconify text-soft" data-icon="lucide:inbox" style="font-size:48px"></span><p class="text-soft mt-3">${t('no_orders_admin')}</p></div>`;return}
  c.innerHTML=orders.slice().reverse().map((o,i)=>`
    <div class="admin-order glass anim-up" style="animation-delay:${i*50}ms">
      <div class="flex items-center justify-between mb-3">
        <div class="flex items-center gap-2"><span class="iconify text-sub" data-icon="lucide:armchair" style="font-size:16px"></span><span class="text-main font-extrabold">${t('table')} ${o.table}</span></div>
        <div class="flex items-center gap-2">
          <span class="status-tag ${o.status==='new'?'status-new':'status-sent'}">${t(o.status)}</span>
          ${o.status==='new'?`<button onclick="markSent(${i})" class="px-3 py-1 rounded-lg text-xs font-bold cursor-pointer transition-all hover:scale-105 active:scale-95" style="background:rgba(0,200,83,0.12);color:#00c853">✓ ${t('sent')}</button>`:''}
        </div>
      </div>
      <div class="space-y-2 mb-3">${o.items.map(it=>`
        <div class="flex items-center justify-between">
          <div class="flex items-center gap-2">
            <span class="avail-dot ${it.available?'avail-yes':'avail-no'}"></span>
            <span class="text-sub text-xs font-medium">${it.name}</span>
            <span class="text-soft text-[10px]">(${it.available?t('available'):t('unavailable')})</span>
          </div>
          <div class="flex items-center gap-3"><span class="text-soft text-xs">×${it.qty}</span><span class="text-main text-xs font-bold">${(it.price*it.qty).toLocaleString()}</span></div>
        </div>`).join('')}</div>
      <div class="flex items-center justify-between pt-3" style="border-top:1px solid rgba(128,128,128,0.15)">
        <span class="text-soft text-xs">${o.time}</span>
        <span class="text-main font-extrabold">${t('total')}: ${o.total.toLocaleString()} ${t('dinar')}</span>
      </div>
    </div>`).join('');
}

// ===== NAVIGATION =====
function goTo(page){
  if(page==='admin'&&!adminLoggedIn){showAdminLogin();return}
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  const target=document.getElementById('page-'+page);
  if(target){target.classList.add('active');target.scrollTop=0}
  currentPage=page;updateNavPill();
  if(page==='menu'){renderCatTabs();renderMenu()}
  if(page==='orders')renderOrders();
  if(page==='gallery')renderGallery();
  if(page==='admin')renderAdminOrders();
  if(page==='tables')renderTables();
}

function updateNavPill(){
  const navItems=document.querySelectorAll('.nav-item');
  const pill=document.getElementById('navPill');
  const map={'tables':'tables','orders':'orders','gallery':'gallery','menu':'tables','admin':'tables'};
  const tp=map[currentPage]||'tables';
  let active=null;
  navItems.forEach(item=>{if(item.dataset.page===tp){item.classList.add('active');active=item}else item.classList.remove('active')});
  if(active){
    const nr=document.getElementById('mainNav').getBoundingClientRect();
    const ir=active.getBoundingClientRect();
    pill.style.left=(ir.left-nr.left)+'px';pill.style.width=ir.width+'px';
  }
}

function selectTable(id){selectedTable=id;cart={};selectedCategory='dessert';document.getElementById('menuTableName').textContent=t('table')+' '+id;renderCatTabs();goTo('menu')}
function selectCategory(catId){selectedCategory=catId;renderCatTabs();renderMenu()}

// ===== CART =====
function changeQty(itemId,delta){
  const all=[...menuData.dessert,...menuData.cake,...menuData.hot,...menuData.cold];
  const item=all.find(i=>i.id===itemId);
  if(!item||!item.available)return;
  if(!cart[itemId])cart[itemId]=0;
  cart[itemId]+=delta;if(cart[itemId]<=0)delete cart[itemId];
  renderMenu();updateBadge();
}
function updateBadge(){
  const b=document.getElementById('orderBadge');
  if(orders.length>0){b.style.display='flex';b.textContent=orders.length}else b.style.display='none';
}
function getCartTotal(){
  let total=0;const all=[...menuData.dessert,...menuData.cake,...menuData.hot,...menuData.cold];
  for(const[id,qty]of Object.entries(cart)){const item=all.find(i=>i.id===id);if(item)total+=item.price*qty}return total;
}
function getCartItems(){
  const all=[...menuData.dessert,...menuData.cake,...menuData.hot,...menuData.cold];
  return Object.entries(cart).map(([id,qty])=>{const item=all.find(i=>i.id===id);return item?{id,name:item.name,price:item.price,qty,available:item.available}:null}).filter(Boolean);
}

// ===== SEND =====
function openSendModal(){if(!getCartItems().length){showToast(t('empty_cart'));return}document.getElementById('sendModal').classList.add('show')}
function closeSendModal(){document.getElementById('sendModal').classList.remove('show')}

function buildOrderText(){
  const items=getCartItems();let text=`🌟 CASTALICA - ${t('table')} ${selectedTable}\n━━━━━━━━━━━━━━━\n`;
  items.forEach(it=>{text+=`${it.available?'✅':'❌'} ${it.name} ×${it.qty} = ${(it.price*it.qty).toLocaleString()} ${t('dinar')}\n`});
  text+=`━━━━━━━━━━━━━━━\n💰 ${t('total')}: ${getCartTotal().toLocaleString()} ${t('dinar')}\n🕐 ${new Date().toLocaleString('ku')}`;return text;
}
function sendWhatsApp(){window.open(`https://wa.me/9647505850338?text=${encodeURIComponent(buildOrderText())}`,'_blank');saveOrder('sent');closeSendModal();showToast(t('order_sent'))}
function sendToAdmin(){saveOrder('new');closeSendModal();showToast(t('order_saved'));cart={};renderMenu();updateBadge()}
function saveOrder(status){orders.push({table:selectedTable,items:getCartItems(),total:getCartTotal(),status,time:new Date().toLocaleString('ku'),timestamp:Date.now()});localStorage.setItem('castalica_orders',JSON.stringify(orders));cart={};updateBadge()}
function markSent(revIndex){const idx=orders.length-1-revIndex;if(idx>=0&&idx<orders.length){orders[idx].status='sent';localStorage.setItem('castalica_orders',JSON.stringify(orders));renderAdminOrders()}}

// ===== GALLERY =====
function downloadImage(url,name){fetch(url).then(r=>r.blob()).then(blob=>{const a=document.createElement('a');a.href=URL.createObjectURL(blob);a.download=name+'.jpg';document.body.appendChild(a);a.click();document.body.removeChild(a);URL.revokeObjectURL(a.href);showToast(t('download')+' ✓')}).catch(()=>{})}

// ===== THEME =====
function toggleTheme(){
  currentTheme=currentTheme==='light'?'dark':'light';
  document.getElementById('bgAnim').className='bg-anim '+currentTheme;
  document.body.classList.toggle('dark',currentTheme==='dark');
  document.getElementById('themeIcon').setAttribute('data-icon',currentTheme==='light'?'lucide:sun':'lucide:moon');
}

// ===== LANGUAGE =====
function toggleLangMenu(){const m=document.getElementById('langMenu');m.style.display=m.style.display==='none'?'block':'none'}
function setLang(lang){
  currentLang=lang;document.getElementById('langMenu').style.display='none';
  document.documentElement.dir=lang==='en'?'ltr':'rtl';document.documentElement.lang=lang;
  applyI18n();
  if(currentPage==='tables')renderTables();if(currentPage==='menu'){renderCatTabs();renderMenu()}
  if(currentPage==='orders')renderOrders();if(currentPage==='gallery')renderGallery();if(currentPage==='admin')renderAdminOrders();
  updateNavPill();
}
function applyI18n(){document.querySelectorAll('[data-i18n]').forEach(el=>{el.textContent=t(el.getAttribute('data-i18n'))})}

// ===== ADMIN =====
function showAdminLogin(){if(adminLoggedIn){goTo('admin');return}document.getElementById('adminLoginModal').classList.add('show');document.getElementById('adminPassInput').value='';document.getElementById('adminError').style.display='none';setTimeout(()=>document.getElementById('adminPassInput').focus(),300)}
function closeAdminLogin(){document.getElementById('adminLoginModal').classList.remove('show')}
function tryAdminLogin(){
  if(document.getElementById('adminPassInput').value==='sayd'){adminLoggedIn=true;closeAdminLogin();goTo('admin')}
  else{document.getElementById('adminError').style.display='block';const inp=document.getElementById('adminPassInput');inp.style.animation='none';setTimeout(()=>{inp.style.animation='shake 0.4s ease'},10)}
}
const sh=document.createElement('style');sh.textContent='@keyframes shake{0%,100%{transform:translateX(0)}25%{transform:translateX(-8px)}75%{transform:translateX(8px)}}';document.head.appendChild(sh);
document.getElementById('adminPassInput').addEventListener('keydown',e=>{if(e.key==='Enter')tryAdminLogin()});

// ===== TOAST =====
function showToast(msg){const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');setTimeout(()=>t.classList.remove('show'),2500)}

// ===== CLOSE MENUS =====
document.addEventListener('click',e=>{const m=document.getElementById('langMenu');if(m.style.display==='block'&&!e.target.closest('.relative'))m.style.display='none'});

// ===== WELCOME 4 SECONDS =====
setTimeout(()=>{const s=document.getElementById('welcomeSplash');if(s){s.classList.add('hide');setTimeout(()=>s.remove(),700)}},4000);

// ===== INIT =====
renderTables();renderGallery();updateBadge();
setTimeout(updateNavPill,100);
window.addEventListener('resize',updateNavPill);
</script>
</body>
</html>
