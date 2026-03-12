<!DOCTYPE html> xxx
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio Administrateur Système</title>
    <!-- Importation d'une police moderne -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <!-- Icônes (FontAwesome) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    
    <style>
        /* --- VARIABLES DE COULEURS --- */
        :root {
            --bg-color: #0f172a;       /* Bleu nuit très sombre */
            --card-bg: #1e293b;        /* Bleu gris pour les cartes */
            --text-main: #e2e8f0;      /* Blanc cassé */
            --text-muted: #94a3b8;     /* Gris clair */
            --accent-primary: #38bdf8; /* Cyan électrique */
            --accent-secondary: #818cf8; /* Indigo */
            --accent-tertiary: #f472b6; /* Rose néon */
            --gradient: linear-gradient(135deg, var(--accent-primary), var(--accent-secondary));
        }

        /* --- RESET & BASE --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            line-height: 1.6;
        }

        a { text-decoration: none; color: inherit; transition: 0.3s; }
        ul { list-style: none; }

        /* --- HEADER / HERO SECTION --- */
        header {
            min-height: 90vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 2rem;
            background: radial-gradient(circle at top right, #1e293b 0%, transparent 40%);
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid var(--accent-primary);
            margin-bottom: 1.5rem;
            object-fit: cover;
            box-shadow: 0 0 20px rgba(56, 189, 248, 0.3);
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 0.5rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .subtitle {
            font-size: 1.5rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: var(--gradient);
            color: white;
            border-radius: 50px;
            font-weight: 600;
            box-shadow: 0 4px 15px rgba(56, 189, 248, 0.4);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(56, 189, 248, 0.6);
        }

        .social-links {
            margin-top: 2rem;
        }

        .social-links a {
            font-size: 1.5rem;
            margin: 0 10px;
            color: var(--text-muted);
        }

        .social-links a:hover {
            color: var(--accent-primary);
        }

        /* --- SECTIONS GÉNÉRALES --- */
        section {
            padding: 5rem 10%;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 4px;
            background: var(--gradient);
            margin
