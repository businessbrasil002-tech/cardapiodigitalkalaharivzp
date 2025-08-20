
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Cardápio Digital - Restaurante Kalahari</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Poppins:wght@400;600&display=swap');
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #0f0f0f;
            color: #e5e5e5;
        }
        
        .title-font {
            font-family: 'Playfair Display', serif;
        }
        
        .menu-item {
            transition: all 0.3s ease;
        }
        
        .menu-item:hover {
            transform: translateY(-5px);
        }
        
        .cart-item {
            border-bottom: 1px solid #333;
            padding-bottom: 1rem;
            margin-bottom: 1rem;
        }
        
        .hidden {
            display: none;
        }
        
        .menu-section {
            scroll-margin-top: 100px;
        }
        
        .hero-image {
            background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://img.restaurantguru.com/r689-interior-Kalahari-2021-09.jpg');
            background-size: cover;
            background-position: center;
        }
    </style>
</head>
<body class="min-h-screen">
    <!-- Header -->
    <header class="sticky top-0 z-50 bg-black shadow-lg">
        <div class="container mx-auto px-3 sm:px-4 py-2 sm:py-3 flex justify-between items-center">
            <h1 class="title-font text-xl sm:text-2xl md:text-3xl text-red-600">RESTAURANTE KALAHARI</h1>
            <div class="flex items-center space-x-4">
                <button id="menuBtn" class="text-white hover:text-red-500 transition">
                    <i class="fas fa-bars text-2xl"></i>
                </button>
                <button id="cartBtn" class="relative text-white hover:text-red-500 transition">
                    <i class="fas fa-shopping-cart text-2xl"></i>
                    <span id="cartCount" class="absolute -top-2 -right-2 bg-red-600 text-white text-xs font-bold rounded-full h-5 w-5 flex items-center justify-center hidden">0</span>
                </button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero-image h-48 sm:h-64 md:h-80 lg:h-96 flex items-center justify-center">
        <div class="text-center px-4">
            <h2 class="title-font text-4xl md:text-6xl text-white mb-4">Cardápio Digital</h2>
            <p class="text-xl text-gray-300">Sabores que conquistam paladares</p>
        </div>
    </section>

    <!-- Menu Navigation -->
    <nav id="menuNav" class="hidden sm:block bg-gray-900 sticky top-16 z-40 shadow-md">
        <div class="container mx-auto px-2 sm:px-4 overflow-x-auto">
            <div class="flex space-x-1 py-2 sm:py-3">
                <a href="#a-la-carte" class="px-4 py-2 text-sm font-medium text-white hover:bg-red-900 rounded transition">A La Carte</a>
                <a href="#carnes" class="px-4 py-2 text-sm font-medium text-white hover:bg-red-900 rounded transition">Carnes</a>
                <a href="#porcoes-fritas" class="px-4 py-2 text-sm font-medium text-white hover:bg-red-900 rounded transition">Porções de Fritas</a>
                <a href="#porcoes-peixe" class="px-4 py-2 text-sm font-medium text-white hover:bg-red-900 rounded transition">Porções de Peixe</a>
                <a href="#churrascos" class="px-4 py-2 text-sm font-medium text-white hover:bg-red-900 rounded transition">Churrascos</a>
                <a href="#pizzas" class="px-4 py-2 text-sm font-medium text-white hover:bg-red-900 rounded transition">Pizzas</a>
                <a href="#bebidas" class="px-4 py-2 text-sm font-medium text-white hover:bg-red-900 rounded transition">Bebidas</a>
                <a href="#sobremesas" class="px-4 py-2 text-sm font-medium text-white hover:bg-red-900 rounded transition">Sobremesas</a>
            </div>
        </div>
    </nav>

    <!-- Mobile Menu -->
    <div id="mobileMenu" class="fixed inset-0 bg-black bg-opacity-90 z-50 hidden">
        <div class="flex justify-end p-4">
            <button id="closeMenuBtn" class="text-white text-3xl">&times;</button>
        </div>
        <div class="flex flex-col items-center justify-center h-full">
            <a href="#a-la-carte" class="text-white text-2xl py-3 hover:text-red-500 transition">A La Carte</a>
            <a href="#carnes" class="text-white text-2xl py-3 hover:text-red-500 transition">Carnes</a>
            <a href="#porcoes-fritas" class="text-white text-2xl py-3 hover:text-red-500 transition">Porções de Fritas</a>
            <a href="#porcoes-peixe" class="text-white text-2xl py-3 hover:text-red-500 transition">Porções de Peixe</a>
            <a href="#churrascos" class="text-white text-2xl py-3 hover:text-red-500 transition">Churrascos</a>
            <a href="#pizzas" class="text-white text-2xl py-3 hover:text-red-500 transition">Pizzas</a>
            <a href="#bebidas" class="text-white text-2xl py-3 hover:text-red-500 transition">Bebidas</a>
            <a href="#sobremesas" class="text-white text-2xl py-3 hover:text-red-500 transition">Sobremesas</a>
        </div>
    </div>

    <!-- Main Content -->
    <main class="container mx-auto px-4 py-8">
        <!-- Menu Sections -->
        <section id="a-la-carte" class="menu-section mb-12">
            <h2 class="title-font text-2xl sm:text-3xl text-red-600 mb-4 sm:mb-6 border-b border-red-900 pb-2">A La Carte</h2>
            
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 sm:gap-6">
                <!-- CHURRASCO COMPLETO -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">CHURRASCO COMPLETO</h3>
                        <p class="text-gray-400 mb-4">(alcatra ou contra filé, arroz branco, tropeiro, maionese e fritas)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 100,00</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 130,00</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('CHURRASCO COMPLETO - Meia', 100.00)" class="bg-red-700 hover:bg-red-800 text-white px-4 py-2 rounded text-sm sm:text-base">Meia</button>
                                <button onclick="addToCart('CHURRASCO COMPLETO - Completa', 130.00)" class="bg-red-700 hover:bg-red-800 text-white px-4 py-2 rounded text-sm sm:text-base">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- CHURRASCO COMPLETO C/ PICANHA -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">CHURRASCO COMPLETO C/ PICANHA</h3>
                        <p class="text-gray-400 mb-4">(picanha, arroz branco, tropeiro, maionese e fritas)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 140,00</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 180,00</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('CHURRASCO COMPLETO C/ PICANHA - Meia', 140.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('CHURRASCO COMPLETO C/ PICANHA - Completa', 180.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- FILÉ À PARMEGIANA -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">FILÉ À PARMEGIANA</h3>
                        <p class="text-gray-400 mb-4">(arroz, purê de batatas ou fritas)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 100,00</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 120,00</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('FILÉ À PARMEGIANA - Meia', 100.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('FILÉ À PARMEGIANA - Completa', 120.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- FILÉ DE SURUBIM À PARMEGIANA -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">FILÉ DE SURUBIM À PARMEGIANA</h3>
                        <p class="text-gray-400 mb-4">(arroz branco, purê de batatas ou fritas)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$00,00</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 00,00</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('FILÉ DE SURUBIM À PARMEGIANA - Meia', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('FILÉ DE SURUBIM À PARMEGIANA - Completa', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- FILÉ DE SURUBIM À MILANESA -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">FILÉ DE SURUBIM À MILANESA</h3>
                        <p class="text-gray-400 mb-4">(arroz grego e salada)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$00,00</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 00,00</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('FILÉ DE SURUBIM À MILANESA - Meia', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('FILÉ DE SURUBIM À MILANESA - Completa', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- MUQUECA DE SURUBIM -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">MUQUECA DE SURUBIM</h3>
                        <p class="text-gray-400 mb-4">(surubim, arroz e pirão)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Completa: R$ 00,00</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('MUQUECA DE SURUBIM - Completa', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Carnes Section -->
        <section id="carnes" class="menu-section mb-12">
            <h2 class="title-font text-3xl text-red-600 mb-6 border-b border-red-900 pb-2">Carnes</h2>
            
            <div class="grid md:grid-cols-2 gap-6">
                <!-- Carne de Sol -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Carne de Sol c/ Mandioca ou Fritas</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 58,90</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 68,90</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('Carne de Sol c/ Mandioca ou Fritas - Meia', 58.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('Carne de Sol c/ Mandioca ou Fritas - Completa', 68.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Carne na Chapa Especial -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Carne na Chapa Especial</h3>
                        <p class="text-gray-400 mb-4">(contra filé, mandioca ou fritas, cebola, mussarela, bacon e orégano)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 69,90</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 84,90</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('Carne na Chapa Especial - Meia', 69.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('Carne na Chapa Especial - Completa', 84.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Frango à Passarinho -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Frango à Passarinho</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 00,00</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 00,00</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('Frango à Passarinho - Meia', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('Frango à Passarinho - Completa', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Porções de Fritas Section -->
        <section id="porcoes-fritas" class="menu-section mb-12">
            <h2 class="title-font text-3xl text-red-600 mb-6 border-b border-red-900 pb-2">Porções de Fritas</h2>
            
            <div class="grid md:grid-cols-2 gap-6">
                <!-- Fritas -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Fritas</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 28,00</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 39,90</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('Fritas - Meia', 28.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('Fritas - Completa', 39.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Fritas c/ Mussarela -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Fritas c/ Mussarela</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 39,90</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 54,50</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('Fritas c/ Mussarela - Meia', 39.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('Fritas c/ Mussarela - Completa', 54.50)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Fritas Especial -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Fritas Especial c/ mussarela e bacon</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 42,90</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 54,90</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('Fritas Especial c/ mussarela e bacon - Meia', 42.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('Fritas Especial c/ mussarela e bacon - Completa', 54.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Batata Americana -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Batata Americana (fritas c/ bacon e cebola)</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 35,00</p>
                                <p class="text-red-500 font-semibold">Completa: R$ 49,90</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('Batata Americana - Meia', 35.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('Batata Americana - Completa', 49.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Completa</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Porções de Peixe Section -->
        <section id="porcoes-peixe" class="menu-section mb-12">
            <h2 class="title-font text-3xl text-red-600 mb-6 border-b border-red-900 pb-2">Porções de Peixe</h2>
            
            <div class="grid md:grid-cols-2 gap-6">
                <!-- SURUBIM À PALITO -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">SURUBIM À PALITO</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 00,00</p>
                                <p class="text-red-500 font-semibold">Inteira: R$ 00,00</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('SURUBIM À PALITO - Meia', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('SURUBIM À PALITO - Inteira', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Inteira</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- PEIXE SEM ESPINHO -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">PEIXE SEM ESPINHO (traíra, curimată ou tilápia)</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Meia: R$ 79,90</p>
                                <p class="text-red-500 font-semibold">Inteira: R$ 89,90</p>
                            </div>
                            <div class="flex space-x-2">
                                <button onclick="addToCart('PEIXE SEM ESPINHO - Meia', 79.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Meia</button>
                                <button onclick="addToCart('PEIXE SEM ESPINHO - Inteira', 89.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Inteira</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Churrascos Section -->
        <section id="churrascos" class="menu-section mb-12">
            <h2 class="title-font text-3xl text-red-600 mb-6 border-b border-red-900 pb-2">Churrascos</h2>
            
            <div class="grid md:grid-cols-2 gap-6">
                <!-- PICANHA -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">PICANHA</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">300g: R$ 63,00</p>
                                <p class="text-red-500 font-semibold">500g: R$ 95,00</p>
                                <p class="text-red-500 font-semibold">1Kg: R$ 190,00</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('PICANHA - 300g', 63.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">300g</button>
                                <button onclick="addToCart('PICANHA - 500g', 95.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">500g</button>
                                <button onclick="addToCart('PICANHA - 1Kg', 190.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">1Kg</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- ALCATRA -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">ALCATRA</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">300g: R$ 42,00</p>
                                <p class="text-red-500 font-semibold">500g: R$ 65,00</p>
                                <p class="text-red-500 font-semibold">1Kg: R$ 130,00</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('ALCATRA - 300g', 42.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">300g</button>
                                <button onclick="addToCart('ALCATRA - 500g', 65.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">500g</button>
                                <button onclick="addToCart('ALCATRA - 1Kg', 130.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">1Kg</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- CONTRA FILÉ -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">CONTRA FILÉ</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">300g: R$ 42,00</p>
                                <p class="text-red-500 font-semibold">500g: R$ 65,00</p>
                                <p class="text-red-500 font-semibold">1Kg: R$ 130,00</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('CONTRA FILÉ - 300g', 42.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">300g</button>
                                <button onclick="addToCart('CONTRA FILÉ - 500g', 65.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">500g</button>
                                <button onclick="addToCart('CONTRA FILÉ - 1Kg', 130.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">1Kg</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- LOMBO SUÍNO -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">LOMBO SUÍNO</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">300g: R$ 00,00</p>
                                <p class="text-red-500 font-semibold">500g: R$ 00,00</p>
                                <p class="text-red-500 font-semibold">1Kg: R$ 00,00</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('LOMBO SUÍNO - 300g', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">300g</button>
                                <button onclick="addToCart('LOMBO SUÍNO - 500g', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">500g</button>
                                <button onclick="addToCart('LOMBO SUÍNO - 1Kg', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">1Kg</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- CORAÇÃO -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">CORAÇÃO</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">300g: R$ 35,00</p>
                                <p class="text-red-500 font-semibold">500g: R$ 45,00</p>
                                <p class="text-red-500 font-semibold">1Kg: R$ 90,00</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('CORAÇÃO - 300g', 35.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">300g</button>
                                <button onclick="addToCart('CORAÇÃO - 500g', 45.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">500g</button>
                                <button onclick="addToCart('CORAÇÃO - 1Kg', 90.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">1Kg</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- MUSSARELA -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">MUSSARELA (Unidade)</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">R$ 25,00</p>
                            </div>
                            <div>
                                <button onclick="addToCart('MUSSARELA (Unidade)', 25.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Adicionar</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- PÃO DE ALHO -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">PÃO DE ALHO (Unidade)</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">R$ 12,00</p>
                            </div>
                            <div>
                                <button onclick="addToCart('PÃO DE ALHO (Unidade)', 12.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Adicionar</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Pizzas Section -->
        <section id="pizzas" class="menu-section mb-12">
            <h2 class="title-font text-3xl text-red-600 mb-6 border-b border-red-900 pb-2">Pizzas</h2>
            
            <div class="grid md:grid-cols-2 gap-6">
                <!-- MINEIRA -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">MINEIRA</h3>
                        <p class="text-gray-400 mb-4">(mussarela, presunto, calabresa, cebola, azeitona, pimentão, tomate e orégano)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Pequena: R$ 42,90</p>
                                <p class="text-red-500 font-semibold">Grande: R$ 59,90</p>
                                <p class="text-red-500 font-semibold">Gigante: R$ 79,90</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('Pizza MINEIRA - Pequena', 42.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Pequena</button>
                                <button onclick="addToCart('Pizza MINEIRA - Grande', 59.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Grande</button>
                                <button onclick="addToCart('Pizza MINEIRA - Gigante', 79.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Gigante</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- MINEIRA ESPECIAL -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">MINEIRA ESPECIAL</h3>
                        <p class="text-gray-400 mb-4">(mussarela, presunto, calabresa, cebola, pimentão, tomate, azeitona, milho verde, uva passas e orégano)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Pequena: R$ 42,90</p>
                                <p class="text-red-500 font-semibold">Grande: R$ 59,90</p>
                                <p class="text-red-500 font-semibold">Gigante: R$ 79,90</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('Pizza MINEIRA ESPECIAL - Pequena', 42.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Pequena</button>
                                <button onclick="addToCart('Pizza MINEIRA ESPECIAL - Grande', 59.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Grande</button>
                                <button onclick="addToCart('Pizza MINEIRA ESPECIAL - Gigante', 79.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Gigante</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- À MODA -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">À MODA</h3>
                        <p class="text-gray-400 mb-4">(mussarela, peito de frango, presunto, calabresa, bacon, milho verde, azeitona, pimentão, tomate e orégano)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Pequena: R$ 42,90</p>
                                <p class="text-red-500 font-semibold">Grande: R$ 59,90</p>
                                <p class="text-red-500 font-semibold">Gigante: R$ 79,90</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('Pizza À MODA - Pequena', 42.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Pequena</button>
                                <button onclick="addToCart('Pizza À MODA - Grande', 59.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Grande</button>
                                <button onclick="addToCart('Pizza À MODA - Gigante', 79.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Gigante</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- FESTIVA -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">FESTIVA</h3>
                        <p class="text-gray-400 mb-4">(mussarela, presunto, uva passas, azeitona e orégano)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Pequena: R$ 42,90</p>
                                <p class="text-red-500 font-semibold">Grande: R$ 59,90</p>
                                <p class="text-red-500 font-semibold">Gigante: R$ 79,90</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('Pizza FESTIVA - Pequena', 42.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Pequena</button>
                                <button onclick="addToCart('Pizza FESTIVA - Grande', 59.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Grande</button>
                                <button onclick="addToCart('Pizza FESTIVA - Gigante', 79.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Gigante</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- PEITO DE FRANGO -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">PEITO DE FRANGO</h3>
                        <p class="text-gray-400 mb-4">(molho à bolonhesa, mussarela, palmito, peito de frango e orégano)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Pequena: R$ 42,90</p>
                                <p class="text-red-500 font-semibold">Grande: R$ 59,90</p>
                                <p class="text-red-500 font-semibold">Gigante: R$ 79,90</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('Pizza PEITO DE FRANGO - Pequena', 42.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Pequena</button>
                                <button onclick="addToCart('Pizza PEITO DE FRANGO - Grande', 59.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Grande</button>
                                <button onclick="addToCart('Pizza PEITO DE FRANGO - Gigante', 79.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Gigante</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- PEITO DE FRANGO E CATUPIRY -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">PEITO DE FRANGO E CATUPIRY</h3>
                        <p class="text-gray-400 mb-4">(mussarela, peito de frango e catupiry)</p>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">Pequena: R$ 42,90</p>
                                <p class="text-red-500 font-semibold">Grande: R$ 59,90</p>
                                <p class="text-red-500 font-semibold">Gigante: R$ 79,90</p>
                            </div>
                            <div class="flex flex-col space-y-2">
                                <button onclick="addToCart('Pizza PEITO DE FRANGO E CATUPIRY - Pequena', 42.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Pequena</button>
                                <button onclick="addToCart('Pizza PEITO DE FRANGO E CATUPIRY - Grande', 59.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Grande</button>
                                <button onclick="addToCart('Pizza PEITO DE FRANGO E CATUPIRY - Gigante', 79.90)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Gigante</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Bebidas Section -->
        <section id="bebidas" class="menu-section mb-12">
            <h2 class="title-font text-3xl text-red-600 mb-6 border-b border-red-900 pb-2">Bebidas</h2>
            
            <div class="grid md:grid-cols-2 gap-6">
                <!-- Refrigerantes -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Refrigerantes</h3>
                        <div class="grid grid-cols-2 gap-2">
                            <div>
                                <p class="text-gray-400">2 Litros</p>
                                <p class="text-red-500 font-semibold">R$ 18,00</p>
                                <button onclick="addToCart('Refrigerante 2 Litros', 18.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">1 Litro</p>
                                <p class="text-red-500 font-semibold">R$ 12,00</p>
                                <button onclick="addToCart('Refrigerante 1 Litro', 12.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">600 ml</p>
                                <p class="text-red-500 font-semibold">R$ 9,00</p>
                                <button onclick="addToCart('Refrigerante 600 ml', 9.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">KS</p>
                                <p class="text-red-500 font-semibold">R$ 6,00</p>
                                <button onclick="addToCart('Refrigerante KS', 6.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">Lata</p>
                                <p class="text-red-500 font-semibold">R$ 7,00</p>
                                <button onclick="addToCart('Refrigerante Lata', 7.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">220 ml</p>
                                <p class="text-red-500 font-semibold">R$ 3,00</p>
                                <button onclick="addToCart('Refrigerante 220 ml', 3.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Águas -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Águas</h3>
                        <div class="grid grid-cols-2 gap-2">
                            <div>
                                <p class="text-gray-400">Água com Gás 500 ml</p>
                                <p class="text-red-500 font-semibold">R$ 5,00</p>
                                <button onclick="addToCart('Água com Gás 500 ml', 5.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">Água Sem Gás 500 ml</p>
                                <p class="text-red-500 font-semibold">R$ 3,00</p>
                                <button onclick="addToCart('Água Sem Gás 500 ml', 3.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">Água Mineral 1,5 Litros</p>
                                <p class="text-red-500 font-semibold">R$ 7,00</p>
                                <button onclick="addToCart('Água Mineral 1,5 Litros', 7.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">Água Tônica</p>
                                <p class="text-red-500 font-semibold">R$ 6,00</p>
                                <button onclick="addToCart('Água Tônica', 6.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">H2OH!</p>
                                <p class="text-red-500 font-semibold">R$ 8,00</p>
                                <button onclick="addToCart('H2OH!', 8.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Sucos -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Sucos</h3>
                        <p class="text-gray-400 mb-2">Suco Natural (todos por R$ 8,00):</p>
                        <div class="grid grid-cols-2 gap-2 mb-3">
                            <button onclick="addToCart('Suco Natural - Laranja', 10.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs">Laranja</button>
                            <button onclick="addToCart('Suco Natural - Abacaxi', 10.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs">Abacaxi</button>
                            <button onclick="addToCart('Suco Natural - Abacaxi com Hortelã', 10.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs">Abacaxi c/ Hortelã</button>
                            <button onclick="addToCart('Suco Natural - Maracujá', 10.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs">Maracujá</button>
                            <button onclick="addToCart('Suco Natural - Tamarindo', 10.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs">Tamarindo</button>
                            <button onclick="addToCart('Suco Natural - Acerola', 10.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs">Acerola</button>
                            <button onclick="addToCart('Suco Natural - Suco Del valle', 6.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs">Suco Mais</button>
                        </div>
                        
                        <p class="text-gray-400 mb-1">Limonada Suíça: R$ 10,00</p>
                        <button onclick="addToCart('Limonada Suíça', 10.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mb-3">Add</button>
                        
                        <p class="text-gray-400 mb-1">Jarras:</p>
                        <div class="flex space-x-2 mb-3">
                            <button onclick="addToCart('Jarra de Suco - 1 Jarra', 30.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs">1 Jarra</button>
                            <button onclick="addToCart('Jarra de Suco - 1/2 Jarra', 23.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs">1/2 Jarra</button>
                        </div>
                        
                        <p class="text-gray-400 mb-1">Suco Detox (Abacaxi, Hortelã, Gengibre e Couve): R$ 00,00</p>
                        <button onclick="addToCart('Suco Detox', 00.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs">Add</button>
                    </div>
                </div>
                
                <!-- Cervejas -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Cervejas</h3>
                        <div class="grid grid-cols-2 gap-2">
                            <div>
                                <p class="text-gray-400">Brahma 600ml</p>
                                <p class="text-red-500 font-semibold">R$ 10,00</p>
                                <button onclick="addToCart('Brahma 600ml', 10.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">Skol 600ml</p>
                                <p class="text-red-500 font-semibold">R$ 10,00</p>
                                <button onclick="addToCart('Skol 600ml', 10.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">Antarctica Original 600ml</p>
                                <p class="text-red-500 font-semibold">R$ 12,00</p>
                                <button onclick="addToCart('Antarctica Original 600ml', 12.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">Heineken 600ml</p>
                                <p class="text-red-500 font-semibold">R$ 15,00</p>
                                <button onclick="addToCart('Heineken 600ml', 15.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">Cerveja Lata</p>
                                <p class="text-red-500 font-semibold">R$ 7,00</p>
                                <button onclick="addToCart('Cerveja Lata', 7.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                            <div>
                                <p class="text-gray-400">Cerveja Lata Sem Álcool</p>
                                <p class="text-red-500 font-semibold">R$ 7,00</p>
                                <button onclick="addToCart('Cerveja Lata Sem Álcool', 7.00)" class="bg-red-700 hover:bg-red-800 text-white px-2 py-1 rounded text-xs mt-1">Add</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Sobremesas Section -->
        <section id="sobremesas" class="menu-section mb-12">
            <h2 class="title-font text-3xl text-red-600 mb-6 border-b border-red-900 pb-2">Sobremesas</h2>
            
            <div class="grid md:grid-cols-2 gap-6">
                <!-- Pudim de Leite Condensado -->
                <div class="menu-item bg-gray-800 rounded-lg overflow-hidden shadow-lg">
                    <div class="p-5">
                        <h3 class="text-xl font-bold text-white mb-2">Pudim de Leite Condensado</h3>
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-red-500 font-semibold">R$ 10,00</p>
                            </div>
                            <div>
                                <button onclick="addToCart('Pudim de Leite Condensado', 10.00)" class="bg-red-700 hover:bg-red-800 text-white px-3 py-1 rounded text-sm">Adicionar</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Shopping Cart Sidebar -->
    <div id="cartSidebar" class="fixed inset-y-0 right-0 w-full sm:w-96 bg-gray-900 shadow-xl transform translate-x-full transition-transform duration-300 ease-in-out z-50 overflow-y-auto">
        <div class="p-6">
            <div class="flex justify-between items-center mb-6">
                <h2 class="title-font text-2xl text-red-600">Seu Pedido</h2>
                <button id="closeCartBtn" class="text-white text-2xl">&times;</button>
            </div>
            
            <div id="cartItems" class="mb-6">
                <!-- Cart items will be added here dynamically -->
                <p class="text-gray-400 text-center py-10">Seu carrinho está vazio</p>
            </div>
            
            <div class="border-t border-gray-700 pt-4 mb-6">
                <div class="flex justify-between mb-2">
                    <span class="text-gray-400">Subtotal:</span>
                    <span id="subtotal" class="text-white font-bold">R$ 0,00</span>
                </div>
                <div class="flex justify-between mb-4">
                    <span class="text-gray-400">Taxa de entrega:</span>
                    <span class="text-white font-bold">A calcular</span>
                </div>
                <div class="flex justify-between text-xl">
                    <span class="text-white">Total:</span>
                    <span id="total" class="text-red-500 font-bold">R$ 0,00</span>
                </div>
            </div>
            
            <!-- Customer Info Form -->
            <div id="customerInfo" class="mb-6">
                <h3 class="text-lg text-white mb-4">Informações para Entrega</h3>
                <div class="space-y-4">
                    <div>
                        <label for="customerName" class="block text-gray-400 mb-1">Nome</label>
                        <input type="text" id="customerName" class="w-full bg-gray-800 border border-gray-700 rounded px-3 py-3 sm:py-2 text-white focus:outline-none focus:ring-2 focus:ring-red-600 text-sm sm:text-base">
                    </div>
                    <div>
                        <label for="customerAddress" class="block text-gray-400 mb-1">Endereço</label>
                        <input type="text" id="customerAddress" class="w-full bg-gray-800 border border-gray-700 rounded px-3 py-2 text-white focus:outline-none focus:ring-2 focus:ring-red-600">
                    </div>
                    <div>
                        <label for="customerPhone" class="block text-gray-400 mb-1">Telefone</label>
                        <input type="tel" id="customerPhone" class="w-full bg-gray-800 border border-gray-700 rounded px-3 py-2 text-white focus:outline-none focus:ring-2 focus:ring-red-600">
                    </div>
                </div>
            </div>
            
            <!-- Payment Method -->
            <div id="paymentMethod" class="mb-6">
                <h3 class="text-lg text-white mb-4">Forma de Pagamento</h3>
                <div class="space-y-3">
                    <div class="flex items-center">
                        <input type="radio" id="paymentCard" name="paymentMethod" value="Cartão" class="h-4 w-4 text-red-600 focus:ring-red-500 border-gray-700 bg-gray-800">
                        <label for="paymentCard" class="ml-2 block text-gray-300">Cartão</label>
                    </div>
                    <div class="flex items-center">
                        <input type="radio" id="paymentCash" name="paymentMethod" value="Dinheiro" class="h-4 w-4 text-red-600 focus:ring-red-500 border-gray-700 bg-gray-800">
                        <label for="paymentCash" class="ml-2 block text-gray-300">Dinheiro</label>
                    </div>
                    <div class="flex items-center">
                        <input type="radio" id="paymentPix" name="paymentMethod" value="PIX" class="h-4 w-4 text-red-600 focus:ring-red-500 border-gray-700 bg-gray-800">
                        <label for="paymentPix" class="ml-2 block text-gray-300">PIX</label>
                    </div>
                </div>
                
                <!-- Change for cash -->
                <div id="changeField" class="mt-4 hidden">
                    <label for="needsChange" class="block text-gray-400 mb-1">Precisa de troco?</label>
                    <div class="flex items-center space-x-4">
                        <div class="flex items-center">
                            <input type="radio" id="needsChangeYes" name="needsChange" value="Sim" class="h-4 w-4 text-red-600 focus:ring-red-500 border-gray-700 bg-gray-800">
                            <label for="needsChangeYes" class="ml-2 block text-gray-300">Sim</label>
                        </div>
                        <div class="flex items-center">
                            <input type="radio" id="needsChangeNo" name="needsChange" value="Não" checked class="h-4 w-4 text-red-600 focus:ring-red-500 border-gray-700 bg-gray-800">
                            <label for="needsChangeNo" class="ml-2 block text-gray-300">Não</label>
                        </div>
                    </div>
                    <div id="changeAmountField" class="mt-2 hidden">
                        <label for="changeAmount" class="block text-gray-400 mb-1">Valor para troco</label>
                        <input type="number" id="changeAmount" class="w-full bg-gray-800 border border-gray-700 rounded px-3 py-2 text-white focus:outline-none focus:ring-2 focus:ring-red-600" placeholder="R$">
                    </div>
                </div>
            </div>
            
            <!-- Submit Order Button -->
            <button id="submitOrderBtn" class="w-full bg-red-700 hover:bg-red-800 text-white font-bold py-3 px-4 rounded-lg transition disabled:opacity-50 disabled:cursor-not-allowed" disabled>
                ENVIAR PEDIDO
            </button>
        </div>
    </div>

    <!-- Overlay -->
    <div id="overlay" class="fixed inset-0 bg-black bg-opacity-50 z-40 hidden" style="backdrop-filter: blur(2px);"></div>

    <script>
        // Cart functionality
        let cart = []; // Array of {name, price, quantity}
        
        // DOM Elements
        const menuBtn = document.getElementById('menuBtn');
        const closeMenuBtn = document.getElementById('closeMenuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        const cartBtn = document.getElementById('cartBtn');
        const closeCartBtn = document.getElementById('closeCartBtn');
        const cartSidebar = document.getElementById('cartSidebar');
        const overlay = document.getElementById('overlay');
        const cartCount = document.getElementById('cartCount');
        const cartItems = document.getElementById('cartItems');
        const subtotalEl = document.getElementById('subtotal');
        const totalEl = document.getElementById('total');
        const submitOrderBtn = document.getElementById('submitOrderBtn');
        const paymentMethodRadios = document.querySelectorAll('input[name="paymentMethod"]');
        const cashRadio = document.getElementById('paymentCash');
        const changeField = document.getElementById('changeField');
        const needsChangeRadios = document.querySelectorAll('input[name="needsChange"]');
        const changeAmountField = document.getElementById('changeAmountField');
        
        // Customer info fields
        const customerName = document.getElementById('customerName');
        const customerAddress = document.getElementById('customerAddress');
        const customerPhone = document.getElementById('customerPhone');
        
        // Event Listeners
        menuBtn.addEventListener('click', () => {
            mobileMenu.classList.remove('hidden');
            overlay.classList.remove('hidden');
        });
        
        closeMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.add('hidden');
            overlay.classList.add('hidden');
        });
        
        cartBtn.addEventListener('click', () => {
            if (cartSidebar.classList.contains('translate-x-full')) {
                cartSidebar.classList.remove('translate-x-full');
                overlay.classList.remove('hidden');
                updateCartDisplay();
            } else {
                cartSidebar.classList.add('translate-x-full');
                overlay.classList.add('hidden');
            }
        });
        
        closeCartBtn.addEventListener('click', () => {
            cartSidebar.classList.add('translate-x-full');
            overlay.classList.add('hidden');
        });
        
        overlay.addEventListener('click', () => {
            cartSidebar.classList.add('translate-x-full');
            mobileMenu.classList.add('hidden');
            overlay.classList.add('hidden');
        });
        
        // Payment method change
        paymentMethodRadios.forEach(radio => {
            radio.addEventListener('change', () => {
                if (cashRadio.checked) {
                    changeField.classList.remove('hidden');
                } else {
                    changeField.classList.add('hidden');
                    changeAmountField.classList.add('hidden');
                }
            });
        });

        needsChangeRadios.forEach(radio => {
            radio.addEventListener('change', () => {
                if (document.getElementById('needsChangeYes').checked) {
                    changeAmountField.classList.remove('hidden');
                } else {
                    changeAmountField.classList.add('hidden');
                }
            });
        });

        // Global functions
        window.addToCart = function(name, price) {
            // Check if item already exists in cart
            const existingItem = cart.find(item => item.name === name);
            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({ name, price, quantity: 1 });
            }
            updateCartCount();
            updateCartDisplay();
            
            // Show feedback
            const btn = event.target;
            btn.innerHTML = '<i class="fas fa-check"></i>';
            btn.classList.remove('bg-red-700');
            btn.classList.add('bg-green-600');
            setTimeout(() => {
                btn.innerHTML = 'Adicionado';
                setTimeout(() => {
                    btn.innerHTML = 'Adicionar';
                    btn.classList.remove('bg-green-600');
                    btn.classList.add('bg-red-700');
                }, 1000);
            }, 500);
            
            // Show cart sidebar when adding items
            if (cartSidebar.classList.contains('translate-x-full')) {
                cartSidebar.classList.remove('translate-x-full');
                overlay.classList.remove('hidden');
            }
        }

        window.removeFromCart = function(index) {
            if (confirm('Tem certeza que deseja remover este item?')) {
                cart.splice(index, 1);
                updateCartCount();
                updateCartDisplay();
            }
        }

        window.updateQuantity = function(index, newQuantity) {
            if (newQuantity < 1) {
                if (confirm('Remover este item do carrinho?')) {
                    removeFromCart(index);
                }
                return;
            }
            cart[index].quantity = newQuantity;
            updateCartDisplay();
        }

        // Update cart count display
        function updateCartCount() {
            const count = cart.length;
            cartCount.textContent = count;
            if (count > 0) {
                cartCount.classList.remove('hidden');
            } else {
                cartCount.classList.add('hidden');
            }
        }

        // Update cart display
        function updateCartDisplay() {
            if (cart.length === 0) {
                cartItems.innerHTML = '<p class="text-gray-400 text-center py-10">Seu carrinho está vazio</p>';
                subtotalEl.textContent = 'R$ 0,00';
                totalEl.textContent = 'R$ 0,00';
                submitOrderBtn.disabled = true;
                return;
                subtotalEl.textContent = 'R$ 0,00';
                totalEl.textContent = 'R$ 0,00';
                submitOrderBtn.disabled = true;
                return;
            }

            let html = '';
            let subtotal = 0;

            cart.forEach((item, index) => {
                subtotal += item.price * item.quantity;
                html += `
                    <div class="cart-item">
                        <div class="flex justify-between">
                            <div>
                                <h4 class="text-white font-medium">${item.name}</h4>
                                <p class="text-red-500">R$ ${(item.price * item.quantity).toFixed(2).replace('.', ',')}</p>
                            </div>
                            <div class="flex items-center space-x-2">
                                <button onclick="updateQuantity(${index}, ${item.quantity - 1})" class="text-white bg-gray-700 hover:bg-gray-600 w-8 h-8 sm:w-6 sm:h-6 rounded flex items-center justify-center">
                                    <i class="fas fa-minus text-sm sm:text-xs"></i>
                                </button>
                                <span class="text-white mx-1 sm:mx-0">${item.quantity}</span>
                                <button onclick="updateQuantity(${index}, ${item.quantity + 1})" class="text-white bg-gray-700 hover:bg-gray-600 w-8 h-8 sm:w-6 sm:h-6 rounded flex items-center justify-center">
                                    <i class="fas fa-plus text-sm sm:text-xs"></i>
                                </button>
                                <button onclick="removeFromCart(${index})" class="text-red-500 hover:text-red-700 ml-2">
                                    <i class="fas fa-trash-alt"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                `;
            });

            cartItems.innerHTML = html;
            subtotalEl.textContent = `R$ ${subtotal.toFixed(2).replace('.', ',')}`;
            totalEl.textContent = `R$ ${subtotal.toFixed(2).replace('.', ',')}`;

            // Enable submit button if customer info is filled
            checkFormCompletion();
        }

        // Check if form is complete to enable submit button
        function checkFormCompletion() {
            const isComplete = customerName.value && customerAddress.value && customerPhone.value;
            submitOrderBtn.disabled = !isComplete || cart.length === 0;
        }

        // Add event listeners for form fields
        customerName.addEventListener('input', checkFormCompletion);
        customerAddress.addEventListener('input', checkFormCompletion);
        customerPhone.addEventListener('input', checkFormCompletion);

        // Submit order
        submitOrderBtn.addEventListener('click', function() {
            const paymentMethod = document.querySelector('input[name="paymentMethod"]:checked').value;
            const needsChange = document.getElementById('needsChangeYes')?.checked || false;
            const changeAmount = document.getElementById('changeAmount')?.value || 0;
            const total = totalEl.textContent;
            
            // Build WhatsApp message
            let message = `*NOVO PEDIDO - RESTAURANTE KALAHARI*%0A%0A`;
            message += `*Cliente:* ${customerName.value}%0A`;
            message += `*Endereço:* ${customerAddress.value}%0A`;
            message += `*Telefone:* ${customerPhone.value}%0A%0A`;
            message += `*Itens do Pedido:*%0A`;
            
            cart.forEach(item => {
                message += `- ${item.name} (${item.quantity}x) - R$ ${(item.price * item.quantity).toFixed(2).replace('.', ',')}%0A`;
            });
            
            message += `%0A*Total:* ${total}%0A`;
            message += `*Forma de Pagamento:* ${paymentMethod}%0A`;
            
            if (paymentMethod === 'Dinheiro' && needsChange) {
                message += `*Troco para:* R$ ${parseFloat(changeAmount).toFixed(2).replace('.', ',')}%0A`;
            }
            
            message += `%0A*Obrigado pelo pedido!*`;
            
            // Open WhatsApp with the order details
            window.open(`https://wa.me/5538998551950?text=${message}`, '_blank');
            
            // Clear cart after submission
            cart = [];
            updateCartCount();
            updateCartDisplay();
            
            // Reset form
            customerName.value = '';
            customerAddress.value = '';
            customerPhone.value = '';
            document.getElementById('paymentCard').checked = true;
            document.getElementById('needsChangeNo').checked = true;
            changeField.classList.add('hidden');
            changeAmountField.classList.add('hidden');
            
            // Close cart
            cartSidebar.classList.add('translate-x-full');
            overlay.classList.add('hidden');
        });

        // Initialize cart count
        updateCartCount();
    </script>
</body>
</html>
