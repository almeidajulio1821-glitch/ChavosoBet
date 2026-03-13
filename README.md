<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>djbet - Plataforma de Apostas</title>
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0a0f1f 0%, #1a1f35 100%);
            color: #fff;
            min-height: 100vh;
        }
        
        /* Header e navegação */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 5%;
            background: rgba(10, 15, 31, 0.95);
            border-bottom: 2px solid #ffd700;
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: #ffd700;
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.5);
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
        }
        
        .nav-links a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            transition: 0.3s;
        }
        
        .nav-links a:hover {
            color: #ffd700;
        }
        
        .nav-buttons {
            display: flex;
            gap: 15px;
        }
        
        .btn {
            padding: 10px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
            cursor: pointer;
            border: none;
            font-size: 1rem;
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid #ffd700;
            color: #ffd700;
        }
        
        .btn-outline:hover {
            background: #ffd700;
            color: #0a0f1f;
        }
        
        .btn-solid {
            background: #ffd700;
            color: #0a0f1f;
            border: 2px solid #ffd700;
        }
        
        .btn-solid:hover {
            background: #ffed4a;
            border-color: #ffed4a;
        }
        
        /* Hero Section */
        .hero {
            text-align: center;
            padding: 80px 20px;
            background: linear-gradient(rgba(10, 15, 31, 0.8), rgba(10, 15, 31, 0.8)), url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><polygon points="0,100 100,0 100,100" fill="%23ffd700" opacity="0.1"/></svg>');
            background-size: cover;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #fff, #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .hero p {
            font-size: 1.3rem;
            color: #ccc;
            margin-bottom: 30px;
        }
        
        .hero-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
        }
        
        /* Cards de recursos */
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            padding: 50px 5%;
        }
        
        .feature-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 215, 0, 0.3);
            transition: 0.3s;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            border-color: #ffd700;
        }
        
        .feature-card i {
            font-size: 3rem;
            color: #ffd700;
            margin-bottom: 20px;
        }
        
        .feature-card h3 {
            margin-bottom: 15px;
        }
        
        /* Seção de jogos */
        .games-section {
            padding: 50px 5%;
            text-align: center;
        }
        
        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }
        
        .game-item {
            background: linear-gradient(145deg, #1e2440, #12172f);
            border-radius: 15px;
            padding: 40px 20px;
            cursor: pointer;
            transition: 0.3s;
            border: 1px solid transparent;
        }
        
        .game-item:hover {
            border-color: #ffd700;
            transform: scale(1.05);
        }
        
        .game-item i {
            font-size: 3rem;
            color: #ffd700;
            margin-bottom: 15px;
        }
        
        /* Modal de Login */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }
        
        .modal.active {
            display: flex;
        }
        
        .modal-content {
            background: #1a1f35;
            padding: 40px;
            border-radius: 20px;
            width: 90%;
            max-width: 400px;
            position: relative;
            border: 2px solid #ffd700;
        }
        
        .close-modal {
            position: absolute;
            top: 10px;
            right: 20px;
            font-size: 2rem;
            cursor: pointer;
            color: #ffd700;
        }
        
        .modal-content h2 {
            margin-bottom: 30px;
            color: #ffd700;
        }
        
        .modal-content input {
            width: 100%;
            padding: 15px;
            margin-bottom: 20px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid #ffd700;
            border-radius: 10px;
            color: #fff;
            font-size: 1rem;
        }
        
        .modal-content button {
            width: 100%;
            padding: 15px;
            background: #ffd700;
            color: #0a0f1f;
            border: none;
            border-radius: 10px;
            font-weight: bold;
            font-size: 1.1rem;
            cursor: pointer;
        }
        
        /* Página do Dashboard */
        .dashboard {
            display: none;
            padding: 50px 5%;
        }
        
        .dashboard.active {
            display: block;
        }
        
        .welcome-card {
            background: rgba(255, 215, 0, 0.1);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            margin-bottom: 40px;
            border: 2px solid #ffd700;
        }
        
        .balance {
            font-size: 3rem;
            color: #ffd700;
            margin: 20px 0;
        }
        
        /* Footer */
        footer {
            background: #0a0f1f;
            padding: 40px 5%;
            text-align: center;
            border-top: 2px solid #ffd700;
            margin-top: 50px;
        }
        
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                gap: 15px;
            }
            .nav-links {
                flex-wrap: wrap;
                justify-content: center;
            }
            .hero h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar">
        <div class="logo">djbet</div>
        <div class="nav-links">
            <a href="#" onclick="showPage('home')">Início</a>
            <a href="#" onclick="showPage('games')">Jogos</a>
            <a href="#" onclick="showPage('promotions')">Promoções</a>
            <a href="#" onclick="showPage('support')">Suporte</a>
        </div>
        <div class="nav-buttons">
            <button class="btn btn-outline" onclick="openModal('login')">Entrar</button>
            <button class="btn btn-solid" onclick="openModal('register')">Cadastrar</button>
        </div>
    </nav>

    <!-- Página Inicial -->
    <div id="home-page" class="page active">
        <!-- Hero Section -->
        <section class="hero">
            <h1>djbet - A Melhor Plataforma de Apostas</h1>
            <p>Experimente a emoção das apostas esportivas e jogos de cassino</p>
            <div class="hero-buttons">
                <button class="btn btn-solid" onclick="openModal('register')">Cadastre-se e Ganhe Bônus</button>
                <button class="btn btn-outline" onclick="showPage('games')">Ver Jogos</button>
            </div>
        </section>

        <!-- Recursos -->
        <section class="features">
            <div class="feature-card">
                <i class="fas fa-chart-line"></i>
                <h3>Odds Competitivas</h3>
                <p>As melhores cotações do mercado</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-shield-alt"></i>
                <h3>Segurança Garantida</h3>
                <p>Seus dados protegidos</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-bolt"></i>
                <h3>Saques Rápidos</h3>
                <p>Via PIX em minutos</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-gift"></i>
                <h3>Bônus Generosos</h3>
                <p>Para novos jogadores</p>
            </div>
        </section>
    </div>

    <!-- Página de Jogos -->
    <div id="games-page" class="page">
        <section class="games-section">
            <h2 style="font-size: 2.5rem; margin-bottom: 30px;">Nossos Jogos</h2>
            <div class="games-grid">
                <div class="game-item" onclick="alert('Jogo: Roleta - Demo')">
                    <i class="fas fa-circle"></i>
                    <h3>Roleta</h3>
                </div>
                <div class="game-item" onclick="alert('Jogo: Blackjack - Demo')">
                    <i class="fas fa-club"></i>
                    <h3>Blackjack</h3>
                </div>
                <div class="game-item" onclick="alert('Jogo: Slots - Demo')">
                    <i class="fas fa-star"></i>
                    <h3>Slots</h3>
                </div>
                <div class="game-item" onclick="alert('Jogo: Crash - Demo')">
                    <i class="fas fa-chart-line"></i>
                    <h3>Crash</h3>
                </div>
                <div class="game-item" onclick="alert('Jogo: Mines - Demo')">
                    <i class="fas fa-bomb"></i>
                    <h3>Mines</h3>
                </div>
                <div class="game-item" onclick="alert('Jogo: Poker - Demo')">
                    <i class="fas fa-diamond"></i>
                    <h3>Poker</h3>
                </div>
            </div>
        </section>
    </div>

    <!-- Página de Promoções -->
    <div id="promotions-page" class="page">
        <section class="games-section">
            <h2 style="font-size: 2.5rem; margin-bottom: 30px;">Promoções</h2>
            <div style="display: grid; gap: 20px; max-width: 600px; margin: 0 auto;">
                <div style="background: linear-gradient(145deg, #1e2440, #12172f); padding: 30px; border-radius: 15px; border-left: 5px solid #ffd700;">
                    <h3>Bônus de Boas-Vindas</h3>
                    <p>Ganhe até R$500 no primeiro depósito</p>
                </div>
                <div style="background: linear-gradient(145deg, #1e2440, #12172f); padding: 30px; border-radius: 15px; border-left: 5px solid #ffd700;">
                    <h3>Cashback Semanal</h3>
                    <p>10% de volta em todas as perdas</p>
                </div>
                <div style="background: linear-gradient(145deg, #1e2440, #12172f); padding: 30px; border-radius: 15px; border-left: 5px solid #ffd700;">
                    <h3>Torneios Diários</h3>
                    <p>Prêmios de R$10.000 todos os dias</p>
                </div>
            </div>
        </section>
    </div>

    <!-- Página de Suporte -->
    <div id="support-page" class="page">
        <section class="games-section">
            <h2 style="font-size: 2.5rem; margin-bottom: 30px;">Suporte</h2>
            <div style="max-width: 600px; margin: 0 auto; background: rgba(255,255,255,0.05); padding: 40px; border-radius: 20px;">
                <p style="margin-bottom: 30px;">Entre em contato conosco:</p>
                <div style="margin-bottom: 20px;">
                    <i class="fab fa-whatsapp" style="color: #25D366; font-size: 2rem; margin-right: 15px;"></i>
                    <span>(11) 99999-9999</span>
                </div>
                <div style="margin-bottom: 20px;">
                    <i class="far fa-envelope" style="color: #ffd700; font-size: 2rem; margin-right: 15px;"></i>
                    <span>suporte@djbet.com</span>
                </div>
                <div>
                    <i class="far fa-clock" style="color: #ffd700; font-size: 2rem; margin-right: 15px;"></i>
                    <span>24 horas por dia, 7 dias por semana</span>
                </div>
            </div>
        </section>
    </div>

    <!-- Dashboard (aparece após login) -->
    <div id="dashboard-page" class="dashboard">
        <div class="welcome-card">
            <h2>Bem-vindo de volta, <span id="user-name">Jogador</span>!</h2>
            <div class="balance">R$ 1.500,00</div>
            <p>Saldo disponível</p>
        </div>
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px;">
            <div style="background: rgba(255,215,0,0.1); padding: 20px; border-radius: 10px;">
                <h3>Últimas Apostas</h3>
                <p>• Roleta: R$50 - Ganhou</p>
                <p>• Crash: R$30 - Perdeu</p>
                <p>• Slots: R$20 - Ganhou</p>
            </div>
            <div style="background: rgba(255,215,0,0.1); padding: 20px; border-radius: 10px;">
                <h3>Bônus Disponíveis</h3>
                <p>• Cashback: R$15</p>
                <p>• Giros Grátis: 50</p>
            </div>
        </div>
    </div>

    <!-- Modal de Login/Cadastro -->
    <div id="auth-modal" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal()">&times;</span>
            <h2 id="modal-title">Entrar</h2>
            <input type="text" id="auth-name" placeholder="Nome" style="display: none;">
            <input type="email" id="auth-email" placeholder="E-mail">
            <input type="password" id="auth-password" placeholder="Senha">
            <button onclick="handleAuth()" id="auth-button">Entrar</button>
        </div>
    </div>

    <footer>
        <p>djbet - Todos os direitos reservados © 2025</p>
        <p style="margin-top: 10px; color: #999;">Menores de 18 anos não podem jogar. Jogue com responsabilidade.</p>
    </footer>

    <script>
        // Controle de páginas
        function showPage(pageName) {
            // Esconde todas as páginas
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            
            // Mostra a página selecionada
            document.getElementById(pageName + '-page').classList.add('active');
            
            // Esconde o dashboard se estiver visível
            document.getElementById('dashboard-page').classList.remove('active');
        }

        // Modal de autenticação
        let currentAuthMode = 'login';
        
        function openModal(mode) {
            currentAuthMode = mode;
            const modal = document.getElementById('auth-modal');
            const title = document.getElementById('modal-title');
            const nameField = document.getElementById('auth-name');
            const authButton = document.getElementById('auth-button');
            
            if (mode === 'login') {
                title.textContent = 'Entrar';
                nameField.style.display = 'none';
                authButton.textContent = 'Entrar';
            } else {
                title.textContent = 'Cadastrar';
                nameField.style.display = 'block';
                authButton.textContent = 'Cadastrar';
            }
            
            modal.classList.add('active');
        }
        
        function closeModal() {
            document.getElementById('auth-modal').classList.remove('active');
        }
        
        function handleAuth() {
            const email = document.getElementById('auth-email').value;
            const password = document.getElementById('auth-password').value;
            
            if (currentAuthMode === 'login') {
                // Login simulado
                if (email && password) {
                    alert('Login realizado com sucesso! (Modo demonstração)');
                    closeModal();
                    // Mostra o dashboard
                    document.querySelectorAll('.page').forEach(page => {
                        page.classList.remove('active');
                    });
                    document.getElementById('dashboard-page').classList.add('active');
                } else {
                    alert('Por favor, preencha todos os campos');
                }
            } else {
                // Cadastro simulado
                const name = document.getElementById('auth-name').value;
                if (name && email && password) {
                    alert('Cadastro realizado com sucesso! (Modo demonstração)');
                    closeModal();
                    // Mostra o dashboard
                    document.querySelectorAll('.page').forEach(page => {
                        page.classList.remove('active');
                    });
                    document.getElementById('dashboard-page').classList.add('active');
                } else {
                    alert('Por favor, preencha todos os campos');
                }
            }
        }

        // Fechar modal clicando fora
        window.onclick = function(event) {
            const modal = document.getElementById('auth-modal');
            if (event.target === modal) {
                closeModal();
            }
        }
    </script>
</body>
</html>
