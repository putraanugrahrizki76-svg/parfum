<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AURA — Parfum Intelligence 2026</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet" />
  <script src="https://unpkg.com/lucide@latest"></script>
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body { font-family: 'Inter', sans-serif; background: #050505; color: #fff; overflow-x: hidden; }

    ::-webkit-scrollbar { width: 4px; }
    ::-webkit-scrollbar-track { background: #0a0a0a; }
    ::-webkit-scrollbar-thumb { background: #333; border-radius: 4px; }

    .mesh-bg {
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
      background:
        radial-gradient(ellipse 600px 600px at 10% 20%, rgba(139,92,246,0.07), transparent),
        radial-gradient(ellipse 500px 500px at 80% 10%, rgba(6,182,212,0.05), transparent),
        radial-gradient(ellipse 700px 700px at 50% 80%, rgba(236,72,153,0.04), transparent),
        radial-gradient(ellipse 400px 400px at 90% 60%, rgba(59,130,246,0.05), transparent);
    }

    .gradient-text {
      background: linear-gradient(135deg, #818cf8, #c084fc, #f472b6, #22d3ee);
      -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
    }
    .gradient-text-gold {
      background: linear-gradient(135deg, #fbbf24, #f59e0b, #d97706);
      -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
    }
    .gradient-border { position: relative; }
    .gradient-border::before {
      content: ''; position: absolute; inset: 0; padding: 1px; border-radius: inherit;
      background: linear-gradient(135deg, rgba(139,92,246,0.3), rgba(6,182,212,0.2), rgba(244,114,182,0.2));
      -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
      -webkit-mask-composite: xor; mask-composite: exclude; pointer-events: none;
    }

    .glass {
      background: rgba(255,255,255,0.02);
      border: 1px solid rgba(255,255,255,0.06);
      backdrop-filter: blur(16px);
      border-radius: 16px;
      transition: all 300ms cubic-bezier(.4,0,.2,1);
    }
    .glass:hover { border-color: rgba(255,255,255,0.1); background: rgba(255,255,255,0.04); }
    .glass-strong {
      background: rgba(10,10,10,0.85);
      border: 1px solid rgba(255,255,255,0.08);
      backdrop-filter: blur(24px);
      border-radius: 16px;
    }

    .product-card {
      background: #080808; border: 1px solid rgba(255,255,255,0.04);
      border-radius: 20px; overflow: hidden;
      transition: all 400ms cubic-bezier(.4,0,.2,1);
    }
    .product-card:hover {
      border-color: rgba(139,92,246,0.3);
      transform: translateY(-6px);
      box-shadow: 0 20px 60px rgba(139,92,246,0.08), 0 0 0 1px rgba(139,92,246,0.1);
    }
    .product-card:hover .p-img { transform: scale(1.08); }
    .product-card:hover .p-overlay { opacity: 1; }
    .product-card:hover .p-quick { transform: translateY(0); opacity: 1; }
    .p-img { transition: transform 700ms cubic-bezier(.4,0,.2,1); }
    .p-overlay {
      opacity: 0; transition: opacity 300ms;
      background: linear-gradient(to top, rgba(0,0,0,0.85) 0%, transparent 60%);
    }
    .p-quick { transform: translateY(10px); opacity: 0; transition: all 300ms ease 100ms; }

    @keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-8px)} }
    @keyframes pulse-ring { 0%{transform:scale(1);opacity:.5} 100%{transform:scale(1.5);opacity:0} }
    @keyframes shimmer { 0%{background-position:-200% 0} 100%{background-position:200% 0} }
    @keyframes fade-up { from{opacity:0;transform:translateY(30px)} to{opacity:1;transform:translateY(0)} }
    @keyframes slide-in-right { from{opacity:0;transform:translateX(30px)} to{opacity:1;transform:translateX(0)} }

    .float { animation: float 5s ease-in-out infinite; }
    .fade-up { animation: fade-up 0.6s ease forwards; }
    .shimmer-bg {
      background: linear-gradient(90deg, transparent 0%, rgba(255,255,255,0.03) 50%, transparent 100%);
      background-size: 200% 100%; animation: shimmer 3s ease infinite;
    }

    .sidebar {
      position: fixed; top: 0; right: 0; bottom: 0; width: 480px; max-width: 100vw;
      z-index: 200; transform: translateX(100%);
      transition: transform 400ms cubic-bezier(.4,0,.2,1);
    }
    .sidebar.open { transform: translateX(0); }
    .sidebar-backdrop {
      position: fixed; inset: 0; background: rgba(0,0,0,0.6);
      backdrop-filter: blur(4px); z-index: 199;
      opacity: 0; pointer-events: none; transition: opacity 300ms;
    }
    .sidebar-backdrop.open { opacity: 1; pointer-events: all; }

    .modal {
      position: fixed; inset: 0; z-index: 300;
      display: flex; align-items: center; justify-content: center;
      opacity: 0; pointer-events: none; transition: opacity 300ms;
    }
    .modal.open { opacity: 1; pointer-events: all; }
    .modal-backdrop { position: absolute; inset: 0; background: rgba(0,0,0,0.7); backdrop-filter: blur(8px); }
    .modal-content {
      position: relative; z-index: 1;
      transform: scale(0.95) translateY(10px);
      transition: transform 300ms cubic-bezier(.4,0,.2,1);
    }
    .modal.open .modal-content { transform: scale(1) translateY(0); }

    .cat-pill {
      padding: 8px 20px; border-radius: 9999px; font-size: 12px; font-weight: 500;
      background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.06);
      color: #737373; cursor: pointer; transition: all 200ms; white-space: nowrap;
    }
    .cat-pill:hover, .cat-pill.active {
      background: rgba(139,92,246,0.1); border-color: rgba(139,92,246,0.3); color: #c4b5fd;
    }

    .input-field {
      width: 100%; background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.08);
      border-radius: 12px; padding: 12px 16px; color: #fff; font-size: 14px;
      font-family: 'Inter', sans-serif; font-weight: 300; outline: none;
      transition: border-color 200ms;
    }
    .input-field:focus { border-color: rgba(139,92,246,0.5); }
    .input-field::placeholder { color: #525252; }
    select.input-field { appearance: none; cursor: pointer; }
    textarea.input-field { resize: vertical; min-height: 80px; }

    .toast-container { position: fixed; bottom: 24px; right: 24px; z-index: 9999; display: flex; flex-direction: column; gap: 8px; }
    .toast-item {
      background: rgba(10,10,10,0.95); border: 1px solid rgba(255,255,255,0.1);
      backdrop-filter: blur(16px); border-radius: 14px; padding: 14px 20px;
      display: flex; align-items: center; gap: 10px; min-width: 280px;
      box-shadow: 0 8px 40px rgba(0,0,0,0.5);
      animation: slide-in-right 0.4s ease forwards;
    }
    .toast-item.removing { animation: fade-out 0.3s ease forwards; }
    @keyframes fade-out { to { opacity: 0; transform: translateX(30px); } }

    .badge-new {
      background: linear-gradient(135deg, #8b5cf6, #6366f1);
      font-size: 9px; font-weight: 600; padding: 4px 10px; border-radius: 9999px;
      text-transform: uppercase; letter-spacing: 0.05em;
    }
    .badge-hot {
      background: linear-gradient(135deg, #f472b6, #ec4899);
      font-size: 9px; font-weight: 600; padding: 4px 10px; border-radius: 9999px;
      text-transform: uppercase; letter-spacing: 0.05em;
    }
    .badge-limited {
      background: linear-gradient(135deg, #fbbf24, #f59e0b);
      color: #000; font-size: 9px; font-weight: 600; padding: 4px 10px; border-radius: 9999px;
      text-transform: uppercase; letter-spacing: 0.05em;
    }

    .stat-card {
      background: rgba(255,255,255,0.02); border: 1px solid rgba(255,255,255,0.06);
      border-radius: 16px; padding: 24px; position: relative; overflow: hidden;
    }
    .stat-card::after {
      content: ''; position: absolute; top: 0; right: 0; width: 80px; height: 80px;
      border-radius: 50%; filter: blur(40px); opacity: 0.15;
    }
    .stat-card.purple::after { background: #8b5cf6; }
    .stat-card.cyan::after { background: #06b6d4; }
    .stat-card.pink::after { background: #ec4899; }
    .stat-card.gold::after { background: #f59e0b; }

    .progress-bar { height: 4px; border-radius: 2px; background: rgba(255,255,255,0.06); overflow: hidden; }
    .progress-fill {
      height: 100%; border-radius: 2px;
      background: linear-gradient(90deg, #8b5cf6, #06b6d4);
      transition: width 600ms cubic-bezier(.4,0,.2,1);
    }

    @media (max-width: 768px) { .sidebar { width: 100vw; } }

    .nav-fixed {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      padding: 16px 24px; transition: all 300ms;
    }
    .nav-scrolled {
      background: rgba(5,5,5,0.85); backdrop-filter: blur(20px);
      border-bottom: 1px solid rgba(255,255,255,0.05);
    }

    .reveal { opacity: 0; transform: translateY(30px); transition: all 0.7s cubic-bezier(.4,0,.2,1); }
    .reveal.visible { opacity: 1; transform: translateY(0); }
  </style>
</head>
<body>

<div class="mesh-bg"></div>

<!-- ====== TOAST CONTAINER ====== -->
<div id="toastContainer" class="toast-container"></div>

<!-- ====== NAVBAR ====== -->
<nav id="mainNav" class="nav-fixed">
  <div class="max-w-7xl mx-auto flex items-center justify-between">
    <a href="#" class="flex items-center gap-2">
      <div class="w-8 h-8 rounded-lg bg-gradient-to-br from-violet-500 to-cyan-400 flex items-center justify-center">
        <i data-lucide="sparkles" class="w-4 h-4 text-white"></i>
      </div>
      <span class="text-lg font-semibold tracking-tight">AURA</span>
    </a>
    <div class="hidden md:flex items-center gap-1">
      <a href="#katalog" class="px-4 py-2 text-xs font-medium text-neutral-400 hover:text-white rounded-lg hover:bg-white/5 transition-all">Katalog</a>
      <a href="#dashboard" class="px-4 py-2 text-xs font-medium text-neutral-400 hover:text-white rounded-lg hover:bg-white/5 transition-all">Dashboard</a>
      <a href="#keunggulan" class="px-4 py-2 text-xs font-medium text-neutral-400 hover:text-white rounded-lg hover:bg-white/5 transition-all">Keunggulan</a>
      <a href="#testimoni" class="px-4 py-2 text-xs font-medium text-neutral-400 hover:text-white rounded-lg hover:bg-white/5 transition-all">Testimoni</a>
    </div>
    <div class="flex items-center gap-2">
      <button onclick="openSidebar('cartSidebar')" class="relative p-2.5 rounded-xl hover:bg-white/5 transition-colors">
        <i data-lucide="shopping-bag" class="w-5 h-5 text-neutral-300"></i>
        <span id="cartCount" class="hidden absolute -top-0.5 -right-0.5 w-5 h-5 bg-gradient-to-r from-violet-500 to-pink-500 rounded-full text-[10px] font-semibold flex items-center justify-center">0</span>
      </button>
      <button onclick="openSidebar('addProductSidebar')" class="hidden md:flex items-center gap-2 bg-gradient-to-r from-violet-600 to-indigo-600 text-white text-xs font-medium px-5 py-2.5 rounded-xl hover:from-violet-500 hover:to-indigo-500 transition-all">
        <i data-lucide="plus" class="w-4 h-4"></i>
        Tambah Produk
      </button>
      <button onclick="openMobileMenu()" class="md:hidden p-2.5 rounded-xl hover:bg-white/5 transition-colors">
        <i data-lucide="menu" class="w-5 h-5"></i>
      </button>
    </div>
  </div>
</nav>

<!-- ====== MOBILE MENU ====== -->
<div id="mobileMenu" class="modal">
  <div class="modal-backdrop" onclick="closeMobileMenu()"></div>
  <div class="modal-content glass-strong p-8 mx-4 w-full max-w-sm">
    <div class="flex items-center justify-between mb-8">
      <span class="text-lg font-semibold">Menu</span>
      <button onclick="closeMobileMenu()" class="p-2 rounded-xl hover:bg-white/5 transition-colors"><i data-lucide="x" class="w-5 h-5"></i></button>
    </div>
    <div class="flex flex-col gap-2">
      <a href="#katalog" onclick="closeMobileMenu()" class="px-4 py-3 text-sm font-medium text-neutral-300 hover:text-white rounded-xl hover:bg-white/5 transition-all">Katalog</a>
      <a href="#dashboard" onclick="closeMobileMenu()" class="px-4 py-3 text-sm font-medium text-neutral-300 hover:text-white rounded-xl hover:bg-white/5 transition-all">Dashboard</a>
      <a href="#keunggulan" onclick="closeMobileMenu()" class="px-4 py-3 text-sm font-medium text-neutral-300 hover:text-white rounded-xl hover:bg-white/5 transition-all">Keunggulan</a>
      <a href="#testimoni" onclick="closeMobileMenu()" class="px-4 py-3 text-sm font-medium text-neutral-300 hover:text-white rounded-xl hover:bg-white/5 transition-all">Testimoni</a>
      <hr class="border-white/5 my-2" />
      <button onclick="closeMobileMenu();openSidebar('addProductSidebar')" class="flex items-center justify-center gap-2 bg-gradient-to-r from-violet-600 to-indigo-600 text-white text-sm font-medium px-5 py-3 rounded-xl">
        <i data-lucide="plus" class="w-4 h-4"></i>
        Tambah Produk
      </button>
    </div>
  </div>
</div>

<!-- ====== ADD PRODUCT SIDEBAR ====== -->
<div id="addProductSidebar" class="sidebar">
  <div class="h-full glass-strong flex flex-col" style="border-radius:0;border-right:none;">
    <div class="p-6 border-b border-white/5 flex items-center justify-between">
      <div>
        <h3 class="text-lg font-semibold" id="formTitle">Tambah Produk</h3>
        <p class="text-xs text-neutral-500 mt-1">Isi detail produk parfum baru</p>
      </div>
      <button onclick="closeSidebar('addProductSidebar')" class="p-2 rounded-xl hover:bg-white/5 transition-colors"><i data-lucide="x" class="w-5 h-5"></i></button>
    </div>
    <div class="flex-1 overflow-y-auto p-6">
      <form id="productForm" onsubmit="handleProductSubmit(event)" class="space-y-5">
        <input type="hidden" id="editId" value="" />
        <div>
          <label class="text-xs font-medium text-neutral-400 mb-2 block">Nama Produk *</label>
          <input type="text" id="pName" class="input-field" placeholder="Contoh: Oud Royal" required />
        </div>
        <div class="grid grid-cols-2 gap-4">
          <div>
            <label class="text-xs font-medium text-neutral-400 mb-2 block">Harga (Rp) *</label>
            <input type="number" id="pPrice" class="input-field" placeholder="485000" required min="0" />
          </div>
          <div>
            <label class="text-xs font-medium text-neutral-400 mb-2 block">Stok *</label>
            <input type="number" id="pStock" class="input-field" placeholder="50" required min="0" />
          </div>
        </div>
        <div class="grid grid-cols-2 gap-4">
          <div>
            <label class="text-xs font-medium text-neutral-400 mb-2 block">Kategori *</label>
            <select id="pCategory" class="input-field" required>
              <option value="">Pilih</option>
              <option value="woody">Woody</option>
              <option value="floral">Floral</option>
              <option value="fresh">Fresh</option>
              <option value="oriental">Oriental</option>
              <option value="aquatic">Aquatic</option>
            </select>
          </div>
          <div>
            <label class="text-xs font-medium text-neutral-400 mb-2 block">Gender</label>
            <select id="pGender" class="input-field">
              <option value="unisex">Unisex</option>
              <option value="men">Men</option>
              <option value="women">Women</option>
            </select>
          </div>
        </div>
        <div>
          <label class="text-xs font-medium text-neutral-400 mb-2 block">Ukuran (ml)</label>
          <input type="text" id="pSize" class="input-field" placeholder="100ml" />
        </div>
        <div>
          <label class="text-xs font-medium text-neutral-400 mb-2 block">Deskripsi</label>
          <textarea id="pDesc" class="input-field" placeholder="Deskripsi singkat aroma parfum..."></textarea>
        </div>
        <div>
          <label class="text-xs font-medium text-neutral-400 mb-2 block">URL Gambar</label>
          <input type="url" id="pImage" class="input-field" placeholder="https://picsum.photos/seed/xxx/600/800.jpg" />
          <p class="text-[10px] text-neutral-600 mt-1">Kosongkan untuk gambar otomatis</p>
        </div>
        <div>
          <label class="text-xs font-medium text-neutral-400 mb-2 block">Tag</label>
          <div class="flex flex-wrap gap-2">
            <label class="flex items-center gap-1.5 px-3 py-1.5 rounded-lg bg-white/3 border border-white/6 cursor-pointer hover:bg-white/5 transition-colors">
              <input type="checkbox" id="tagNew" class="accent-violet-500 w-3 h-3" /> <span class="text-xs text-neutral-400">New</span>
            </label>
            <label class="flex items-center gap-1.5 px-3 py-1.5 rounded-lg bg-white/3 border border-white/6 cursor-pointer hover:bg-white/5 transition-colors">
              <input type="checkbox" id="tagHot" class="accent-pink-500 w-3 h-3" /> <span class="text-xs text-neutral-400">Bestseller</span>
            </label>
            <label class="flex items-center gap-1.5 px-3 py-1.5 rounded-lg bg-white/3 border border-white/6 cursor-pointer hover:bg-white/5 transition-colors">
              <input type="checkbox" id="tagLimited" class="accent-amber-500 w-3 h-3" /> <span class="text-xs text-neutral-400">Limited</span>
            </label>
          </div>
        </div>
        <div class="pt-4">
          <button type="submit" class="w-full bg-gradient-to-r from-violet-600 to-indigo-600 text-white text-sm font-medium py-3.5 rounded-xl hover:from-violet-500 hover:to-indigo-500 transition-all flex items-center justify-center gap-2">
            <i data-lucide="save" class="w-4 h-4"></i>
            <span id="submitBtnText">Simpan Produk</span>
          </button>
        </div>
      </form>
    </div>
  </div>
</div>
<div id="addProductBackdrop" class="sidebar-backdrop" onclick="closeSidebar('addProductSidebar')"></div>

<!-- ====== CART SIDEBAR ====== -->
<div id="cartSidebar" class="sidebar">
  <div class="h-full glass-strong flex flex-col" style="border-radius:0;border-right:none;">
    <div class="p-6 border-b border-white/5 flex items-center justify-between">
      <div>
        <h3 class="text-lg font-semibold">Keranjang</h3>
        <p class="text-xs text-neutral-500 mt-1" id="cartItemCount">0 item</p>
      </div>
      <button onclick="closeSidebar('cartSidebar')" class="p-2 rounded-xl hover:bg-white/5 transition-colors"><i data-lucide="x" class="w-5 h-5"></i></button>
    </div>
    <div id="cartItems" class="flex-1 overflow-y-auto p-6">
      <div id="cartEmpty" class="flex flex-col items-center justify-center h-full text-center">
        <div class="w-16 h-16 rounded-2xl bg-white/3 border border-white/6 flex items-center justify-center mb-4">
          <i data-lucide="shopping-bag" class="w-7 h-7 text-neutral-600"></i>
        </div>
        <p class="text-sm text-neutral-500">Keranjang masih kosong</p>
        <p class="text-xs text-neutral-600 mt-1">Tambahkan produk dari katalog</p>
      </div>
      <div id="cartList" class="space-y-4 hidden"></div>
    </div>
    <div id="cartFooter" class="p-6 border-t border-white/5 hidden">
      <div class="flex items-center justify-between mb-2">
        <span class="text-sm text-neutral-400">Subtotal</span>
        <span class="text-sm font-medium" id="cartSubtotal">Rp 0</span>
      </div>
      <div class="flex items-center justify-between mb-4">
        <span class="text-sm text-neutral-400">Ongkir</span>
        <span class="text-sm font-medium text-green-400">GRATIS</span>
      </div>
      <div class="flex items-center justify-between mb-6 pt-3 border-t border-white/5">
        <span class="text-base font-semibold">Total</span>
        <span class="text-base font-semibold gradient-text-gold" id="cartTotal">Rp 0</span>
      </div>
      <button onclick="handleCheckout()" class="w-full bg-gradient-to-r from-violet-600 to-indigo-600 text-white text-sm font-medium py-3.5 rounded-xl hover:from-violet-500 hover:to-indigo-500 transition-all flex items-center justify-center gap-2">
        <i data-lucide="credit-card" class="w-4 h-4"></i>
        Checkout Sekarang
      </button>
    </div>
  </div>
</div>
<div id="cartBackdrop" class="sidebar-backdrop" onclick="closeSidebar('cartSidebar')"></div>

<!-- ====== DELETE CONFIRM MODAL ====== -->
<div id="deleteModal" class="modal">
  <div class="modal-backdrop" onclick="closeDeleteModal()"></div>
  <div class="modal-content glass-strong p-8 mx-4 w-full max-w-sm text-center">
    <div class="w-14 h-14 rounded-2xl bg-red-500/10 border border-red-500/20 flex items-center justify-center mx-auto mb-5">
      <i data-lucide="trash-2" class="w-6 h-6 text-red-400"></i>
    </div>
    <h3 class="text-lg font-semibold mb-2">Hapus Produk?</h3>
    <p class="text-sm text-neutral-400 font-light mb-6" id="deleteMsg">Produk ini akan dihapus secara permanen.</p>
    <div class="flex gap-3">
      <button onclick="closeDeleteModal()" class="flex-1 py-3 rounded-xl border border-white/10 text-sm font-medium hover:bg-white/5 transition-colors">Batal</button>
      <button onclick="confirmDelete()" class="flex-1 py-3 rounded-xl bg-red-500 text-sm font-medium hover:bg-red-600 transition-colors">Hapus</button>
    </div>
  </div>
</div>

<!-- ====== HERO SECTION ====== -->
<section class="relative min-h-screen flex items-center justify-center overflow-hidden pt-20">
  <div class="absolute inset-0">
    <img src="https://picsum.photos/seed/aura-perfume-hero-2026/1920/1080.jpg" alt="" class="w-full h-full object-cover opacity-30" />
    <div class="absolute inset-0 bg-gradient-to-b from-[#050505] via-[#050505]/60 to-[#050505]"></div>
  </div>
  <div class="relative z-10 text-center px-6 max-w-5xl mx-auto">
    <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full border border-violet-500/20 bg-violet-500/5 mb-8 fade-up">
      <span class="relative flex h-2 w-2">
        <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-violet-400 opacity-75"></span>
        <span class="relative inline-flex rounded-full h-2 w-2 bg-violet-400"></span>
      </span>
      <span class="text-[11px] font-mono tracking-[0.2em] uppercase text-violet-300">Platform Penjualan 2026</span>
    </div>
    <h1 class="text-5xl md:text-7xl lg:text-[5.5rem] font-semibold tracking-tight leading-[1.05] fade-up" style="animation-delay:0.1s">
      Kelola Parfum,<br/>
      <span class="gradient-text">Maksimalkan Cuan</span>
    </h1>
    <p class="mt-7 text-base md:text-lg font-light text-neutral-400 max-w-2xl mx-auto leading-relaxed fade-up" style="animation-delay:0.2s">
      Satu platform untuk menambah produk, mengelola stok, menerima pesanan, dan menganalisis penjualan parfum Anda secara real-time.
    </p>
    <div class="mt-10 flex flex-col sm:flex-row items-center justify-center gap-4 fade-up" style="animation-delay:0.3s">
      <button onclick="openSidebar('addProductSidebar')" class="bg-gradient-to-r from-violet-600 to-indigo-600 text-white text-sm font-medium px-8 py-3.5 rounded-xl hover:from-violet-500 hover:to-indigo-500 transition-all flex items-center gap-2">
        <i data-lucide="plus" class="w-4 h-4"></i>
        Tambah Produk Baru
      </button>
      <a href="#katalog" class="border border-white/10 text-white text-sm font-medium px-8 py-3.5 rounded-xl hover:bg-white/5 transition-all flex items-center gap-2">
        <i data-lucide="eye" class="w-4 h-4"></i>
        Lihat Katalog
      </a>
    </div>
    <div class="mt-20 grid grid-cols-2 md:grid-cols-4 gap-4 max-w-3xl mx-auto fade-up" style="animation-delay:0.4s">
      <div class="glass p-5 text-center">
        <p class="text-2xl font-semibold" id="heroProductCount">0</p>
        <p class="text-[10px] font-mono tracking-widest uppercase text-neutral-500 mt-1">Produk</p>
      </div>
      <div class="glass p-5 text-center">
        <p class="text-2xl font-semibold" id="heroSalesCount">0</p>
        <p class="text-[10px] font-mono tracking-widest uppercase text-neutral-500 mt-1">Terjual</p>
      </div>
      <div class="glass p-5 text-center">
        <p class="text-2xl font-semibold gradient-text-gold" id="heroRevenue">Rp 0</p>
        <p class="text-[10px] font-mono tracking-widest uppercase text-neutral-500 mt-1">Revenue</p>
      </div>
      <div class="glass p-5 text-center">
        <p class="text-2xl font-semibold">4.9<span class="text-amber-400">★</span></p>
        <p class="text-[10px] font-mono tracking-widest uppercase text-neutral-500 mt-1">Rating</p>
      </div>
    </div>
  </div>
  <div class="absolute bottom-8 left-1/2 -translate-x-1/2 float">
    <i data-lucide="chevrons-down" class="w-5 h-5 text-neutral-600"></i>
  </div>
</section>

<!-- ====== DASHBOARD ====== -->
<section id="dashboard" class="relative py-24 md:py-32">
  <div class="max-w-7xl mx-auto px-6 lg:px-12">
    <div class="reveal mb-12">
      <p class="text-[11px] font-mono tracking-[0.2em] uppercase text-violet-400 mb-3">Dashboard Penjualan</p>
      <h2 class="text-3xl md:text-4xl font-semibold tracking-tight">Ringkasan <span class="gradient-text">Bisnis</span></h2>
    </div>
    <div class="grid grid-cols-2 lg:grid-cols-4 gap-4 mb-8">
      <div class="stat-card purple reveal">
        <div class="flex items-center gap-2 mb-3">
          <div class="w-8 h-8 rounded-lg bg-violet-500/10 flex items-center justify-center"><i data-lucide="package" class="w-4 h-4 text-violet-400"></i></div>
          <span class="text-[10px] font-mono tracking-wider uppercase text-neutral-500">Total Produk</span>
        </div>
        <p class="text-2xl font-semibold" id="statProducts">0</p>
        <div class="progress-bar mt-3"><div class="progress-fill" id="progProducts" style="width:0%"></div></div>
      </div>
      <div class="stat-card cyan reveal">
        <div class="flex items-center gap-2 mb-3">
          <div class="w-8 h-8 rounded-lg bg-cyan-500/10 flex items-center justify-center"><i data-lucide="trending-up" class="w-4 h-4 text-cyan-400"></i></div>
          <span class="text-[10px] font-mono tracking-wider uppercase text-neutral-500">Total Terjual</span>
        </div>
        <p class="text-2xl font-semibold" id="statSold">0</p>
        <div class="progress-bar mt-3"><div class="progress-fill" id="progSold" style="width:0%"></div></div>
      </div>
      <div class="stat-card pink reveal">
        <div class="flex items-center gap-2 mb-3">
          <div class="w-8 h-8 rounded-lg bg-pink-500/10 flex items-center justify-center"><i data-lucide="wallet" class="w-4 h-4 text-pink-400"></i></div>
          <span class="text-[10px] font-mono tracking-wider uppercase text-neutral-500">Revenue</span>
        </div>
        <p class="text-2xl font-semibold" id="statRevenue">Rp 0</p>
        <div class="progress-bar mt-3"><div class="progress-fill" id="progRevenue" style="width:0%"></div></div>
      </div>
      <div class="stat-card gold reveal">
        <div class="flex items-center gap-2 mb-3">
          <div class="w-8 h-8 rounded-lg bg-amber-500/10 flex items-center justify-center"><i data-lucide="alert-triangle" class="w-4 h-4 text-amber-400"></i></div>
          <span class="text-[10px] font-mono tracking-wider uppercase text-neutral-500">Stok Rendah</span>
        </div>
        <p class="text-2xl font-semibold" id="statLowStock">0</p>
        <div class="progress-bar mt-3"><div class="progress-fill" style="width:30%;background:linear-gradient(90deg,#f59e0b,#ef4444)"></div></div>
      </div>
    </div>
    <div class="glass p-6 reveal">
      <div class="flex items-center justify-between mb-5">
        <h3 class="text-sm font-semibold">Penjualan Terbaru</h3>
        <span class="text-[10px] font-mono tracking-wider text-neutral-500 uppercase" id="salesCountLabel">0 transaksi</span>
      </div>
      <div id="recentSalesList" class="space-y-3">
        <p class="text-sm text-neutral-600 text-center py-8">Belum ada penjualan</p>
      </div>
    </div>
  </div>
</section>

<!-- ====== KATALOG ====== -->
<section id="katalog" class="relative py-24 md:py-32 bg-[#030303]">
  <div class="max-w-7xl mx-auto px-6 lg:px-12">
    <div class="reveal mb-10">
      <div class="flex flex-col md:flex-row md:items-end md:justify-between gap-6">
        <div>
          <p class="text-[11px] font-mono tracking-[0.2em] uppercase text-violet-400 mb-3">Katalog</p>
          <h2 class="text-3xl md:text-4xl font-semibold tracking-tight">Koleksi <span class="gradient-text">Parfum</span></h2>
        </div>
        <button onclick="openSidebar('addProductSidebar')" class="flex items-center gap-2 bg-gradient-to-r from-violet-600 to-indigo-600 text-white text-xs font-medium px-6 py-3 rounded-xl hover:from-violet-500 hover:to-indigo-500 transition-all shrink-0">
          <i data-lucide="plus" class="w-4 h-4"></i>
          Tambah Produk
        </button>
      </div>
    </div>
    <div class="flex flex-wrap gap-2 mb-10 reveal">
      <button class="cat-pill active" onclick="filterProducts(this,'all')">Semua</button>
      <button class="cat-pill" onclick="filterProducts(this,'woody')">Woody</button>
      <button class="cat-pill" onclick="filterProducts(this,'floral')">Floral</button>
      <button class="cat-pill" onclick="filterProducts(this,'fresh')">Fresh</button>
      <button class="cat-pill" onclick="filterProducts(this,'oriental')">Oriental</button>
      <button class="cat-pill" onclick="filterProducts(this,'aquatic')">Aquatic</button>
    </div>
    <div id="productGrid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6"></div>
    <div id="emptyCatalog" class="hidden text-center py-20">
      <div class="w-20 h-20 rounded-2xl bg-white/3 border border-white/6 flex items-center justify-center mx-auto mb-5">
        <i data-lucide="package-open" class="w-8 h-8 text-neutral-600"></i>
      </div>
      <p class="text-neutral-400 font-medium">Katalog masih kosong</p>
      <p class="text-sm text-neutral-600 mt-1 mb-6">Tambahkan produk pertama Anda untuk memulai</p>
      <button onclick="openSidebar('addProductSidebar')" class="bg-gradient-to-r from-violet-600 to-indigo-600 text-white text-sm font-medium px-6 py-3 rounded-xl inline-flex items-center gap-2">
        <i data-lucide="plus" class="w-4 h-4"></i>
        Tambah Produk
      </button>
    </div>
  </div>
</section>

<!-- ====== KEUNGGULAN ====== -->
<section id="keunggulan" class="relative py-24 md:py-32">
  <div class="max-w-7xl mx-auto px-6 lg:px-12">
    <div class="reveal text-center mb-16">
      <p class="text-[11px] font-mono tracking-[0.2em] uppercase text-violet-400 mb-3">Kenapa AURA</p>
      <h2 class="text-3xl md:text-4xl font-semibold tracking-tight">Fitur <span class="gradient-text">Unggulan</span></h2>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
      <div class="glass p-7 reveal gradient-border">
        <div class="w-10 h-10 rounded-xl bg-violet-500/10 flex items-center justify-center mb-5"><i data-lucide="zap" class="w-5 h-5 text-violet-400"></i></div>
        <h3 class="text-base font-semibold mb-2">Tambah Produk Instan</h3>
        <p class="text-sm font-light text-neutral-400 leading-relaxed">Tambah produk baru dalam hitungan detik. Form lengkap dengan kategori, harga, stok, dan tag.</p>
      </div>
      <div class="glass p-7 reveal gradient-border">
        <div class="w-10 h-10 rounded-xl bg-cyan-500/10 flex items-center justify-center mb-5"><i data-lucide="bar-chart-3" class="w-5 h-5 text-cyan-400"></i></div>
        <h3 class="text-base font-semibold mb-2">Dashboard Real-time</h3>
        <p class="text-sm font-light text-neutral-400 leading-relaxed">Pantau revenue, stok, dan penjualan secara real-time. Data selalu up-to-date.</p>
      </div>
      <div class="glass p-7 reveal gradient-border">
        <div class="w-10 h-10 rounded-xl bg-pink-500/10 flex items-center justify-center mb-5"><i data-lucide="shopping-cart" class="w-5 h-5 text-pink-400"></i></div>
        <h3 class="text-base font-semibold mb-2">Keranjang & Checkout</h3>
        <p class="text-sm font-light text-neutral-400 leading-relaxed">Sistem keranjang belanja terintegrasi dengan perhitungan otomatis dan checkout mudah.</p>
      </div>
      <div class="glass p-7 reveal gradient-border">
        <div class="w-10 h-10 rounded-xl bg-amber-500/10 flex items-center justify-center mb-5"><i data-lucide="pencil" class="w-5 h-5 text-amber-400"></i></div>
        <h3 class="text-base font-semibold mb-2">Edit & Hapus Produk</h3>
        <p class="text-sm font-light text-neutral-400 leading-relaxed">Kelola katalog dengan mudah. Edit detail atau hapus produk yang tidak lagi tersedia.</p>
      </div>
      <div class="glass p-7 reveal gradient-border">
        <div class="w-10 h-10 rounded-xl bg-green-500/10 flex items-center justify-center mb-5"><i data-lucide="filter" class="w-5 h-5 text-green-400"></i></div>
        <h3 class="text-base font-semibold mb-2">Filter Kategori</h3>
        <p class="text-sm font-light text-neutral-400 leading-relaxed">Filter produk berdasarkan kategori aroma. Tampilkan hanya yang Anda cari.</p>
      </div>
      <div class="glass p-7 reveal gradient-border">
        <div class="w-10 h-10 rounded-xl bg-red-500/10 flex items-center justify-center mb-5"><i data-lucide="alert-triangle" class="w-5 h-5 text-red-400"></i></div>
        <h3 class="text-base font-semibold mb-2">Peringatan Stok</h3>
        <p class="text-sm font-light text-neutral-400 leading-relaxed">Deteksi otomatis produk dengan stok rendah agar Anda tidak kehabisan barang.</p>
      </div>
    </div>
  </div>
</section>

<!-- ====== TESTIMONI ====== -->
<section id="testimoni" class="relative py-24 md:py-32 bg-[#030303]">
  <div class="max-w-7xl mx-auto px-6 lg:px-12">
    <div class="reveal text-center mb-16">
      <p class="text-[11px] font-mono tracking-[0.2em] uppercase text-violet-400 mb-3">Testimoni</p>
      <h2 class="text-3xl md:text-4xl font-semibold tracking-tight">Dipercaya <span class="gradient-text">Seller Parfum</span></h2>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-5">
      <div class="glass p-7 reveal">
        <div class="flex gap-0.5 mb-4">
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
        </div>
        <p class="text-sm font-light text-neutral-300 leading-relaxed mb-6">"AURA benar-benar mengubah cara saya jualan parfum online. Dashboard-nya super intuitif, tambah produk tinggal klik. Revenue naik 3x dalam 2 bulan!"</p>
        <div class="flex items-center gap-3">
          <img src="https://picsum.photos/seed/seller-rina/80/80.jpg" class="w-9 h-9 rounded-full object-cover border border-white/10" alt="" />
          <div>
            <p class="text-sm font-medium">Rina Kusuma</p>
            <p class="text-[11px] text-neutral-500">Owner, ScentHouse</p>
          </div>
        </div>
      </div>
      <div class="glass p-7 reveal">
        <div class="flex gap-0.5 mb-4">
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
        </div>
        <p class="text-sm font-light text-neutral-300 leading-relaxed mb-6">"Fitur manajemen stok dan peringatan stok rendah sangat membantu. Saya tidak pernah lagi kehabisan produk bestseller. Wajib punya untuk seller parfum!"</p>
        <div class="flex items-center gap-3">
          <img src="https://picsum.photos/seed/seller-arman/80/80.jpg" class="w-9 h-9 rounded-full object-cover border border-white/10" alt="" />
          <div>
            <p class="text-sm font-medium">Arman Hakim</p>
            <p class="text-[11px] text-neutral-500">Founder, OudGallery</p>
          </div>
        </div>
      </div>
      <div class="glass p-7 reveal">
        <div class="flex gap-0.5 mb-4">
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
          <i data-lucide="star" class="w-4 h-4 text-amber-400 fill-amber-400"></i>
        </div>
        <p class="text-sm font-light text-neutral-300 leading-relaxed mb-6">"Desain katalognya premium banget. Customer langsung ketarik lihat produknya. Checkout process juga smooth, conversion rate naik drastis."</p>
        <div class="flex items-center gap-3">
          <img src="https://picsum.photos/seed/seller-dela/80/80.jpg" class="w-9 h-9 rounded-full object-cover border border-white/10" alt="" />
          <div>
            <p class="text-sm font-medium">Dela Putri</p>
            <p class="text-[11px] text-neutral-500">CEO, AromaCo</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ====== CTA ====== -->
<section class="relative py-24 md:py-32 overflow-hidden">
  <div class="absolute inset-0">
    <img src="https://picsum.photos/seed/aura-cta-2026/1920/800.jpg" alt="" class="w-full h-full object-cover opacity-15" />
    <div class="absolute inset-0 bg-gradient-to-b from-[#050505] via-transparent to-[#050505]"></div>
  </div>
  <div class="relative z-10 max-w-2xl mx-auto text-center px-6 reveal">
    <h2 class="text-3xl md:text-5xl font-semibold tracking-tight">Mulai Jualan<br/><span class="gradient-text">Sekarang</span></h2>
    <p class="mt-5 text-base font-light text-neutral-400 leading-relaxed">Tambahkan produk pertama Anda dan lihat sendiri bagaimana AURA mempermudah penjualan parfum Anda.</p>
    <button onclick="openSidebar('addProductSidebar')" class="mt-8 bg-gradient-to-r from-violet-600 to-indigo-600 text-white text-sm font-medium px-10 py-4 rounded-xl hover:from-violet-500 hover:to-indigo-500 transition-all inline-flex items-center gap-2">
      <i data-lucide="plus" class="w-5 h-5"></i>
      Tambah Produk Pertama
    </button>
  </div>
</section>

<!-- ====== FOOTER ====== -->
<footer class="border-t border-white/5 bg-[#030303]">
  <div class="max-w-7xl mx-auto px-6 lg:px-12 py-12">
    <div class="flex flex-col md:flex-row items-center justify-between gap-4">
      <div class="flex items-center gap-2">
        <div class="w-7 h-7 rounded-lg bg-gradient-to-br from-violet-500 to-cyan-400 flex items-center justify-center">
          <i data-lucide="sparkles" class="w-3.5 h-3.5 text-white"></i>
        </div>
        <span class="text-sm font-semibold tracking-tight">AURA</span>
        <span class="text-xs text-neutral-600 ml-2">© 2026</span>
      </div>
      <p class="text-xs text-neutral-600 font-light">Made with ♥ for perfume sellers everywhere</p>
    </div>
  </div>
</footer>

<!-- ==================== JAVASCRIPT ==================== -->
<script>
  lucide.createIcons();

  // ====== DATA — KATALOG KOSONG ======
  let products = [];
  let cart = [];
  let sales = [];
  let nextId = 1;
  let currentFilter = 'all';
  let deleteTargetId = null;

  // ====== TOAST ======
  function toast(msg, type = 'success') {
    const container = document.getElementById('toastContainer');
    const iconMap = { success: 'check-circle', error: 'x-circle', info: 'info' };
    const colorMap = { success: 'text-green-400', error: 'text-red-400', info: 'text-blue-400' };
    const el = document.createElement('div');
    el.className = 'toast-item';
    el.innerHTML = `<i data-lucide="${iconMap[type]}" class="w-5 h-5 ${colorMap[type]} shrink-0"></i><span class="text-sm font-light text-neutral-300">${msg}</span>`;
    container.appendChild(el);
    lucide.createIcons({ nodes: [el] });
    setTimeout(() => { el.classList.add('removing'); setTimeout(() => el.remove(), 300); }, 3500);
  }

  // ====== SIDEBAR ======
  function openSidebar(id) {
    document.getElementById(id).classList.add('open');
    document.getElementById(id + 'Backdrop').classList.add('open');
    document.body.style.overflow = 'hidden';
    if (id === 'cartSidebar') renderCart();
  }
  function closeSidebar(id) {
    document.getElementById(id).classList.remove('open');
    document.getElementById(id + 'Backdrop').classList.remove('open');
    document.body.style.overflow = '';
    if (id === 'addProductSidebar') resetForm();
  }

  // ====== MOBILE MENU ======
  function openMobileMenu() { document.getElementById('mobileMenu').classList.add('open'); document.body.style.overflow = 'hidden'; }
  function closeMobileMenu() { document.getElementById('mobileMenu').classList.remove('open'); document.body.style.overflow = ''; }

  // ====== FORMAT ======
  function fmt(n) { return 'Rp ' + n.toLocaleString('id-ID'); }
  function catLabel(c) { return { woody:'Woody', floral:'Floral', fresh:'Fresh', oriental:'Oriental', aquatic:'Aquatic' }[c] || c; }
  function genderLabel(g) { return { unisex:'Unisex', men:'Men', women:'Women' }[g] || g; }

  // ====== RENDER PRODUCTS ======
  function renderProducts() {
    const grid = document.getElementById('productGrid');
    const empty = document.getElementById('emptyCatalog');
    let filtered = currentFilter === 'all' ? products : products.filter(p => p.category === currentFilter);

    if (filtered.length === 0) {
      grid.innerHTML = '';
      empty.classList.remove('hidden');
      lucide.createIcons();
      return;
    }
    empty.classList.add('hidden');

    grid.innerHTML = filtered.map((p, i) => {
      const lowStock = p.stock <= 10 && p.stock > 0;
      const outOfStock = p.stock === 0;
      const tagHtml = p.tags.map(t => {
        if (t === 'new') return '<span class="badge-new">New</span>';
        if (t === 'hot') return '<span class="badge-hot">Bestseller</span>';
        if (t === 'limited') return '<span class="badge-limited">Limited</span>';
        return '';
      }).join(' ');

      return `
        <div class="product-card" data-id="${p.id}" style="animation: fade-up 0.5s ease ${i * 50}ms forwards; opacity: 0;">
          <div class="relative aspect-[3/4] overflow-hidden">
            <img src="${p.image}" alt="${p.name}" class="p-img w-full h-full object-cover ${outOfStock ? 'opacity-40' : ''}" loading="lazy" />
            <div class="p-overlay absolute inset-0 flex items-end p-4">
              <div class="p-quick w-full space-y-2">
                <button onclick="addToCart(${p.id})" ${outOfStock ? 'disabled' : ''}
                  class="w-full ${outOfStock ? 'bg-neutral-700 text-neutral-400 cursor-not-allowed' : 'bg-white text-black hover:bg-neutral-200'} text-xs font-medium py-2.5 rounded-full transition-colors flex items-center justify-center gap-1.5">
                  <i data-lucide="${outOfStock ? 'ban' : 'shopping-bag'}" class="w-3.5 h-3.5"></i>
                  ${outOfStock ? 'Habis' : 'Tambah ke Keranjang'}
                </button>
                <div class="flex gap-2">
                  <button onclick="editProduct(${p.id})" class="flex-1 py-2 rounded-full border border-white/20 text-xs font-medium hover:bg-white/10 transition-colors flex items-center justify-center gap-1">
                    <i data-lucide="pencil" class="w-3 h-3"></i> Edit
                  </button>
                  <button onclick="deleteProduct(${p.id})" class="flex-1 py-2 rounded-full border border-red-500/30 text-red-400 text-xs font-medium hover:bg-red-500/10 transition-colors flex items-center justify-center gap-1">
                    <i data-lucide="trash-2" class="w-3 h-3"></i> Hapus
                  </button>
                </div>
              </div>
            </div>
            ${tagHtml ? `<div class="absolute top-3 left-3 flex gap-1.5">${tagHtml}</div>` : ''}
            ${lowStock && !outOfStock ? '<div class="absolute top-3 right-3 bg-amber-500/90 text-black text-[9px] font-semibold px-2.5 py-1 rounded-full uppercase tracking-wider">Stok Rendah</div>' : ''}
            ${outOfStock ? '<div class="absolute top-3 right-3 bg-red-500/90 text-white text-[9px] font-semibold px-2.5 py-1 rounded-full uppercase tracking-wider">Habis</div>' : ''}
          </div>
          <div class="p-5">
            <p class="text-[10px] font-mono tracking-widest uppercase text-neutral-500 mb-1.5">${catLabel(p.category)} · ${genderLabel(p.gender)}${p.size ? ' · ' + p.size : ''}</p>
            <h3 class="text-base font-semibold">${p.name}</h3>
            <p class="text-xs text-neutral-500 font-light mt-1 line-clamp-2">${p.desc || '-'}</p>
            <div class="flex items-end justify-between mt-3">
              <p class="text-lg font-semibold">${fmt(p.price)}</p>
              <p class="text-[10px] font-mono text-neutral-600">${p.sold} sold · ${p.stock} stok</p>
            </div>
          </div>
        </div>
      `;
    }).join('');

    lucide.createIcons();
  }

  // ====== FILTER ======
  function filterProducts(btn, cat) {
    document.querySelectorAll('.cat-pill').forEach(p => p.classList.remove('active'));
    btn.classList.add('active');
    currentFilter = cat;
    renderProducts();
  }

  // ====== ADD/EDIT PRODUCT ======
  function handleProductSubmit(e) {
    e.preventDefault();
    const editId = document.getElementById('editId').value;
    const name = document.getElementById('pName').value.trim();
    const price = parseInt(document.getElementById('pPrice').value);
    const stock = parseInt(document.getElementById('pStock').value);
    const category = document.getElementById('pCategory').value;
    const gender = document.getElementById('pGender').value;
    const size = document.getElementById('pSize').value.trim();
    const desc = document.getElementById('pDesc').value.trim();
    const image = document.getElementById('pImage').value.trim() || `https://picsum.photos/seed/parfum-${name.replace(/\s+/g,'-').toLowerCase()}-${Date.now()}/600/800.jpg`;
    const tags = [];
    if (document.getElementById('tagNew').checked) tags.push('new');
    if (document.getElementById('tagHot').checked) tags.push('hot');
    if (document.getElementById('tagLimited').checked) tags.push('limited');

    if (editId) {
      const idx = products.findIndex(p => p.id === parseInt(editId));
      if (idx >= 0) {
        products[idx] = { ...products[idx], name, price, stock, category, gender, size, desc, image, tags };
        toast(`"${name}" berhasil diperbarui`);
      }
    } else {
      products.push({ id: nextId++, name, price, stock, category, gender, size, desc, image, tags, sold: 0 });
      toast(`"${name}" berhasil ditambahkan!`);
    }

    closeSidebar('addProductSidebar');
    renderProducts();
    updateDashboard();
  }

  function editProduct(id) {
    const p = products.find(x => x.id === id);
    if (!p) return;
    document.getElementById('editId').value = p.id;
    document.getElementById('pName').value = p.name;
    document.getElementById('pPrice').value = p.price;
    document.getElementById('pStock').value = p.stock;
    document.getElementById('pCategory').value = p.category;
    document.getElementById('pGender').value = p.gender;
    document.getElementById('pSize').value = p.size || '';
    document.getElementById('pDesc').value = p.desc || '';
    document.getElementById('pImage').value = p.image || '';
    document.getElementById('tagNew').checked = p.tags.includes('new');
    document.getElementById('tagHot').checked = p.tags.includes('hot');
    document.getElementById('tagLimited').checked = p.tags.includes('limited');
    document.getElementById('formTitle').textContent = 'Edit Produk';
    document.getElementById('submitBtnText').textContent = 'Perbarui Produk';
    openSidebar('addProductSidebar');
  }

  function resetForm() {
    document.getElementById('productForm').reset();
    document.getElementById('editId').value = '';
    document.getElementById('formTitle').textContent = 'Tambah Produk';
    document.getElementById('submitBtnText').textContent = 'Simpan Produk';
  }

  // ====== DELETE ======
  function deleteProduct(id) {
    const p = products.find(x => x.id === id);
    if (!p) return;
    deleteTargetId = id;
    document.getElementById('deleteMsg').textContent = `"${p.name}" akan dihapus secara permanen.`;
    document.getElementById('deleteModal').classList.add('open');
  }
  function closeDeleteModal() {
    document.getElementById('deleteModal').classList.remove('open');
    deleteTargetId = null;
  }
  function confirmDelete() {
    if (deleteTargetId !== null) {
      const p = products.find(x => x.id === deleteTargetId);
      products = products.filter(x => x.id !== deleteTargetId);
      cart = cart.filter(c => c.id !== deleteTargetId);
      toast(`"${p?.name}" berhasil dihapus`, 'info');
      renderProducts();
      updateDashboard();
      updateCartBadge();
    }
    closeDeleteModal();
  }

  // ====== CART ======
  function addToCart(id) {
    const p = products.find(x => x.id === id);
    if (!p || p.stock === 0) return;
    const existing = cart.find(c => c.id === id);
    if (existing) {
      if (existing.qty >= p.stock) { toast('Stok tidak mencukupi', 'error'); return; }
      existing.qty++;
    } else {
      cart.push({ id, qty: 1 });
    }
    updateCartBadge();
    toast(`"${p.name}" ditambahkan ke keranjang`);
  }

  function removeFromCart(id) {
    cart = cart.filter(c => c.id !== id);
    updateCartBadge();
    renderCart();
  }

  function changeQty(id, delta) {
    const item = cart.find(c => c.id === id);
    const p = products.find(x => x.id === id);
    if (!item || !p) return;
    item.qty += delta;
    if (item.qty <= 0) { removeFromCart(id); return; }
    if (item.qty > p.stock) { item.qty = p.stock; toast('Stok tidak mencukupi', 'error'); }
    updateCartBadge();
    renderCart();
  }

  function updateCartBadge() {
    const total = cart.reduce((s, c) => s + c.qty, 0);
    const badge = document.getElementById('cartCount');
    if (total > 0) {
      badge.textContent = total;
      badge.classList.remove('hidden');
    } else {
      badge.classList.add('hidden');
    }
  }

  function renderCart() {
    const list = document.getElementById('cartList');
    const empty = document.getElementById('cartEmpty');
    const footer = document.getElementById('cartFooter');
    const countLabel = document.getElementById('cartItemCount');

    if (cart.length === 0) {
      list.classList.add('hidden'); empty.classList.remove('hidden'); footer.classList.add('hidden');
      countLabel.textContent = '0 item';
      return;
    }

    empty.classList.add('hidden'); list.classList.remove('hidden'); footer.classList.remove('hidden');
    const totalQty = cart.reduce((s, c) => s + c.qty, 0);
    countLabel.textContent = `${totalQty} item`;

    let subtotal = 0;
    list.innerHTML = cart.map(c => {
      const p = products.find(x => x.id === c.id);
      if (!p) return '';
      const lineTotal = p.price * c.qty;
      subtotal += lineTotal;
      return `
        <div class="flex gap-4 p-3 rounded-xl bg-white/[0.02] border border-white/[0.04]">
          <img src="${p.image}" class="w-16 h-20 rounded-lg object-cover shrink-0" alt="" />
          <div class="flex-1 min-w-0">
            <div class="flex items-start justify-between gap-2">
              <div>
                <p class="text-sm font-medium truncate">${p.name}</p>
                <p class="text-[10px] font-mono text-neutral-500 mt-0.5">${catLabel(p.category)} · ${p.size || '-'}</p>
              </div>
              <button onclick="removeFromCart(${p.id})" class="p-1 rounded-lg hover:bg-white/5 transition-colors shrink-0"><i data-lucide="x" class="w-3.5 h-3.5 text-neutral-500"></i></button>
            </div>
            <div class="flex items-center justify-between mt-2.5">
              <div class="flex items-center gap-0.5">
                <button onclick="changeQty(${p.id},-1)" class="w-7 h-7 rounded-lg border border-white/10 flex items-center justify-center hover:bg-white/5 transition-colors text-xs">−</button>
                <span class="w-8 text-center text-xs font-medium">${c.qty}</span>
                <button onclick="changeQty(${p.id},1)" class="w-7 h-7 rounded-lg border border-white/10 flex items-center justify-center hover:bg-white/5 transition-colors text-xs">+</button>
              </div>
              <p class="text-sm font-semibold">${fmt(lineTotal)}</p>
            </div>
          </div>
        </div>
      `;
    }).join('');

    document.getElementById('cartSubtotal').textContent = fmt(subtotal);
    document.getElementById('cartTotal').textContent = fmt(subtotal);
    lucide.createIcons();
  }

  // ====== CHECKOUT ======
  function handleCheckout() {
    if (cart.length === 0) return;
    let totalRevenue = 0;
    let totalItems = 0;
    const saleItems = [];

    cart.forEach(c => {
      const p = products.find(x => x.id === c.id);
      if (!p) return;
      const lineTotal = p.price * c.qty;
      totalRevenue += lineTotal;
      totalItems += c.qty;
      p.sold += c.qty;
      p.stock = Math.max(0, p.stock - c.qty);
      saleItems.push({ name: p.name, qty: c.qty, total: lineTotal });
    });

    sales.unshift({
      id: sales.length + 1,
      date: new Date().toLocaleString('id-ID'),
      items: saleItems,
      total: totalRevenue,
      qty: totalItems
    });

    cart = [];
    updateCartBadge();
    closeSidebar('cartSidebar');
    renderProducts();
    updateDashboard();
    toast(`Checkout berhasil! Total: ${fmt(totalRevenue)}`);
  }

  // ====== DASHBOARD ======
  function updateDashboard() {
    const totalProducts = products.length;
    const totalSold = products.reduce((s, p) => s + p.sold, 0);
    const totalRevenue = products.reduce((s, p) => s + (p.sold * p.price), 0);
    const lowStock = products.filter(p => p.stock <= 10 && p.stock > 0).length;
    const outOfStock = products.filter(p => p.stock === 0).length;

    document.getElementById('statProducts').textContent = totalProducts;
    document.getElementById('statSold').textContent = totalSold.toLocaleString('id-ID');
    document.getElementById('statRevenue').textContent = fmt(totalRevenue);
    document.getElementById('statLowStock').textContent = lowStock + outOfStock;

    document.getElementById('progProducts').style.width = Math.min(100, (totalProducts / 50) * 100) + '%';
    document.getElementById('progSold').style.width = Math.min(100, (totalSold / 1000) * 100) + '%';
    document.getElementById('progRevenue').style.width = Math.min(100, (totalRevenue / 500000000) * 100) + '%';

    document.getElementById('heroProductCount').textContent = totalProducts;
    document.getElementById('heroSalesCount').textContent = totalSold.toLocaleString('id-ID');
    document.getElementById('heroRevenue').textContent = fmt(totalRevenue);

    const salesList = document.getElementById('recentSalesList');
    const salesLabel = document.getElementById('salesCountLabel');
    salesLabel.textContent = sales.length + ' transaksi';

    if (sales.length === 0) {
      salesList.innerHTML = '<p class="text-sm text-neutral-600 text-center py-8">Belum ada penjualan</p>';
    } else {
      salesList.innerHTML = sales.slice(0, 5).map(s => `
        <div class="flex items-center gap-4 p-3 rounded-xl bg-white/[0.02] border border-white/[0.04]">
          <div class="w-9 h-9 rounded-lg bg-green-500/10 flex items-center justify-center shrink-0">
            <i data-lucide="check-circle" class="w-4 h-4 text-green-400"></i>
          </div>
          <div class="flex-1 min-w-0">
            <p class="text-sm font-medium truncate">${s.items.map(i => i.name).join(', ')}</p>
            <p class="text-[10px] text-neutral-500">${s.date} · ${s.qty} item</p>
          </div>
          <p class="text-sm font-semibold gradient-text-gold shrink-0">${fmt(s.total)}</p>
        </div>
      `).join('');
      lucide.createIcons();
    }
  }

  // ====== SCROLL EFFECTS ======
  function observeReveal() {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) { entry.target.classList.add('visible'); }
      });
    }, { threshold: 0.08, rootMargin: '0px 0px -40px 0px' });
    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
  }

  window.addEventListener('scroll', () => {
    const nav = document.getElementById('mainNav');
    if (window.scrollY > 80) { nav.classList.add('nav-scrolled'); }
    else { nav.classList.remove('nav-scrolled'); }
  });

  // ====== INIT ======
  renderProducts();
  updateDashboard();
  observeReveal();
</script>

</body>
</html>
