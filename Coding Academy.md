<!DOCTYPE html>
<html lang="id" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RedCode Academy - Platform Pelatihan & Bootcamp IT Terbaik</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            50: '#fef2f2',
                            100: '#fee2e2',
                            500: '#ef4444',
                            600: '#dc2626',
                            700: '#b91c1c',
                            900: '#7f1d1d',
                        },
                        accent: {
                            400: '#facc15',
                            500: '#eab308',
                            600: '#ca8a04',
                        }
                    }
                }
            }
        }
    </script>
    <!-- Google Fonts: Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Alpine.js for interactive state management -->
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <style>
        body { font-family: 'Inter', sans-serif; }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col selection:bg-red-600 selection:text-white" x-data="codingAcademyApp()">

    <!-- Header / Navbar -->
    <header class="sticky top-0 z-50 backdrop-blur-md bg-white/90 border-b border-red-100 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <!-- Brand Logo -->
            <div class="flex items-center space-x-3 cursor-pointer" @click="activeTab = 'gallery'">
                <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-red-600 to-rose-500 flex items-center justify-center shadow-md shadow-red-500/20 text-white font-black text-xl">
                    R
                </div>
                <div>
                    <span class="text-xl font-extrabold tracking-tight text-slate-900">RedCode</span>
                    <span class="text-xs block font-bold text-red-600 uppercase tracking-widest">Academy</span>
                </div>
            </div>

            <!-- Navigation Switcher Tabs -->
            <nav class="flex items-center space-x-1 sm:space-x-2 bg-slate-100 p-1.5 rounded-2xl border border-slate-200">
                <button 
                    @click="activeTab = 'gallery'"
                    :class="activeTab === 'gallery' ? 'bg-red-600 text-white shadow-md shadow-red-600/20 font-semibold' : 'text-slate-600 hover:text-slate-900 hover:bg-slate-200/60 font-medium'"
                    class="px-4 sm:px-6 py-2.5 rounded-xl text-sm transition-all duration-200 flex items-center space-x-2">
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z"></path>
                    </svg>
                    <span>Gallery Kegiatan</span>
                </button>
                <button 
                    @click="activeTab = 'pendaftaran'"
                    :class="activeTab === 'pendaftaran' ? 'bg-red-600 text-white shadow-md shadow-red-600/20 font-semibold' : 'text-slate-600 hover:text-slate-900 hover:bg-slate-200/60 font-medium'"
                    class="px-4 sm:px-6 py-2.5 rounded-xl text-sm transition-all duration-200 flex items-center space-x-2">
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M18 9v3m0 0v3m0-3h3m-3 0h-3m-2-5a4 4 0 11-8 0 4 4 0 018 0zM3 20a6 6 0 0112 0v1H3v-1z"></path>
                    </svg>
                    <span>Form Pendaftaran</span>
                </button>
            </nav>
        </div>
    </header>

    <!-- Main Content Container -->
    <main class="flex-grow max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-10 w-full">

        <!-- ==================== TAMPILAN 1: GALLERY KEGIATAN ==================== -->
        <section x-show="activeTab === 'gallery'" x-transition:enter="transition ease-out duration-300" x-transition:enter-start="opacity-0 translate-y-4" x-transition:enter-end="opacity-100 translate-y-0" class="space-y-12">
            <!-- Hero Banner -->
            <div class="relative overflow-hidden rounded-3xl bg-gradient-to-br from-red-900 via-red-800 to-slate-900 text-white p-8 sm:p-12 md:p-16 text-center shadow-xl">
                <div class="absolute -top-24 -left-24 w-72 h-72 bg-yellow-500/20 rounded-full blur-3xl pointer-events-none"></div>
                <div class="absolute -bottom-24 -right-24 w-72 h-72 bg-red-500/30 rounded-full blur-3xl pointer-events-none"></div>
                
                <span class="inline-flex items-center space-x-1.5 px-4 py-1.5 rounded-full text-xs font-bold bg-yellow-400 text-slate-900 shadow-md mb-6">
                    <span class="w-2 h-2 rounded-full bg-red-600 animate-pulse"></span>
                    <span>Pendaftaran Batch Baru Telah Dibuka</span>
                </span>
                <h1 class="text-3xl sm:text-5xl md:text-6xl font-extrabold tracking-tight mb-6 leading-tight">
                    Wujudkan Karier Impianmu di Dunia IT Bersama <span class="text-yellow-400 underline decoration-yellow-400/40 decoration-4">RedCode</span>
                </h1>
                <p class="max-w-2xl mx-auto text-slate-200 text-base sm:text-lg mb-8 leading-relaxed">
                    Pelatihan intensif berstandar industri dengan kurikulum terkini, mentor berpengalaman, dan proyek nyata siap kerja.
                </p>
                <div class="flex flex-wrap justify-center gap-4">
                    <button @click="activeTab = 'pendaftaran'" class="px-8 py-4 rounded-2xl bg-yellow-400 hover:bg-yellow-500 text-slate-950 font-bold shadow-lg shadow-yellow-500/20 transition-all transform hover:-translate-y-0.5">
                        Daftar Pendaftaran Sekarang
                    </button>
                    <a href="#gallery-cards" class="px-8 py-4 rounded-2xl bg-white/10 hover:bg-white/20 text-white border border-white/20 font-semibold transition-all">
                        Eksplorasi Program
                    </a>
                </div>
            </div>

            <!-- Gallery Header & Filters -->
            <div id="gallery-cards" class="flex flex-col md:flex-row items-start md:items-center justify-between gap-4 pt-4">
                <div>
                    <h2 class="text-2xl sm:text-3xl font-extrabold text-slate-900 tracking-tight">Galeri & Dokumentasi Kegiatan</h2>
                    <p class="text-slate-600 text-sm mt-1">Pilih program pelatihan terbaik yang sesuai dengan minat dan passion digital Anda.</p>
                </div>
                <div class="flex items-center space-x-2 bg-white p-1.5 rounded-xl border border-slate-200 shadow-sm overflow-x-auto max-w-full">
                    <button @click="filterCategory = 'all'" :class="filterCategory === 'all' ? 'bg-red-600 text-white shadow' : 'text-slate-600 hover:text-slate-900'" class="px-4 py-2 rounded-lg text-xs font-semibold transition-all whitespace-nowrap">Semua</button>
                    <button @click="filterCategory = 'web'" :class="filterCategory === 'web' ? 'bg-red-600 text-white shadow' : 'text-slate-600 hover:text-slate-900'" class="px-4 py-2 rounded-lg text-xs font-semibold transition-all whitespace-nowrap">Web Dev</button>
                    <button @click="filterCategory = 'data'" :class="filterCategory === 'data' ? 'bg-red-600 text-white shadow' : 'text-slate-600 hover:text-slate-900'" class="px-4 py-2 rounded-lg text-xs font-semibold transition-all whitespace-nowrap">Python & Data</button>
                    <button @click="filterCategory = 'mobile'" :class="filterCategory === 'mobile' ? 'bg-red-600 text-white shadow' : 'text-slate-600 hover:text-slate-900'" class="px-4 py-2 rounded-lg text-xs font-semibold transition-all whitespace-nowrap">Mobile App</button>
                </div>
            </div>

            <!-- Gallery Cards Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Card 1: Web Dev Masterclass -->
                <div class="group bg-white rounded-3xl border border-slate-200 overflow-hidden hover:border-red-400 transition-all duration-300 flex flex-col shadow-lg hover:shadow-xl" x-show="filterCategory === 'all' || filterCategory === 'web'">
                    <div class="relative h-56 overflow-hidden bg-slate-100">
                        <img src="https://images.unsplash.com/photo-1531482615713-2afd69097998?q=80&w=800&auto=format&fit=crop" alt="Web Dev Masterclass" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.src='https://placehold.co/600x400/f1f5f9/475569?text=Web+Dev+Masterclass'">
                        <div class="absolute top-4 left-4">
                            <span class="px-3 py-1 rounded-full text-xs font-bold bg-red-600 text-white shadow">JavaScript / Web Dev</span>
                        </div>
                        <div class="absolute top-4 right-4">
                            <span class="px-2.5 py-1 rounded-full text-xs font-bold bg-yellow-400 text-slate-900 shadow">Best Seller</span>
                        </div>
                    </div>
                    <div class="p-6 flex flex-col flex-grow justify-between">
                        <div>
                            <div class="flex items-center text-xs text-red-600 font-bold mb-2 space-x-2">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"></path></svg>
                                <span>Batch 15 • Dimulai 1 Mei 2026</span>
                            </div>
                            <h3 class="text-xl font-bold text-slate-900 mb-2 group-hover:text-red-600 transition-colors">Web Dev Masterclass</h3>
                            <p class="text-slate-600 text-sm leading-relaxed mb-4">Pelatihan komprehensif membangun website responsif dan aplikasi web interaktif menggunakan HTML, Tailwind CSS, JavaScript modern, dan React.</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 flex items-center justify-between">
                            <span class="text-xs text-slate-500 font-semibold">Durasi: 3 Bulan</span>
                            <button @click="activeTab = 'pendaftaran'; formData.bahasa = 'JavaScript'" class="text-xs font-bold text-red-600 hover:text-red-700 flex items-center space-x-1">
                                <span>Daftar Sekarang</span>
                                <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path></svg>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Card 2: Python for AI -->
                <div class="group bg-white rounded-3xl border border-slate-200 overflow-hidden hover:border-red-400 transition-all duration-300 flex flex-col shadow-lg hover:shadow-xl" x-show="filterCategory === 'all' || filterCategory === 'data'">
                    <div class="relative h-56 overflow-hidden bg-slate-100">
                        <img src="https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?q=80&w=800&auto=format&fit=crop" alt="Python for AI" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.src='https://placehold.co/600x400/f1f5f9/475569?text=Python+for+AI'">
                        <div class="absolute top-4 left-4">
                            <span class="px-3 py-1 rounded-full text-xs font-bold bg-red-600 text-white shadow">Python</span>
                        </div>
                        <div class="absolute top-4 right-4">
                            <span class="px-2.5 py-1 rounded-full text-xs font-bold bg-yellow-400 text-slate-900 shadow">Trending</span>
                        </div>
                    </div>
                    <div class="p-6 flex flex-col flex-grow justify-between">
                        <div>
                            <div class="flex items-center text-xs text-red-600 font-bold mb-2 space-x-2">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"></path></svg>
                                <span>Batch 10 • Dimulai 10 Mei 2026</span>
                            </div>
                            <h3 class="text-xl font-bold text-slate-900 mb-2 group-hover:text-red-600 transition-colors">Python for AI & Data</h3>
                            <p class="text-slate-600 text-sm leading-relaxed mb-4">Pelajari dasar pemrograman Python, analisis data tingkat lanjut, machine learning, serta pemodelan kecerdasan buatan masa kini.</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 flex items-center justify-between">
                            <span class="text-xs text-slate-500 font-semibold">Durasi: 3 Bulan</span>
                            <button @click="activeTab = 'pendaftaran'; formData.bahasa = 'Python'" class="text-xs font-bold text-red-600 hover:text-red-700 flex items-center space-x-1">
                                <span>Daftar Sekarang</span>
                                <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path></svg>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Card 3: UI/UX Design -->
                <div class="group bg-white rounded-3xl border border-slate-200 overflow-hidden hover:border-red-400 transition-all duration-300 flex flex-col shadow-lg hover:shadow-xl" x-show="filterCategory === 'all' || filterCategory === 'web'">
                    <div class="relative h-56 overflow-hidden bg-slate-100">
                        <img src="https://images.unsplash.com/photo-1581291518633-83b4ebd1d83e?q=80&w=800&auto=format&fit=crop" alt="UI/UX Design" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.src='https://placehold.co/600x400/f1f5f9/475569?text=UI+UX+Design'">
                        <div class="absolute top-4 left-4">
                            <span class="px-3 py-1 rounded-full text-xs font-bold bg-red-600 text-white shadow">UI/UX & Web</span>
                        </div>
                    </div>
                    <div class="p-6 flex flex-col flex-grow justify-between">
                        <div>
                            <div class="flex items-center text-xs text-red-600 font-bold mb-2 space-x-2">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"></path></svg>
                                <span>Batch 8 • Dimulai 15 Mei 2026</span>
                            </div>
                            <h3 class="text-xl font-bold text-slate-900 mb-2 group-hover:text-red-600 transition-colors">UI/UX Design Masterclass</h3>
                            <p class="text-slate-600 text-sm leading-relaxed mb-4">Kuasai riset pengguna, wireframing, prototyping interaktif menggunakan Figma, serta implementasi desain antarmuka modern yang memukau.</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 flex items-center justify-between">
                            <span class="text-xs text-slate-500 font-semibold">Durasi: 2 Bulan</span>
                            <button @click="activeTab = 'pendaftaran'; formData.bahasa = 'JavaScript'" class="text-xs font-bold text-red-600 hover:text-red-700 flex items-center space-x-1">
                                <span>Daftar Sekarang</span>
                                <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path></svg>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Card 4: Mobile App Dev -->
                <div class="group bg-white rounded-3xl border border-slate-200 overflow-hidden hover:border-red-400 transition-all duration-300 flex flex-col shadow-lg hover:shadow-xl" x-show="filterCategory === 'all' || filterCategory === 'mobile'">
                    <div class="relative h-56 overflow-hidden bg-slate-100">
                        <img src="https://images.unsplash.com/photo-1512941937669-90a1b58e7e9c?q=80&w=800&auto=format&fit=crop" alt="Mobile App Dev" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.src='https://placehold.co/600x400/f1f5f9/475569?text=Mobile+App+Dev'">
                        <div class="absolute top-4 left-4">
                            <span class="px-3 py-1 rounded-full text-xs font-bold bg-red-600 text-white shadow">Mobile App</span>
                        </div>
                    </div>
                    <div class="p-6 flex flex-col flex-grow justify-between">
                        <div>
                            <div class="flex items-center text-xs text-red-600 font-bold mb-2 space-x-2">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"></path></svg>
                                <span>Batch 7 • Dimulai 20 Mei 2026</span>
                            </div>
                            <h3 class="text-xl font-bold text-slate-900 mb-2 group-hover:text-red-600 transition-colors">Mobile App Development</h3>
                            <p class="text-slate-600 text-sm leading-relaxed mb-4">Pelatihan pembuatan aplikasi mobile Android dan iOS menggunakan teknologi Flutter serta bahasa pemrograman Java & Kotlin.</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 flex items-center justify-between">
                            <span class="text-xs text-slate-500 font-semibold">Durasi: 3 Bulan</span>
                            <button @click="activeTab = 'pendaftaran'; formData.bahasa = 'Java'" class="text-xs font-bold text-red-600 hover:text-red-700 flex items-center space-x-1">
                                <span>Daftar Sekarang</span>
                                <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path></svg>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Card 5: Backend PHP & Laravel -->
                <div class="group bg-white rounded-3xl border border-slate-200 overflow-hidden hover:border-red-400 transition-all duration-300 flex flex-col shadow-lg hover:shadow-xl" x-show="filterCategory === 'all' || filterCategory === 'web'">
                    <div class="relative h-56 overflow-hidden bg-slate-100">
                        <img src="https://images.unsplash.com/photo-1555066931-4365d14bab8c?q=80&w=800&auto=format&fit=crop" alt="Backend PHP Laravel" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.src='https://placehold.co/600x400/f1f5f9/475569?text=PHP+Laravel'">
                        <div class="absolute top-4 left-4">
                            <span class="px-3 py-1 rounded-full text-xs font-bold bg-red-600 text-white shadow">PHP / Backend</span>
                        </div>
                    </div>
                    <div class="p-6 flex flex-col flex-grow justify-between">
                        <div>
                            <div class="flex items-center text-xs text-red-600 font-bold mb-2 space-x-2">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"></path></svg>
                                <span>Batch 9 • Dimulai 1 Juni 2026</span>
                            </div>
                            <h3 class="text-xl font-bold text-slate-900 mb-2 group-hover:text-red-600 transition-colors">PHP & Laravel Masterclass</h3>
                            <p class="text-slate-600 text-sm leading-relaxed mb-4">Pelatihan pembuatan REST API, sistem manajemen database handal, dan arsitektur backend perusahaan dengan framework Laravel.</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 flex items-center justify-between">
                            <span class="text-xs text-slate-500 font-semibold">Durasi: 3 Bulan</span>
                            <button @click="activeTab = 'pendaftaran'; formData.bahasa = 'PHP'" class="text-xs font-bold text-red-600 hover:text-red-700 flex items-center space-x-1">
                                <span>Daftar Sekarang</span>
                                <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path></svg>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Card 6: Go Backend Systems -->
                <div class="group bg-white rounded-3xl border border-slate-200 overflow-hidden hover:border-red-400 transition-all duration-300 flex flex-col shadow-lg hover:shadow-xl" x-show="filterCategory === 'all' || filterCategory === 'data'">
                    <div class="relative h-56 overflow-hidden bg-slate-100">
                        <img src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?q=80&w=800&auto=format&fit=crop" alt="Go Backend Systems" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.src='https://placehold.co/600x400/f1f5f9/475569?text=Go+Language'">
                        <div class="absolute top-4 left-4">
                            <span class="px-3 py-1 rounded-full text-xs font-bold bg-red-600 text-white shadow">Go / Backend</span>
                        </div>
                    </div>
                    <div class="p-6 flex flex-col flex-grow justify-between">
                        <div>
                            <div class="flex items-center text-xs text-red-600 font-bold mb-2 space-x-2">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"></path></svg>
                                <span>Batch 5 • Dimulai 5 Juni 2026</span>
                            </div>
                            <h3 class="text-xl font-bold text-slate-900 mb-2 group-hover:text-red-600 transition-colors">Go (Golang) High Performance</h3>
                            <p class="text-slate-600 text-sm leading-relaxed mb-4">Belajar bahasa Go untuk membangun layanan mikro (microservices) dan sistem backend berkecepatan tinggi skala enterprise.</p>
                        </div>
                        <div class="pt-4 border-t border-slate-100 flex items-center justify-between">
                            <span class="text-xs text-slate-500 font-semibold">Durasi: 2.5 Bulan</span>
                            <button @click="activeTab = 'pendaftaran'; formData.bahasa = 'Go'" class="text-xs font-bold text-red-600 hover:text-red-700 flex items-center space-x-1">
                                <span>Daftar Sekarang</span>
                                <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path></svg>
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>


        <!-- ==================== TAMPILAN 2: FORM PENDAFTARAN & HASIL ==================== -->
        <section x-show="activeTab === 'pendaftaran'" x-transition:enter="transition ease-out duration-300" x-transition:enter-start="opacity-0 translate-y-4" x-transition:enter-end="opacity-100 translate-y-0" class="max-w-3xl mx-auto space-y-8">
            
            <!-- Header Form -->
            <div class="text-center space-y-3">
                <span class="inline-flex items-center px-3.5 py-1 rounded-full text-xs font-bold bg-yellow-400/20 text-red-700 border border-yellow-400/40">
                    Formulir Registrasi Resmi
                </span>
                <h1 class="text-3xl sm:text-4xl font-extrabold text-slate-900 tracking-tight">Pendaftaran Peserta Coding Academy</h1>
                <p class="text-slate-600 text-sm sm:text-base max-w-xl mx-auto">Isi data diri Anda dengan lengkap dan benar pada formulir di bawah ini.</p>
            </div>

            <!-- Card Wrapper -->
            <div class="bg-white border border-slate-200 rounded-3xl p-6 sm:p-10 shadow-xl relative overflow-hidden">
                <div class="absolute top-0 right-0 w-96 h-96 bg-red-600/5 rounded-full blur-3xl pointer-events-none"></div>

                <!-- 1. FORM INPUT VIEW -->
                <form x-show="!isSubmitted" @submit.prevent="triggerConfirmationModal" class="space-y-6 relative z-10">
                    
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                        <!-- NIK -->
                        <div class="space-y-2">
                            <label class="block text-sm font-bold text-slate-700">NIK (Nomor Induk Kependudukan) <span class="text-red-600">*</span></label>
                            <input 
                                type="text" 
                                x-model="formData.nik" 
                                placeholder="Contoh: 3201234567890001" 
                                maxlength="16"
                                required
                                class="w-full bg-slate-50 border border-slate-300 rounded-xl px-4 py-3.5 text-slate-900 placeholder-slate-400 focus:outline-none focus:border-red-600 focus:ring-1 focus:ring-red-600 transition-all text-sm font-mono">
                            <p class="text-xs text-slate-500">Masukkan 16 digit NIK KTP Anda.</p>
                        </div>

                        <!-- Nama Lengkap -->
                        <div class="space-y-2">
                            <label class="block text-sm font-bold text-slate-700">Nama Lengkap <span class="text-red-600">*</span></label>
                            <input 
                                type="text" 
                                x-model="formData.nama" 
                                placeholder="Contoh: Budi Santoso, S.Kom" 
                                required
                                class="w-full bg-slate-50 border border-slate-300 rounded-xl px-4 py-3.5 text-slate-900 placeholder-slate-400 focus:outline-none focus:border-red-600 focus:ring-1 focus:ring-red-600 transition-all text-sm">
                        </div>
                    </div>

                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                        <!-- Pilihan Jenis Kelamin -->
                        <div class="space-y-2">
                            <label class="block text-sm font-bold text-slate-700">Pilihan Jenis Kelamin <span class="text-red-600">*</span></label>
                            <div class="grid grid-cols-2 gap-4">
                                <label :class="formData.jenisKelamin === 'Laki-laki' ? 'border-red-600 bg-red-50 text-red-900 font-semibold' : 'border-slate-300 bg-slate-50 text-slate-700'" class="flex items-center justify-center px-4 py-3.5 rounded-xl border cursor-pointer hover:border-red-400 transition-all text-sm">
                                    <input type="radio" name="jenisKelamin" value="Laki-laki" x-model="formData.jenisKelamin" class="sr-only">
                                    <span>Laki-laki</span>
                                </label>
                                <label :class="formData.jenisKelamin === 'Perempuan' ? 'border-red-600 bg-red-50 text-red-900 font-semibold' : 'border-slate-300 bg-slate-50 text-slate-700'" class="flex items-center justify-center px-4 py-3.5 rounded-xl border cursor-pointer hover:border-red-400 transition-all text-sm">
                                    <input type="radio" name="jenisKelamin" value="Perempuan" x-model="formData.jenisKelamin" class="sr-only">
                                    <span>Perempuan</span>
                                </label>
                            </div>
                        </div>

                        <!-- No HP -->
                        <div class="space-y-2">
                            <label class="block text-sm font-bold text-slate-700">No HP / WhatsApp <span class="text-red-600">*</span></label>
                            <input 
                                type="tel" 
                                x-model="formData.noHp" 
                                placeholder="Contoh: 081234567890" 
                                required
                                class="w-full bg-slate-50 border border-slate-300 rounded-xl px-4 py-3.5 text-slate-900 placeholder-slate-400 focus:outline-none focus:border-red-600 focus:ring-1 focus:ring-red-600 transition-all text-sm">
                        </div>
                    </div>

                    <!-- Pilihan Bahasa Pemrograman yang Diminati -->
                    <div class="space-y-2">
                        <label class="block text-sm font-bold text-slate-700">Pilihan Bahasa Pemrograman yang Diminati <span class="text-red-600">*</span></label>
                        <select 
                            x-model="formData.bahasa" 
                            required
                            class="w-full bg-slate-50 border border-slate-300 rounded-xl px-4 py-3.5 text-slate-900 focus:outline-none focus:border-red-600 focus:ring-1 focus:ring-red-600 transition-all text-sm">
                            <option value="" disabled selected>-- Pilih Bahasa Pemrograman --</option>
                            <option value="Python">Python</option>
                            <option value="JavaScript">JavaScript</option>
                            <option value="Java">Java</option>
                            <option value="C++">C++</option>
                            <option value="PHP">PHP</option>
                            <option value="Go">Go</option>
                        </select>
                    </div>

                    <!-- Alamat -->
                    <div class="space-y-2">
                        <label class="block text-sm font-bold text-slate-700">Alamat Lengkap <span class="text-red-600">*</span></label>
                        <textarea 
                            x-model="formData.alamat" 
                            rows="3" 
                            placeholder="Masukkan alamat lengkap Anda di sini..." 
                            required
                            class="w-full bg-slate-50 border border-slate-300 rounded-xl px-4 py-3.5 text-slate-900 placeholder-slate-400 focus:outline-none focus:border-red-600 focus:ring-1 focus:ring-red-600 transition-all text-sm resize-none"></textarea>
                    </div>

                    <!-- Action Buttons -->
                    <div class="pt-4 flex items-center justify-end space-x-4">
                        <button 
                            type="button" 
                            @click="activeTab = 'gallery'"
                            class="px-6 py-3.5 rounded-xl bg-slate-100 hover:bg-slate-200 text-slate-700 font-bold text-sm transition-all">
                            Batal
                        </button>
                        <button 
                            type="submit" 
                            class="px-8 py-3.5 rounded-xl bg-gradient-to-r from-red-600 to-rose-600 hover:from-red-500 hover:to-rose-500 text-white font-bold text-sm shadow-lg shadow-red-600/30 transition-all transform hover:-translate-y-0.5">
                            Simpan / Daftar
                        </button>
                    </div>
                </form>


                <!-- 2. SUCCESS SUMMARY VIEW (Menampilkan hasil isian form setelah tombol "Ya" diklik) -->
                <div x-show="isSubmitted" x-transition class="space-y-8 relative z-10">
                    <div class="text-center space-y-4">
                        <div class="w-20 h-20 bg-yellow-400/20 border border-yellow-400 text-yellow-600 rounded-full flex items-center justify-center mx-auto shadow-md">
                            <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M5 13l4 4L19 7"></path>
                            </svg>
                        </div>
                        <div>
                            <h2 class="text-2xl sm:text-3xl font-extrabold text-slate-900">Pendaftaran Berhasil Disimpan!</h2>
                            <p class="text-slate-600 text-sm mt-1">Berikut adalah rincian data pendaftaran Anda di RedCode Academy:</p>
                        </div>
                    </div>

                    <!-- Detail Data Card -->
                    <div class="bg-slate-50 border border-slate-200 rounded-2xl p-6 sm:p-8 space-y-6 shadow-inner">
                        <div class="border-b border-slate-200 pb-4 flex items-center justify-between">
                            <span class="text-xs font-bold text-red-600 uppercase tracking-wider">Ringkasan Data Formulir</span>
                            <span class="px-3 py-1 rounded-full text-xs font-bold bg-yellow-400 text-slate-900">Tersimpan</span>
                        </div>

                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 text-sm">
                            <div>
                                <span class="text-slate-500 block text-xs font-semibold uppercase tracking-wider mb-1">NIK</span>
                                <span class="text-slate-900 font-bold font-mono text-base" x-text="submittedData.nik"></span>
                            </div>
                            <div>
                                <span class="text-slate-500 block text-xs font-semibold uppercase tracking-wider mb-1">Nama Lengkap</span>
                                <span class="text-slate-900 font-bold text-base" x-text="submittedData.nama"></span>
                            </div>
                            <div>
                                <span class="text-slate-500 block text-xs font-semibold uppercase tracking-wider mb-1">Jenis Kelamin</span>
                                <span class="text-slate-900 font-bold text-base" x-text="submittedData.jenisKelamin"></span>
                            </div>
                            <div>
                                <span class="text-slate-500 block text-xs font-semibold uppercase tracking-wider mb-1">No. HP / WhatsApp</span>
                                <span class="text-slate-900 font-bold text-base" x-text="submittedData.noHp"></span>
                            </div>
                            <div>
                                <span class="text-slate-500 block text-xs font-semibold uppercase tracking-wider mb-1">Bahasa Pemrograman Diminati</span>
                                <span class="text-red-600 font-extrabold text-base" x-text="submittedData.bahasa"></span>
                            </div>
                            <div>
                                <span class="text-slate-500 block text-xs font-semibold uppercase tracking-wider mb-1">Alamat Lengkap</span>
                                <span class="text-slate-900 font-medium text-sm leading-relaxed" x-text="submittedData.alamat"></span>
                            </div>
                        </div>
                    </div>

                    <!-- Post-Submit Navigation Options -->
                    <div class="flex flex-col sm:flex-row items-center justify-center gap-4 pt-4">
                        <button 
                            @click="resetFormState()" 
                            class="w-full sm:w-auto px-8 py-3.5 rounded-xl bg-red-600 hover:bg-red-700 text-white font-bold text-sm shadow-lg shadow-red-600/30 transition-all">
                            Daftar Lagi
                        </button>
                        <button 
                            @click="activeTab = 'gallery'" 
                            class="w-full sm:w-auto px-8 py-3.5 rounded-xl bg-slate-200 hover:bg-slate-300 text-slate-800 font-bold text-sm transition-all">
                            Kembali ke Gallery Kegiatan
                        </button>
                    </div>
                </div>

            </div>
        </section>

    </main>

    <!-- ==================== CUSTOM CONFIRMATION MODAL DIALOG ==================== -->
    <div x-show="showConfirmModal" x-transition.opacity class="fixed inset-0 z-50 flex items-center justify-center bg-slate-900/60 backdrop-blur-sm p-4">
        <div @click.outside="showConfirmModal = false" class="bg-white border border-slate-200 rounded-3xl p-6 sm:p-8 max-w-md w-full shadow-2xl space-y-6 text-center">
            <div class="w-16 h-16 bg-yellow-100 border border-yellow-300 rounded-full flex items-center justify-center mx-auto text-yellow-600">
                <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"></path>
                </svg>
            </div>
            <div class="space-y-2">
                <h3 class="text-xl font-bold text-slate-900">Konfirmasi Penyimpanan</h3>
                <p class="text-slate-600 text-sm font-medium">Apakah Anda sudah yakin untuk menyimpan?</p>
            </div>
            <div class="grid grid-cols-2 gap-4 pt-2">
                <button 
                    @click="showConfirmModal = false" 
                    class="w-full py-3 rounded-xl bg-slate-100 hover:bg-slate-200 text-slate-700 font-bold text-sm transition-all">
                    Tidak
                </button>
                <button 
                    @click="executeSave()" 
                    class="w-full py-3 rounded-xl bg-red-600 hover:bg-red-700 text-white font-bold text-sm shadow-md shadow-red-600/30 transition-all">
                    Ya
                </button>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="border-t border-slate-200 bg-white mt-20 py-8 text-center text-xs text-slate-500">
        <div class="max-w-7xl mx-auto px-4 flex flex-col sm:flex-row items-center justify-between gap-4">
            <p>&copy; 2026 RedCode Academy. Seluruh hak cipta dilindungi.</p>
            <div class="flex space-x-6 text-slate-600 font-medium">
                <span class="hover:text-red-600 cursor-pointer">Kebijakan Privasi</span>
                <span class="hover:text-red-600 cursor-pointer">Syarat & Ketentuan</span>
                <span class="hover:text-red-600 cursor-pointer">Bantuan</span>
            </div>
        </div>
    </footer>

    <!-- Application Script Logic -->
    <script>
        function codingAcademyApp() {
            return {
                activeTab: 'gallery',
                filterCategory: 'all',
                showConfirmModal: false,
                isSubmitted: false,
                formData: {
                    nik: '',
                    nama: '',
                    jenisKelamin: 'Laki-laki',
                    noHp: '',
                    bahasa: '',
                    alamat: ''
                },
                submittedData: {},

                triggerConfirmationModal() {
                    // Munculkan custom modal dialog konfirmasi
                    this.showConfirmModal = true;
                },

                executeSave() {
                    this.showConfirmModal = false;
                    // Simpan data dan ubah state form menjadi submitted
                    this.submittedData = { ...this.formData };
                    this.isSubmitted = true;
                    window.scrollTo({ top: 100, behavior: 'smooth' });
                },

                resetFormState() {
                    this.isSubmitted = false;
                    this.formData = {
                        nik: '',
                        nama: '',
                        jenisKelamin: 'Laki-laki',
                        noHp: '',
                        bahasa: '',
                        alamat: ''
                    };
                }
            }
        }
    </script>
</body>
</html>
