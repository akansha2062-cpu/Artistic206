# Artistic206<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fine Art Portfolio & Print Store</title>
    <meta name="description" content="Explore original acrylic paintings, detailed graphite sketches, prints, and book custom artwork commissions.">
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">

    <style>
        :root {
            --bg-color: #121212;
            --card-bg: #1e1e1e;
            --accent-gold: #d4af37;
            --text-primary: #f5f5f5;
            --text-secondary: #a0a0a0;
            --border-color: #333333;
            --font-heading: 'Cormorant Garamond', serif;
            --font-body: 'Inter', sans-serif;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-primary);
            font-family: var(--font-body);
            line-height: 1.6;
        }

        /* Header Navigation */
        header {
            position: sticky;
            top: 0;
            background-color: rgba(18, 18, 18, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border-color);
            z-index: 1000;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.2rem 2rem;
        }

        .logo {
            font-family: var(--font-heading);
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--accent-gold);
            text-decoration: none;
            letter-spacing: 1px;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--text-primary);
            text-decoration: none;
            font-size: 0.95rem;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--accent-gold);
        }

        /* Hero Section */
        .hero {
            padding: 6rem 2rem;
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-family: var(--font-heading);
            font-size: 3.2rem;
            line-height: 1.2;
            margin-bottom: 1rem;
            color: var(--text-primary);
        }

        .hero p {
            font-size: 1.1rem;
            color: var(--text-secondary);
            margin-bottom: 2rem;
        }

        .btn-gold {
            display: inline-block;
            background-color: var(--accent-gold);
            color: #121212;
            padding: 0.8rem 2rem;
            border-radius: 4px;
            text-decoration: none;
            font-weight: 600;
            transition: transform 0.2s ease, opacity 0.3s ease;
        }

        .btn-gold:hover {
            opacity: 0.9;
            transform: translateY(-2px);
        }

        /* Gallery Section */
        .gallery-section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        .section-title {
            font-family: var(--font-heading);
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 2rem;
            color: var(--accent-gold);
        }

        .filter-buttons {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }

        .filter-btn {
            background: transparent;
            border: 1px solid var(--border-color);
            color: var(--text-secondary);
            padding: 0.5rem 1.5rem;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .filter-btn.active, .filter-btn:hover {
            border-color: var(--accent-gold);
            color: var(--accent-gold);
        }

        .art-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
        }

        .art-card {
            background-color: var(--card-bg);
            border-radius: 8px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            transition: transform 0.3s ease;
        }

        .art-card:hover {
            transform: translateY(-5px);
        }

        .art-card img {
            width: 100%;
            height: 320px;
            object-fit: cover;
            cursor: pointer;
        }

        .art-info {
            padding: 1.2rem;
        }

        .art-title {
            font-family: var(--font-heading);
            font-size: 1.4rem;
            margin-bottom: 0.3rem;
        }

        .art-meta {
            font-size: 0.85rem;
            color: var(--text-secondary);
            margin-bottom: 0.8rem;
        }

        .art-price {
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--accent-gold);
        }

        /* Contact & Commission Form */
        .commission-section {
            background-color: var(--card-bg);
            padding: 4rem 2rem;
            margin-top: 4rem;
            border-top: 1px solid var(--border-color);
        }

        .form-container {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
            color: var(--text-secondary);
        }

        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            background-color: var(--bg-color);
            border: 1px solid var(--border-color);
            color: var(--text-primary);
            border-radius: 4px;
        }

        /* Footer */
        footer {
            border-top: 1px solid var(--border-color);
            padding: 2rem;
            text-align: center;
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        /* Lightbox Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            max-width: 90%;
            max-height: 80%;
            border-radius: 4px;
        }

        .close-modal {
            position: absolute;
            top: 20px;
            right: 30px;
            color: #fff;
            font-size: 2rem;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .hero h1 { font-size: 2.2rem; }
            .nav-links { display: none; }
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <header>
        <nav class="nav-container">
            <a href="#" class="logo">ART GALLERY</a>
            <ul class="nav-links">
                <li><a href="#gallery">Gallery</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#commission">Commissions</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <h1>Capturing Divinity, Culture & Emotion</h1>
        <p>Explore original handcrafted acrylic paintings, detailed graphite sketches, and archival prints.</p>
        <a href="#gallery" class="btn-gold">Explore Artworks</a>
    </section>

    <!-- Gallery Section -->
    <section class="gallery-section" id="gallery">
        <h2 class="section-title">Artwork Collection</h2>
        
        <div class="filter-buttons">
            <button class="filter-btn active" onclick="filterArt('all')">All Works</button>
            <button class="filter-btn" onclick="filterArt('acrylic')">Acrylic Paintings</button>
            <button class="filter-btn" onclick="filterArt('graphite')">Graphite Sketches</button>
            <button class="filter-btn" onclick="filterArt('prints')">Prints</button>
        </div>

        <div class="art-grid">
            <!-- Item 1 -->
            <div class="art-card acrylic">
                <img src="https://images.unsplash.com/photo-1579783902614-a3fb3927b675?auto=format&fit=crop&w=600&q=80" alt="Acrylic Painting" onclick="openModal(this.src)">
                <div class="art-info">
                    <h3 class="art-title">Serene Devotion</h3>
                    <p class="art-meta">Acrylic on Canvas • 18" x 24"</p>
                    <div class="art-price">Original Available</div>
                </div>
            </div>

            <!-- Item 2 -->
            <div class="art-card graphite">
                <img src="https://images.unsplash.com/photo-1578301978693-85fa9c0320b9?auto=format&fit=crop&w=600&q=80" alt="Graphite Sketch" onclick="openModal(this.src)">
                <div class="art-info">
                    <h3 class="art-title">Divine Grace</h3>
                    <p class="art-meta">Graphite on Paper • A3 Size</p>
                    <div class="art-price">Original Available</div>
                </div>
            </div>

            <!-- Item 3 -->
            <div class="art-card prints">
                <img src="https://images.unsplash.com/photo-1579783900882-c0d3dad7b119?auto=format&fit=crop&w=600&q=80" alt="Fine Art Print" onclick="openModal(this.src)">
                <div class="art-info">
                    <h3 class="art-title">Sacred Flow Print</h3>
                    <p class="art-meta">Archival Matte Paper Print</p>
                    <div class="art-price">From ₹999</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Custom Commission Section -->
    <section class="commission-section" id="commission">
        <h2 class="section-title">Commission Custom Art</h2>
        <div class="form-container">
            <form action="https://formspree.io/f/your_form_id" method="POST">
                <div class="form-group">
                    <label>Full Name</label>
                    <input type="text" name="name" required placeholder="Enter your name">
                </div>
                <div class="form-group">
                    <label>Email Address</label>
                    <input type="email" name="email" required placeholder="Enter your email">
                </div>
                <div class="form-group">
                    <label>Preferred Medium</label>
                    <select name="medium">
                        <option value="acrylic">Acrylic Painting</option>
                        <option value="graphite">Graphite / Pencil Sketch</option>
                        <option value="print">Custom Size Print</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Details & Requirements</label>
                    <textarea name="message" rows="4" placeholder="Describe your idea or desired dimensions"></textarea>
                </div>
                <button type="submit" class="btn-gold" style="width:100%; border:none; cursor:pointer;">Send Inquiry</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 Fine Art Portfolio. All rights reserved.</p>
    </footer>

    <!-- Image Modal Lightbox -->
    <div id="imageModal" class="modal">
        <span class="close-modal" onclick="closeModal()">&times;</span>
        <img class="modal-content" id="imgModalSrc">
    </div>

    <!-- JavaScript Functions -->
    <script>
        // Gallery Filter
        function filterArt(category) {
            const cards = document.querySelectorAll('.art-card');
            const buttons = document.querySelectorAll('.filter-btn');

            buttons.forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');

            cards.forEach(card => {
                if (category === 'all' || card.classList.contains(category)) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        // Image Lightbox
        function openModal(src) {
            document.getElementById('imageModal').style.display = 'flex';
            document.getElementById('imgModalSrc').src = src;
        }

        function closeModal() {
            document.getElementById('imageModal').style.display = 'none';
        }
    </script>
</body>
</html>
