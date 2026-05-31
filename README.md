# VoltTech-Services
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VoltTech | Soluciones Residenciales</title>
    <!-- Fuente Inter: Técnica, limpia y profesional -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        :root {
            --navy: #002B49;     /* Azul del engranaje */
            --yellow: #FFD700;   /* Amarillo del fondo */
            --blue: #0088CC;     /* Azul de las gotas/tubería */
            --light-bg: #F3F4F6;
            --white: #FFFFFF;
            --text-dark: #1F2937;
            --text-muted: #4B5563;
            --border: #E5E7EB;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Inter', sans-serif;
            color: var(--text-dark);
            background-color: var(--white);
            line-height: 1.5;
        }

        /* --- NAVEGACIÓN --- */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 5%;
            background: var(--white);
            border-bottom: 1px solid var(--border);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .nav-logo {
            height: 45px;
            display: flex;
            align-items: center;
        }

        .nav-logo img { height: 100%; width: auto; }

        .nav-links { display: none; }
        @media (min-width: 768px) {
            .nav-links { display: flex; gap: 20px; }
            .nav-links a { 
                text-decoration: none; 
                color: var(--text-dark); 
                font-size: 14px; 
                font-weight: 500; 
            }
        }

        /* --- HERO SECTION (CENTRADO Y SOBRIO) --- */
        .hero {
            padding: 60px 5%;
            text-align: center;
            background: linear-gradient(180deg, var(--white) 0%, var(--light-bg) 100%);
        }

        .hero-logo-main {
            max-width: 220px; /* El logo que enviaste como centro visual */
            height: auto;
            margin-bottom: 20px;
        }

        .hero h1 {
            font-size: 2rem;
            color: var(--navy);
            margin-bottom: 10px;
            font-weight: 700;
            text-transform: uppercase;
        }

        .hero p {
            max-width: 600px;
            margin: 0 auto 30px;
            color: var(--text-muted);
            font-size: 1.1rem;
        }

        .btn-whatsapp {
            background-color: #25D366; /* Verde estándar de contacto */
            color: white;
            padding: 16px 32px;
            border-radius: 6px;
            text-decoration: none;
            font-weight: 700;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            transition: opacity 0.2s;
        }

        .btn-whatsapp:hover { opacity: 0.9; }

        /* --- VALORES (CONFIANZA) --- */
        .trust-bar {
            background: var(--navy);
            color: white;
            padding: 30px 5%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            text-align: center;
        }

        .trust-item h4 { color: var(--yellow); font-size: 0.9rem; margin-bottom: 5px; }
        .trust-item p { font-size: 0.8rem; opacity: 0.8; }

        /* --- SERVICIOS (FUNCIONALES) --- */
        .section { padding: 80px 5%; }
        .section-title { margin-bottom: 40px; text-align: center; }
        .section-title h2 { color: var(--navy); font-size: 1.8rem; }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .card {
            padding: 30px;
            border: 1px solid var(--border);
            border-radius: 4px;
            background: white;
        }

        .card i { color: var(--blue); margin-bottom: 15px; }
        .card h3 { font-size: 1.1rem; margin-bottom: 10px; color: var(--navy); }
        .card p { font-size: 0.9rem; color: var(--text-muted); }

        /* --- GALERÍA SOBRIA --- */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 10px;
        }
        .gallery-item {
            aspect-ratio: 1;
            background: #eee;
            overflow: hidden;
        }
        .gallery-item img { width: 100%; height: 100%; object-fit: cover; }

        /* --- FOOTER --- */
        footer {
            padding: 50px 5%;
            background: var(--light-bg);
            border-top: 1px solid var(--border);
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 8px;
            text-decoration: none;
            color: var(--text-dark);
            margin-bottom: 10px;
            font-size: 0.9rem;
        }

        /* --- BOTÓN FLOTANTE --- */
        .float-wa {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #25D366;
            color: white;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }

        @media (max-width: 600px) {
            .hero h1 { font-size: 1.6rem; }
        }
    </style>
</head>
<body>

    <nav>
        <div class="nav-logo">
            <img src="logo.png" alt="VoltTech Logo">
        </div>
        <div class="nav-links">
            <a href="#servicios">Servicios</a>
            <a href="#trabajos">Trabajos</a>
            <a href="#contacto">Contacto</a>
        </div>
    </nav>

    <section class="hero">
        <!-- AQUÍ VA TU LOGO (El que enviaste) -->
        <img src="logo.png" alt="VoltTech Soluciones Residenciales" class="hero-logo-main">
        <h1>Soluciones Eléctricas Residenciales</h1>
        <p>Servicio técnico profesional de instalación y mantenimiento eléctrico y plomería. Atención segura y puntual para su hogar.</p>
        <a href="https://wa.me/50575422893" class="btn-whatsapp">
            <i data-lucide="message-circle"></i> Solicitar servicio por WhatsApp
        </a>
    </section>

    <section class="trust-bar">
        <div class="trust-item">
            <h4>TRABAJO TÉCNICO</h4>
            <p>Diagnósticos precisos y sin rodeos.</p>
        </div>
        <div class="trust-item">
            <h4>LIMPIEZA</h4>
            <p>Respetamos y cuidamos su hogar.</p>
        </div>
        <div class="trust-item">
            <h4>RESPONSABILIDAD</h4>
            <p>Cumplimos con lo acordado.</p>
        </div>
        <div class="trust-item">
            <h4>PUNTUALIDAD</h4>
            <p>Llegamos en el horario pactado.</p>
        </div>
    </section>

    <section id="servicios" class="section">
        <div class="section-title">
            <h2>Nuestros Servicios</h2>
        </div>
        <div class="services-grid">
            <div class="card">
                <i data-lucide="zap"></i>
                <h3>Instalaciones Eléctricas</h3>
                <p>Nuevos puntos de luz, tomacorrientes y cableado general de la vivienda.</p>
            </div>
            <div class="card">
                <i data-lucide="wrench"></i>
                <h3>Reparaciones</h3>
                <p>Corrección de fallas, cortocircuitos y problemas de suministro.</p>
            </div>
            <div class="card">
                <i data-lucide="shield-check"></i>
                <h3>Mantenimiento</h3>
                <p>Revisión periódica para prevenir daños y asegurar el sistema.</p>
            </div>
            <div class="card">
                <i data-lucide="power"></i>
                <h3>Breakers y Paneles</h3>
                <p>Reemplazo y actualización de centros de carga y protecciones.</p>
            </div>
            <div class="card">
                <i data-lucide="droplets"></i>
                <h3>Bombas de Agua</h3>
                <p>Instalación y diagnóstico de equipos de bombeo residencial.</p>
            </div>
            <div class="card">
                <i data-lucide="activity"></i>
                <h3>Diagnóstico de Fallas</h3>
                <p>Evaluación técnica para identificar problemas ocultos.</p>
            </div>
            <div class="card">
                <i data-lucide="pipette"></i>
                <h3>Plomería Residencial</h3>
                <p>Reparaciones generales de tuberías y grifería.</p>
            </div>
            <div class="card">
                <i data-lucide="layers"></i>
                <h3>Sistemas Hidráulicos</h3>
                <p>Mantenimiento de redes de agua y drenajes domésticos.</p>
            </div>
        </div>
    </section>

    <section id="trabajos" class="section" style="background: #fafafa;">
        <div class="section-title">
            <h2>Trabajos Realizados</h2>
        </div>
        <div class="gallery-grid">
            <!-- Fotos de trabajos reales -->
            <div class="gallery-item"><img src="https://images.unsplash.com/photo-1621905251189-08b45d6a269e?auto=format&fit=crop&q=60&w=500" alt="Trabajo"></div>
            <div class="gallery-item"><img src="https://images.unsplash.com/photo-1558211583-d26f610c1eb1?auto=format&fit=crop&q=60&w=500" alt="Trabajo"></div>
            <div class="gallery-item"><img src="https://images.unsplash.com/photo-1544724569-5f546fd6f2b5?auto=format&fit=crop&q=60&w=500" alt="Trabajo"></div>
        </div>
    </section>

    <footer id="contacto">
        <div class="footer-content">
            <div>
                <h3 style="margin-bottom: 15px; font-size: 1rem;">VoltTech</h3>
                <p style="font-size: 0.85rem; color: var(--text-muted);">Servicios eléctricos y plomería.<br>Managua, Nicaragua.</p>
            </div>
            <div>
                <h3 style="margin-bottom: 15px; font-size: 1rem;">Contacto</h3>
                <a href="tel:+50575422893" class="contact-link"><i data-lucide="phone" size="16"></i> WhatsApp: +505 7542-2893</a>
                <a href="mailto:volttechservices.nic@gmail.com" class="contact-link"><i data-lucide="mail" size="16"></i> volttechservices.nic@gmail.com</a>
                <a href="https://www.facebook.com/share/18g69wiZav" target="_blank" rel="noopener noreferrer" class="contact-link">
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" style="flex-shrink:0;">
                        <path fill="#1877F2" d="M24 12.073C24 5.405 18.627 0 12 0S0 5.405 0 12.073C0 18.1 4.388 23.094 10.125 24v-8.437H7.078v-3.49h3.047V9.413c0-3.026 1.791-4.697 4.533-4.697 1.313 0 2.686.235 2.686.235v2.97h-1.514c-1.491 0-1.956.93-1.956 1.886v2.267h3.328l-.532 3.49h-2.796V24C19.612 23.094 24 18.1 24 12.073z"/>
                    </svg>
                    Facebook
                </a>
            </div>
        </div>
        <div style="margin-top: 40px; padding-top: 20px; border-top: 1px solid var(--border); font-size: 0.75rem; text-align: center; color: var(--text-muted);">
            © 2023 VoltTech. Soluciones residenciales técnicas y seguras.
        </div>
    </footer>

    <a href="https://wa.me/50575422893" class="float-wa">
        <i data-lucide="message-circle"></i>
    </a>

    <script>
        lucide.createIcons();
    </script>
</body>
</html>
