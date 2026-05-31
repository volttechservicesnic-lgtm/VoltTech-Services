
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
    
    <!-- SDK oficial de Supabase para manejo de base de datos relacional en cliente -->
    <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
    
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
        .badge-reagendada_confirmada { background-color: #D1FAE5; color: #047857; }
        .badge-esperando_respuesta_del_cliente { background-color: #FEF3C7; color: #B45309; }
        .badge-reagendacion_rechazada { background-color: #FEE2E2; color: #B91C1C; }
        .badge-nueva_propuesta_del_cliente { background-color: #FFEDD5; color: #C2410C; }
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
        .event-pill-reagendada_confirmada { background-color: #D1FAE5; color: #047857; border-left: 2px solid var(--status-completed); }

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
    </style>
</head>
<body>
    <!-- INTERFAZ CLIENTE: RESPUESTAS DE ENLACES EXTERNOS (Aceptar / Rechazar / Proponer) -->
    <div id="customer-action-view" style="display:none; min-height:85vh; background-color: #F3F4F6; padding: 40px 5%; align-items:center; justify-content:center;">
        <div class="modal-content" style="max-width: 550px; margin: auto; box-shadow: 0 4px 20px rgba(0,0,0,0.08); text-align: center;">
            <div id="customer-loading">
                <p>Cargando información técnica de su solicitud...</p>
            </div>
            
            <div id="customer-success" style="display:none;">
                <div class="success-icon" style="color: #10B981; margin-bottom: 15px;">
                    <i data-lucide="badge-check" style="width: 64px; height: 64px; margin: 0 auto;"></i>
                </div>
                <h2 id="customer-success-title" class="success-title">¡Respuesta Registrada!</h2>
                <p id="customer-success-text" class="success-text" style="margin-bottom: 20px;">Su respuesta ha sido registrada exitosamente. Gracias por confiar en VoltTech.</p>
                <button class="btn-close-modal" onclick="window.location.href = window.location.pathname">Volver al inicio</button>
            </div>

            <div id="customer-proposal-form-container" style="display:none; text-align: left;">
                <div class="modal-header">
                    <h2>Proponer Fecha Alternativa</h2>
                    <p>Sugerir día y hora más conveniente para su inspección técnica de VoltTech.</p>
                </div>
                <form id="customer-proposal-form">
                    <input type="hidden" id="cust-ticket-id">
                    <div class="form-grid" style="grid-template-columns: 1fr; margin-bottom:15px;">
                        <div class="form-group">
                            <label for="cust-new-date">Nueva Fecha Sugerida *</label>
                            <input type="date" id="cust-new-date" required>
                        </div>
                        <div class="form-group">
                            <label for="cust-new-time">Nueva Hora Sugerida *</label>
                            <input type="time" id="cust-new-time" required>
                        </div>
                    </div>
                    <button type="submit" class="btn-submit"><i data-lucide="send"></i> Enviar Alternativa al Administrador</button>
                </form>
            </div>
        </div>
    </div>

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
                                <option value="Propuesta de Reagendación Pendiente">Propuesta Pendiente</option>
                                <option value="Reagendada Confirmada">Reagendada Confirmada</option>
                                <option value="Esperando respuesta del cliente">Esperando respuesta del cliente</option>
                                <option value="Reagendación Rechazada">Reagendación Rechazada</option>
                                <option value="Nueva propuesta del cliente">Nueva propuesta del cliente</option>
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
        <div class="login-card" id="login-form-container">
            <h2><i data-lucide="lock"></i> Acceso Protegido</h2>
            <p>Ingrese la contraseña de seguridad para acceder al panel VoltTech.</p>
            <form id="admin-login-form">
                <div class="form-group" style="margin-bottom: 15px;">
                    <input type="password" id="admin-login-password" placeholder="••••••••" required>
                </div>
                <div style="margin-bottom: 15px; text-align: right;">
                    <a href="#" id="admin-forgot-password-trigger" style="font-size: 0.8rem; color: var(--blue); text-decoration: none;">¿Olvidó su contraseña?</a>
                </div>
                <div style="display: flex; gap: 10px;">
                    <button type="button" class="btn-submit" id="admin-login-cancel" style="background:#E5E7EB; color:var(--text-dark); margin:0;">Cancelar</button>
                    <button type="submit" class="btn-submit" style="margin:0;">Verificar</button>
                </div>
            </form>
        </div>

        <!-- Módulo de Recuperación de Contraseña -->
        <div class="login-card" id="recovery-form-container" style="display:none;">
            <h2><i data-lucide="shield-alert"></i> Recuperación</h2>
            <div id="recovery-step-1">
                <p>Se enviará un código temporal de verificación de 6 dígitos al correo electrónico registrado de recuperación.</p>
                <button type="button" class="btn-submit" id="btn-send-recovery-code" style="margin-bottom: 10px;"><i data-lucide="mail"></i> Enviar Código de Verificación</button>
                <br>
                <a href="#" id="btn-back-to-login" style="font-size: 0.8rem; color: var(--text-muted); text-decoration: none;">Volver al Login</a>
            </div>

            <div id="recovery-step-2" style="display:none;">
                <p>Escriba el código de 6 dígitos recibido por correo electrónico.</p>
                <div class="form-group" style="margin-bottom: 15px;">
                    <input type="text" id="recovery-input-code" placeholder="123456" maxlength="6" style="text-align:center; font-size:1.5rem; letter-spacing:4px;" required>
                </div>
                <button type="button" class="btn-submit" id="btn-verify-recovery-code" style="margin-bottom: 10px;">Verificar Código</button>
            </div>

            <div id="recovery-step-3" style="display:none; text-align:left;">
                <p style="text-align:center; margin-bottom:15px;">Código verificado. Establezca una nueva contraseña segura.</p>
                <div class="form-grid" style="grid-template-columns: 1fr; gap:10px;">
                    <div class="form-group">
                        <label for="rec-new-pwd">Nueva Contraseña *</label>
                        <input type="password" id="rec-new-pwd" required>
                    </div>
                    <div class="form-group">
                        <label for="rec-confirm-pwd">Confirmar Contraseña *</label>
                        <input type="password" id="rec-confirm-pwd" required>
                    </div>
                </div>
                <button type="button" class="btn-submit" id="btn-reset-password-submit" style="margin-top:15px;"><i data-lucide="check"></i> Guardar y Entrar</button>
            </div>
        </div>
    </div>

    <!-- MODAL 1: DETALLES DE LA SOLICITUD -->
    <div id="admin-modal-details" class="modal">
        <div class="modal-content">
            <span class="close-btn" id="close-modal-details-btn">&times;</span>
            <div class="modal-header">
                <h2>Detalles de la Solicitud</h2>
                <p>Información completa registrada e historial técnico de auditoría.</p>
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
                <p>La cita quedará en espera de confirmación por el cliente sin modificar el calendario temporal.</p>
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
                <button type="submit" class="btn-submit"><i data-lucide="send"></i> Enviar Propuesta a Cliente</button>
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
        const EMAILJS_TEMPLATE_CLIENT_ID = "template_i8im4bh";      // Única plantilla para clientes
        const EMAILJS_TEMPLATE_ADMIN_ID = "template_ji86ohj";       // Notificaciones al Administrador
        const EMAILJS_TEMPLATE_RESET_CODE_ID = "template_reset_pwd"; // Código de recuperación

        // Inicializar SDK de EmailJS
        emailjs.init({ publicKey: EMAILJS_PUBLIC_KEY });

        // Pie de firma institucional obligatorio de VoltTech
        const INSTITUTIONAL_FOOTER = 
            "\n\nAgradecemos la confianza depositada en nuestros servicios.\n\n" +
            "Trabajamos para brindarle atención técnica responsable, puntual y de calidad.\n\n" +
            "Gracias por preferir VoltTech Servicios.\n\n" +
            "Atentamente,\n\n" +
            "VoltTech Servicios\n" +
            "Electricidad y Plomería Residencial\n" +
            "WhatsApp: +505 7542-2893\n" +
            "Correo: volttechservices.nic@gmail.com";


        // ==========================================================================
        // --- SISTEMA CRIPTOGRÁFICO DE CONTRASEÑA (CON FALLBACK INTEGRADO) ---
        // ==========================================================================
        async function hashPassword(password) {
            if (window.crypto && window.crypto.subtle) {
                try {
                    const encoder = new TextEncoder();
                    const data = encoder.encode(password);
                    const hash = await crypto.subtle.digest('SHA-256', data);
                    return Array.from(new Uint8Array(hash)).map(b => b.toString(16).padStart(2, '0')).join('');
                } catch (e) {
                    console.warn("Fallo criptográfico nativo. Usando fallback de hash integrado.");
                }
            }
            let hash = 0;
            for (let i = 0; i < password.length; i++) {
                const char = password.charCodeAt(i);
                hash = (hash << 5) - hash + char;
                hash = hash & hash; 
            }
            return "fallback_" + Math.abs(hash).toString(16);
        }

        async function initSecurity() {
            try {
                if (!localStorage.getItem('volttech_admin_pwd_hash')) {
                    const defaultHash = await hashPassword('volttech2026');
                    localStorage.setItem('volttech_admin_pwd_hash', defaultHash);
                    localStorage.setItem('volttech_last_pwd_change', new Date().toISOString());
                    localStorage.setItem('volttech_recovery_email', 'volttechservices.nic@gmail.com');
                    localStorage.setItem('volttech_recovery_phone', '+50575422893');
                    localStorage.setItem('volttech_auto_logout_time', '10'); 
                }
            } catch (securityInitError) {
                console.error("Error al escribir configuración inicial en localStorage:", securityInitError);
            }
        }


        // ==========================================================================
        // --- SISTEMA DE ALMACENAMIENTO DE SOLICITUDES (LOCALSTORAGE) ---
        // ==========================================================================
        let volttech_requests = [];
        try {
            volttech_requests = JSON.parse(localStorage.getItem('volttech_all_requests')) || [];
        } catch (readError) {
            console.error("Error leyendo solicitudes desde el almacenamiento local:", readError);
        }

        // Datos de prueba iniciales si está vacío
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
                    status: "Pendiente",
                    history: [
                        { date: new Date(today.getTime() - (5 * 24 * 60 * 60 * 1000)).toISOString(), action: "Solicitud registrada por el cliente.", actor: "Cliente" }
                    ]
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
                    confirmedAt: new Date().toISOString(),
                    history: [
                        { date: new Date(today.getTime() - (2 * 24 * 60 * 60 * 1000)).toISOString(), action: "Solicitud registrada por el cliente.", actor: "Cliente" },
                        { date: new Date().toISOString(), action: "Solicitud confirmada por el administrador.", actor: "Administrador" }
                    ]
                }
            ];
            try {
                localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));
            } catch (writeError) {
                console.error("Error escribiendo solicitudes en el almacenamiento local:", writeError);
            }
        }

        // Recuperador de valores seguro contra elementos DOM inexistentes o nulos
        const getInputValue = (id) => {
            const el = document.getElementById(id);
            return el ? el.value : '';
        };

        function addHistoryEntry(request, action, actor = "Administrador") {
            if (!request) return;
            if (!request.history) {
                request.history = [];
            }
            request.history.push({
                date: new Date().toISOString(),
                action: action,
                actor: actor
            });
        }


        // ==========================================================================
        // --- MANEJO DE PORTALES PÚBLICOS (MODALES) ---
        // ==========================================================================
        const openModal = (e) => {
            if (e) e.preventDefault();
            const modalInspection = document.getElementById('inspection-modal');
            if (modalInspection) modalInspection.classList.add('active');
            document.body.style.overflow = 'hidden'; 
        };

        const closeModal = () => {
            const modalInspection = document.getElementById('inspection-modal');
            if (modalInspection) modalInspection.classList.remove('active');
            document.body.style.overflow = ''; 
            
            setTimeout(() => {
                const inspectionForm = document.getElementById('inspection-form');
                const formContainer = document.getElementById('modal-form-container');
                const successContainer = document.getElementById('modal-success-container');
                if (inspectionForm) inspectionForm.reset();
                if (formContainer) formContainer.style.display = 'block';
                if (successContainer) successContainer.style.display = 'none';
            }, 300);
        };

        const generateVTCode = () => {
            const today = new Date();
            const yyyy = today.getFullYear();
            const mm = String(today.getMonth() + 1).padStart(2, '0');
            const dd = String(today.getDate()).padStart(2, '0');
            const randomDigits = Math.floor(1000 + Math.random() * 9000);
            return `VT-${yyyy}${mm}${dd}-${randomDigits}`;
        };

        const mostrarPantallaExito = (code) => {
            const span = document.getElementById('success-vt-code');
            const container = document.getElementById('modal-form-container');
            const success = document.getElementById('modal-success-container');

            if (span) span.textContent = code;
            if (container) container.style.display = 'none';
            if (success) success.style.display = 'block';
        };


        // ==========================================================================
        // --- PORTAL DE ACCIONES EXTERNAS PARA EL CLIENTE ---
        // ==========================================================================
        async function handleCustomerAction(action, ticketId) {
            const customerActionView = document.getElementById('customer-action-view');
            const publicWebsite = document.getElementById('public-website');
            const customerLoading = document.getElementById('customer-loading');
            const customerSuccess = document.getElementById('customer-success');
            const customerSuccessTitle = document.getElementById('customer-success-title');
            const customerSuccessText = document.getElementById('customer-success-text');
            const customerProposalContainer = document.getElementById('customer-proposal-form-container');

            if (publicWebsite) publicWebsite.style.display = 'none';
            if (customerActionView) customerActionView.style.display = 'flex';

            volttech_requests = JSON.parse(localStorage.getItem('volttech_all_requests')) || [];
            const reqIndex = volttech_requests.findIndex(r => r && r.ticket === ticketId);

            if (reqIndex === -1) {
                if (customerLoading) {
                    customerLoading.innerHTML = `<p style="color:var(--status-cancelled); font-weight:700;">Error: No se localizó la solicitud con código ${ticketId}.</p>`;
                }
                return;
            }

            const req = volttech_requests[reqIndex];

            if (action === 'accept') {
                req.status = "Reagendada Confirmada";
                if (req.newDate && req.newTime) {
                    req.date = req.newDate;
                    req.time = req.newTime;
                }
                
                addHistoryEntry(req, `Propuesta de reagendamiento aceptada por el cliente. Nueva fecha confirmada: ${req.date} a las ${req.time}`, "Cliente");
                localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));

                // Notificación de confirmación unificada al cliente utilizando la plantilla de cliente única (CLIENTE)
                const clientPayload = {
                    subject: `Reagendamiento Confirmado - ${req.ticket}`,
                    ticket: req.ticket,
                    name: req.name,
                    email: req.email,
                    service: req.service,
                    date: req.date,
                    time: req.time,
                    message: `Su cita de inspección ha sido reprogramada exitosamente para la nueva fecha elegida.\n\nNueva fecha: ${req.date}\nNueva hora: ${req.time}` + INSTITUTIONAL_FOOTER
                };

                const adminPayload = {
                    ticket: req.ticket,
                    name: req.name,
                    email: req.email,
                    phone: req.phone,
                    service: req.service,
                    subject: `Reagendación aceptada - ${req.ticket}`,
                    message: `El cliente ${req.name} ha aceptado la propuesta de reagendamiento. La cita ha sido confirmada para el día ${req.date} a las ${req.time}.`
                };

                emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_CLIENT_ID, clientPayload);
                emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ADMIN_ID, adminPayload);

                if (customerLoading) customerLoading.style.display = 'none';
                if (customerSuccessTitle) customerSuccessTitle.textContent = "¡Cita Confirmada!";
                if (customerSuccessText) customerSuccessText.textContent = `La propuesta fue aceptada con éxito. Su cita técnica de inspección ha sido agendada para el día ${req.date} a las ${req.time}.`;
                if (customerSuccess) customerSuccess.style.display = 'block';

            } else if (action === 'reject') {
                req.status = "Reagendación Rechazada";
                addHistoryEntry(req, "Cliente rechazó la propuesta de reagendamiento.", "Cliente");
                localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));

                const adminPayload = {
                    ticket: req.ticket,
                    name: req.name,
                    email: req.email,
                    phone: req.phone,
                    service: req.service,
                    subject: `Reagendación rechazada - ${req.ticket}`,
                    message: `El cliente ${req.name} ha rechazado la propuesta de reagendamiento para su solicitud de servicio.`
                };

                emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ADMIN_ID, adminPayload);

                if (customerLoading) customerLoading.style.display = 'none';
                if (customerSuccessTitle) customerSuccessTitle.textContent = "Propuesta Rechazada";
                if (customerSuccessText) customerSuccessText.textContent = "Ha rechazado la fecha alternativa de servicio técnico sugerida. El administrador ha sido notificado.";
                if (customerSuccess) customerSuccess.style.display = 'block';

            } else if (action === 'propose') {
                if (customerLoading) customerLoading.style.display = 'none';
                const ticketInput = document.getElementById('cust-ticket-id');
                const dateInput = document.getElementById('cust-new-date');
                const timeInput = document.getElementById('cust-new-time');
                
                if (ticketInput) ticketInput.value = ticketId;
                if (dateInput) dateInput.value = req.date;
                if (timeInput) timeInput.value = req.time;
                if (customerProposalContainer) customerProposalContainer.style.display = 'block';
            }
            lucide.createIcons();
        }


        // ==========================================================================
        // --- CONTROLADORES DE ACCESO ADMINISTRATIVO ---
        // ==========================================================================
        const showLoginModal = (e) => {
            if (e) e.preventDefault();
            const adminLoginModal = document.getElementById('admin-login-modal');
            const loginFormContainer = document.getElementById('login-form-container');
            const recoveryFormContainer = document.getElementById('recovery-form-container');
            const adminLoginPassword = document.getElementById('admin-login-password');

            if (adminLoginModal) adminLoginModal.classList.add('active');
            if (loginFormContainer) loginFormContainer.style.display = 'block';
            if (recoveryFormContainer) recoveryFormContainer.style.display = 'none';
            if (adminLoginPassword) {
                adminLoginPassword.value = '';
                adminLoginPassword.focus();
            }
        };

        const enterAdminPanel = () => {
            const publicWebsite = document.getElementById('public-website');
            const adminPanel = document.getElementById('admin-panel');

            if (publicWebsite) publicWebsite.style.display = 'none';
            if (adminPanel) adminPanel.style.display = 'block';
            
            resetActivityTimer();
            startAutoLogoutTracker();
            syncAdminPanel();
            loadSecurityTab();
            lucide.createIcons();
        };

        const exitAdminPanel = () => {
            const publicWebsite = document.getElementById('public-website');
            const adminPanel = document.getElementById('admin-panel');

            if (autoLogoutInterval) clearInterval(autoLogoutInterval);
            if (adminPanel) adminPanel.style.display = 'none';
            if (publicWebsite) publicWebsite.style.display = 'block';
            window.scrollTo({ top: 0, behavior: 'instant' });
        };


        // --- AUTOMÁTICO INACTIVIDAD ---
        let lastActivityTime = Date.now();
        let autoLogoutInterval = null;

        function resetActivityTimer() {
            lastActivityTime = Date.now();
        }

        function startAutoLogoutTracker() {
            try {
                const autoLogoutMinutes = parseInt(localStorage.getItem('volttech_auto_logout_time')) || 10;
                const autoLogoutMs = autoLogoutMinutes * 60 * 1000;

                if (autoLogoutInterval) clearInterval(autoLogoutInterval);

                autoLogoutInterval = setInterval(() => {
                    const adminPanel = document.getElementById('admin-panel');
                    if (adminPanel && adminPanel.style.display === 'block') {
                        const inactiveTime = Date.now() - lastActivityTime;
                        if (inactiveTime >= autoLogoutMs) {
                            exitAdminPanel();
                            alert("Su sesión ha expirado por inactividad.");
                        }
                    }
                }, 10000); 
            } catch (autoLogoutError) {
                console.error("Error al configurar el auto-logout:", autoLogoutError);
            }
        }


        // --- PESTAÑA SEGURIDAD ---
        function loadSecurityTab() {
            const emailEl = document.getElementById('sec-recovery-email');
            const phoneEl = document.getElementById('sec-recovery-phone');
            const logoutEl = document.getElementById('sec-auto-logout');
            const lastChangeEl = document.getElementById('sec-last-pwd-change');

            try {
                if (emailEl) emailEl.value = localStorage.getItem('volttech_recovery_email') || '';
                if (phoneEl) phoneEl.value = localStorage.getItem('volttech_recovery_phone') || '';
                if (logoutEl) logoutEl.value = localStorage.getItem('volttech_auto_logout_time') || '10';
                
                const lastChange = localStorage.getItem('volttech_last_pwd_change');
                if (lastChangeEl) lastChangeEl.textContent = lastChange ? new Date(lastChange).toLocaleString('es-NI') : 'Nunca';
            } catch (securityReadError) {
                console.error("Error al cargar la pestaña de seguridad:", securityReadError);
            }
        }


        // --- OPERACIONES GENERALES DE LA TABLA ---
        const syncAdminPanel = () => {
            try {
                volttech_requests = JSON.parse(localStorage.getItem('volttech_all_requests')) || [];
            } catch (readError) {
                console.error("Error de lectura al sincronizar el panel:", readError);
            }
            calculateMetrics();
            renderTable();
            renderCalendar();
        };

        const calculateMetrics = () => {
            const pending = volttech_requests.filter(r => r && r.status === 'Pendiente').length;
            const confirmed = volttech_requests.filter(r => r && (r.status === 'Confirmada' || r.status === 'Reagendada Confirmada')).length;
            const completed = volttech_requests.filter(r => r && r.status === 'Completada').length;
            const cancelled = volttech_requests.filter(r => r && (r.status === 'Cancelada' || r.status === 'Cancelada por Cliente' || r.status === 'Reagendación Rechazada')).length;
            
            const today = new Date();
            const currentYear = today.getFullYear();
            const currentMonth = today.getMonth();
            const totalThisMonth = volttech_requests.filter(r => {
                if (!r) return false;
                const reqDate = new Date(r.createdAt);
                return reqDate.getFullYear() === currentYear && reqDate.getMonth() === currentMonth;
            }).length;

            const elPending = document.getElementById('stat-count-pending');
            const elConfirmed = document.getElementById('stat-count-confirmed');
            const elCompleted = document.getElementById('stat-count-completed');
            const elCancelled = document.getElementById('stat-count-cancelled');
            const elMonth = document.getElementById('stat-count-month');

            if (elPending) elPending.textContent = pending;
            if (elConfirmed) elConfirmed.textContent = confirmed;
            if (elCompleted) elCompleted.textContent = completed;
            if (elCancelled) elCancelled.textContent = cancelled;
            if (elMonth) elMonth.textContent = totalThisMonth;
        };

        const filterAndSearchRequests = () => {
            const query = getInputValue('admin-search-box').toLowerCase().trim();
            const statusVal = getInputValue('admin-filter-status');
            const serviceVal = getInputValue('admin-filter-service');
            const dateVal = getInputValue('admin-filter-date');

            return volttech_requests.filter(r => {
                if (!r) return false;
                const matchesSearch = !query || 
                    (r.ticket && r.ticket.toLowerCase().includes(query)) ||
                    (r.name && r.name.toLowerCase().includes(query)) ||
                    (r.phone && r.phone.toLowerCase().includes(query)) ||
                    (r.email && r.email.toLowerCase().includes(query));

                const matchesStatus = !statusVal || r.status === statusVal;
                const matchesService = !serviceVal || r.service === serviceVal;

                const targetDate = r.newDate || r.date;
                const matchesDate = !dateVal || targetDate === dateVal;

                return matchesSearch && matchesStatus && matchesService && matchesDate;
            });
        };

        const renderTable = () => {
            const filtered = filterAndSearchRequests();
            const tbody = document.getElementById('admin-table-body');
            if (!tbody) return;

            tbody.innerHTML = '';

            if (filtered.length === 0) {
                tbody.innerHTML = `<tr><td colspan="11" style="text-align:center; padding: 30px; color: var(--text-muted);">No se encontraron solicitudes que coincidan con los filtros.</td></tr>`;
                return;
            }

            filtered.sort((a, b) => new Date(b.createdAt) - new Date(a.createdAt));

            filtered.forEach(r => {
                if (!r) return;
                const creationDate = new Date(r.createdAt).toLocaleDateString('es-NI', { day: '2-digit', month: '2-digit', year: 'numeric' });
                const dateDisplay = r.newDate ? `<span style="text-decoration: line-through; opacity: 0.6;">${r.date}</span><br><span style="color:var(--status-rescheduled); font-weight:700;">${r.newDate}</span>` : r.date;
                const timeDisplay = r.newTime ? `<span style="text-decoration: line-through; opacity: 0.6;">${r.time}</span><br><span style="color:var(--status-rescheduled); font-weight:700;">${r.newTime}</span>` : r.time;
                
                const currentStatus = r.status || "Pendiente";
                // Normalizador seguro de strings de estados para badges sin acentos (Soluciona Reagendación)
                const statusBadgeClass = currentStatus.toLowerCase().normalize("NFD").replace(/[\u0300-\u036f]/g, "").replace(/ /g, '_');

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
                    <td><span class="badge badge-${statusBadgeClass}">${currentStatus}</span></td>
                    <td style="text-align: center;">
                        <div class="actions-cell">
                            <button class="btn-action btn-action-view" data-tooltip="Ver detalles" onclick="viewRequestDetails('${r.ticket}')">
                                <i data-lucide="eye" size="14"></i>
                            </button>
                            ${currentStatus === 'Pendiente' || currentStatus === 'Esperando revisión del administrador' || currentStatus === 'Nueva propuesta del cliente' ? `
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
                            ${currentStatus === 'Confirmada' || currentStatus === 'Reagendada Confirmada' ? `
                                <button class="btn-action btn-action-complete" data-tooltip="Completar" onclick="completeRequest('${r.ticket}')">
                                    <i data-lucide="check-square" size="14"></i>
                                </button>
                                <button class="btn-action btn-action-cancel" data-tooltip="Cancelar" onclick="openCancelModal('${r.ticket}')">
                                    <i data-lucide="x" size="14"></i>
                                </button>
                            ` : ''}
                            ${currentStatus === 'Esperando respuesta del cliente' ? `
                                <span style="font-size:0.75rem; color:var(--text-muted); font-style:italic; padding:6px;">Esperando cliente</span>
                            ` : ''}
                        </div>
                    </td>
                `;
                tbody.appendChild(tr);
            });
            lucide.createIcons();
        };


        // --- ACCIONES ADMIN ---
        window.viewRequestDetails = (ticketId) => {
            const req = volttech_requests.find(r => r && r.ticket === ticketId);
            if (!req) return;

            const content = document.getElementById('admin-details-content');
            if (!content) return;
            
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

            let historyHtml = '<div class="detail-item detail-full"><h4>Historial de Auditoría:</h4><div style="background:#F9FAFB; padding:12px; border-radius:6px; border:1px solid var(--border); max-height:180px; overflow-y:auto; display:flex; flex-direction:column; gap:8px; margin-top:5px;">';
            if (req.history && req.history.length > 0) {
                req.history.forEach(h => {
                    const dateStr = new Date(h.date).toLocaleString('es-NI');
                    historyHtml += `
                        <div style="font-size:0.8rem; border-left:2px solid var(--blue); padding-left:8px; line-height:1.3;">
                            <span style="color:var(--text-muted); font-size:0.75rem;">${dateStr} - <strong>${h.actor}</strong></span>
                            <p style="margin:2px 0 0; color:var(--text-dark);">${h.action}</p>
                        </div>
                    `;
                });
            } else {
                historyHtml += '<p style="color:var(--text-muted); font-size:0.8rem; font-style:italic;">No hay historial registrado.</p>';
            }
            historyHtml += '</div></div>';

            const currentStatus = req.status || "Pendiente";
            const statusBadgeClass = currentStatus.toLowerCase().normalize("NFD").replace(/[\u0300-\u036f]/g, "").replace(/ /g, '_');

            content.innerHTML = `
                <div class="detail-item"><h4>Código UVT:</h4><p style="font-weight:700; color:var(--navy);">${req.ticket}</p></div>
                <div class="detail-item"><h4>Estado:</h4><p><span class="badge badge-${statusBadgeClass}">${currentStatus}</span></p></div>
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
                ${historyHtml}
            `;

            const detailModal = document.getElementById('admin-modal-details');
            if (detailModal) detailModal.classList.add('active');
        };

        window.confirmRequest = (ticketId) => {
            if (!confirm(`¿Confirmar la solicitud técnica ${ticketId}? Se enviará un correo de confirmación al cliente.`)) return;

            const reqIndex = volttech_requests.findIndex(r => r && r.ticket === ticketId);
            if (reqIndex === -1) return;

            const req = volttech_requests[reqIndex];
            req.status = "Confirmada";
            req.confirmedAt = new Date().toISOString();
            
            if (req.newDate && req.newTime) {
                req.date = req.newDate;
                req.time = req.newTime;
            }

            addHistoryEntry(req, "Solicitud confirmada por el administrador.");
            localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));

            // Notificación al cliente utilizando la plantilla de cliente única (ASUNTO Y MENSAJE DINÁMICO)
            const emailPayload = {
                subject: `Solicitud Confirmada - ${req.ticket}`,
                ticket: req.ticket,
                name: req.name,
                email: req.email,
                service: req.service,
                date: req.date,
                time: req.time,
                message: `Nos complace informarle que su solicitud ha sido confirmada. Nuestro equipo técnico le atenderá en la fecha y hora programadas.` + INSTITUTIONAL_FOOTER
            };

            emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_CLIENT_ID, emailPayload);

            syncAdminPanel();
            alert(`La solicitud ${ticketId} ha sido confirmada.`);
        };

        window.completeRequest = (ticketId) => {
            if (!confirm(`¿Marcar la visita técnica ${ticketId} como Completada?`)) return;

            const reqIndex = volttech_requests.findIndex(r => r && r.ticket === ticketId);
            if (reqIndex === -1) return;

            const req = volttech_requests[reqIndex];
            req.status = "Completada";
            req.completedAt = new Date().toISOString();

            addHistoryEntry(req, "Servicio completado exitosamente.");
            localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));
            syncAdminPanel();
            alert(`La solicitud ${ticketId} ha sido completada.`);
        };


        // --- CALENDARIO VISUAL (REFACTORIZADO Y SEGURO) ---
        let calendarCurrentDate = new Date(2026, 4, 1); 

        const monthNames = [
            "enero", "febrero", "marzo", "abril", "mayo", "junio",
            "julio", "agosto", "septiembre", "octubre", "noviembre", "diciembre"
        ];

        const getFormattedDateString = (y, m, d) => {
            const dateObj = new Date(y, m, d);
            const yyyy = dateObj.getFullYear();
            const mm = String(dateObj.getMonth() + 1).padStart(2, '0');
            const dd = String(dateObj.getDate()).padStart(2, '0');
            return `${yyyy}-${mm}-${dd}`;
        };

        const renderCalendar = () => {
            // LOG: Renderizando calendario (REQUISITO MODO DEPURACIÓN)
            console.log("Renderizando calendario");
            try {
                const calendarContainer = document.getElementById('calendar-container');
                if (!calendarContainer) return;

                calendarContainer.innerHTML = '';

                const year = calendarCurrentDate.getFullYear();
                const month = calendarCurrentDate.getMonth();

                const monthLabel = document.getElementById('calendar-current-month-label');
                if (monthLabel) monthLabel.textContent = `${monthNames[month]} ${year}`;

                const daysOfWeek = ["Dom", "Lun", "Mar", "Mié", "Jue", "Vie", "Sáb"];
                daysOfWeek.forEach(day => {
                    const headerCell = document.createElement('div');
                    headerCell.className = 'calendar-day-header';
                    headerCell.textContent = day;
                    calendarContainer.appendChild(headerCell);
                });

                const firstDayIndex = new Date(year, month, 1).getDay();
                const totalDaysInMonth = new Date(year, month + 1, 0).getDate();
                const totalDaysInPrevMonth = new Date(year, month, 0).getDate();

                for (let i = firstDayIndex; i > 0; i--) {
                    const dayNum = totalDaysInPrevMonth - i + 1;
                    const cell = createCalendarCell(year, month - 1, dayNum, true);
                    calendarContainer.appendChild(cell);
                }

                const today = new Date();
                for (let dayNum = 1; dayNum <= totalDaysInMonth; dayNum++) {
                    const isToday = today.getFullYear() === year && today.getMonth() === month && today.getDate() === dayNum;
                    const cell = createCalendarCell(year, month, dayNum, false, isToday);
                    calendarContainer.appendChild(cell);
                }

                const totalCellsRendered = firstDayIndex + totalDaysInMonth;
                const remainingCells = 42 - totalCellsRendered;
                for (let i = 1; i <= remainingCells; i++) {
                    const cell = createCalendarCell(year, month + 1, i, true);
                    calendarContainer.appendChild(cell);
                }
                
                // LOG: Calendario renderizado (REQUISITO MODO DEPURACIÓN)
                console.log("Calendario renderizado");
            } catch (calendarError) {
                console.error("Error crítico durante el render del calendario:", calendarError);
            }
        };

        const createCalendarCell = (year, month, dayNum, isOtherMonth, isToday = false) => {
            const cell = document.createElement('div');
            cell.className = 'calendar-cell';
            if (isOtherMonth) cell.classList.add('other-month');
            if (isToday) cell.classList.add('today');

            // Formatear fecha de forma robusta tolerando desbordes
            const dateStr = getFormattedDateString(year, month, dayNum);

            cell.innerHTML = `<div class="calendar-date-number">${dayNum}</div>`;

            // Filtrar únicamente confirmadas y reagendadas confirmadas (las canceladas se descartan) (REQUISITO CALENDARIO)
            const dayEvents = volttech_requests.filter(r => {
                if (!r) return false;
                const targetDate = r.newDate || r.date;
                return targetDate === dateStr && (r.status === 'Confirmada' || r.status === 'Reagendada Confirmada');
            });

            const eventsContainer = document.createElement('div');
            eventsContainer.className = 'calendar-events-container';

            dayEvents.forEach(evt => {
                const eventPill = document.createElement('div');
                const cleanStatusClass = (evt.status || "Pendiente").toLowerCase().normalize("NFD").replace(/[\u0300-\u036f]/g, "").replace(/ /g, '_');
                eventPill.className = `calendar-event-pill event-pill-${cleanStatusClass}`;
                eventPill.textContent = `${evt.time || ''} - ${evt.name || ''}`;
                eventPill.setAttribute('title', `${evt.service || ''} (${evt.name || ''})`);
                
                eventPill.addEventListener('click', (e) => {
                    e.stopPropagation();
                    viewRequestDetails(evt.ticket);
                });

                eventsContainer.appendChild(eventPill);
            });

            cell.appendChild(eventsContainer);
            return cell;
        };


        // ==========================================================================
        // --- CONTROLADOR DE EVENTOS PROTEGIDOS (setupEventListeners) ---
        // ==========================================================================
        function setupEventListeners() {
            // Sitio Público: Apertura y Cierre de Modal
            const openBtnHero = document.getElementById('hero-btn-inspection');
            const openBtnNav = document.getElementById('nav-btn-inspection');
            const closeBtnInspection = document.getElementById('close-modal-btn');
            const successCloseBtn = document.getElementById('btn-success-close');

            if (openBtnHero) openBtnHero.addEventListener('click', openModal);
            if (openBtnNav) openBtnNav.addEventListener('click', openModal);
            if (closeBtnInspection) closeBtnInspection.addEventListener('click', closeModal);
            if (successCloseBtn) successCloseBtn.addEventListener('click', closeModal);

            // Envío del Formulario Público (Soportado con extractores seguros contra fallas DOM)
            const inspectionForm = document.getElementById('inspection-form');
            if (inspectionForm) {
                inspectionForm.addEventListener('submit', function(e) {
                    e.preventDefault();
                    
                    // LOG: "Inicio del envío" (REQUISITO MODO DEPURACIÓN)
                    console.log("Inicio del envío");

                    const submitBtn = inspectionForm.querySelector('.btn-submit');
                    const originalBtnHTML = submitBtn ? submitBtn.innerHTML : '';
                    if (submitBtn) {
                        submitBtn.disabled = true;
                        submitBtn.innerHTML = 'Enviando Solicitud...';
                    }

                    const referenceCode = generateVTCode();

                    // Lecturas seguras usando el ayudante getInputValue
                    const submissionData = {
                        ticket: referenceCode,
                        createdAt: new Date().toISOString(),
                        name: getInputValue('ins-nombre'),
                        phone: getInputValue('ins-telefono'),
                        email: getInputValue('ins-email'),
                        address: getInputValue('ins-direccion'),
                        service: getInputValue('ins-servicio'),
                        date: getInputValue('ins-fecha'),
                        time: getInputValue('ins-hora'),
                        message: getInputValue('ins-descripcion'),
                        status: "Pendiente",
                        history: [
                            { date: new Date().toISOString(), action: "Solicitud registrada por el cliente.", actor: "Cliente" }
                        ]
                    };

                    volttech_requests.push(submissionData);
                    try {
                        localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));
                        localStorage.setItem('volttech_last_inspection', JSON.stringify(submissionData));
                        
                        // LOG: "Solicitud guardada" (REQUISITO MODO DEPURACIÓN)
                        console.log("Solicitud guardada");
                    } catch (storageError) {
                        console.error("Error guardando localmente:", storageError);
                    }

                    // Enviar correos: el cliente recibe la confirmación inicial en la plantilla única
                    const clientPayload = {
                        subject: `Confirmación de solicitud de servicio - ${referenceCode}`,
                        ticket: referenceCode,
                        name: submissionData.name,
                        email: submissionData.email,
                        service: submissionData.service,
                        date: submissionData.date,
                        time: submissionData.time,
                        message: "Su solicitud de inspección técnica ha sido registrada de forma segura en nuestro sistema de atención.\n\nPronto evaluaremos la disponibilidad del horario propuesto." + INSTITUTIONAL_FOOTER
                    };

                    // Despachar promesas con logs específicos integrados (REQ)
                    const sendToClient = emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_CLIENT_ID, clientPayload)
                        .then((res) => {
                            // LOG: "Correo cliente enviado" (REQUISITO MODO DEPURACIÓN)
                            console.log("Correo cliente enviado");
                            return res;
                        })
                        .catch((err) => {
                            console.error("Falla en el correo del cliente:", err);
                            throw err;
                        });

                    const sendToAdmin = emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ADMIN_ID, submissionData)
                        .then((res) => {
                            // LOG: "Correo administrador enviado" (REQUISITO MODO DEPURACIÓN)
                            console.log("Correo administrador enviado");
                            return res;
                        })
                        .catch((err) => {
                            console.error("Falla en el correo del administrador:", err);
                            throw err;
                        });

                    // Timeout de seguridad de 15 segundos (REQUISITO CONTROL DE CARGA INFINITA)
                    const timeoutPromise = new Promise((_, reject) => {
                        setTimeout(() => {
                            reject(new Error("La operación tardó más de 15 segundos (Límite de tiempo de red excedido). Verifique sus credenciales o su conexión."));
                        }, 15000);
                    });

                    // Ejecutar carrera de promesas para controlar el timeout
                    Promise.race([
                        Promise.all([sendToClient, sendToAdmin]),
                        timeoutPromise
                    ])
                        .then(([resClient, resAdmin]) => {
                            // LOG: "Proceso completado" (REQUISITO MODO DEPURACIÓN)
                            console.log("Proceso completado");

                            mostrarPantallaExito(referenceCode);
                            
                            // Se ejecuta de manera segura en try/catch para evitar caídas falsas por render del admin
                            try {
                                syncAdminPanel();
                            } catch (adminError) {
                                console.error("Error al sincronizar el panel (No crítico):", adminError);
                            }
                        })
                        .catch((error) => {
                            console.error("ERROR CRÍTICO AL ENVIAR LA SOLICITUD:", error);
                            // Mostrar mensaje de error real en pantalla
                            alert("Atención: " + (error.message || error.text || error) + "\n\nCódigo de seguimiento generado: " + referenceCode);
                            mostrarPantallaExito(referenceCode); // Preservamos el flujo visual
                            
                            try {
                                syncAdminPanel();
                            } catch (adminError) {
                                console.error("Error al sincronizar el panel (No crítico):", adminError);
                            }
                        })
                        .finally(() => {
                            // Asegurar que el botón vuelva a habilitarse en éxito o error
                            if (submitBtn) {
                                submitBtn.disabled = false;
                                submitBtn.innerHTML = originalBtnHTML;
                            }
                        });
                });
            }

            // Portal del Cliente (Sugerencia Alternativa)
            const customerProposalForm = document.getElementById('customer-proposal-form');
            if (customerProposalForm) {
                customerProposalForm.addEventListener('submit', function(e) {
                    e.preventDefault();
                    const ticketId = document.getElementById('cust-ticket-id').value;
                    const customDate = document.getElementById('cust-new-date').value;
                    const customTime = document.getElementById('cust-new-time').value;

                    volttech_requests = JSON.parse(localStorage.getItem('volttech_all_requests')) || [];
                    const reqIndex = volttech_requests.findIndex(r => r && r.ticket === ticketId);
                    if (reqIndex === -1) return;

                    const req = volttech_requests[reqIndex];
                    req.status = "Esperando revisión del administrador";
                    req.newDate = customDate;
                    req.newTime = customTime;
                    addHistoryEntry(req, `Cliente propuso fecha alternativa: ${customDate} a las ${customTime}`, "Cliente");
                    
                    localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));

                    // Notificar al administrador por EmailJS
                    const adminPayload = {
                        ticket: req.ticket,
                        name: req.name,
                        email: req.email,
                        phone: req.phone,
                        service: req.service,
                        subject: `Nueva contrapropuesta de fecha - ${req.ticket}`,
                        message: `El cliente ${req.name} sugiere el día ${customDate} a las ${customTime} para realizar la inspección técnica.`
                    };

                    emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ADMIN_ID, adminPayload);

                    const customerProposalContainer = document.getElementById('customer-proposal-form-container');
                    const customerSuccess = document.getElementById('customer-success');
                    const customerSuccessTitle = document.getElementById('customer-success-title');
                    const customerSuccessText = document.getElementById('customer-success-text');

                    if (customerProposalContainer) customerProposalContainer.style.display = 'none';
                    if (customerSuccessTitle) customerSuccessTitle.textContent = "Sugerencia Recibida";
                    if (customerSuccessText) customerSuccessText.textContent = `La propuesta alternativa (${customDate} a las ${customTime}) ha sido enviada al administrador. Evaluaremos el ajuste de agenda inmediatamente.`;
                    if (customerSuccess) customerSuccess.style.display = 'block';
                    lucide.createIcons();
                });
            }

            // Acceso Administrativo (Botón Admin Superior)
            const navAdminAccessBtn = document.getElementById('nav-admin-access-btn');
            const adminLoginCancel = document.getElementById('admin-login-cancel');
            const adminLoginForm = document.getElementById('admin-login-form');
            const adminLogoutBtn = document.getElementById('admin-logout-btn');

            if (navAdminAccessBtn) navAdminAccessBtn.addEventListener('click', showLoginModal);
            if (adminLoginCancel) adminLoginCancel.addEventListener('click', () => {
                const adminLoginModal = document.getElementById('admin-login-modal');
                if (adminLoginModal) adminLoginModal.classList.remove('active');
            });

            if (adminLoginForm) {
                adminLoginForm.addEventListener('submit', async (e) => {
                    e.preventDefault();
                    const adminLoginPassword = document.getElementById('admin-login-password');
                    const adminLoginModal = document.getElementById('admin-login-modal');
                    if (!adminLoginPassword) return;

                    const inputHash = await hashPassword(adminLoginPassword.value);
                    const storedHash = localStorage.getItem('volttech_admin_pwd_hash');

                    if (inputHash === storedHash) {
                        if (adminLoginModal) adminLoginModal.classList.remove('active');
                        enterAdminPanel();
                    } else {
                        alert("Contraseña de administración incorrecta.");
                        adminLoginPassword.value = '';
                        adminLoginPassword.focus();
                    }
                });
            }

            if (adminLogoutBtn) adminLogoutBtn.addEventListener('click', exitAdminPanel);

            // Inactividad y Auto-Logout
            const adminPanel = document.getElementById('admin-panel');
            if (adminPanel) {
                adminPanel.addEventListener('mousemove', resetActivityTracker);
                adminPanel.addEventListener('keydown', resetActivityTracker);
                adminPanel.addEventListener('click', resetActivityTracker);
            }

            function resetActivityTracker() {
                resetActivityTimer();
            }

            // Módulo de Recuperación
            const forgotPasswordTrigger = document.getElementById('admin-forgot-password-trigger');
            const btnBackToLogin = document.getElementById('btn-back-to-login');
            const btnSendRecoveryCode = document.getElementById('btn-send-recovery-code');
            const btnVerifyRecoveryCode = document.getElementById('btn-verify-recovery-code');
            const btnResetPasswordSubmit = document.getElementById('btn-reset-password-submit');

            if (forgotPasswordTrigger) {
                forgotPasswordTrigger.addEventListener('click', (e) => {
                    e.preventDefault();
                    const loginFormContainer = document.getElementById('login-form-container');
                    const recoveryFormContainer = document.getElementById('recovery-form-container');
                    if (loginFormContainer) loginFormContainer.style.display = 'none';
                    if (recoveryFormContainer) recoveryFormContainer.style.display = 'block';
                    
                    const r1 = document.getElementById('recovery-step-1');
                    const r2 = document.getElementById('recovery-step-2');
                    const r3 = document.getElementById('recovery-step-3');
                    
                    if (r1) r1.style.display = 'block';
                    if (r2) r2.style.display = 'none';
                    if (r3) r3.style.display = 'none';
                });
            }

            if (btnBackToLogin) {
                btnBackToLogin.addEventListener('click', (e) => {
                    e.preventDefault();
                    const loginFormContainer = document.getElementById('login-form-container');
                    const recoveryFormContainer = document.getElementById('recovery-form-container');
                    if (recoveryFormContainer) recoveryFormContainer.style.display = 'none';
                    if (loginFormContainer) loginFormContainer.style.display = 'block';
                });
            }

            if (btnSendRecoveryCode) {
                btnSendRecoveryCode.addEventListener('click', () => {
                    const recoveryEmail = localStorage.getItem('volttech_recovery_email');
                    const tempCode = String(Math.floor(100000 + Math.random() * 900000));
                    sessionStorage.setItem('volttech_temp_recovery_code', tempCode);

                    const payload = {
                        to_email: recoveryEmail,
                        recovery_code: tempCode
                    };

                    btnSendRecoveryCode.disabled = true;
                    btnSendRecoveryCode.textContent = 'Enviando...';

                    emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_RESET_CODE_ID, payload)
                        .then(() => {
                            alert(`Se ha enviado un código temporal a: ${recoveryEmail}`);
                            const r1 = document.getElementById('recovery-step-1');
                            const r2 = document.getElementById('recovery-step-2');
                            const recoveryInputCode = document.getElementById('recovery-input-code');
                            
                            if (r1) r1.style.display = 'none';
                            if (r2) r2.style.display = 'block';
                            if (recoveryInputCode) recoveryInputCode.focus();
                        })
                        .catch((error) => {
                            console.error("Falla recuperador EmailJS:", error);
                            alert("Error despachando código.");
                        })
                        .finally(() => {
                            btnSendRecoveryCode.disabled = false;
                            btnSendRecoveryCode.textContent = 'Enviar Código de Verificación';
                        });
                });
            }

            if (btnVerifyRecoveryCode) {
                btnVerifyRecoveryCode.addEventListener('click', () => {
                    const recoveryInputCode = document.getElementById('recovery-input-code');
                    const inputVal = recoveryInputCode ? recoveryInputCode.value.trim() : '';
                    const storedCode = sessionStorage.getItem('volttech_temp_recovery_code');

                    if (inputVal === storedCode && inputVal !== '') {
                        const r2 = document.getElementById('recovery-step-2');
                        const r3 = document.getElementById('recovery-step-3');
                        if (r2) r2.style.display = 'none';
                        if (r3) r3.style.display = 'block';
                    } else {
                        alert("Código incorrecto.");
                        if (recoveryInputCode) {
                            recoveryInputCode.value = '';
                            recoveryInputCode.focus();
                        }
                    }
                });
            }

            if (btnResetPasswordSubmit) {
                btnResetPasswordSubmit.addEventListener('click', async () => {
                    const newPwdEl = document.getElementById('rec-new-pwd');
                    const confirmPwdEl = document.getElementById('rec-confirm-pwd');
                    
                    const newPwd = newPwdEl ? newPwdEl.value : '';
                    const confirmPwd = confirmPwdEl ? confirmPwdEl.value : '';

                    const pwdRegex = /^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$/;
                    if (!pwdRegex.test(newPwd)) {
                        alert("Debe poseer letras, números y longitud de mínimo 8.");
                        return;
                    }

                    if (newPwd !== confirmPwd) {
                        alert("Las claves no coinciden.");
                        return;
                    }

                    const newHash = await hashPassword(newPwd);
                    localStorage.setItem('volttech_admin_pwd_hash', newHash);
                    localStorage.setItem('volttech_last_pwd_change', new Date().toISOString());

                    alert("Cambio de clave exitoso.");
                    sessionStorage.removeItem('volttech_temp_recovery_code');
                    const loginFormContainer = document.getElementById('login-form-container');
                    const recoveryFormContainer = document.getElementById('recovery-form-container');
                    if (recoveryFormContainer) recoveryFormContainer.style.display = 'none';
                    if (loginFormContainer) loginFormContainer.style.display = 'block';
                });
            }

            const securitySettingsForm = document.getElementById('admin-security-settings-form');
            if (securitySettingsForm) {
                securitySettingsForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const recEmail = document.getElementById('sec-recovery-email').value;
                    const recPhone = document.getElementById('sec-recovery-phone').value;
                    const autoLogout = document.getElementById('sec-auto-logout').value;

                    localStorage.setItem('volttech_recovery_email', recEmail);
                    localStorage.setItem('volttech_recovery_phone', recPhone);
                    localStorage.setItem('volttech_auto_logout_time', autoLogout);

                    alert("Ajustes guardados.");
                    startAutoLogoutTracker();
                });
            }

            const changePasswordForm = document.getElementById('admin-change-password-form');
            if (changePasswordForm) {
                changePasswordForm.addEventListener('submit', async (e) => {
                    e.preventDefault();
                    const current = document.getElementById('pwd-current').value;
                    const newPwd = document.getElementById('pwd-new').value;
                    const confirmPwd = document.getElementById('pwd-confirm').value;

                    const currentHash = await hashPassword(current);
                    const storedHash = localStorage.getItem('volttech_admin_pwd_hash');

                    if (currentHash !== storedHash) {
                        alert("Clave actual incorrecta.");
                        return;
                    }

                    const pwdRegex = /^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$/;
                    if (!pwdRegex.test(newPwd)) {
                        alert("Mínimo 8 caracteres, al menos un número y una letra.");
                        return;
                    }

                    if (newPwd !== confirmPwd) {
                        alert("Las contraseñas no coinciden.");
                        return;
                    }

                    const newHash = await hashPassword(newPwd);
                    localStorage.setItem('volttech_admin_pwd_hash', newHash);
                    localStorage.setItem('volttech_last_pwd_change', new Date().toISOString());

                    alert("Cambio seguro procesado.");
                    changePasswordForm.reset();
                    loadSecurityTab();
                });
            }

            // Table filters
            const searchBox = document.getElementById('admin-search-box');
            const filterStatus = document.getElementById('admin-filter-status');
            const filterService = document.getElementById('admin-filter-service');
            const filterDate = document.getElementById('admin-filter-date');
            const clearFiltersBtn = document.getElementById('admin-clear-filters');

            if (searchBox) searchBox.addEventListener('input', renderTable);
            if (filterStatus) filterStatus.addEventListener('change', renderTable);
            if (filterService) filterService.addEventListener('change', renderTable);
            if (filterDate) filterDate.addEventListener('change', renderTable);

            if (clearFiltersBtn) {
                clearFiltersBtn.addEventListener('click', () => {
                    const searchEl = document.getElementById('admin-search-box');
                    const statusEl = document.getElementById('admin-filter-status');
                    const serviceEl = document.getElementById('admin-filter-service');
                    const dateEl = document.getElementById('admin-filter-date');

                    if (searchEl) searchEl.value = '';
                    if (statusEl) statusEl.value = '';
                    if (serviceEl) serviceEl.value = '';
                    if (dateEl) dateEl.value = '';

                    renderTable();
                });
            }

            // Gestión de pestañas administrativas
            const tabButtons = document.querySelectorAll('.admin-tab-btn');
            const tabContents = document.querySelectorAll('.admin-section-content');

            if (tabButtons && tabButtons.length > 0) {
                tabButtons.forEach(btn => {
                    btn.addEventListener('click', () => {
                        tabButtons.forEach(b => b.classList.remove('active'));
                        tabContents.forEach(c => c.classList.remove('active'));
                        btn.classList.add('active');
                        const targetTab = btn.getAttribute('data-tab');
                        const targetEl = document.getElementById(targetTab);
                        if (targetEl) targetEl.classList.add('active');

                        if (targetTab === 'admin-tab-calendar') {
                            renderCalendar();
                        }
                    });
                });
            }

            const closeRescheduleBtn = document.getElementById('close-modal-reschedule-btn');
            if (closeRescheduleBtn) {
                closeRescheduleBtn.addEventListener('click', () => {
                    const rescheduleModal = document.getElementById('admin-modal-reschedule');
                    if (rescheduleModal) rescheduleModal.classList.remove('active');
                });
            }

            const closeCancelBtn = document.getElementById('close-modal-cancel-btn');
            if (closeCancelBtn) {
                closeCancelBtn.addEventListener('click', () => {
                    const cancelModal = document.getElementById('admin-modal-cancel');
                    if (cancelModal) cancelModal.classList.remove('active');
                });
            }

            // Formularios administrativos (Proponer reagendamiento / Cancelar)
            const rescheduleForm = document.getElementById('admin-reschedule-form');
            if (rescheduleForm) {
                rescheduleForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const ticketId = document.getElementById('reschedule-ticket-id').value;
                    const newDate = document.getElementById('reschedule-new-date').value;
                    const newTime = document.getElementById('reschedule-new-time').value;

                    const reqIndex = volttech_requests.findIndex(r => r && r.ticket === ticketId);
                    if (reqIndex === -1) return;

                    const req = volttech_requests[reqIndex];
                    req.status = "Esperando respuesta del cliente"; // (REQUISITO ESTADO "Esperando respuesta del cliente")
                    req.newDate = newDate;
                    req.newTime = newTime;
                    req.rescheduledAt = new Date().toISOString();

                    addHistoryEntry(req, `Propuesta de nueva fecha enviada al cliente: ${newDate} a las ${newTime}`);
                    localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));

                    const currentOrigin = window.location.href.split('?')[0]; 
                    const acceptLink = `${currentOrigin}?action=accept&ticket=${req.ticket}`;
                    const cancelLink = `${currentOrigin}?action=reject&ticket=${req.ticket}`; // Redirección si el cliente rechaza
                    const proposeLink = `${currentOrigin}?action=propose&ticket=${req.ticket}`;

                    const msgBody = `Por motivos operativos le proponemos una nueva fecha para la realización del servicio.\n\n` +
                        `• Servicio: ${req.service}\n` +
                        `• Nueva fecha propuesta: ${newDate}\n` +
                        `• Nueva hora propuesta: ${newTime}\n\n` +
                        `Por favor, seleccione una de las siguientes opciones:\n\n` +
                        `[1. ACEPTAR NUEVA FECHA]\n${acceptLink}\n\n` +
                        `[2. RECHAZAR NUEVA FECHA]\n${cancelLink}\n\n` +
                        `[3. PROPONER OTRA FECHA Y HORA]\n${proposeLink}\n\n`;

                    // Notificación utilizando la plantilla única con variables (REQUISITO REAGENDACIÓN)
                    const emailPayload = {
                        subject: `Propuesta de Nueva Fecha - ${req.ticket}`,
                        ticket: req.ticket,
                        name: req.name,
                        email: req.email,
                        service: req.service,
                        date: req.date,
                        time: req.time,
                        new_date: newDate,
                        new_time: newTime,
                        message: msgBody + INSTITUTIONAL_FOOTER
                    };

                    emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_CLIENT_ID, emailPayload);

                    const rescheduleModal = document.getElementById('admin-modal-reschedule');
                    if (rescheduleModal) rescheduleModal.classList.remove('active');
                    syncAdminPanel();
                    alert(`Se ha enviado la propuesta de reagendamiento al cliente.`);
                });
            }

            const cancelForm = document.getElementById('admin-cancel-form');
            if (cancelForm) {
                cancelForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const ticketId = document.getElementById('cancel-ticket-id').value;
                    const reason = document.getElementById('cancel-reason').value;

                    const reqIndex = volttech_requests.findIndex(r => r && r.ticket === ticketId);
                    if (reqIndex === -1) return;

                    const req = volttech_requests[reqIndex];
                    req.status = "Cancelada";
                    req.cancellationReason = reason;
                    req.cancelledAt = new Date().toISOString();

                    addHistoryEntry(req, `Solicitud cancelada por administrador. Motivo: ${reason}`);
                    localStorage.setItem('volttech_all_requests', JSON.stringify(volttech_requests));

                    // Notificación de cancelación en la plantilla única (REQUISITO CANCELACIÓN)
                    const emailPayload = {
                        subject: `Solicitud Cancelada - ${req.ticket}`,
                        ticket: req.ticket,
                        name: req.name,
                        email: req.email,
                        service: req.service,
                        date: req.date,
                        time: req.time,
                        message: `Le informamos que su solicitud ha sido cancelada. Si desea una nueva visita técnica, puede realizar una nueva solicitud cuando lo desee.` + INSTITUTIONAL_FOOTER
                    };

                    emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_CLIENT_ID, emailPayload);

                    const cancelModal = document.getElementById('admin-modal-cancel');
                    if (cancelModal) cancelModal.classList.remove('active');
                    syncAdminPanel();
                    alert(`La solicitud ${ticketId} ha sido cancelada.`);
                });
            }

            const prevMonthBtn = document.getElementById('calendar-prev-month');
            if (prevMonthBtn) {
                prevMonthBtn.addEventListener('click', () => {
                    calendarCurrentDate.setMonth(calendarCurrentDate.getMonth() - 1);
                    renderCalendar();
                });
            }

            const nextMonthBtn = document.getElementById('calendar-next-month');
            if (nextMonthBtn) {
                nextMonthBtn.addEventListener('click', () => {
                    calendarCurrentDate.setMonth(calendarCurrentDate.getMonth() + 1);
                    renderCalendar();
                });
            }
        }


        // --- INICIALIZADOR GLOBAL (PAGE LOAD) ---
        document.addEventListener("DOMContentLoaded", async () => {
            // 1. Vincular los escuchadores de forma inmediata (SÍNCRONO - NO BLOQUEANTE)
            setupEventListeners();

            // 2. Inicializar base de datos de seguridad de forma segura
            try {
                await initSecurity();
            } catch (securityError) {
                console.error("Error al inicializar la seguridad local:", securityError);
            }

            // 3. Cargar las vistas iniciales de forma segura
            try {
                const params = new URLSearchParams(window.location.search);
                const action = params.get('action');
                const ticket = params.get('ticket');

                if (action && ticket) {
                    handleCustomerAction(action, ticket);
                } else {
                    calculateMetrics();
                    renderTable();
                    renderCalendar();
                }
            } catch (initError) {
                console.error("Error al renderizar las vistas iniciales:", initError);
            }
        });
    </script>
</body>
</html>
