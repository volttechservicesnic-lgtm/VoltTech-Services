
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

            /* Colores de estados administrativos */
            --status-pending: #F59E0B;     /* Amarillo/Naranja */
            --status-confirmed: #0088CC;   /* Azul */
            --status-rescheduled: #D97706; /* Naranja oscuro */
            --status-completed: #10B981;   /* Verde */
            --status-cancelled: #EF4444;   /* Rojo */
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Inter', sans-serif;
            color: var(--text-dark);
            background-color: var(--white);
            line-height: 1.5;
            -webkit-font-smoothing: antialiased;
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

        /* Contenedor del Logo de la barra de navegación (Proporciones corregidas) */
        .nav-logo {
            height: 40px;
            display: flex;
            align-items: center;
        }

        .nav-logo img { 
            height: 100%; 
            width: auto; 
            max-width: 140px;
            object-fit: contain; 
        }

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

        /* --- HERO SECTION (Ajustes de Fondo y Estética) --- */
        .hero {
            position: relative;
            padding: 60px 5% 80px;
            text-align: center;
            background: linear-gradient(180deg, var(--white) 0%, var(--light-bg) 100%);
            overflow: hidden;
        }

        /* Sutil marca de agua de fondo (Logo como fondo) */
        .hero::before {
            content: "";
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 300px;
            height: 300px;
            background: url('logo.png') no-repeat center center;
            background-size: contain;
            opacity: 0.03; /* Muy tenue para no dificultar la legibilidad */
            pointer-events: none;
            z-index: 1;
        }

        /* Contenedor de elementos para posicionar por encima de la marca de agua */
        .hero-content {
            position: relative;
            z-index: 2;
        }

        /* Contenedor Armónico del Logo del Hero */
        .hero-logo-container {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            background: var(--white);
            padding: 12px;
            border-radius: 8px;
            border: 1px solid var(--border);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.04);
            margin-bottom: 25px;
            width: 100px;
            height: 100px;
        }

        .hero-logo-main {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }

        .hero h1 {
            font-size: 1.8rem;
            color: var(--navy);
            margin-bottom: 15px;
            font-weight: 700;
            text-transform: uppercase;
        }

        @media (min-width: 768px) {
            .hero h1 {
                font-size: 2.2rem;
            }
        }

        .hero p {
            max-width: 600px;
            margin: 0 auto 30px;
            color: var(--text-muted);
            font-size: 1rem;
        }

        @media (min-width: 768px) {
            .hero p {
                font-size: 1.1rem;
            }
        }

        /* Contenedor de Botones del Hero */
        .hero-actions {
            display: flex;
            flex-direction: column;
            gap: 12px;
            align-items: center;
            justify-content: center;
            width: 100%;
            max-width: 500px;
            margin: 20px auto 0;
        }

        @media (min-width: 600px) {
            .hero-actions {
                flex-direction: row;
                max-width: none;
            }
        }

        /* Botones estructurados */
        .btn-whatsapp, .btn-inspection {
            width: 100%;
            height: 52px;
            padding: 0 24px;
            border-radius: 6px;
            font-family: 'Inter', sans-serif;
            font-weight: 700;
            font-size: 0.95rem;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            text-decoration: none;
            border: none;
            cursor: pointer;
            box-sizing: border-box;
            transition: background-color 0.2s, opacity 0.2s;
        }

        @media (min-width: 600px) {
            .btn-whatsapp, .btn-inspection {
                width: auto;
            }
        }

        .btn-whatsapp {
            background-color: #25D366;
            color: white;
        }
        .btn-whatsapp:hover { opacity: 0.9; }

        .btn-inspection {
            background-color: var(--navy);
            color: var(--white);
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
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 20px;
            text-align: center;
        }

        .trust-item h4 { color: var(--yellow); font-size: 0.9rem; margin-bottom: 5px; }
        .trust-item p { font-size: 0.8rem; opacity: 0.8; }

        /* --- SERVICIOS --- */
        .section { padding: 60px 5%; }
        @media (min-width: 768px) {
            .section { padding: 80px 5%; }
        }
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
            padding: 15px 10px;
        }

        .modal.active {
            display: block;
        }

        .modal-content {
            background-color: var(--white);
            border-radius: 8px;
            width: 100%;
            max-width: 600px;
            padding: 24px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            position: relative;
            margin: 15px auto;
            animation: modalFadeIn 0.3s ease;
        }

        @media (min-width: 768px) {
            .modal-content {
                padding: 40px;
                margin: 40px auto;
            }
        }

        @keyframes modalFadeIn {
            from { transform: translateY(-15px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .close-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 24px;
            font-weight: bold;
            color: var(--text-muted);
            cursor: pointer;
            width: 32px;
            height: 32px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            background: var(--light-bg);
            transition: background-color 0.2s, color 0.2s;
        }

        .close-btn:hover {
            color: var(--navy);
            background: var(--border);
        }

        .modal-header {
            margin-bottom: 24px;
            padding-right: 35px;
        }

        .modal-header h2 {
            color: var(--navy);
            font-size: 1.4rem;
            margin-bottom: 6px;
        }

        .modal-header p {
            color: var(--text-muted);
            font-size: 0.85rem;
            line-height: 1.4;
        }

        /* DISEÑO DE FORMULARIO DE INSPECCIÓN */
        .form-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 12px;
        }

        @media (min-width: 600px) {
            .form-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 16px;
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
            font-size: 0.8rem;
            font-weight: 600;
            color: var(--navy);
        }

        .form-group input, 
        .form-group select, 
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid var(--border);
            border-radius: 6px;
            font-family: 'Inter', sans-serif;
            font-size: 16px; /* Evita zoom en iOS */
            color: var(--text-dark);
            outline: none;
            background-color: var(--white);
            box-sizing: border-box;
            transition: border-color 0.2s;
            -webkit-appearance: none;
            appearance: none;
        }

        .form-group input:focus, 
        .form-group select:focus, 
        .form-group textarea:focus {
            border-color: var(--blue);
        }

        .form-group select {
            background-image: url("data:image/svg+xml;charset=UTF-8,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%234B5563' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E");
            background-repeat: no-repeat;
            background-position: right 12px center;
            background-size: 16px;
            padding-right: 40px;
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
            width: 18px;
            height: 18px;
            margin-top: 2px;
            cursor: pointer;
            flex-shrink: 0;
        }

        .checkbox-group label {
            font-size: 0.8rem;
            color: var(--text-muted);
            line-height: 1.4;
            cursor: pointer;
            user-select: none;
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
            padding: 12px 28px;
            border-radius: 6px;
            font-weight: 600;
            font-size: 0.95rem;
            cursor: pointer;
            transition: background-color 0.2s;
        }

        .btn-close-modal:hover {
            background-color: var(--blue);
        }


        /* ==========================================================================
           --- ESTILOS GENERALES DEL PANEL DE CONTROL ADMINISTRATIVO (GÉNERICO) ---
           ========================================================================== */
        
        #admin-panel {
            display: none; /* Oculto por defecto */
            background-color: #F9FAFB;
            min-height: 100vh;
            color: var(--text-dark);
            padding-bottom: 60px;
            position: relative;
        }

        .admin-header {
            background-color: var(--navy);
            color: var(--white);
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
            border-bottom: 4px solid var(--blue);
        }

        .admin-header h1 {
            font-size: 1.5rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .admin-nav-tabs {
            display: flex;
            background: #E5E7EB;
            padding: 4px;
            border-radius: 8px;
            gap: 4px;
            margin: 25px 5% 15px;
        }

        .admin-tab-btn {
            flex: 1;
            border: none;
            background: none;
            padding: 10px;
            font-family: 'Inter', sans-serif;
            font-weight: 600;
            font-size: 0.85rem;
            color: var(--text-muted);
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.2s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .admin-tab-btn.active {
            background: var(--white);
            color: var(--navy);
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
        }

        .admin-container {
            padding: 0 5%;
        }

        .admin-section-content {
            display: none;
        }

        .admin-section-content.active {
            display: block;
            animation: modalFadeIn 0.3s ease;
        }

        /* --- DASHBOARD & METRICAS --- */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 15px;
            margin-bottom: 25px;
        }

        .stat-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 8px;
            padding: 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            box-shadow: 0 1px 3px rgba(0,0,0,0.02);
        }

        .stat-info h3 {
            font-size: 0.8rem;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 0.05em;
            margin-bottom: 5px;
        }

        .stat-info p {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--navy);
        }

        .stat-icon {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Colores dinámicos del dashboard */
        .stat-pending { background-color: #FEF3C7; color: #D97706; }
        .stat-confirmed { background-color: #E0F2FE; color: #0284C7; }
        .stat-completed { background-color: #D1FAE5; color: #059669; }
        .stat-cancelled { background-color: #FEE2E2; color: #DC2626; }
        .stat-total { background-color: #F3F4F6; color: var(--navy); }

        /* --- FILTROS Y CONTROLES DE TABLA --- */
        .controls-card {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.02);
        }

        .search-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
            margin-bottom: 15px;
        }

        @media (min-width: 768px) {
            .search-grid {
                grid-template-columns: 2fr 1fr;
            }
        }

        .search-input-wrapper {
            position: relative;
            display: flex;
            align-items: center;
        }

        .search-input-wrapper i {
            position: absolute;
            left: 12px;
            color: var(--text-muted);
        }

        .search-input-wrapper input {
            padding-left: 40px !important;
        }

        .filters-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
            gap: 10px;
        }

        /* --- TABLA ADMINISTRATIVA --- */
        .table-wrapper {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 8px;
            overflow-x: auto;
            box-shadow: 0 1px 3px rgba(0,0,0,0.02);
        }

        .admin-table {
            width: 100%;
            border-collapse: collapse;
            text-align: left;
            font-size: 0.85rem;
        }

        .admin-table th {
            background-color: #F3F4F6;
            color: var(--navy);
            font-weight: 700;
            padding: 12px 16px;
            border-bottom: 1px solid var(--border);
            white-space: nowrap;
        }

        .admin-table td {
            padding: 12px 16px;
            border-bottom: 1px solid var(--border);
            color: var(--text-dark);
            white-space: nowrap;
        }

        .admin-table tr:hover {
            background-color: #F9FAFB;
        }

        /* --- BADGES (ETIQUETAS DE ESTADO) --- */
        .badge {
            display: inline-flex;
            align-items: center;
            gap: 5px;
            padding: 4px 8px;
            border-radius: 9999px;
            font-size: 0.75rem;
            font-weight: 700;
            text-transform: uppercase;
        }

        .badge-pendiente { background-color: #FEF3C7; color: #B45309; }
        .badge-confirmada { background-color: #E0F2FE; color: #0369A1; }
        .badge-reagendada { background-color: #FFEDD5; color: #C2410C; }
        .badge-completada { background-color: #D1FAE5; color: #047857; }
        .badge-cancelada { background-color: #FEE2E2; color: #B91C1C; }

        /* Botones de acción en tabla */
        .actions-cell {
            display: flex;
            gap: 5px;
        }

        .btn-action {
            border: none;
            background: #F3F4F6;
            color: var(--text-dark);
            padding: 6px;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.2s;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }

        .btn-action:hover {
            background: #E5E7EB;
            color: var(--navy);
        }

        .btn-action-view { background-color: #F3F4F6; }
        .btn-action-confirm { background-color: #E0F2FE; color: #0369A1; }
        .btn-action-confirm:hover { background-color: #BAE6FD; }
        .btn-action-reschedule { background-color: #FFEDD5; color: #C2410C; }
        .btn-action-reschedule:hover { background-color: #FED7AA; }
        .btn-action-complete { background-color: #D1FAE5; color: #047857; }
        .btn-action-complete:hover { background-color: #A7F3D0; }
        .btn-action-cancel { background-color: #FEE2E2; color: #B91C1C; }
        .btn-action-cancel:hover { background-color: #FCA5A5; }

        /* Tooltip simple para acciones */
        .btn-action::after {
            content: attr(data-tooltip);
            position: absolute;
            bottom: 125%;
            left: 50%;
            transform: translateX(-50%);
            background: var(--navy);
            color: var(--white);
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 0.7rem;
            white-space: nowrap;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.2s;
            z-index: 100;
        }

        .btn-action:hover::after {
            opacity: 1;
        }

        /* --- CALENDARIO VISUAL --- */
        .calendar-wrapper {
            background: var(--white);
            border: 1px solid var(--border);
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.02);
        }

        .calendar-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .calendar-header h2 {
            font-size: 1.2rem;
            color: var(--navy);
            font-weight: 700;
            text-transform: capitalize;
        }

        .calendar-grid {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 5px;
        }

        .calendar-day-header {
            text-align: center;
            font-weight: 700;
            font-size: 0.75rem;
            color: var(--text-muted);
            padding: 10px 0;
            background-color: #F3F4F6;
            border-radius: 4px;
        }

        .calendar-cell {
            min-height: 90px;
            border: 1px solid var(--border);
            border-radius: 4px;
            padding: 5px;
            background-color: var(--white);
            display: flex;
            flex-direction: column;
            gap: 4px;
            transition: background-color 0.2s;
        }

        .calendar-cell.other-month {
            background-color: #F9FAFB;
            opacity: 0.5;
        }

        .calendar-cell.today {
            border-color: var(--blue);
            background-color: #F0F9FF;
        }

        .calendar-date-number {
            font-size: 0.75rem;
            font-weight: 700;
            color: var(--text-muted);
            margin-bottom: 2px;
        }

        .calendar-events-container {
            display: flex;
            flex-direction: column;
            gap: 2px;
            flex-grow: 1;
            overflow-y: auto;
            max-height: 65px;
        }

        .calendar-event-pill {
            font-size: 0.65rem;
            font-weight: 600;
            padding: 2px 4px;
            border-radius: 3px;
            cursor: pointer;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            transition: opacity 0.2s;
        }

        .calendar-event-pill:hover {
            opacity: 0.8;
        }

        .event-pill-confirmada { background-color: #E0F2FE; color: #0369A1; border-left: 2px solid var(--blue); }
        .event-pill-reagendada { background-color: #FFEDD5; color: #C2410C; border-left: 2px solid var(--status-rescheduled); }

        /* --- MODALES ADMINISTRATIVOS --- */
        .modal-body-details {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
            font-size: 0.9rem;
        }

        @media (min-width: 600px) {
            .modal-body-details {
                grid-template-columns: repeat(2, 1fr);
            }
            .detail-full {
                grid-column: span 2;
            }
        }

        .detail-item h4 {
            font-size: 0.75rem;
            color: var(--text-muted);
            text-transform: uppercase;
            margin-bottom: 2px;
        }

        .detail-item p {
            color: var(--text-dark);
            font-weight: 500;
        }

        /* --- SEGURIDAD: LOGIN MODAL --- */
        #admin-login-modal {
            display: none;
            position: fixed;
            z-index: 3000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 43, 73, 0.8);
            backdrop-filter: blur(8px);
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        #admin-login-modal.active {
            display: flex;
        }

        .login-card {
            background: var(--white);
            border-radius: 8px;
            padding: 30px;
            width: 100%;
            max-width: 400px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
            text-align: center;
            animation: modalFadeIn 0.3s ease;
        }

        .login-card h2 {
            color: var(--navy);
            font-size: 1.3rem;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .login-card p {
            font-size: 0.85rem;
            color: var(--text-muted);
            margin-bottom: 20px;
        }

        /* --- FOOTER LINK --- */
        .footer-admin-link {
            text-align: center;
            margin-top: 15px;
        }

        .footer-admin-link a {
            color: var(--text-muted);
            font-size: 0.75rem;
            text-decoration: none;
            font-weight: 500;
        }

        .footer-admin-link a:hover {
            color: var(--blue);
            text-decoration: underline;
        }
    </style>
</head>
<body>

    <!-- NAVEGACIÓN PRINCIPAL -->
    <nav>
        <div class="nav-logo">
            <img src="logo.png" alt="VoltTech Logo">
        </div>
        <div class="nav-links">
            <a href="#servicios">Servicios</a>
            <a href="#trabajos">Trabajos</a>
            <a href="#contacto">Contacto</a>
            <!-- Botones de acción directa -->
            <a href="#" class="nav-btn-accent" id="nav-btn-inspection">Solicitar Inspección</a>
            <a href="#" style="font-size: 13px; color: var(--text-muted); border-left: 1px solid var(--border); padding-left: 15px; display: inline-flex; align-items: center; gap: 5px;" id="nav-admin-access-btn">
                <i data-lucide="shield-check" size="14"></i> Admin
            </a>
        </div>
    </nav>

    <!-- BLOQUE COMPLETO DE LA PÁGINA PÚBLICA -->
    <div id="public-website">
        <!-- Sección Hero con marca de agua incorporada en fondo -->
        <section class="hero">
            <div class="hero-content">
                <!-- Contenedor del Logo Principal con Proporciones Controladas -->
                <div class="hero-logo-container">
                    <img src="logo.png" alt="VoltTech Soluciones Residenciales" class="hero-logo-main">
                </div>
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
                    <div class="footer-admin-link">
                        <a href="#" id="footer-admin-trigger"><i data-lucide="lock" size="10"></i> Acceso al Panel de Control</a>
                    </div>
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
                © 2026 VoltTech. Soluciones residenciales técnicas y seguras.
            </div>
        </footer>
    </div>


    <!-- ==========================================================================
       --- SECCIÓN ADMINISTRATIVA COMPLETA (OCULTA POR DEFECTO) ---
       ========================================================================== -->
    <div id="admin-panel">
        <header class="admin-header">
            <h1><i data-lucide="shield-check"></i> Panel de Control Administrativo</h1>
            <button class="btn-inspection" id="admin-logout-btn" style="height: 40px; font-size: 0.85rem; background: var(--navy); border: 1px solid rgba(255,255,255,0.3);">
                <i data-lucide="log-out"></i> Salir del Panel
            </button>
        </header>

        <!-- Pestañas de navegación interna de Administración -->
        <div class="admin-nav-tabs">
            <button class="admin-tab-btn active" data-tab="admin-tab-stats">
                <i data-lucide="bar-chart-3"></i> Estadísticas
            </button>
            <button class="admin-tab-btn" data-tab="admin-tab-table">
                <i data-lucide="list"></i> Solicitudes
            </button>
            <button class="admin-tab-btn" data-tab="admin-tab-calendar">
                <i data-lucide="calendar"></i> Calendario Visual
            </button>
        </div>

        <div class="admin-container">
            
            <!-- PESTAÑA 1: INDICADORES ESTADÍSTICOS -->
            <section id="admin-tab-stats" class="admin-section-content active">
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-info">
                            <h3>Pendientes</h3>
                            <p id="stat-count-pending">0</p>
                        </div>
                        <div class="stat-icon stat-pending"><i data-lucide="clock"></i></div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-info">
                            <h3>Confirmadas</h3>
                            <p id="stat-count-confirmed">0</p>
                        </div>
                        <div class="stat-icon stat-confirmed"><i data-lucide="check-circle-2"></i></div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-info">
                            <h3>Completadas</h3>
                            <p id="stat-count-completed">0</p>
                        </div>
                        <div class="stat-icon stat-completed"><i data-lucide="check-square"></i></div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-info">
                            <h3>Canceladas</h3>
                            <p id="stat-count-cancelled">0</p>
                        </div>
                        <div class="stat-icon stat-cancelled"><i data-lucide="x-circle"></i></div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-info">
                            <h3>Total del Mes</h3>
                            <p id="stat-count-month">0</p>
                        </div>
                        <div class="stat-icon stat-total"><i data-lucide="trending-up"></i></div>
                    </div>
                </div>
            </section>

            <!-- PESTAÑA 2: LISTADO / FILTRADO / BÚSQUEDA -->
            <section id="admin-tab-table" class="admin-section-content">
                <div class="controls-card">
                    <div class="search-grid">
                        <div class="search-input-wrapper">
                            <i data-lucide="search" size="18"></i>
                            <input type="text" id="admin-search-box" placeholder="Buscar por Código UVT, nombre, teléfono o correo electrónico...">
                        </div>
                        <div class="form-group" style="gap:0;">
                            <input type="date" id="admin-filter-date">
                        </div>
                    </div>
                    <div class="filters-grid">
                        <div class="form-group" style="gap:0;">
                            <select id="admin-filter-status">
                                <option value="">Todos los estados</option>
                                <option value="Pendiente">Pendiente</option>
                                <option value="Confirmada">Confirmada</option>
                                <option value="Reagendada">Reagendada</option>
                                <option value="Completada">Completada</option>
                                <option value="Cancelada">Cancelada</option>
                            </select>
                        </div>
                        <div class="form-group" style="gap:0;">
                            <select id="admin-filter-service">
                                <option value="">Todos los servicios</option>
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
                        <button class="btn-inspection" id="admin-clear-filters" style="height:44px; font-size:0.85rem; background: #E5E7EB; color: var(--text-dark);">
                            <i data-lucide="filter-x"></i> Limpiar
                        </button>
                    </div>
                </div>

                <div class="table-wrapper">
                    <table class="admin-table">
                        <thead>
                            <tr>
                                <th>Código UVT</th>
                                <th>Creación</th>
                                <th>Cliente</th>
                                <th>Teléfono</th>
                                <th>Correo</th>
                                <th>Dirección</th>
                                <th>Servicio</th>
                                <th>Fecha Solicitada</th>
                                <th>Hora</th>
                                <th>Estado</th>
                                <th style="text-align: center;">Acciones</th>
                            </tr>
                        </thead>
                        <tbody id="admin-table-body">
                            <!-- Inyección dinámica de solicitudes -->
                        </tbody>
                    </table>
                </div>
            </section>

            <!-- PESTAÑA 3: CALENDARIO VISUAL -->
            <section id="admin-tab-calendar" class="admin-section-content">
                <div class="calendar-wrapper">
                    <div class="calendar-header">
                        <button class="btn-action" id="calendar-prev-month"><i data-lucide="chevron-left"></i></button>
                        <h2 id="calendar-current-month-label">Enero 2026</h2>
                        <button class="btn-action" id="calendar-next-month"><i data-lucide="chevron-right"></i></button>
                    </div>
                    <div class="calendar-grid" id="calendar-container">
                        <!-- Inyección dinámica de días y citas -->
                    </div>
                </div>
            </section>

        </div>
    </div>


    <!-- ==========================================================================
       --- VENTANAS EMERGENTES (MODALES) DE ADMINISTRACIÓN ---
       ========================================================================== -->

    <!-- LOGIN MODAL DE SEGURIDAD -->
    <div id="admin-login-modal">
        <div class="login-card">
            <h2><i data-lucide="lock"></i> Acceso Protegido</h2>
            <p>Ingrese la contraseña de seguridad para acceder al panel VoltTech.</p>
            <form id="admin-login-form">
                <div class="form-group" style="margin-bottom: 15px;">
                    <input type="password" id="admin-login-password" placeholder="••••••••" required>
                </div>
                <div style="display: flex; gap: 10px;">
                    <button type="button" class="btn-submit" id="admin-login-cancel" style="background:#E5E7EB; color:var(--text-dark); margin:0;">Cancelar</button>
                    <button type="submit" class="btn-submit" style="margin:0;">Verificar</button>
                </div>
            </form>
        </div>
    </div>

    <!-- MODAL 1: DETALLES DE LA SOLICITUD -->
    <div id="admin-modal-details" class="modal">
        <div class="modal-content">
            <span class="close-btn" id="close-modal-details-btn">&times;</span>
            <div class="modal-header">
                <h2>Detalles de la Solicitud</h2>
                <p>Información completa registrada del servicio técnico.</p>
            </div>
            <div class="modal-body-details" id="admin-details-content">
                <!-- Inyección dinámica de detalles del cliente -->
            </div>
        </div>
    </div>

    <!-- MODAL 2: FORMULARIO DE REAGENDACIÓN -->
    <div id="admin-modal-reschedule" class="modal">
        <div class="modal-content" style="max-width: 450px;">
            <span class="close-btn" id="close-modal-reschedule-btn">&times;</span>
            <div class="modal-header">
                <h2>Proponer Reagendamiento</h2>
                <p>Seleccione los nuevos datos temporales que serán propuestos al cliente.</p>
            </div>
            <form id="admin-reschedule-form">
                <input type="hidden" id="reschedule-ticket-id">
                <div class="form-grid" style="grid-template-columns: 1fr;">
                    <div class="form-group">
                        <label for="reschedule-new-date">Nueva Fecha Propuesta *</label>
                        <input type="date" id="reschedule-new-date" required>
                    </div>
                    <div class="form-group">
                        <label for="reschedule-new-time">Nueva Hora Propuesta *</label>
                        <input type="time" id="reschedule-new-time" required>
                    </div>
                </div>
                <button type="submit" class="btn-submit"><i data-lucide="check"></i> Confirmar y Enviar Propuesta</button>
            </form>
        </div>
    </div>

    <!-- MODAL 3: CANCELACIÓN DE SOLICITUD -->
    <div id="admin-modal-cancel" class="modal">
        <div class="modal-content" style="max-width: 450px;">
            <span class="close-btn" id="close-modal-cancel-btn">&times;</span>
            <div class="modal-header">
                <h2>Cancelar Solicitud</h2>
                <p>Indique las razones para archivar y cancelar esta visita técnica.</p>
            </div>
            <form id="admin-cancel-form">
                <input type="hidden" id="cancel-ticket-id">
                <div class="form-group" style="margin-bottom: 15px;">
                    <label for="cancel-reason">Motivo de Cancelación *</label>
                    <textarea id="cancel-reason" placeholder="Escriba la causa de la cancelación..." required></textarea>
                </div>
                <button type="submit" class="btn-submit" style="background: var(--status-cancelled);"><i data-lucide="trash-2"></i> Cancelar Solicitud Permanentemente</button>
            </form>
        </div>
    </div>


    <!-- PUBLIC FORM: VENTANA MODAL PARA SOLICITUD DE INSPECCIÓN PÚBLICA -->
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
                            <input type="text" id="ins-nombre" name="name" placeholder="Ej. Juan Pérez" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="ins-telefono">Número de Teléfono *</label>
                            <input type="tel" id="ins-telefono" name="phone" placeholder="Ej. 7542-2893" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="ins-email">Correo Electrónico *</label>
                            <input type="email" id="ins-email" name="email" placeholder="cliente@correo.com" required>
                        </div>
                        
                        <div class="form-group full-width">
                            <label for="ins-direccion">Dirección del Servicio *</label>
                            <input type="text" id="ins-direccion" name="address" placeholder="Calle, Barrio o Residencial, Managua" required>
                        </div>
                        
                        <div class="form-group full-width">
                            <label for="ins-servicio">Tipo de Servicio *</label>
                            <select id="ins-servicio" name="service" required>
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
                            <input type="date" id="ins-fecha" name="date" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="ins-hora">Hora preferida de visita *</label>
                            <input type="time" id="ins-hora" name="time" required>
                        </div>
                        
                        <div class="form-group full-width">
                            <label for="ins-descripcion">Descripción del problema o trabajo solicitado *</label>
                            <textarea id="ins-descripcion" name="message" placeholder="Describa brevemente el problema eléctrico o de plomería..." required></textarea>
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


    <script>
        // --- CONFIGURACIÓN DE EMAILJS ---
        const EMAILJS_PUBLIC_KEY = "NFTtUpZvGUe9peZW1"; 
        const EMAILJS_SERVICE_ID = "service_volttech";
        
        // Identificadores de Plantillas
        const EMAILJS_TEMPLATE_CLIENT_ID = "template_i8im4bh";    // Confirmación inicial
        const EMAILJS_TEMPLATE_ADMIN_ID = "template_ji86ohj";     // Nueva solicitud (admin)
        const EMAILJS_TEMPLATE_CONFIRM_ID = "template_confirm";   // Solicitud Confirmada (admin -> cliente)
        const EMAILJS_TEMPLATE_RESCHEDULE_ID = "template_re_agenda"; // Propuesta de reagendamiento (admin -> cliente)

        // Inicializar SDK de EmailJS
        emailjs.init({ publicKey: EMAILJS_PUBLIC_KEY });

        // Contraseña estática de administración
        const ADMIN_PASSWORD = "volttech2026";

        // --- SISTEMA DE ALMACENAMIENTO (REUTILIZAR LOCALSTORAGE) ---
        // Se cargan las solicitudes guardadas o se genera mock data en caso de estar vacío para validaciones inmediatas
        let volttech_requests = JSON.parse(localStorage.getItem('volttech_all_requests')) || [];

        // Generación de Datos de Prueba en caso de carga inicial vacía
        if (volttech_requests.length === 0) {
            const today = new Date();
            const formatDate = (offsetDays) => {
                const targetDate = new Date(today);
                targetDate.setDate(today.getDate() + offsetDays);
                const yyyy = targetDate.getFullYear();
                const mm = String(targetDate.getMonth() + 1).padStart(2, '0');
                const dd = String(targetDate.getDate()).padStart(2, '0');
                return `${yyyy}-${mm}-${dd}`;
            };

            volttech_requests = [
                {
                    ticket: "VT-20260520-4821",
                    createdAt: new Date(today.getTime() - (5 * 24 * 60 * 60 * 1000)).toISOString(),
                    name: "Roberto Castillo",
                    phone: "+505 8899-4422",
                    email: "roberto.castillo@test.com",
                    address: "Altamira D'Este, No. 42, Managua",
                    service: "Diagnóstico de fallas",
                    date: formatDate(1),
                    time: "10:30",
                    message: "Hay fluctuaciones constantes de voltaje en toda la casa, temo que dañe los equipos.",
                    status: "Pendiente"
                },
                {
                    ticket: "VT-20260525-9931",
                    createdAt: new Date(today.getTime() - (2 * 24 * 60 * 60 * 1000)).toISOString(),
                    name: "Mariela Gutiérrez",
                    phone: "+505 7766-3311",
                    email: "mariela.g@test.com",
                    address: "Km 11.5 Carretera Sur, Residencial Las Colinas",
                    service: "Mantenimiento preventivo",
                    date: formatDate(2),
                    time: "14:00",
                    message: "Mantenimiento general al panel de breakers y distribución de cargas de la bomba de agua.",
                    status: "Confirmada",
                    confirmedAt: new Date().toISOString()
                },
                {
                    ticket: "VT-20260528-1120",
                    createdAt: new Date().toISOString(),
                    name: "Carlos Ortega",
                    phone: "+505 5544-2288",
                    email: "carlos.ortega@test.com",
                    address: "Colonia Centroamérica, Sector F, Managua",
                    service: "Instalación de luminarias",
                    date: formatDate(3),
                    time: "09:00",
                    message: "Instalación de 4 lámparas LED empotradas en área de terraza exterior.",
                    status: "Reagendada",
                    newDate: formatDate(4),
                    newTime: "11:00",
                    rescheduledAt: new Date().toISOString()
                }
            ];
            localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));
        }

        // --- MANEJO DEL SITIO WEB PÚBLICO (MODAL DE SOLICITUD) ---
        const modal = document.getElementById('inspection-modal');
        const openBtnHero = document.getElementById('hero-btn-inspection');
        const openBtnNav = document.getElementById('nav-btn-inspection');
        const closeBtn = document.getElementById('close-modal-btn');
        const successCloseBtn = document.getElementById('btn-success-close');
        
        const form = document.getElementById('inspection-form');
        const formContainer = document.getElementById('modal-form-container');
        const successContainer = document.getElementById('modal-success-container');
        const successCodeSpan = document.getElementById('success-vt-code');

        const openModal = (e) => {
            if (e) e.preventDefault();
            modal.classList.add('active');
            document.body.style.overflow = 'hidden'; 
        };

        const closeModal = () => {
            modal.classList.remove('active');
            document.body.style.overflow = ''; 
            
            setTimeout(() => {
                form.reset();
                formContainer.style.display = 'block';
                successContainer.style.display = 'none';
            }, 300);
        };

        if (openBtnHero) openBtnHero.addEventListener('click', openModal);
        if (openBtnNav) openBtnNav.addEventListener('click', openModal);
        if (closeBtn) closeBtn.addEventListener('click', closeModal);
        if (successCloseBtn) successCloseBtn.addEventListener('click', closeModal);

        window.addEventListener('click', (e) => {
            if (e.target === modal) {
                closeModal();
            }
        });

        const generateVTCode = () => {
            const today = new Date();
            const yyyy = today.getFullYear();
            const mm = String(today.getMonth() + 1).padStart(2, '0');
            const dd = String(today.getDate()).padStart(2, '0');
            const randomDigits = Math.floor(1000 + Math.random() * 9000);
            return `VT-${yyyy}${mm}${dd}-${randomDigits}`;
        };

        // Enviar Formulario del Cliente
        form.addEventListener('submit', function(e) {
            e.preventDefault();

            const referenceCode = generateVTCode();

            const submissionData = {
                ticket: referenceCode,
                createdAt: new Date().toISOString(),
                name: document.getElementById('ins-nombre').value,
                phone: document.getElementById('ins-telefono').value,
                email: document.getElementById('ins-email').value,
                address: document.getElementById('ins-direccion').value,
                service: document.getElementById('ins-servicio').value,
                date: document.getElementById('ins-fecha').value,
                time: document.getElementById('ins-hora').value,
                message: document.getElementById('ins-descripcion').value,
                status: "Pendiente"
            };

            // Logs técnicos interactivos previos al envío
            console.log("--- INICIANDO ENVÍO DESDE SITIO PÚBLICO ---");
            console.log("Datos de solicitud:", submissionData);

            // Guardar en almacenamiento global e individual
            volttech_requests.push(submissionData);
            localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));
            localStorage.setItem('volttech_last_inspection', JSON.stringify(submissionData));

            const submitBtn = form.querySelector('.btn-submit');
            const originalBtnHTML = submitBtn.innerHTML;
            submitBtn.disabled = true;
            submitBtn.innerHTML = 'Enviando...';

            // Envíos de correo mediante EmailJS
            const sendToClient = emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_CLIENT_ID, submissionData);
            const sendToAdmin = emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ADMIN_ID, submissionData);

            Promise.all([sendToClient, sendToAdmin])
                .then(([resClient, resAdmin]) => {
                    console.log("SUCCESS [PÚBLICO]: Correos enviados correctamente.", resClient, resAdmin);
                    mostrarPantallaExito(referenceCode);
                    syncAdminPanel(); // Si el panel admin está activo en segundo plano, se sincroniza
                })
                .catch((error) => {
                    console.error("ERROR [PÚBLICO]: Ocurrió una falla parcial o total en EmailJS.", error);
                    // Éxito visual del frontend para evitar interrumpir al usuario
                    mostrarPantallaExito(referenceCode);
                    syncAdminPanel();
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


        // ==========================================================================
        // --- PANEL DE CONTROL ADMINISTRATIVO (LÓGICA JAVASCRIPT) ---
        // ==========================================================================

        const publicWebsite = document.getElementById('public-website');
        const adminPanel = document.getElementById('admin-panel');
        const navAdminAccessBtn = document.getElementById('nav-admin-access-btn');
        const footerAdminTrigger = document.getElementById('footer-admin-trigger');
        const adminLoginModal = document.getElementById('admin-login-modal');
        const adminLoginForm = document.getElementById('admin-login-form');
        const adminLoginPassword = document.getElementById('admin-login-password');
        const adminLoginCancel = document.getElementById('admin-login-cancel');
        const adminLogoutBtn = document.getElementById('admin-logout-btn');

        // Navegación de pestañas en Panel Administrativo
        const tabButtons = document.querySelectorAll('.admin-tab-btn');
        const tabContents = document.querySelectorAll('.admin-section-content');

        tabButtons.forEach(btn => {
            btn.addEventListener('click', () => {
                tabButtons.forEach(b => b.classList.remove('active'));
                tabContents.forEach(c => c.classList.remove('active'));
                btn.classList.add('active');
                const targetTab = btn.getAttribute('data-tab');
                document.getElementById(targetTab).classList.add('active');
                
                // Si la pestaña abierta es la del calendario, renderizamos de nuevo para ajustar tamaños
                if (targetTab === 'admin-tab-calendar') {
                    renderCalendar();
                }
            });
        });

        // Eventos de acceso de seguridad (Password Prompt)
        const showLoginModal = (e) => {
            e.preventDefault();
            adminLoginModal.classList.add('active');
            adminLoginPassword.value = '';
            adminLoginPassword.focus();
        };

        if (navAdminAccessBtn) navAdminAccessBtn.addEventListener('click', showLoginModal);
        if (footerAdminTrigger) footerAdminTrigger.addEventListener('click', showLoginModal);
        if (adminLoginCancel) adminLoginCancel.addEventListener('click', () => adminLoginModal.classList.remove('active'));

        adminLoginForm.addEventListener('submit', (e) => {
            e.preventDefault();
            if (adminLoginPassword.value === ADMIN_PASSWORD) {
                adminLoginModal.classList.remove('active');
                enterAdminPanel();
            } else {
                alert("Contraseña de administración incorrecta.");
                adminLoginPassword.value = '';
                adminLoginPassword.focus();
            }
        });

        const enterAdminPanel = () => {
            publicWebsite.style.display = 'none';
            adminPanel.style.display = 'block';
            document.body.style.overflow = ''; 
            syncAdminPanel();
            lucide.createIcons();
        };

        const exitAdminPanel = () => {
            adminPanel.style.display = 'none';
            publicWebsite.style.display = 'block';
            window.scrollTo({ top: 0, behavior: 'instant' });
        };

        if (adminLogoutBtn) adminLogoutBtn.addEventListener('click', exitAdminPanel);

        // --- SINCRONIZACIÓN Y RENDERIZACIÓN DE VISTAS ADMINISTRATIVAS ---
        const syncAdminPanel = () => {
            volttech_requests = JSON.parse(localStorage.getItem('volttech_all_requests')) || [];
            calculateMetrics();
            renderTable();
            renderCalendar();
        };

        // 1. Panel de Estadísticas (Métricas exactas)
        const calculateMetrics = () => {
            const pending = volttech_requests.filter(r => r.status === 'Pendiente').length;
            const confirmed = volttech_requests.filter(r => r.status === 'Confirmada').length;
            const completed = volttech_requests.filter(r => r.status === 'Completada').length;
            const cancelled = volttech_requests.filter(r => r.status === 'Cancelada').length;
            
            // Filtro por mes actual
            const today = new Date();
            const currentYear = today.getFullYear();
            const currentMonth = today.getMonth(); // 0-11
            const totalThisMonth = volttech_requests.filter(r => {
                const reqDate = new Date(r.createdAt);
                return reqDate.getFullYear() === currentYear && reqDate.getMonth() === currentMonth;
            }).length;

            document.getElementById('stat-count-pending').textContent = pending;
            document.getElementById('stat-count-confirmed').textContent = confirmed;
            document.getElementById('stat-count-completed').textContent = completed;
            document.getElementById('stat-count-cancelled').textContent = cancelled;
            document.getElementById('stat-count-month').textContent = totalThisMonth;
        };

        // 2. Tabla de Solicitudes (Filtros y Búsqueda)
        const searchBox = document.getElementById('admin-search-box');
        const filterStatus = document.getElementById('admin-filter-status');
        const filterService = document.getElementById('admin-filter-service');
        const filterDate = document.getElementById('admin-filter-date');
        const clearFiltersBtn = document.getElementById('admin-clear-filters');

        const filterAndSearchRequests = () => {
            const query = searchBox.value.toLowerCase().trim();
            const statusVal = filterStatus.value;
            const serviceVal = filterService.value;
            const dateVal = filterDate.value; // yyyy-mm-dd

            return volttech_requests.filter(r => {
                // Filtro de búsqueda rápida
                const matchesSearch = !query || 
                    r.ticket.toLowerCase().includes(query) ||
                    r.name.toLowerCase().includes(query) ||
                    r.phone.toLowerCase().includes(query) ||
                    r.email.toLowerCase().includes(query);

                // Filtro de estado
                const matchesStatus = !statusVal || r.status === statusVal;

                // Filtro de tipo de servicio
                const matchesService = !serviceVal || r.service === serviceVal;

                // Filtro de fecha (fecha propuesta o reagendada)
                const targetDate = r.newDate || r.date;
                const matchesDate = !dateVal || targetDate === dateVal;

                return matchesSearch && matchesStatus && matchesService && matchesDate;
            });
        };

        const renderTable = () => {
            const filtered = filterAndSearchRequests();
            const tbody = document.getElementById('admin-table-body');
            tbody.innerHTML = '';

            if (filtered.length === 0) {
                tbody.innerHTML = `<tr><td colspan="11" style="text-align:center; padding: 30px; color: var(--text-muted);">No se encontraron solicitudes que coincidan con los filtros.</td></tr>`;
                return;
            }

            // Ordenar de más reciente a más antiguo por fecha de creación
            filtered.sort((a, b) => new Date(b.createdAt) - new Date(a.createdAt));

            filtered.forEach(r => {
                const creationDate = new Date(r.createdAt).toLocaleDateString('es-NI', { day: '2-digit', month: '2-digit', year: 'numeric' });
                
                // Formatear si tiene fecha reagendada
                const dateDisplay = r.newDate ? `<span style="text-decoration: line-through; opacity: 0.6;">${r.date}</span><br><span style="color:var(--status-rescheduled); font-weight:700;">${r.newDate}</span>` : r.date;
                const timeDisplay = r.newTime ? `<span style="text-decoration: line-through; opacity: 0.6;">${r.time}</span><br><span style="color:var(--status-rescheduled); font-weight:700;">${r.newTime}</span>` : r.time;

                const tr = document.createElement('tr');
                tr.innerHTML = `
                    <td style="font-weight: 700; color: var(--navy);">${r.ticket}</td>
                    <td>${creationDate}</td>
                    <td style="font-weight: 600;">${r.name}</td>
                    <td>${r.phone}</td>
                    <td>${r.email}</td>
                    <td style="max-width: 200px; overflow: hidden; text-overflow: ellipsis; white-space: nowrap;" title="${r.address}">${r.address}</td>
                    <td>${r.service}</td>
                    <td>${dateDisplay}</td>
                    <td>${timeDisplay}</td>
                    <td><span class="badge badge-${r.status.toLowerCase()}">${r.status}</span></td>
                    <td style="text-align: center;">
                        <div class="actions-cell">
                            <button class="btn-action btn-action-view" data-tooltip="Ver detalles" onclick="viewRequestDetails('${r.ticket}')">
                                <i data-lucide="eye" size="14"></i>
                            </button>
                            ${r.status === 'Pendiente' ? `
                                <button class="btn-action btn-action-confirm" data-tooltip="Confirmar" onclick="confirmRequest('${r.ticket}')">
                                    <i data-lucide="check" size="14"></i>
                                </button>
                                <button class="btn-action btn-action-reschedule" data-tooltip="Reagendar" onclick="openRescheduleModal('${r.ticket}')">
                                    <i data-lucide="calendar" size="14"></i>
                                </button>
                                <button class="btn-action btn-action-cancel" data-tooltip="Cancelar" onclick="openCancelModal('${r.ticket}')">
                                    <i data-lucide="x" size="14"></i>
                                </button>
                            ` : ''}
                            ${r.status === 'Confirmada' || r.status === 'Reagendada' ? `
                                <button class="btn-action btn-action-complete" data-tooltip="Completar" onclick="completeRequest('${r.ticket}')">
                                    <i data-lucide="check-square" size="14"></i>
                                </button>
                                <button class="btn-action btn-action-cancel" data-tooltip="Cancelar" onclick="openCancelModal('${r.ticket}')">
                                    <i data-lucide="x" size="14"></i>
                                </button>
                            ` : ''}
                        </div>
                    </td>
                `;
                tbody.appendChild(tr);
            });
            lucide.createIcons();
        };

        // Escuchadores de eventos para filtros de tabla
        searchBox.addEventListener('input', renderTable);
        filterStatus.addEventListener('change', renderTable);
        filterService.addEventListener('change', renderTable);
        filterDate.addEventListener('change', renderTable);
        
        clearFiltersBtn.addEventListener('click', () => {
            searchBox.value = '';
            filterStatus.value = '';
            filterService.value = '';
            filterDate.value = '';
            renderTable();
        });


        // --- PROCESOS Y ACCIONES DE SOLICITUDES ---

        // A. Ver detalles
        window.viewRequestDetails = (ticketId) => {
            const req = volttech_requests.find(r => r.ticket === ticketId);
            if (!req) return;

            const content = document.getElementById('admin-details-content');
            
            let extraInfo = '';
            if (req.confirmedAt) {
                extraInfo += `<div class="detail-item detail-full"><h4>Confirmada el:</h4><p>${new Date(req.confirmedAt).toLocaleString('es-NI')}</p></div>`;
            }
            if (req.rescheduledAt) {
                extraInfo += `<div class="detail-item detail-full"><h4>Reagendada el:</h4><p>${new Date(req.rescheduledAt).toLocaleString('es-NI')}</p></div>`;
                extraInfo += `<div class="detail-item"><h4>Nueva Fecha Propuesta:</h4><p>${req.newDate}</p></div>`;
                extraInfo += `<div class="detail-item"><h4>Nueva Hora Propuesta:</h4><p>${req.newTime}</p></div>`;
            }
            if (req.completedAt) {
                extraInfo += `<div class="detail-item detail-full"><h4>Completada el:</h4><p>${new Date(req.completedAt).toLocaleString('es-NI')}</p></div>`;
            }
            if (req.cancelledAt) {
                extraInfo += `<div class="detail-item detail-full"><h4>Cancelada el:</h4><p>${new Date(req.cancelledAt).toLocaleString('es-NI')}</p></div>`;
                extraInfo += `<div class="detail-item detail-full"><h4>Motivo de Cancelación:</h4><p style="color:var(--status-cancelled); font-style: italic;">"${req.cancellationReason}"</p></div>`;
            }

            content.innerHTML = `
                <div class="detail-item"><h4>Código UVT:</h4><p style="font-weight:700; color:var(--navy);">${req.ticket}</p></div>
                <div class="detail-item"><h4>Estado:</h4><p><span class="badge badge-${req.status.toLowerCase()}">${req.status}</span></p></div>
                <div class="detail-item"><h4>Fecha de Creación:</h4><p>${new Date(req.createdAt).toLocaleString('es-NI')}</p></div>
                <div class="detail-item"><h4>Tipo de Servicio:</h4><p>${req.service}</p></div>
                <div class="detail-item"><h4>Nombre del Cliente:</h4><p>${req.name}</p></div>
                <div class="detail-item"><h4>Teléfono:</h4><p>${req.phone}</p></div>
                <div class="detail-item detail-full"><h4>Correo Electrónico:</h4><p>${req.email}</p></div>
                <div class="detail-item detail-full"><h4>Dirección:</h4><p>${req.address}</p></div>
                <div class="detail-item"><h4>Fecha Solicitada original:</h4><p>${req.date}</p></div>
                <div class="detail-item"><h4>Hora Solicitada original:</h4><p>${req.time}</p></div>
                <div class="detail-item detail-full"><h4>Descripción/Mensaje:</h4><p style="background:#F3F4F6; padding:10px; border-radius:4px; margin-top:5px; font-size:0.85rem;">${req.message}</p></div>
                ${extraInfo}
            `;

            document.getElementById('admin-modal-details').classList.add('active');
        };

        document.getElementById('close-modal-details-btn').addEventListener('click', () => {
            document.getElementById('admin-modal-details').classList.remove('active');
        });

        // B. Confirmar Solicitud
        window.confirmRequest = (ticketId) => {
            if (!confirm(`¿Confirmar la solicitud técnica ${ticketId}? Se enviará un correo automático al cliente.`)) return;

            const reqIndex = volttech_requests.findIndex(r => r.ticket === ticketId);
            if (reqIndex === -1) return;

            volttech_requests[reqIndex].status = "Confirmada";
            volttech_requests[reqIndex].confirmedAt = new Date().toISOString();

            // Guardar cambios en LocalStorage
            localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));

            // Enviar correo automático de confirmación al cliente mediante EmailJS [4]
            const emailPayload = {
                ticket: volttech_requests[reqIndex].ticket,
                name: volttech_requests[reqIndex].name,
                email: volttech_requests[reqIndex].email,
                date: volttech_requests[reqIndex].date,
                time: volttech_requests[reqIndex].time
            };

            console.log("--- ENVIANDO CONFIRMACIÓN DE SOLICITUD A CLIENTE ---", emailPayload);

            emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_CONFIRM_ID, emailPayload)
                .then((res) => {
                    console.log("SUCCESS [ADMIN-CONFIRMACIÓN]: Correo de confirmación enviado.", res.status, res.text);
                })
                .catch((error) => {
                    console.error("ERROR [ADMIN-CONFIRMACIÓN]: Falló envío de correo automático.", error);
                });

            syncAdminPanel();
            alert(`La solicitud ${ticketId} ha sido confirmada con éxito.`);
        };

        // C. Reagendar Solicitud (Formulario modal)
        const rescheduleModal = document.getElementById('admin-modal-reschedule');
        const rescheduleForm = document.getElementById('admin-reschedule-form');

        window.openRescheduleModal = (ticketId) => {
            const req = volttech_requests.find(r => r.ticket === ticketId);
            if (!req) return;

            document.getElementById('reschedule-ticket-id').value = ticketId;
            document.getElementById('reschedule-new-date').value = req.date;
            document.getElementById('reschedule-new-time').value = req.time;

            rescheduleModal.classList.add('active');
        };

        document.getElementById('close-modal-reschedule-btn').addEventListener('click', () => {
            rescheduleModal.classList.remove('active');
        });

        rescheduleForm.addEventListener('submit', (e) => {
            e.preventDefault();
            const ticketId = document.getElementById('reschedule-ticket-id').value;
            const newDate = document.getElementById('reschedule-new-date').value;
            const newTime = document.getElementById('reschedule-new-time').value;

            const reqIndex = volttech_requests.findIndex(r => r.ticket === ticketId);
            if (reqIndex === -1) return;

            volttech_requests[reqIndex].status = "Reagendada";
            volttech_requests[reqIndex].newDate = newDate;
            volttech_requests[reqIndex].newTime = newTime;
            volttech_requests[reqIndex].rescheduledAt = new Date().toISOString();

            localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));

            // Enviar correo automático de propuesta de nueva fecha al cliente [4]
            const emailPayload = {
                ticket: volttech_requests[reqIndex].ticket,
                name: volttech_requests[reqIndex].name,
                email: volttech_requests[reqIndex].email,
                new_date: newDate,
                new_time: newTime
            };

            console.log("--- ENVIANDO PROPUESTA DE REAGENDAMIENTO A CLIENTE ---", emailPayload);

            emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_RESCHEDULE_ID, emailPayload)
                .then((res) => {
                    console.log("SUCCESS [ADMIN-REAGENDAR]: Propuesta enviada al correo del cliente.", res.status, res.text);
                })
                .catch((error) => {
                    console.error("ERROR [ADMIN-REAGENDAR]: Falló envío de propuesta por EmailJS.", error);
                });

            rescheduleModal.classList.remove('active');
            syncAdminPanel();
            alert(`Se ha reagendado la solicitud ${ticketId} correctamente.`);
        });

        // D. Completar Solicitud
        window.completeRequest = (ticketId) => {
            if (!confirm(`¿Marcar la visita técnica ${ticketId} como Completada?`)) return;

            const reqIndex = volttech_requests.findIndex(r => r.ticket === ticketId);
            if (reqIndex === -1) return;

            volttech_requests[reqIndex].status = "Completada";
            volttech_requests[reqIndex].completedAt = new Date().toISOString();

            localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));
            syncAdminPanel();
            alert(`La solicitud ${ticketId} ha sido marcada como completada.`);
        };

        // E. Cancelar Solicitud (Formulario modal)
        const cancelModal = document.getElementById('admin-modal-cancel');
        const cancelForm = document.getElementById('admin-cancel-form');

        window.openCancelModal = (ticketId) => {
            document.getElementById('cancel-ticket-id').value = ticketId;
            document.getElementById('cancel-reason').value = '';
            cancelModal.classList.add('active');
        };

        document.getElementById('close-modal-cancel-btn').addEventListener('click', () => {
            cancelModal.classList.remove('active');
        });

        cancelForm.addEventListener('submit', (e) => {
            e.preventDefault();
            const ticketId = document.getElementById('cancel-ticket-id').value;
            const reason = document.getElementById('cancel-reason').value;

            const reqIndex = volttech_requests.findIndex(r => r.ticket === ticketId);
            if (reqIndex === -1) return;

            volttech_requests[reqIndex].status = "Cancelada";
            volttech_requests[reqIndex].cancellationReason = reason;
            volttech_requests[reqIndex].cancelledAt = new Date().toISOString();

            localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));
            cancelModal.classList.remove('active');
            syncAdminPanel();
            alert(`La solicitud ${ticketId} ha sido cancelada.`);
        });


        // --- 3. CALENDARIO VISUAL INTERACTIVO (VANILLA JS) ---

        let calendarCurrentDate = new Date(2026, 4, 1); // Inicializado en Mayo de 2026 para coincidir con la mock data

        const monthNames = [
            "enero", "febrero", "marzo", "abril", "mayo", "junio",
            "julio", "agosto", "septiembre", "octubre", "noviembre", "diciembre"
        ];

        const renderCalendar = () => {
            const calendarContainer = document.getElementById('calendar-container');
            if (!calendarContainer) return;

            calendarContainer.innerHTML = '';

            const year = calendarCurrentDate.getFullYear();
            const month = calendarCurrentDate.getMonth();

            document.getElementById('calendar-current-month-label').textContent = `${monthNames[month]} ${year}`;

            // Cabeceras de días de la semana
            const daysOfWeek = ["Dom", "Lun", "Mar", "Mié", "Jue", "Vie", "Sáb"];
            daysOfWeek.forEach(day => {
                const headerCell = document.createElement('div');
                headerCell.className = 'calendar-day-header';
                headerCell.textContent = day;
                calendarContainer.appendChild(headerCell);
            });

            // Primer día del mes y número total de días
            const firstDayIndex = new Date(year, month, 1).getDay();
            const totalDaysInMonth = new Date(year, month + 1, 0).getDate();
            const totalDaysInPrevMonth = new Date(year, month, 0).getDate();

            // Rellenar días del mes anterior
            for (let i = firstDayIndex; i > 0; i--) {
                const dayNum = totalDaysInPrevMonth - i + 1;
                const cell = createCalendarCell(year, month - 1, dayNum, true);
                calendarContainer.appendChild(cell);
            }

            // Rellenar días del mes actual
            const today = new Date();
            for (let dayNum = 1; dayNum <= totalDaysInMonth; dayNum++) {
                const isToday = today.getFullYear() === year && today.getMonth() === month && today.getDate() === dayNum;
                const cell = createCalendarCell(year, month, dayNum, false, isToday);
                calendarContainer.appendChild(cell);
            }

            // Rellenar días del mes siguiente para completar la cuadrícula de 42 celdas
            const totalCellsRendered = firstDayIndex + totalDaysInMonth;
            const remainingCells = 42 - totalCellsRendered;
            for (let i = 1; i <= remainingCells; i++) {
                const cell = createCalendarCell(year, month + 1, i, true);
                calendarContainer.appendChild(cell);
            }
        };

        const createCalendarCell = (year, month, dayNum, isOtherMonth, isToday = false) => {
            const cell = document.createElement('div');
            cell.className = 'calendar-cell';
            if (isOtherMonth) cell.classList.add('other-month');
            if (isToday) cell.classList.add('today');

            const dateStr = `${year}-${String(month + 1).padStart(2, '0')}-${String(dayNum).padStart(2, '0')}`;

            cell.innerHTML = `<div class="calendar-date-number">${dayNum}</div>`;

            // Filtrar visitas agendadas o confirmadas en esta fecha
            const dayEvents = volttech_requests.filter(r => {
                const targetDate = r.newDate || r.date;
                return targetDate === dateStr && (r.status === 'Confirmada' || r.status === 'Reagendada');
            });

            const eventsContainer = document.createElement('div');
            eventsContainer.className = 'calendar-events-container';

            dayEvents.forEach(evt => {
                const eventPill = document.createElement('div');
                eventPill.className = `calendar-event-pill event-pill-${evt.status.toLowerCase()}`;
                eventPill.textContent = `${evt.time} - ${evt.name}`;
                eventPill.setAttribute('title', `${evt.service} (${evt.name})`);
                
                // Acción para abrir drill-down de detalles directo desde el calendario
                eventPill.addEventListener('click', (e) => {
                    e.stopPropagation();
                    viewRequestDetails(evt.ticket);
                });

                eventsContainer.appendChild(eventPill);
            });

            cell.appendChild(eventsContainer);
            return cell;
        };

        // Controles de navegación de meses del calendario
        document.getElementById('calendar-prev-month').addEventListener('click', () => {
            calendarCurrentDate.setMonth(calendarCurrentDate.getMonth() - 1);
            renderCalendar();
        });

        document.getElementById('calendar-next-month').addEventListener('click', () => {
            calendarCurrentDate.setMonth(calendarCurrentDate.getMonth() + 1);
            renderCalendar();
        });
    </script>
</body>
</html>
