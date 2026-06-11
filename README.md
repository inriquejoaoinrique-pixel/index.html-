<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jotapemartking | Inteligência Digital e Escala de Vendas</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* CONFIGURAÇÕES GERAIS E PALETA MULTI-AZUL */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            scroll-behavior: smooth;
        }

        :root {
            --bg-deep: #030914;       /* Azul Espacial Ultra Escuro (Fundo de Alto Padrão) */
            --bg-card: #0a1326;       /* Azul Sólido para Blocos de Destaque */
            --blue-main: #0052d4;     /* Azul Royal (Garante Autoridade e Confiança) */
            --blue-electric: #00d2ff; /* Azul Ciano Magnético / Neon (Idêntico à Logo JP) */
            --text-muted: #94a3b8;    /* Cinza Azulado para leitura confortável */
            --white: #ffffff;
        }

        body {
            background-color: var(--bg-deep);
            color: var(--white);
            overflow-x: hidden;
            line-height: 1.6;
        }

        a { text-decoration: none; color: inherit; }

        /* HEADER FLUTUANTE */
        header {
            background-color: rgba(3, 9, 20, 0.95);
            backdrop-filter: blur(12px);
            padding: 15px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(0, 210, 255, 0.12);
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo-circulo {
            width: 48px;
            height: 48px;
            background-color: #070d19;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 900;
            font-size: 20px;
            letter-spacing: -1px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 0 15px rgba(0, 210, 255, 0.2);
        }

        .logo-circulo .letra-j { color: var(--blue-electric); text-shadow: 0 0 8px rgba(0, 210, 255, 0.6); }
        .logo-circulo .letra-p { color: var(--white); }

        .logo-texto {
            font-size: 18px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            line-height: 1;
        }

        .logo-texto span {
            display: block;
            font-size: 11px;
            color: var(--blue-electric);
            font-weight: 600;
            margin-top: 3px;
            letter-spacing: 1px;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 35px;
        }

        nav ul li a {
            font-weight: 600;
            font-size: 15px;
            color: var(--white);
            transition: color 0.3s ease;
        }

        nav ul li a:hover { color: var(--blue-electric); }

        /* PADRONIZAÇÃO DE SEÇÕES */
        section { padding: 110px 8%; }

        .header-secao {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 65px auto;
        }

        .header-secao h2 {
            font-size: 40px;
            font-weight: 800;
            margin-bottom: 15px;
            letter-spacing: -0.5px;
        }

        .header-secao h2 span { color: var(--blue-electric); }
        .header-secao p { font-size: 18px; color: var(--text-muted); }

        /* 1º BLOCO: SEÇÃO HERO (INÍCIO) */
        .hero {
            min-height: 100vh;
            background: radial-gradient(circle at top right, #091e3d 0%, var(--bg-deep) 75%);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 140px 8% 80px 8%;
            text-align: center;
        }

        .hero-emblema-logo {
            width: 90px;
            height: 90px;
            background-color: #070d19;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 900;
            font-size: 38px;
            letter-spacing: -2px;
            border: 2px solid var(--blue-electric);
            box-shadow: 0 0 30px rgba(0, 210, 255, 0.3);
            margin-bottom: 25px;
        }
        .hero-emblema-logo .letra-j { color: var(--blue-electric); text-shadow: 0 0 10px rgba(0, 210, 255, 0.6); }
        .hero-emblema-logo .letra-p { color: var(--white); }

        .badge-tag {
            background: rgba(0, 210, 255, 0.08);
            border: 1px solid var(--blue-electric);
            color: var(--blue-electric);
            padding: 8px 22px;
            border-radius: 50px;
            font-size: 13px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            margin-bottom: 30px;
            animation: pulse-glow 2.5s infinite;
        }

        .hero h1 {
            font-size: 54px;
            font-weight: 900;
            line-height: 1.15;
            max-width: 950px;
            margin-bottom: 25px;
            letter-spacing: -1px;
        }

        .hero h1 span {
            background: linear-gradient(45deg, var(--blue-electric), #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 20px;
            color: var(--text-muted);
            max-width: 720px;
            margin-bottom: 45px;
        }

        .botoes-grupo {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn {
            padding: 16px 36px;
            border-radius: 8px;
            font-weight: 700;
            font-size: 16px;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
            cursor: pointer;
            border: none;
        }

        .btn-principal {
            background-color: #25d366;
            color: var(--white);
            box-shadow: 0 10px 25px rgba(37, 211, 102, 0.25);
        }

        .btn-principal:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(37, 211, 102, 0.4);
        }

        .btn-secundario {
            background: linear-gradient(135deg, var(--blue-main), #1d4ed8);
            color: var(--white);
            border: 1px solid rgba(0, 210, 255, 0.25);
            box-shadow: 0 10px 25px rgba(0, 82, 212, 0.25);
        }

        .btn-secundario:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(0, 82, 212, 0.4);
        }

        /* 2º BLOCO: PORTFÓLIO & CASES (MOVI CONSTRUTORA) */
        .portfolio-cases {
            background-color: var(--bg-card);
        }

        .case-container {
            background: linear-gradient(135deg, rgba(0, 82, 212, 0.15), rgba(3, 9, 20, 0.8));
            border: 1px solid rgba(0, 210, 255, 0.2);
            border-radius: 16px;
            padding: 50px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
        }

        .case-header {
            display: flex;
            align-items: center;
            gap: 20px;
            margin-bottom: 30px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            padding-bottom: 20px;
        }

        .case-header i {
            font-size: 40px;
            color: var(--blue-electric);
        }

        .case-header h3 {
            font-size: 32px;
            font-weight: 800;
            letter-spacing: -0.5px;
        }

        .case-header h3 span {
            color: var(--blue-electric);
        }

        .case-content {
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 50px;
            align-items: start;
        }

        .case-texto p {
            font-size: 17px;
            color: #cbd5e1;
            margin-bottom: 25px;
            line-height: 1.8;
            text-align: justify;
        }

        .case-texto p strong {
            color: var(--white);
            border-bottom: 2px solid var(--blue-electric);
        }

        .case-resultados {
            display: grid;
            grid-template-columns: 1fr;
            gap: 20px;
        }

        .metric-card {
            background-color: rgba(3, 9, 20, 0.6);
            border-left: 4px solid var(--blue-electric);
            padding: 25px;
            border-radius: 0 12px 12px 0;
        }

        .metric-card h4 {
            font-size: 28px;
            color: var(--blue-electric);
            font-weight: 800;
            margin-bottom: 5px;
        }

        .metric-card p {
            font-size: 15px;
            color: var(--text-muted);
            font-weight: 600;
        }

        /* 3º BLOCO: CONTATO & ATENDIMENTO */
        .contato-secao {
            background: linear-gradient(180deg, var(--bg-deep) 0%, #051124 100%);
        }

        .grid-contato {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: start;
        }

        .contato-info h3 {
            font-size: 28px;
            margin-bottom: 25px;
            font-weight: 800;
        }

        .contato-info p {
            font-size: 16px;
            color: #cbd5e1;
            margin-bottom: 40px;
        }

        .lista-canais {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .canal-item {
            display: flex;
            align-items: center;
            gap: 20px;
            background-color: var(--bg-card);
            padding: 20px;
            border-radius: 12px;
            border: 1px solid rgba(255,255,255,0.02);
        }

        .canal-item i {
            font-size: 24px;
            color: var(--blue-electric);
        }

        .canal-item h5 {
            font-size: 16px;
            font-weight: 700;
            margin-bottom: 2px;
        }

        .canal-item p {
            font-size: 14px;
            color: var(--text-muted);
            margin-bottom: 0;
        }

        /* FORMULÁRIO DE CONTATO NATIVO */
        .contato-formulario {
            background-color: var(--bg-card);
            padding: 40px;
            border-radius: 16px;
            border: 1px solid rgba(255,255,255,0.04);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }

        .grupo-input {
            margin-bottom: 20px;
        }

        .grupo-input label {
            display: block;
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 8px;
            color: #cbd5e1;
        }

        .grupo-input input, .grupo-input textarea {
            width: 100%;
            padding: 14px;
            background-color: var(--bg-deep);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            color: var(--white);
            font-size: 15px;
            transition: border-color 0.3s;
        }

        .grupo-input input:focus, .grupo-input textarea:focus {
            outline: none;
            border-color: var(--blue-electric);
        }

        .btn-enviar {
            width: 100%;
            background: linear-gradient(135deg, var(--blue-main), #1d4ed8);
            color: var(--white);
            padding: 15px;
            border: none;
            border-radius: 8px;
            font-weight: 700;
            font-size: 16px;
            cursor: pointer;
            transition: transform 0.2s;
        }

        .btn-enviar:hover {
            transform: translateY(-2px);
        }

        /* MODAL WHATSAPP */
        .modal-container {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(3, 9, 20, 0.88);
            backdrop-filter: blur(8px);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background-color: var(--bg-card);
            border: 2px solid var(--blue-electric);
            border-radius: 16px;
            padding: 45px 35px;
            max-width: 500px;
            width: 90%;
            text-align: center;
            position: relative;
            box-shadow: 0 25px 60px rgba(0, 210, 255, 0.15);
        }

        .modal-content h4 { font-size: 24px; margin-bottom: 12px; font-weight: 800; }
        .modal-content p { color: var(--text-muted); font-size: 15px; margin-bottom: 35px; }

        .botoes-modal { display: flex; flex-direction: column; gap: 16px; }

        .btn-whats-opcao {
            background-color: #25d366;
            color: var(--white);
            padding: 15px;
            border-radius: 8px;
            font-weight: 700;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            transition: all 0.2s ease;
        }

        .btn-whats-opcao:hover {
            transform: scale(1.02);
            background-color: #1ebd54;
        }

        .fechar-modal {
            position: absolute;
            top: 15px;
            right: 22px;
            font-size: 26px;
            color: var(--text-muted);
            cursor: pointer;
            transition: color 0.2s;
        }

        .fechar-modal:hover { color: var(--white); }

        /* FOOTER */
        footer {
            background-color: #02050d;
            padding: 45px 8%;
            text-align: center;
            font-size: 14px;
            color: var(--text-muted);
            border-top: 1px solid rgba(255,255,255,0.04);
        }

        @keyframes pulse-glow {
            0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(0, 210, 255, 0.4); }
            70% { transform: scale(1.02); box-shadow: 0 0 0 10px rgba(0, 210, 255, 0); }
            100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(0, 210, 255, 0); }
        }

        /* RESPONSIVIDADE */
        @media (max-width: 968px) {
            .case-content, .grid-contato { grid-template-columns: 1fr; gap: 40px; }
            .hero h1 { font-size: 35px; }
            .hero p { font-size: 16px; }
            header { padding: 15px 5%; }
            nav { display: none; }
            section { padding: 75px 5%; }
            .btn { width: 100%; justify-content: center; }
            .header-secao h2 { font-size: 32px; }
            .case-container { padding: 30px 20px; }
        }
    </style>
</head>
<body>

    <!-- MENU DE NAVEGAÇÃO SUPERIOR -->
    <header>
        <div class="logo-container">
            <div class="logo-circulo">
                <span class="letra-j">J</span><span class="letra-p">P</span>
            </div>
            <div class="logo-texto">
                Jotapemartking
                <span>MARKETING DIGITAL</span>
            </div>
        </div>
        <nav>
            <ul>
                <li><a href="#inicio">Início</a></li>
                <li><a href="#portfolio">Portfólio & Cases</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </nav>
    </header>

    <!-- 1º: INÍCIO (HERO SECTION) -->
    <section class="hero" id="inicio">
        <div class="hero-emblema-logo">
            <span class="letra-j">J</span><span class="letra-p">P</span>
        </div>
        
        <div class="badge-tag"><i class="fas fa-rocket"></i> Crescimento Exponencial</div>
        <h1>Construindo Estratégias Digitais que Convertem Cliques em <span>Lucro Real</span></h1>
        <p>Pare de gastar tempo com publicações genéricas que não geram negócios. Na Jotapemartking, nós desenvolvemos ecossistemas magnéticos focados em atrair clientes qualificados prontos para comprar de você.</p>
        
        <div class="botoes-grupo">
            <button onclick="abrirAtendimento()" class="btn btn-principal">
                <i class="fab fa-whatsapp"></i> Iniciar Escala de Vendas
            </button>
            <a href="https://www.instagram.com/jp.marketing.oficial?utm_source=qr" target="_blank" class="btn btn-secundario">
                <i class="fab fa-instagram"></i> Conhecer Nosso Instagram
            </a>
        </div>
    </section>

    <!-- 2º: PORTFÓLIO & CASES (DESTACANDO A MOVI CONSTRUTORA) -->
    <section class="portfolio-cases" id="portfolio">
        <div class="header-secao">
            <h2>Portfólio & <span>Cases de Sucesso</span></h2>
            <p>Resultados sólidos e engenharia de desejo aplicados na prática.</p>
        </div>

        <div class="case-container">
            <div class="case-header">
                <i class="fas fa-building"></i>
                <h3>MOVI <span>CONSTRUTORA E ENGENHARIA</span></h3>
            </div>
            
            <div class="case-content">
                <div class="case-texto">
                    <p>
                        A presença digital deixou de ser apenas uma vantagem competitiva e se tornou um fator essencial para empresas do setor imobiliário e de construção civil que desejam crescer de forma consistente. A <strong>Movi Construtora e Engenharia</strong> confiou à <strong>Jotapemartking</strong> o desafio de reestruturar seu ecossistema comercial na internet.
                    </p>
                    <p>
                        Nós analisamos friamente o mercado imobiliário e de alto padrão, identificamos as maiores brechas deixadas pelos concorrentes diretos e implementamos anúncios patrocinados cirúrgicos e segmentados. Criamos uma verdadeira <strong>Engenharia de Desejo</strong>, combinando análise de tráfego pago (Meta Ads e Google Ads), posicionamento estratégico sofisticado e comunicação de alto impacto para atrair clientes de alto poder aquisitivo.
                    </p>
                    <p>
                        A combinação de <strong>Branding Premium</strong> com <strong>Funis Automáticos de Captação</strong> permitiu que quebrássemos as principais objeções de vendas antes mesmo do cliente iniciar a conversa, blindando a comunicação e direcionando leads altamente qualificados direto para o time de fechamento da construtora.
                    </p>
                </div>

                <div class="case-resultados">
                    <div class="metric-card">
                        <h4>+ Visibilidade</h4>
                        <p>Fortalecimento e reconhecimento de marca no mercado regional.</p>
                    </div>
                    <div class="metric-card">
                        <h4>Leads de Elite</h4>
                        <p>Contatos qualificados com alto interesse em construção e incorporação.</p>
                    </div>
                    <div class="metric-card">
                        <h4>Escala Previsível</h4>
                        <p>Processo comercial automatizado gerando novas oportunidades recorrentes.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 3º: CONTATO & ATENDIMENTO COM FORMULÁRIO -->
    <section class="contato-secao" id="contato">
        <div class="header-secao">
            <h2>Fale com um <span>Especialista</span></h2>
            <p>O próximo nível comercial do seu negócio começa com um simples alinhamento.</p>
        </div>

        <div class="grid-contato">
            <div class="contato-info">
                <h3>Preparado para Liderar o Seu Mercado?</h3>
                <p>Não continue deixando dinheiro na mesa para concorrentes menos preparados. Escolha o canal de sua preferência abaixo ou preencha o formulário para agendar uma consultoria estratégica com nosso time.</p>
                
                <div class="lista-canais">
                    <div class="canal-item" style="cursor: pointer;" onclick="abrirAtendimento()">
                        <i class="fab fa-whatsapp"></i>
                        <div>
                            <h5>Atendimento Via WhatsApp</h5>
                            <p>Clique para abrir nossos canais diretos de escala comercial.</p>
                        </div>
                    </div>
                    <div class="canal-item">
                        <i class="fas fa-envelope"></i>
                        <div>
                            <h5>E-mail Corporativo</h5>
                            <p>contato@jotapemartking.com</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="contato-formulario">
                <form action="#" method="POST" onsubmit="event.preventDefault(); alert('Mensagem enviada com sucesso! Nosso time entrará em contato.');">
                    <div class="grupo-input">
                        <label for="nome">Seu Nome / Nome da Empresa</label>
                        <input type="text" id="nome" placeholder="Ex: Movi Construtora" required>
                    </div>
                    <div class="grupo-input">
                        <label for="email">Seu Melhor E-mail</label>
                        <input type="email" id="email" placeholder="Ex: contato@suaempresa.com" required>
                    </div>
                    <div class="grupo-input">
                        <label for="mensagem">Como podemos alavancar seu negócio?</label>
                        <textarea id="mensagem" rows="4" placeholder="Conte-nos brevemente sobre seu produto ou serviço..." required></textarea>
                    </div>
                    <button type="submit" class="btn-enviar">Solicitar Diagnóstico Estratégico</button>
                </form>
            </div>
        </div>
    </section>

    <!-- POP-UP / MODAL EXCLUSIVO PARA DIRECIONAR OS DOIS NÚMEROS DE WHATSAPP -->
    <div id="modalWhats" class="modal-container">
        <div class="modal-content">
            <span onclick="fecharAtendimento()" class="fechar-modal">&times;</span>
            <h4>Selecione um Canal de Atendimento</h4>
            <p>Para garantir total agilidade, clique em uma das opções abaixo para falar diretamente com nosso time via WhatsApp:</p>
            <div class="botoes-modal">
                <a href="https://wa.me/558193774327?text=Olá! Vim pelo site da Jotapemartking e gostaria de saber mais sobre as estratégias de marketing para minha empresa." target="_blank" class="btn-whats-opcao">
                    <i class="fab fa-whatsapp"></i> Atendimento Comercial 01
                </a>
                <a href="https://wa.me/558196572994?text=Olá! Conheci a Jotapemartking através do site e quero alinhar uma consultoria estratégica para meu negócio." target="_blank" class="btn-whats-opcao">
                    <i class="fab fa-whatsapp"></i> Atendimento Comercial 02
                </a>
            </div>
        </div>
    </div>

    <!-- FOOTER REGULAR -->
    <footer>
        <p>&copy; 2026 Jotapemartking. Todos os direitos reservados. Impulsionando marcas rumo ao topo comercial.</p>
    </footer>

    <!-- LOGICA SCRIPT DO MODAL -->
    <script>
        function abrirAtendimento() {
            document.getElementById('modalWhats').style.display = 'flex';
        }
        function fecharAtendimento() {
            document.getElementById('modalWhats').style.display = 'none';
        }
        window.onclick = function(event) {
            let modal = document.getElementById('modalWhats');
            if (event.target == modal) {
                modal.style.display = 'none';
            }
        }
    </script>

</body>
</html>
