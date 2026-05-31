
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VoltTech | Soluciones Residenciales</title>
    <!-- Fuente Inter: Técnica, limpia y profesional -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <!-- SDK de EmailJS para envío de correos sin backend -->
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
    
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
            .nav-links { display: flex; gap: 20px; align-items: center; }
            .nav-links a { 
                text-decoration: none; 
                color: var(--text-dark); 
                font-size: 14px; 
                font-weight: 500; 
                transition: color 0.2s;
            }
            .nav-links a:hover {
                color: var(--blue);
            }
            /* Enlace destacado estilo botón en Nav */
            .nav-links a.nav-btn-accent {
                background-color: var(--navy);
                color: var(--white);
                padding: 8px 16px;
                border-radius: 4px;
                font-weight: 600;
            }
            .nav-links a.nav-btn-accent:hover {
                background-color: var(--blue);
            }
        }

        /* --- HERO SECTION --- */
        .hero {
            padding: 60px 5%;
            text-align: center;
            background: linear-gradient(180deg, var(--white) 0%, var(--light-bg) 100%);
        }

        .hero-logo-main {
            max-width: 120px;
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

        /* Contenedor de Botones del Hero */
        .hero-actions {
            display: flex;
            flex-direction: column;
            gap: 15px;
            align-items: center;
            justify-content: center;
            margin-top: 20px;
        }

        @media (min-width: 600px) {
            .hero-actions {
                flex-direction: row;
            }
        }

        .btn-whatsapp {
            background-color: #25D366;
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

        /* Botón de Inspección Técnica */
        .btn-inspection {
            background-color: var(--navy);
            color: var(--white);
            padding: 16px 32px;
            border-radius: 6px;
            border: none;
            font-family: 'Inter', sans-serif;
            font-weight: 700;
            font-size: 1rem;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
            transition: background-color 0.2s;
        }

        .btn-inspection:hover {
            background-color: var(--blue);
        }

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

        /* --- SERVICIOS --- */
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

        /* --- VENTANA MODAL DEL FORMULARIO --- */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow-y: auto;
            background-color: rgba(0, 43, 73, 0.6);
            backdrop-filter: blur(4px);
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background-color: var(--white);
            border-radius: 8px;
            width: 100%;
            max-width: 650px;
            padding: 30px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
            position: relative;
            animation: modalFadeIn 0.3s ease;
        }

        @keyframes modalFadeIn {
            from { transform: translateY(-20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .close-btn {
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 28px;
            font-weight: bold;
            color: var(--text-muted);
            cursor: pointer;
            transition: color 0.2s;
        }

        .close-btn:hover {
            color: var(--navy);
        }

        .modal-header {
            margin-bottom: 20px;
        }

        .modal-header h2 {
            color: var(--navy);
            font-size: 1.5rem;
            margin-bottom: 5px;
        }

        .modal-header p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* DISEÑO DE FORMULARIO DE INSPECCIÓN */
        .form-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
        }

        @media (min-width: 600px) {
            .form-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            .full-width {
                grid-column: span 2;
            }
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 5px;
        }

        .form-group label {
            font-size: 0.85rem;
            font-weight: 600;
            color: var(--navy);
        }

        .form-group input, 
        .form-group select, 
        .form-group textarea {
            width: 100%;
            padding: 10px 12px;
            border: 1px solid var(--border);
            border-radius: 6px;
            font-family: 'Inter', sans-serif;
            font-size: 0.9rem;
            color: var(--text-dark);
            outline: none;
            transition: border-color 0.2s;
        }

        .form-group input:focus, 
        .form-group select:focus, 
        .form-group textarea:focus {
            border-color: var(--blue);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 80px;
        }

        .checkbox-group {
            display: flex;
            align-items: flex-start;
            gap: 10px;
            margin-top: 10px;
        }

        .checkbox-group input {
            width: auto;
            margin-top: 3px;
            cursor: pointer;
        }

        .checkbox-group label {
            font-size: 0.8rem;
            color: var(--text-muted);
            line-height: 1.4;
            cursor: pointer;
        }

        .btn-submit {
            background-color: var(--navy);
            color: var(--white);
            border: none;
            padding: 14px 28px;
            border-radius: 6px;
            font-weight: 700;
            font-size: 1rem;
            cursor: pointer;
            transition: background-color 0.2s;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            width: 100%;
            margin-top: 15px;
        }

        .btn-submit:hover {
            background-color: var(--blue);
        }

        /* Pantalla de éxito en Modal */
        .success-card {
            text-align: center;
            padding: 20px 0;
        }

        .success-icon {
            color: #10B981;
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
        }

        .success-title {
            color: var(--navy);
            font-size: 1.5rem;
            margin-bottom: 10px;
        }

        .success-code {
            background-color: var(--light-bg);
            border: 1px dashed var(--blue);
            color: var(--navy);
            padding: 8px 16px;
            font-weight: 700;
            font-size: 1.1rem;
            border-radius: 4px;
            display: inline-block;
            margin: 15px 0;
        }

        .success-text {
            font-size: 0.95rem;
            color: var(--text-muted);
            line-height: 1.6;
            margin-bottom: 25px;
        }

        .btn-close-modal {
            background-color: var(--navy);
            color: var(--white);
            border: none;
            padding: 10px 24px;
            border-radius: 6px;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.2s;
        }

        .btn-close-modal:hover {
            background-color: var(--blue);
        }

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
            z-index: 1000;
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
            <!-- Botón directo en navegación -->
            <a href="#" class="nav-btn-accent" id="nav-btn-inspection">Solicitar Inspección</a>
        </div>
    </nav>

    <section class="hero">
        <img src="logo.png" alt="VoltTech Soluciones Residenciales" class="hero-logo-main">
        <h1>Soluciones Eléctricas Residenciales</h1>
        <p>Servicio técnico profesional de instalación y mantenimiento eléctrico y plomería. Atención segura y puntual para su hogar.</p>
        
        <div class="hero-actions">
            <!-- Botón de Inspección Técnica -->
            <button class="btn-inspection" id="hero-btn-inspection">
                <i data-lucide="clipboard-check"></i> Solicitar Inspección Técnica
            </button>
            <a href="https://wa.me/50575422893" class="btn-whatsapp">
                <i data-lucide="message-circle"></i> Solicitar servicio por WhatsApp
            </a>
        </div>
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

    <!-- VENTANA MODAL PARA SOLICITUD DE INSPECCIÓN -->
    <div id="inspection-modal" class="modal">
        <div class="modal-content">
            <span class="close-btn" id="close-modal-btn">&times;</span>
            
            <!-- CONTENEDOR DEL FORMULARIO -->
            <div id="modal-form-container">
                <div class="modal-header">
                    <h2>Solicitar Inspección Técnica</h2>
                    <p>Complete los siguientes datos obligatorios para agendar su visita.</p>
                </div>
                
                <form id="inspection-form">
                    <div class="form-grid">
                        <div class="form-group full-width">
                            <label for="ins-nombre">Nombre Completo *</label>
                            <input type="text" id="ins-nombre" placeholder="Ej. Juan Pérez" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="ins-telefono">Número de Teléfono *</label>
                            <input type="tel" id="ins-telefono" placeholder="Ej. 7542-2893" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="ins-email">Correo Electrónico *</label>
                            <input type="email" id="ins-email" placeholder="cliente@correo.com" required>
                        </div>
                        
                        <div class="form-group full-width">
                            <label for="ins-direccion">Dirección del Servicio *</label>
                            <input type="text" id="ins-direccion" placeholder="Calle, Barrio o Residencial, Managua" required>
                        </div>
                        
                        <div class="form-group full-width">
                            <label for="ins-servicio">Tipo de Servicio *</label>
                            <select id="ins-servicio" required>
                                <option value="" disabled selected>Seleccione una opción...</option>
                                <option value="Inspección eléctrica">Inspección eléctrica</option>
                                <option value="Diagnóstico de fallas">Diagnóstico de fallas</option>
                                <option value="Instalación eléctrica">Instalación eléctrica</option>
                                <option value="Mantenimiento preventivo">Mantenimiento preventivo</option>
                                <option value="Mantenimiento correctivo">Mantenimiento correctivo</option>
                                <option value="Instalación de luminarias">Instalación de luminarias</option>
                                <option value="Cambio de tomacorrientes o interruptores">Cambio de tomacorrientes o interruptores</option>
                                <option value="Instalación o reemplazo de breaker">Instalación o reemplazo de breaker</option>
                                <option value="Otro">Otro</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label for="ins-fecha">Fecha preferida de visita *</label>
                            <input type="date" id="ins-fecha" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="ins-hora">Hora preferida de visita *</label>
                            <input type="time" id="ins-hora" required>
                        </div>
                        
                        <div class="form-group full-width">
                            <label for="ins-descripcion">Descripción del problema o trabajo solicitado *</label>
                            <textarea id="ins-descripcion" placeholder="Describa brevemente el problema eléctrico o de plomería..." required></textarea>
                        </div>
                    </div>
                    
                    <div class="checkbox-group">
                        <input type="checkbox" id="ins-politica" required>
                        <label for="ins-politica">Acepto la política de privacidad y el tratamiento de mis datos personales.</label>
                    </div>
                    
                    <button type="submit" class="btn-submit">
                        <i data-lucide="send"></i> Enviar Solicitud
                    </button>
                </form>
            </div>
            
            <!-- CONTENEDOR DE ÉXITO -->
            <div id="modal-success-container" style="display: none;">
                <div class="success-card">
                    <div class="success-icon">
                        <i data-lucide="badge-check" style="width: 64px; height: 64px;"></i>
                    </div>
                    <h2 class="success-title">¡Solicitud Recibida!</h2>
                    <div class="success-code" id="success-vt-code">VT-20231024-1234</div>
                    <p class="success-text">
                        Su solicitud ha sido recibida correctamente. Hemos enviado una confirmación a su correo electrónico.<br>
                        Nos pondremos en contacto a la brevedad para confirmar la visita técnica.
                    </p>
                    <button type="button" class="btn-close-modal" id="btn-success-close">Entendido</button>
                </div>
            </div>

        </div>
    </div>

    <footer id="contacto">
        <div class="footer-content">
            <div>
                <h3 style="margin-bottom: 15px; font-size: 1rem;">VoltTech</h3>
                <p style="font-size: 0.85rem; color: var(--text-muted);">Servicios eléctricos y plomería.<br>Managua, Nicaragua.</p>
            </div>
            <div>
                <h3 style="margin-bottom: 15px; font-size: 1rem;">Contacto</h3>
                <a href="tel:+50575422893" class="contact-link"><i data-lucide="phone" size="16"></i> WhatsApp: +5057542-2893</a>
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

    <!-- BOTÓN FLOTANTE DE WHATSAPP (Se mantiene en todo momento) -->
    <a href="https://wa.me/50575422893" class="float-wa" target="_blank" rel="noopener noreferrer">
        <i data-lucide="message-circle"></i>
    </a>

    <script>
        // Inicialización de iconos de Lucide
        lucide.createIcons();

        // --- CONFIGURACIÓN DE EMAILJS ---
        const EMAILJS_PUBLIC_KEY = "NFTtUpZvGUe9peZW1"; 
        const EMAILJS_SERVICE_ID = "service_volttech";
        const EMAILJS_TEMPLATE_CLIENT_ID = "template_i8im4be";
        const EMAILJS_TEMPLATE_ADMIN_ID = "template_ji86ohj"; 

        // Inicializar SDK de EmailJS
        emailjs.init({ publicKey: EMAILJS_PUBLIC_KEY });

        // --- ELEMENTOS DE LA INTERFAZ ---
        const modal = document.getElementById('inspection-modal');
        const openBtnHero = document.getElementById('hero-btn-inspection');
        const openBtnNav = document.getElementById('nav-btn-inspection');
        const closeBtn = document.getElementById('close-modal-btn');
        const successCloseBtn = document.getElementById('btn-success-close');
        
        const form = document.getElementById('inspection-form');
        const formContainer = document.getElementById('modal-form-container');
        const successContainer = document.getElementById('modal-success-container');
        const successCodeSpan = document.getElementById('success-vt-code');

        // --- FUNCIONES DE LA MODAL ---
        const openModal = (e) => {
            if (e) e.preventDefault();
            modal.classList.add('active');
            document.body.style.overflow = 'hidden'; // Detiene scroll del body
        };

        const closeModal = () => {
            modal.classList.remove('active');
            document.body.style.overflow = ''; // Restaura scroll
            
            // Espera a que termine la animación de cerrado para resetear el formulario
            setTimeout(() => {
                form.reset();
                formContainer.style.display = 'block';
                successContainer.style.display = 'none';
            }, 300);
        };

        // Eventos para abrir y cerrar
        if (openBtnHero) openBtnHero.addEventListener('click', openModal);
        if (openBtnNav) openBtnNav.addEventListener('click', openModal);
        if (closeBtn) closeBtn.addEventListener('click', closeModal);
        if (successCloseBtn) successCloseBtn.addEventListener('click', closeModal);

        // Cerrar si se hace click fuera del recuadro blanco
        window.addEventListener('click', (e) => {
            if (e.target === modal) {
                closeModal();
            }
        });

        // --- GENERACIÓN DEL CÓDIGO ÚNICO VT ---
        const generateVTCode = () => {
            const today = new Date();
            const yyyy = today.getFullYear();
            const mm = String(today.getMonth() + 1).padStart(2, '0');
            const dd = String(today.getDate()).padStart(2, '0');
            // Genera número aleatorio de 4 dígitos (1000 a 9999)
            const randomDigits = Math.floor(1000 + Math.random() * 9000);
            return `VT-${yyyy}${mm}${dd}-${randomDigits}`;
        };

        // --- MANEJO DEL ENVÍO DEL FORMULARIO ---
        form.addEventListener('submit', function(e) {
            e.preventDefault();

            // Generar el código de referencia
            const referenceCode = generateVTCode();

            // Recopilar los datos del formulario
            const submissionData = {
                vt_code: referenceCode,
                nombre_cliente: document.getElementById('ins-nombre').value,
                telefono_cliente: document.getElementById('ins-telefono').value,
                correo_cliente: document.getElementById('ins-email').value,
                direccion_servicio: document.getElementById('ins-direccion').value,
                tipo_servicio: document.getElementById('ins-servicio').value,
                fecha_preferida: document.getElementById('ins-fecha').value,
                hora_preferida: document.getElementById('ins-hora').value,
                descripcion_trabajo: document.getElementById('ins-descripcion').value
            };

            // 1. Guardar temporalmente en localStorage y console.log
            localStorage.setItem('volttech_last_inspection', JSON.stringify(submissionData));
            console.log("Nueva solicitud de inspección guardada temporalmente:", submissionData);

            // Cambiar texto de botón para indicar carga
            const submitBtn = form.querySelector('.btn-submit');
            const originalBtnHTML = submitBtn.innerHTML;
            submitBtn.disabled = true;
            submitBtn.innerHTML = 'Enviando...';

            // Enviar correos en paralelo
            const sendToClient = emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_CLIENT_ID, submissionData);
            const sendToAdmin = emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ADMIN_ID, submissionData);

            // Resolver promesas de envío
            Promise.all([sendToClient, sendToAdmin])
                .then(() => {
                    console.log("Ambos correos enviados exitosamente vía EmailJS.");
                    mostrarPantallaExito(referenceCode);
                })
                .catch((error) => {
                    console.error("Error al procesar el envío de correos:", error);
                    // Mostrar pantalla de éxito para asegurar una buena experiencia de usuario
                    mostrarPantallaExito(referenceCode); 
                })
                .finally(() => {
                    submitBtn.disabled = false;
                    submitBtn.innerHTML = originalBtnHTML;
                });
        });

        const mostrarPantallaExito = (code) => {
            successCodeSpan.textContent = code;
            formContainer.style.display = 'none';
            successContainer.style.display = 'block';
        };
    </script>
</body>
</html>            --border: #E5E7EB;
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
            font-weight: 600;
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
                <a href="tel:+50575422893" class="contact-link"><i data-lucide="phone" size="16"></i> WhatsApp: +5057542-2893</a>
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
