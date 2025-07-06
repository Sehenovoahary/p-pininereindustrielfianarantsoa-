<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fianarantsoa - Pépinière Industrielle Agro-transformation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            color: white;
            overflow-x: hidden;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            padding: 40px 0;
            position: relative;
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4);
            border-radius: 2px;
        }

        .header h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 3s ease-in-out infinite;
        }

        .header h2 {
            font-size: 1.8rem;
            color: #a8d0f0;
            font-weight: 300;
            margin-bottom: 30px;
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .vision-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .sectors-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin: 50px 0;
        }

        .sector-card {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            transition: all 0.4s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .sector-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transform: rotate(45deg);
            transition: all 0.6s;
            opacity: 0;
        }

        .sector-card:hover::before {
            animation: shine 1.5s ease-in-out;
        }

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); opacity: 0; }
            50% { opacity: 1; }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); opacity: 0; }
        }

        .sector-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            border-color: #4ecdc4;
        }

        .sector-icon {
            font-size: 4rem;
            margin-bottom: 20px;
            display: block;
            text-align: center;
        }

        .sector-title {
            font-size: 1.8rem;
            font-weight: bold;
            margin-bottom: 15px;
            color: #4ecdc4;
            text-align: center;
        }

        .sector-description {
            line-height: 1.6;
            margin-bottom: 20px;
            opacity: 0.9;
        }

        .sector-details {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.4s ease, opacity 0.4s ease;
            opacity: 0;
        }

        .sector-card.expanded .sector-details {
            max-height: 300px;
            opacity: 1;
        }

        .impact-metrics {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 50px 0;
        }

        .metric {
            text-align: center;
            padding: 30px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            transition: transform 0.3s ease;
        }

        .metric:hover {
            transform: scale(1.05);
        }

        .metric-number {
            font-size: 3rem;
            font-weight: bold;
            color: #ff6b6b;
            display: block;
        }

        .metric-label {
            font-size: 1.1rem;
            margin-top: 10px;
            opacity: 0.8;
        }

        .roadmap {
            margin: 60px 0;
        }

        .roadmap-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 40px;
            color: #4ecdc4;
        }

        .timeline {
            position: relative;
            padding: 20px 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 4px;
            background: linear-gradient(to bottom, #4ecdc4, #ff6b6b);
            transform: translateX(-50%);
        }

        .timeline-item {
            position: relative;
            margin: 40px 0;
            opacity: 0;
            animation: fadeInUp 0.8s ease forwards;
        }

        .timeline-item:nth-child(odd) {
            animation-delay: 0.2s;
        }

        .timeline-item:nth-child(even) {
            animation-delay: 0.4s;
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .timeline-content {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            padding: 25px;
            border-radius: 15px;
            width: 45%;
            position: relative;
        }

        .timeline-item:nth-child(odd) .timeline-content {
            margin-left: 55%;
        }

        .timeline-item:nth-child(even) .timeline-content {
            margin-right: 55%;
        }

        .timeline-dot {
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            width: 20px;
            height: 20px;
            background: #4ecdc4;
            border-radius: 50%;
            border: 4px solid #1e3c72;
            z-index: 2;
        }

        .cta-section {
            text-align: center;
            padding: 60px 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            margin: 50px 0;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            color: white;
            padding: 15px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.2rem;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            margin: 10px;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        @media (max-width: 768px) {
            .header h1 { font-size: 2.5rem; }
            .header h2 { font-size: 1.3rem; }
            .sectors-grid { grid-template-columns: 1fr; }
            .timeline::before { left: 20px; }
            .timeline-content { width: calc(100% - 60px); margin-left: 60px !important; margin-right: 0 !important; }
            .timeline-dot { left: 20px; }
        }
    </style>
</head>
<body>
    <div class="container">
        <header class="header">
            <h1>FIANARANTSOA</h1>
            <h2>Pépinière Industrielle d'Agro-transformation</h2>
            <p style="font-size: 1.2rem; opacity: 0.8; margin-top: 20px;">
                Transformer les ressources agricoles locales en opportunités industrielles durables
            </p>
        </header>

        <section class="vision-section">
            <h3 style="font-size: 2rem; margin-bottom: 20px; color: #4ecdc4;">🎯 Vision Stratégique</h3>
            <p style="font-size: 1.2rem; line-height: 1.8;">
                Développer Fianarantsoa comme hub industriel régional spécialisé dans la transformation 
                des produits agricoles locaux, créant une chaîne de valeur intégrée qui génère des emplois 
                durables et valorise le patrimoine agricole de la région des Hautes Terres.
            </p>
        </section>

        <section class="sectors-grid">
            <div class="sector-card" onclick="toggleDetails(this)">
                <span class="sector-icon">🥜</span>
                <h3 class="sector-title">Transformation Arachide</h3>
                <p class="sector-description">
                    Développement d'une filière complète de transformation de l'arachide en produits à haute valeur ajoutée.
                </p>
                <div class="sector-details">
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 15px;">
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🏭 Produits Finis</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Huile d'arachide premium (500ml, 1L)</li>
                                <li>• Beurre d'arachide bio (250g, 500g)</li>
                                <li>• Arachides grillées épicées</li>
                                <li>• Barres énergétiques aux arachides</li>
                                <li>• Pâte d'arachide industrielle</li>
                                <li>• Tourteaux protéinés</li>
                            </ul>
                        </div>
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🎯 Marchés Visés</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Supermarchés Madagascar (70%)</li>
                                <li>• Export Océan Indien (20%)</li>
                                <li>• Industrie agroalimentaire (10%)</li>
                                <li>• Restaurants et hôtels</li>
                                <li>• Marchés bio européens</li>
                            </ul>
                        </div>
                    </div>
                    <div style="margin-top: 15px; padding: 10px; background: rgba(255,107,107,0.2); border-radius: 8px;">
                        <strong style="color: #4ecdc4;">💰 Investissement: 8M USD</strong> | 
                        <strong style="color: #4ecdc4;">👥 500 emplois directs</strong>
                    </div>
                </div>
            </div>

            <div class="sector-card" onclick="toggleDetails(this)">
                <span class="sector-icon">🍊</span>
                <h3 class="sector-title">Fruits & Légumes</h3>
                <p class="sector-description">
                    Transformation et conservation des fruits et légumes locaux pour les marchés national et international.
                </p>
                <div class="sector-details">
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 15px;">
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🏭 Produits Finis</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Confitures artisanales (220g, 450g)</li>
                                <li>• Jus de fruits 100% naturels</li>
                                <li>• Fruits séchés bio premium</li>
                                <li>• Légumes surgelés IQF</li>
                                <li>• Concentrés de tomates</li>
                                <li>• Pickles et chutneys</li>
                                <li>• Compotes sans sucre ajouté</li>
                            </ul>
                        </div>
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🎯 Marchés Visés</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Grande distribution nationale (50%)</li>
                                <li>• Export Maurice/Réunion (30%)</li>
                                <li>• Secteur HORECA (15%)</li>
                                <li>• Marchés bio européens (5%)</li>
                                <li>• Programmes scolaires</li>
                                <li>• E-commerce local</li>
                            </ul>
                        </div>
                    </div>
                    <div style="margin-top: 15px; padding: 10px; background: rgba(255,107,107,0.2); border-radius: 8px;">
                        <strong style="color: #4ecdc4;">💰 Investissement: 12M USD</strong> | 
                        <strong style="color: #4ecdc4;">👥 750 emplois directs</strong>
                    </div>
                </div>
            </div>

            <div class="sector-card" onclick="toggleDetails(this)">
                <span class="sector-icon">🌽</span>
                <h3 class="sector-title">Transformation Maïs</h3>
                <p class="sector-description">
                    Valorisation du maïs local en produits alimentaires et industriels diversifiés.
                </p>
                <div class="sector-details">
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 15px;">
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🏭 Produits Finis</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Farine de maïs fortifiée (1kg, 5kg)</li>
                                <li>• Semoule fine et grosse</li>
                                <li>• Flocons de maïs petit-déjeuner</li>
                                <li>• Amidon industriel</li>
                                <li>• Polenta instantanée</li>
                                <li>• Aliments composés pour volaille</li>
                                <li>• Snacks soufflés au maïs</li>
                            </ul>
                        </div>
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🎯 Marchés Visés</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Ménages urbains et ruraux (60%)</li>
                                <li>• Industrie alimentaire (25%)</li>
                                <li>• Éleveurs et coopératives (10%)</li>
                                <li>• Programmes nutritionnels (5%)</li>
                                <li>• Export sous-région</li>
                                <li>• Boulangeries industrielles</li>
                            </ul>
                        </div>
                    </div>
                    <div style="margin-top: 15px; padding: 10px; background: rgba(255,107,107,0.2); border-radius: 8px;">
                        <strong style="color: #4ecdc4;">💰 Investissement: 6M USD</strong> | 
                        <strong style="color: #4ecdc4;">👥 400 emplois directs</strong>
                    </div>
                </div>
            </div>

            <div class="sector-card" onclick="toggleDetails(this)">
                <span class="sector-icon">🍠</span>
                <h3 class="sector-title">Valorisation Manioc</h3>
                <p class="sector-description">
                    Transformation du manioc en produits alimentaires et industriels innovants.
                </p>
                <div class="sector-details">
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 15px;">
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🏭 Produits Finis</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Farine de manioc (1kg, 5kg, 25kg)</li>
                                <li>• Tapioca perles et fécule</li>
                                <li>• Chips de manioc épicées</li>
                                <li>• Cossettes séchées</li>
                                <li>• Gari (semoule de manioc)</li>
                                <li>• Bioéthanol carburant</li>
                                <li>• Amidon modifié industriel</li>
                            </ul>
                        </div>
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🎯 Marchés Visés</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Boulangeries et pâtisseries (40%)</li>
                                <li>• Industrie alimentaire (30%)</li>
                                <li>• Ménages (20%)</li>
                                <li>• Secteur énergétique (10%)</li>
                                <li>• Export Afrique de l'Ouest</li>
                                <li>• Marchés sans gluten</li>
                            </ul>
                        </div>
                    </div>
                    <div style="margin-top: 15px; padding: 10px; background: rgba(255,107,107,0.2); border-radius: 8px;">
                        <strong style="color: #4ecdc4;">💰 Investissement: 5M USD</strong> | 
                        <strong style="color: #4ecdc4;">👥 350 emplois directs</strong>
                    </div>
                </div>
            </div>

            <div class="sector-card" onclick="toggleDetails(this)">
                <span class="sector-icon">💄</span>
                <h3 class="sector-title">Cosmétiques Naturels</h3>
                <p class="sector-description">
                    Production de cosmétiques à base d'ingrédients naturels locaux pour les marchés premium.
                </p>
                <div class="sector-details">
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 15px;">
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🏭 Produits Finis</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Crèmes visage anti-âge premium</li>
                                <li>• Shampoings aux plantes locales</li>
                                <li>• Savons artisanaux bio</li>
                                <li>• Huiles de massage thérapeutiques</li>
                                <li>• Baumes à lèvres naturels</li>
                                <li>• Masques purifiants à l'argile</li>
                                <li>• Déodorants sans aluminium</li>
                            </ul>
                        </div>
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🎯 Marchés Visés</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Marchés bio européens (50%)</li>
                                <li>• Spas et centres wellness (25%)</li>
                                <li>• Pharmacies et parapharmacies (15%)</li>
                                <li>• E-commerce international (10%)</li>
                                <li>• Tourisme de luxe Madagascar</li>
                                <li>• Marques privées internationales</li>
                            </ul>
                        </div>
                    </div>
                    <div style="margin-top: 15px; padding: 10px; background: rgba(255,107,107,0.2); border-radius: 8px;">
                        <strong style="color: #4ecdc4;">💰 Investissement: 10M USD</strong> | 
                        <strong style="color: #4ecdc4;">👥 300 emplois directs</strong>
                    </div>
                </div>
            </div>

            <div class="sector-card" onclick="toggleDetails(this)">
                <span class="sector-icon">🌿</span>
                <h3 class="sector-title">Huiles Essentielles</h3>
                <p class="sector-description">
                    Extraction et commercialisation d'huiles essentielles de plantes aromatiques locales.
                </p>
                <div class="sector-details">
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 15px;">
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🏭 Produits Finis</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Huile d'eucalyptus médicale</li>
                                <li>• Essence de géranium rosat</li>
                                <li>• Huiles essentielles composées</li>
                                <li>• Diffuseurs et roll-on</li>
                                <li>• Hydrolats thérapeutiques</li>
                                <li>• Capsules aromathérapie</li>
                                <li>• Mélanges personnalisés spa</li>
                            </ul>
                        </div>
                        <div>
                            <h5 style="color: #ff6b6b; margin-bottom: 10px;">🎯 Marchés Visés</h5>
                            <ul style="list-style: none; padding: 0; font-size: 0.9rem;">
                                <li>• Industrie parfumerie France (40%)</li>
                                <li>• Laboratoires pharmaceutiques (30%)</li>
                                <li>• Aromathérapeutes certifiés (20%)</li>
                                <li>• Grossistes spécialisés (10%)</li>
                                <li>• Marques cosmétiques premium</li>
                                <li>• Médecine alternative</li>
                            </ul>
                        </div>
                    </div>
                    <div style="margin-top: 15px; padding: 10px; background: rgba(255,107,107,0.2); border-radius: 8px;">
                        <strong style="color: #4ecdc4;">💰 Investissement: 4M USD</strong> | 
                        <strong style="color: #4ecdc4;">👥 250 emplois directs</strong>
                    </div>
                </div>
            </div>
        </section>

        <section class="impact-metrics">
            <div class="metric">
                <span class="metric-number">2,550</span>
                <span class="metric-label">Emplois Directs Créés</span>
            </div>
            <div class="metric">
                <span class="metric-number">7,650</span>
                <span class="metric-label">Emplois Indirects</span>
            </div>
            <div class="metric">
                <span class="metric-number">45M</span>
                <span class="metric-label">Investissement Total (USD)</span>
            </div>
            <div class="metric">
                <span class="metric-number">50%</span>
                <span class="metric-label">Augmentation Revenus Agricoles</span>
            </div>
        </section>

        <section class="roadmap">
            <h2 class="roadmap-title">🚀 Feuille de Route</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <h4 style="color: #4ecdc4; margin-bottom: 15px;">Phase 4 (2030+) - Excellence</h4>
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9rem;">
                            <div>
                                <p style="font-weight: bold; color: #ff6b6b; margin-bottom: 8px;">🔬 Innovation & R&D</p>
                                <ul style="list-style: none; padding: 0;">
                                    <li>• Centre R&D agro-transformation</li>
                                    <li>• Partenariats universités internationales</li>
                                    <li>• Laboratoire nouveaux produits</li>
                                    <li>• Incubateur startups agritech</li>
                                </ul>
                            </div>
                            <div>
                                <p style="font-weight: bold; color: #ff6b6b; margin-bottom: 8px;">🏆 Leadership Régional</p>
                                <ul style="list-style: none; padding: 0;">
                                    <li>• Hub logistique Océan Indien</li>
                                    <li>• Standards qualité internationaux</li>
                                    <li>• Formation centre d'excellence</li>
                                    <li>• Économie circulaire intégrée</li>
                                </ul>
                            </div>
                        </div>
                        <div style="margin-top: 15px; padding: 10px; background: rgba(78, 205, 196, 0.2); border-radius: 8px;">
                            <strong>💰 Budget Phase: 4M USD/an | 🎯 Objectif: Hub régional reconnu</strong>
                        </div>
                    </div>
                </div>: #4ecdc4; margin-bottom: 15px;">Phase 1 (2025-2026) - Fondations</h4>
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9rem;">
                            <div>
                                <p style="font-weight: bold; color: #ff6b6b; margin-bottom: 8px;">📋 Études & Planification</p>
                                <ul style="list-style: none; padding: 0;">
                                    <li>• Études de faisabilité détaillées</li>
                                    <li>• Études d'impact environnemental</li>
                                    <li>• Acquisition et viabilisation terrains</li>
                                    <li>• Plans d'aménagement zone industrielle</li>
                                </ul>
                            </div>
                            <div>
                                <p style="font-weight: bold; color: #ff6b6b; margin-bottom: 8px;">🏗️ Infrastructure</p>
                                <ul style="list-style: none; padding: 0;">
                                    <li>• Construction routes d'accès</li>
                                    <li>• Réseau électrique et eau</li>
                                    <li>• Système de traitement déchets</li>
                                    <li>• Centre de formation technique</li>
                                </ul>
                            </div>
                        </div>
                        <div style="margin-top: 15px; padding: 10px; background: rgba(78, 205, 196, 0.2); border-radius: 8px;">
                            <strong>💰 Budget Phase: 8M USD | 🎯 Objectif: 200 emplois temporaires</strong>
                        </div>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <h4 style="color: #4ecdc4; margin-bottom: 15px;">Phase 2 (2026-2028) - Déploiement</h4>
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9rem;">
                            <div>
                                <p style="font-weight: bold; color: #ff6b6b; margin-bottom: 8px;">🏭 Premières Unités</p>
                                <ul style="list-style: none; padding: 0;">
                                    <li>• Usine transformation arachide</li>
                                    <li>• Unité traitement maïs</li>
                                    <li>• Installation équipements lourds</li>
                                    <li>• Laboratoires qualité</li>
                                </ul>
                            </div>
                            <div>
                                <p style="font-weight: bold; color: #ff6b6b; margin-bottom: 8px;">🌾 Chaîne d'Approvisionnement</p>
                                <ul style="list-style: none; padding: 0;">
                                    <li>• Contrats producteurs (500 agriculteurs)</li>
                                    <li>• Centres de collecte régionaux</li>
                                    <li>• Formation techniques agricoles</li>
                                    <li>• Certification bio internationale</li>
                                </ul>
                            </div>
                        </div>
                        <div style="margin-top: 15px; padding: 10px; background: rgba(78, 205, 196, 0.2); border-radius: 8px;">
                            <strong>💰 Budget Phase: 18M USD | 🎯 Objectif: 900 emplois directs</strong>
                        </div>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <h4 style="color: #4ecdc4; margin-bottom: 15px;">Phase 3 (2028-2030) - Expansion</h4>
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9rem;">
                            <div>
                                <p style="font-weight: bold; color: #ff6b6b; margin-bottom: 8px;">💄 Diversification</p>
                                <ul style="list-style: none; padding: 0;">
                                    <li>• Unité cosmétiques naturels</li>
                                    <li>• Distillerie huiles essentielles</li>
                                    <li>• Usine transformation fruits/légumes</li>
                                    <li>• Ligne traitement manioc</li>
                                </ul>
                            </div>
                            <div>
                                <p style="font-weight: bold; color: #ff6b6b; margin-bottom: 8px;">🌍 Export & Marketing</p>
                                <ul style="list-style: none; padding: 0;">
                                    <li>• Bureaux commerciaux Maurice/Réunion</li>
                                    <li>• Certifications internationales</li>
                                    <li>• Marques propres premium</li>
                                    <li>• Plateformes e-commerce</li>
                                </ul>
                            </div>
                        </div>
                        <div style="margin-top: 15px; padding: 10px; background: rgba(78, 205, 196, 0.2); border-radius: 8px;">
                            <strong>💰 Budget Phase: 15M USD | 🎯 Objectif: 1100 emplois supplémentaires</strong>
                        </div>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-dot"></div>
                    <div class="timeline-content">
                        <h4 style="color: #4ecdc4; margin-bottom: 15px;">Phase 4 (2030+) - Excellence</h4>
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.9rem;">
                            <div>
                                <p style="font-weight: bold; color: #ff6b6b; margin-bottom: 8px;">🔬 Innovation & R&D</p>
                                <ul style="list-style: none; padding: 0;">
                                    <li>• Centre R&D agro-transformation</li>
                                    <li>• Partenariats universités internationales</li>
                                    <li>• Laboratoire nouveaux produits</li>
                                    <li>• Incubateur startups agritech</li>
                                </ul>
                            </div>
                            <div>
                                <p style="font-weight: bold; color: #ff6b6b; margin-bottom: 8px;">🏆 Leadership Régional</p>
                                <ul style="list-style: none; padding: 0;">
                                    <li>• Hub logistique Océan Indien</li>
                                    <li>• Standards qualité internationaux</li>
                                    <li>• Formation centre d'excellence</li>
                                    <li>• Économie circulaire intégrée</li>
                                </ul>
                            </div>
                        </div>
                        <div style="margin-top: 15px; padding: 10px; background: rgba(78, 205, 196, 0.2); border-radius: 8px;">
                            <strong>💰 Budget Phase: 4M USD/an | 🎯 Objectif: Hub régional reconnu</strong>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="cta-section">
            <h2 style="font-size: 2.5rem; margin-bottom: 20px; color: #4ecdc4;">
                Ensemble, Transformons l'Avenir
            </h2>
            <p style="font-size: 1.3rem; margin-bottom: 30px; opacity: 0.9;">
                Rejoignez-nous dans cette vision ambitieuse pour faire de Fianarantsoa 
                le leader de l'agro-transformation à Madagascar
            </p>
            <button class="cta-button" onclick="showPartnership()">🤝 Partenariat Stratégique</button>
            <button class="cta-button" onclick="showInvestment()">💰 Opportunités d'Investissement</button>
        </section>
    </div>

    <script>
        function toggleDetails(card) {
            card.classList.toggle('expanded');
        }

        function showPartnership() {
            const partnershipDetails = `
🤝 OPPORTUNITÉS DE PARTENARIAT

💡 PARTENARIATS TECHNOLOGIQUES
• Transfert de technologies de transformation
• Expertise en certification bio/équitable
• Systèmes qualité internationaux
• Innovation produits et packaging

🌍 ALLIANCES COMMERCIALES
• Réseaux de distribution internationaux
• Marques privées et co-branding
• Plateformes e-commerce spécialisées
• Accords d'exclusivité territoriale

🎓 COOPÉRATION FORMATION
• Centres de formation technique
• Programmes d'échange international
• Développement compétences locales
• Recherche appliquée collaborative

📈 INVESTISSEMENTS STRATÉGIQUES
• Fonds d'investissement sectoriels
• Partenariats public-privé
• Financement équipements industriels
• Programmes développement rural

💰 AVANTAGES PARTENAIRES
• Accès matières premières premium
• Coûts production compétitifs
• Incitations fiscales gouvernementales
• Position stratégique Océan Indien

Contact: partenariat@fianarantsoa-agro.mg
            `;
            
            // Create modal
            const modal = document.createElement('div');
            modal.style.cssText = `
                position: fixed; top: 0; left: 0; width: 100%; height: 100%; 
                background: rgba(0,0,0,0.8); display: flex; align-items: center; 
                justify-content: center; z-index: 1000; backdrop-filter: blur(5px);
            `;
            
            const content = document.createElement('div');
            content.style.cssText = `
                background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
                color: white; padding: 40px; border-radius: 20px; max-width: 800px;
                max-height: 80vh; overflow-y: auto; border: 2px solid #4ecdc4;
                box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            `;
            
            content.innerHTML = `
                <h3 style="color: #4ecdc4; margin-bottom: 20px; font-size: 1.8rem;">
                    🤝 Opportunités de Partenariat
                </h3>
                <pre style="white-space: pre-wrap; font-family: Arial; line-height: 1.6; font-size: 0.9rem;">
                    ${partnershipDetails}
                </pre>
                <button onclick="this.parentElement.parentElement.remove()" 
                        style="background: #ff6b6b; color: white; border: none; padding: 10px 20px; 
                               border-radius: 25px; cursor: pointer; font-size: 1rem; margin-top: 20px;">
                    Fermer
                </button>
            `;
            
            modal.appendChild(content);
            document.body.appendChild(modal);
            
            modal.onclick = (e) => {
                if (e.target === modal) modal.remove();
            };
        }

        function showInvestment() {
            const investmentDetails = `
💰 OPPORTUNITÉS D'INVESTISSEMENT

📊 SECTEURS D'INVESTISSEMENT
• Transformation arachide: 8M USD (ROI: 18-22%)
• Fruits & légumes: 12M USD (ROI: 15-20%)
• Transformation maïs: 6M USD (ROI: 20-25%)
• Valorisation manioc: 5M USD (ROI: 16-21%)
• Cosmétiques naturels: 10M USD (ROI: 25-30%)
• Huiles essentielles: 4M USD (ROI: 30-35%)

🏦 TYPES DE FINANCEMENT
• Participation au capital (20-51%)
• Prêts à long terme (7-10 ans)
• Financement équipements
• Crédit-bail industriel
• Obligations convertibles

🎯 GARANTIES ET SÉCURITÉ
• Garantie gouvernementale partielle
• Assurance crédit international
• Contrats d'approvisionnement sécurisés
• Diversification risques multi-secteurs

💡 AVANTAGES INVESTISSEURS
• Exemptions fiscales 5-10 ans
• Rapatriement profits libre
• Protection investissements étrangers
• Accès préférentiel marchés régionaux

📈 PROJECTIONS FINANCIÈRES
• Retour sur investissement: 3-5 ans
• Création valeur: 200-300M USD (2030)
• Emplois générés: 10,000+ (direct/indirect)
• Impact social: 50,000 bénéficiaires

🌱 IMPACT DÉVELOPPEMENT DURABLE
• Réduction pauvreté rurale
• Autonomisation femmes (40% emplois)
• Pratiques agricoles durables
• Économie circulaire intégrée

Contact: investment@fianarantsoa-agro.mg
Tél: +261 XX XX XX XX
            `;
            
            // Create modal
            const modal = document.createElement('div');
            modal.style.cssText = `
                position: fixed; top: 0; left: 0; width: 100%; height: 100%; 
                background: rgba(0,0,0,0.8); display: flex; align-items: center; 
                justify-content: center; z-index: 1000; backdrop-filter: blur(5px);
            `;
            
            const content = document.createElement('div');
            content.style.cssText = `
                background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
                color: white; padding: 40px; border-radius: 20px; max-width: 800px;
                max-height: 80vh; overflow-y: auto; border: 2px solid #4ecdc4;
                box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            `;
            
            content.innerHTML = `
                <h3 style="color: #4ecdc4; margin-bottom: 20px; font-size: 1.8rem;">
                    💰 Opportunités d'Investissement
                </h3>
                <pre style="white-space: pre-wrap; font-family: Arial; line-height: 1.6; font-size: 0.9rem;">
                    ${investmentDetails}
                </pre>
                <button onclick="this.parentElement.parentElement.remove()" 
                        style="background: #ff6b6b; color: white; border: none; padding: 10px 20px; 
                               border-radius: 25px; cursor: pointer; font-size: 1rem; margin-top: 20px;">
                    Fermer
                </button>
            `;
            
            modal.appendChild(content);
            document.body.appendChild(modal);
            
            modal.onclick = (e) => {
                if (e.target === modal) modal.remove();
            };
        }

        // Animation d'entrée pour les éléments
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Animer les cartes secteurs au scroll
        document.querySelectorAll('.sector-card').forEach((card, index) => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(50px)';
            card.style.transition = `all 0.6s ease ${index * 0.1}s`;
            observer.observe(card);
        });

        // Animer les métriques
        document.querySelectorAll('.metric').forEach((metric, index) => {
            metric.style.opacity = '0';
            metric.style.transform = 'translateY(30px)';
            metric.style.transition = `all 0.5s ease ${index * 0.1}s`;
            observer.observe(metric);
        });

        // Timeline animation
        document.querySelectorAll('.timeline-item').forEach(item => {
            item.style.transform = 'translateY(30px)';
            observer.observe(item);
        });
    </script>
</body>
</html>
