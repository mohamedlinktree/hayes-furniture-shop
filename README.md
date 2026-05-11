<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Furniture Shop Hayes | Quality Furniture Since 1996</title>
    <link rel="preconnect" href="[fonts.googleapis.com](https://fonts.googleapis.com)">
    <link rel="preconnect" href="[fonts.gstatic.com](https://fonts.gstatic.com)" crossorigin>
    <link href="[fonts.googleapis.com](https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&family=Inter:wght@300;400;500;600&display=swap)" rel="stylesheet">
    <style>
        :root {
            --color-primary: #2C3E2D;
            --color-secondary: #8B7355;
            --color-accent: #C4A77D;
            --color-cream: #F8F5F0;
            --color-dark: #1A1A1A;
            --color-text: #333333;
            --color-text-light: #666666;
            --color-white: #FFFFFF;
            --font-display: 'Playfair Display', Georgia, serif;
            --font-body: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --shadow-sm: 0 2px 8px rgba(0,0,0,0.08);
            --shadow-md: 0 4px 20px rgba(0,0,0,0.12);
            --shadow-lg: 0 8px 40px rgba(0,0,0,0.16);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-body);
            color: var(--color-text);
            line-height: 1.6;
            background: var(--color-white);
            overflow-x: hidden;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            padding: 1rem 2rem;
            transition: var(--transition);
            background: transparent;
        }

        .navbar.scrolled {
            background: rgba(255, 255, 255, 0.98);
            backdrop-filter: blur(10px);
            box-shadow: var(--shadow-sm);
            padding: 0.75rem 2rem;
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: var(--font-display);
            font-size: 1.5rem;
            font-weight: 600;
            color: var(--color-white);
            text-decoration: none;
            transition: var(--transition);
        }

        .navbar.scrolled .logo {
            color: var(--color-primary);
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--color-white);
            text-decoration: none;
            font-size: 0.9rem;
            font-weight: 500;
            letter-spacing: 0.5px;
            transition: var(--transition);
            position: relative;
        }

        .navbar.scrolled .nav-links a {
            color: var(--color-text);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--color-accent);
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-cta {
            background: var(--color-accent);
            color: var(--color-dark) !important;
            padding: 0.6rem 1.5rem;
            border-radius: 4px;
        }

        .nav-cta::after {
            display: none;
        }

        .nav-cta:hover {
            background: var(--color-secondary);
            color: var(--color-white) !important;
        }

        .mobile-menu-btn {
            display: none;
            flex-direction: column;
            gap: 5px;
            background: none;
            border: none;
            cursor: pointer;
            padding: 5px;
        }

        .mobile-menu-btn span {
            width: 25px;
            height: 2px;
            background: var(--color-white);
            transition: var(--transition);
        }

        .navbar.scrolled .mobile-menu-btn span {
            background: var(--color-dark);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            background: linear-gradient(135deg, rgba(44, 62, 45, 0.9) 0%, rgba(26, 26, 26, 0.85) 100%),
                        url('[images.unsplash.com](https://images.unsplash.com/photo-1555041469-a586c61ea9bc?w=1920&q=80)') center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 2rem;
            position: relative;
        }

        .hero::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 150px;
            background: linear-gradient(to top, var(--color-white), transparent);
        }

        .hero-content {
            max-width: 900px;
            z-index: 1;
        }

        .hero-badge {
            display: inline-block;
            background: rgba(196, 167, 125, 0.2);
            border: 1px solid var(--color-accent);
            color: var(--color-accent);
            padding: 0.5rem 1.5rem;
            border-radius: 50px;
            font-size: 0.85rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 1.5rem;
            animation: fadeInUp 0.8s ease forwards;
        }

        .hero h1 {
            font-family: var(--font-display);
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            color: var(--color-white);
            font-weight: 600;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            animation: fadeInUp 0.8s ease 0.2s forwards;
            opacity: 0;
        }

        .hero p {
            font-size: 1.2rem;
            color: rgba(255, 255, 255, 0.85);
            max-width: 600px;
            margin: 0 auto 2.5rem;
            animation: fadeInUp 0.8s ease 0.4s forwards;
            opacity: 0;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 0.8s ease 0.6s forwards;
            opacity: 0;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 1rem 2rem;
            border-radius: 4px;
            font-size: 0.95rem;
            font-weight: 500;
            text-decoration: none;
            transition: var(--transition);
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background: var(--color-accent);
            color: var(--color-dark);
        }

        .btn-primary:hover {
            background: var(--color-secondary);
            color: var(--color-white);
            transform: translateY(-2px);
            box-shadow: var(--shadow-md);
        }

        .btn-secondary {
            background: transparent;
            color: var(--color-white);
            border: 2px solid rgba(255, 255, 255, 0.4);
        }

        .btn-secondary:hover {
            background: var(--color-white);
            color: var(--color-dark);
            border-color: var(--color-white);
        }

        .scroll-indicator {
            position: absolute;
            bottom: 3rem;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        .scroll-indicator span {
            display: block;
            width: 30px;
            height: 50px;
            border: 2px solid rgba(255, 255, 255, 0.5);
            border-radius: 25px;
            position: relative;
        }

        .scroll-indicator span::before {
            content: '';
            position: absolute;
            top: 8px;
            left: 50%;
            width: 6px;
            height: 6px;
            background: var(--color-white);
            border-radius: 50%;
            transform: translateX(-50%);
            animation: scroll 2s infinite;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
            40% { transform: translateX(-50%) translateY(-10px); }
            60% { transform: translateX(-50%) translateY(-5px); }
        }

        @keyframes scroll {
            0% { opacity: 1; top: 8px; }
            100% { opacity: 0; top: 32px; }
        }

        /* Section Styles */
        section {
            padding: 6rem 2rem;
        }

        .section-header {
            text-align: center;
            max-width: 700px;
            margin: 0 auto 4rem;
        }

        .section-label {
            display: inline-block;
            color: var(--color-secondary);
            font-size: 0.85rem;
            letter-spacing: 3px;
            text-transform: uppercase;
            margin-bottom: 1rem;
            font-weight: 600;
        }

        .section-title {
            font-family: var(--font-display);
            font-size: clamp(2rem, 4vw, 3rem);
            color: var(--color-primary);
            margin-bottom: 1rem;
        }

        .section-subtitle {
            color: var(--color-text-light);
            font-size: 1.1rem;
        }

        /* About Section */
        .about {
            background: var(--color-cream);
        }

        .about-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-image {
            position: relative;
        }

        .about-image img {
            width: 100%;
            height: 500px;
            object-fit: cover;
            border-radius: 8px;
            box-shadow: var(--shadow-lg);
        }

        .about-image::before {
            content: '';
            position: absolute;
            top: -20px;
            left: -20px;
            right: 20px;
            bottom: 20px;
            border: 3px solid var(--color-accent);
            border-radius: 8px;
            z-index: -1;
        }

        .experience-badge {
            position: absolute;
            bottom: -30px;
            right: -30px;
            background: var(--color-primary);
            color: var(--color-white);
            padding: 1.5rem 2rem;
            border-radius: 8px;
            text-align: center;
            box-shadow: var(--shadow-lg);
        }

        .experience-badge .number {
            font-family: var(--font-display);
            font-size: 3rem;
            font-weight: 700;
            line-height: 1;
            color: var(--color-accent);
        }

        .experience-badge span {
            display: block;
            font-size: 0.9rem;
            margin-top: 0.25rem;
        }

        .about-content h2 {
            font-family: var(--font-display);
            font-size: 2.5rem;
            color: var(--color-primary);
            margin-bottom: 1.5rem;
        }

        .about-content p {
            color: var(--color-text-light);
            margin-bottom: 1.5rem;
            font-size: 1.05rem;
        }

        .about-features {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .about-feature {
            display: flex;
            align-items: flex-start;
            gap: 1rem;
        }

        .about-feature-icon {
            width: 50px;
            height: 50px;
            background: var(--color-accent);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        .about-feature-icon svg {
            width: 24px;
            height: 24px;
            fill: var(--color-dark);
        }

        .about-feature h4 {
            font-size: 1rem;
            color: var(--color-primary);
            margin-bottom: 0.25rem;
        }

        .about-feature p {
            font-size: 0.9rem;
            margin: 0;
        }

        /* Categories Section */
        .categories {
            background: var(--color-white);
        }

        .categories-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1.5rem;
        }

        .category-card {
            position: relative;
            height: 400px;
            border-radius: 8px;
            overflow: hidden;
            cursor: pointer;
            group: category;
        }

        .category-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .category-card:hover img {
            transform: scale(1.1);
        }

        .category-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(to top, rgba(0, 0, 0, 0.8) 0%, transparent 60%);
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            padding: 2rem;
            transition: var(--transition);
        }

        .category-card:hover .category-overlay {
            background: linear-gradient(to top, rgba(44, 62, 45, 0.95) 0%, rgba(44, 62, 45, 0.7) 100%);
        }

        .category-overlay h3 {
            font-family: var(--font-display);
            font-size: 1.5rem;
            color: var(--color-white);
            margin-bottom: 0.5rem;
        }

        .category-overlay p {
            color: rgba(255, 255, 255, 0.8);
            font-size: 0.9rem;
            transform: translateY(20px);
            opacity: 0;
            transition: var(--transition);
        }

        .category-card:hover .category-overlay p {
            transform: translateY(0);
            opacity: 1;
        }

        .category-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--color-accent);
            font-size: 0.9rem;
            font-weight: 500;
            margin-top: 1rem;
            transform: translateY(20px);
            opacity: 0;
            transition: var(--transition);
        }

        .category-card:hover .category-link {
            transform: translateY(0);
            opacity: 1;
        }

        /* Featured Products */
        .products {
            background: var(--color-cream);
        }

        .products-grid {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
        }

        .product-card {
            background: var(--color-white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-lg);
        }

        .product-image {
            position: relative;
            height: 280px;
            overflow: hidden;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .product-card:hover .product-image img {
            transform: scale(1.05);
        }

        .product-badge {
            position: absolute;
            top: 1rem;
            left: 1rem;
            background: var(--color-primary);
            color: var(--color-white);
            padding: 0.35rem 0.75rem;
            border-radius: 4px;
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .product-badge.sale {
            background: #C75050;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-category {
            color: var(--color-secondary);
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 0.5rem;
        }

        .product-info h3 {
            font-family: var(--font-display);
            font-size: 1.25rem;
            color: var(--color-primary);
            margin-bottom: 0.75rem;
        }

        .product-price {
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .product-price .current {
            font-size: 1.25rem;
            font-weight: 600;
            color: var(--color-primary);
        }

        .product-price .original {
            font-size: 1rem;
            color: var(--color-text-light);
            text-decoration: line-through;
        }

        /* Services Section */
        .services {
            background: var(--color-primary);
            color: var(--color-white);
        }

        .services .section-label {
            color: var(--color-accent);
        }

        .services .section-title {
            color: var(--color-white);
        }

        .services .section-subtitle {
            color: rgba(255, 255, 255, 0.7);
        }

        .services-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 2rem;
        }

        .service-card {
            text-align: center;
            padding: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            transition: var(--transition);
        }

        .service-card:hover {
            background: rgba(255, 255, 255, 0.05);
            border-color: var(--color-accent);
        }

        .service-icon {
            width: 70px;
            height: 70px;
            background: rgba(196, 167, 125, 0.15);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1.5rem;
        }

        .service-icon svg {
            width: 32px;
            height: 32px;
            fill: var(--color-accent);
        }

        .service-card h3 {
            font-family: var(--font-display);
            font-size: 1.25rem;
            margin-bottom: 0.75rem;
        }

        .service-card p {
            font-size: 0.95rem;
            color: rgba(255, 255, 255, 0.7);
            line-height: 1.6;
        }

        /* Testimonials */
        .testimonials {
            background: var(--color-white);
        }

        .testimonials-slider {
            max-width: 1000px;
            margin: 0 auto;
            position: relative;
        }

        .testimonial-card {
            text-align: center;
            padding: 3rem;
        }

        .testimonial-quote {
            width: 60px;
            height: 60px;
            background: var(--color-cream);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 2rem;
        }

        .testimonial-quote svg {
            width: 28px;
            height: 28px;
            fill: var(--color-accent);
        }

        .testimonial-text {
            font-family: var(--font-display);
            font-size: 1.5rem;
            color: var(--color-primary);
            line-height: 1.6;
            margin-bottom: 2rem;
            font-style: italic;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
        }

        .testimonial-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            object-fit: cover;
        }

        .testimonial-info h4 {
            font-size: 1rem;
            color: var(--color-primary);
            margin-bottom: 0.25rem;
        }

        .testimonial-info p {
            font-size: 0.9rem;
            color: var(--color-text-light);
        }

        .testimonial-stars {
            display: flex;
            gap: 0.25rem;
            justify-content: center;
            margin-bottom: 1.5rem;
        }

        .testimonial-stars svg {
            width: 20px;
            height: 20px;
            fill: var(--color-accent);
        }

        /* Contact Section */
        .contact {
            background: var(--color-cream);
        }

        .contact-wrapper {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            gap: 4rem;
        }

        .contact-info h2 {
            font-family: var(--font-display);
            font-size: 2.5rem;
            color: var(--color-primary);
            margin-bottom: 1rem;
        }

        .contact-info > p {
            color: var(--color-text-light);
            margin-bottom: 2rem;
            font-size: 1.05rem;
        }

        .contact-details {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 1rem;
        }

        .contact-item-icon {
            width: 50px;
            height: 50px;
            background: var(--color-primary);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        .contact-item-icon svg {
            width: 22px;
            height: 22px;
            fill: var(--color-accent);
        }

        .contact-item h4 {
            font-size: 1rem;
            color: var(--color-primary);
            margin-bottom: 0.25rem;
        }

        .contact-item p {
            color: var(--color-text-light);
            font-size: 0.95rem;
        }

        .contact-item a {
            color: var(--color-secondary);
            text-decoration: none;
            transition: var(--transition);
        }

        .contact-item a:hover {
            color: var(--color-primary);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }

        .social-link {
            width: 45px;
            height: 45px;
            background: var(--color-primary);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }

        .social-link:hover {
            background: var(--color-accent);
        }

        .social-link svg {
            width: 20px;
            height: 20px;
            fill: var(--color-white);
        }

        .social-link:hover svg {
            fill: var(--color-dark);
        }

        .contact-form-wrapper {
            background: var(--color-white);
            padding: 3rem;
            border-radius: 12px;
            box-shadow: var(--shadow-md);
        }

        .contact-form h3 {
            font-family: var(--font-display);
            font-size: 1.5rem;
            color: var(--color-primary);
            margin-bottom: 1.5rem;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
            margin-bottom: 1rem;
        }

        .form-group {
            margin-bottom: 1rem;
        }

        .form-group label {
            display: block;
            font-size: 0.9rem;
            color: var(--color-text);
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 0.9rem 1rem;
            border: 1px solid #E0E0E0;
            border-radius: 6px;
            font-family: var(--font-body);
            font-size: 0.95rem;
            transition: var(--transition);
            background: var(--color-white);
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--color-accent);
            box-shadow: 0 0 0 3px rgba(196, 167, 125, 0.15);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }

        .btn-submit {
            width: 100%;
            padding: 1rem;
            background: var(--color-primary);
            color: var(--color-white);
            border: none;
            border-radius: 6px;
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            transition: var(--transition);
        }

        .btn-submit:hover {
            background: var(--color-secondary);
            transform: translateY(-2px);
        }

        /* Map Section */
        .map-section {
            height: 400px;
            position: relative;
        }

        .map-section iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        /* Footer */
        .footer {
            background: var(--color-dark);
            color: var(--color-white);
            padding: 5rem 2rem 2rem;
        }

        .footer-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1.5fr 1fr 1fr 1fr;
            gap: 3rem;
            padding-bottom: 3rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .footer-brand h3 {
            font-family: var(--font-display);
            font-size: 1.75rem;
            margin-bottom: 1rem;
        }

        .footer-brand p {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.95rem;
            line-height: 1.7;
            margin-bottom: 1.5rem;
        }

        .footer-column h4 {
            font-size: 1rem;
            margin-bottom: 1.5rem;
            color: var(--color-accent);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.75rem;
        }

        .footer-links a {
            color: rgba(255, 255, 255, 0.6);
            text-decoration: none;
            font-size: 0.95rem;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--color-white);
            padding-left: 5px;
        }

        .footer-hours {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.95rem;
        }

        .footer-hours p {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }

        .footer-bottom {
            max-width: 1200px;
            margin: 0 auto;
            padding-top: 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .footer-bottom p {
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.9rem;
        }

        .footer-bottom-links {
            display: flex;
            gap: 2rem;
        }

        .footer-bottom-links a {
            color: rgba(255, 255, 255, 0.5);
            text-decoration: none;
            font-size: 0.9rem;
            transition: var(--transition);
        }

        .footer-bottom-links a:hover {
            color: var(--color-white);
        }

        /* Mobile Responsive */
        @media (max-width: 1024px) {
            .categories-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .products-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .services-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .footer-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 0;
                right: -100%;
                width: 80%;
                max-width: 400px;
                height: 100vh;
                background: var(--color-white);
                flex-direction: column;
                padding: 5rem 2rem 2rem;
                gap: 1.5rem;
                transition: var(--transition);
                box-shadow: var(--shadow-lg);
            }

            .nav-links.active {
                right: 0;
            }

            .nav-links a {
                color: var(--color-text);
                font-size: 1.1rem;
            }

            .mobile-menu-btn {
                display: flex;
                z-index: 1001;
            }

            .about-grid {
                grid-template-columns: 1fr;
                gap: 3rem;
            }

            .about-image {
                order: -1;
            }

            .about-image::before {
                display: none;
            }

            .experience-badge {
                right: 1rem;
                bottom: -20px;
            }

            .about-features {
                grid-template-columns: 1fr;
            }

            .categories-grid {
                grid-template-columns: 1fr;
            }

            .category-card {
                height: 300px;
            }

            .products-grid {
                grid-template-columns: 1fr;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .contact-wrapper {
                grid-template-columns: 1fr;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .footer-grid {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .social-links {
                justify-content: center;
            }

            .footer-bottom {
                flex-direction: column;
                text-align: center;
            }
        }

        /* Animations on scroll */
        .animate-on-scroll {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .animate-on-scroll.animated {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar" id="navbar">
        <div class="nav-container">
            <a href="#" class="logo">The Furniture Shop</a>
            <ul class="nav-links" id="navLinks">
                <li><a href="#about">About</a></li>
                <li><a href="#categories">Collections</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#contact">Contact</a></li>
                <li><a href="#contact" class="nav-cta">Visit Store</a></li>
            </ul>
            <button class="mobile-menu-btn" id="mobileMenuBtn" aria-label="Toggle menu">
                <span></span>
                <span></span>
                <span></span>
            </button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <span class="hero-badge">Established 1996</span>
            <h1>Transform Your Space with Timeless Furniture</h1>
            <p>Discover handpicked furniture collections that blend quality craftsmanship with exceptional value. Direct from manufacturers to your home.</p>
            <div class="hero-buttons">
                <a href="#categories" class="btn btn-primary">
                    Explore Collections
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M5 12h14M12 5l7 7-7 7"/>
                    </svg>
                </a>
                <a href="#contact" class="btn btn-secondary">Visit Our Store</a>
            </div>
        </div>
        <div class="scroll-indicator">
            <span></span>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="about-grid">
            <div class="about-image animate-on-scroll">
                <img src="[images.unsplash.com](https://images.unsplash.com/photo-1556228453-efd6c1ff04f6?w=800&q=80)" alt="Furniture showroom interior">
                <div class="experience-badge">
                    <span class="number">29+</span>
                    <span>Years Experience</span>
                </div>
            </div>
            <div class="about-content animate-on-scroll">
                <h2>Your Trusted Furniture Partner in Hayes</h2>
                <p>Since 1996, The Furniture Shop has been serving the Hayes community with a commitment to quality, value, and exceptional customer service. We believe everyone deserves beautiful furniture that doesn't break the bank.</p>
                <p>By working directly with manufacturers and cutting out the middleman, we pass the savings on to you. Visit our showroom on Coldharbour Lane to experience our extensive collection firsthand.</p>
                <div class="about-features">
                    <div class="about-feature">
                        <div class="about-feature-icon">
                            <svg viewBox="0 0 24 24"><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41L9 16.17z"/></svg>
                        </div>
                        <div>
                            <h4>Factory Direct Prices</h4>
                            <p>Save more by cutting out the middleman</p>
                        </div>
                    </div>
                    <div class="about-feature">
                        <div class="about-feature-icon">
                            <svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg>
                        </div>
                        <div>
                            <h4>Quality Guaranteed</h4>
                            <p>Handpicked furniture built to last</p>
                        </div>
                    </div>
                    <div class="about-feature">
                        <div class="about-feature-icon">
                            <svg viewBox="0 0 24 24"><path d="M18 18.5a1.5 1.5 0 0 0 1.5-1.5V8c0-.4-.2-.7-.4-1L16 2.9c-.2-.2-.5-.4-.8-.4H8.8c-.3 0-.6.2-.8.4L5 7c-.3.3-.5.6-.5 1v9a1.5 1.5 0 0 0 1.5 1.5H18zM12 17a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm0-6a2 2 0 1 0 0 4 2 2 0 0 0 0-4z"/></svg>
                        </div>
                        <div>
                            <h4>Home Delivery</h4>
                            <p>Convenient delivery service available</p>
                        </div>
                    </div>
                    <div class="about-feature">
                        <div class="about-feature-icon">
                            <svg viewBox="0 0 24 24"><path d="M16 11c1.66 0 2.99-1.34 2.99-3S17.66 5 16 5c-1.66 0-3 1.34-3 3s1.34 3 3 3zm-8 0c1.66 0 2.99-1.34 2.99-3S9.66 5 8 5C6.34 5 5 6.34 5 8s1.34 3 3 3zm0 2c-2.33 0-7 1.17-7 3.5V19h14v-2.5c0-2.33-4.67-3.5-7-3.5zm8 0c-.29 0-.62.02-.97.05 1.16.84 1.97 1.97 1.97 3.45V19h6v-2.5c0-2.33-4.67-3.5-7-3.5z"/></svg>
                        </div>
                        <div>
                            <h4>Expert Advice</h4>
                            <p>Friendly staff to help you choose</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories" id="categories">
        <div class="section-header">
            <span class="section-label">Our Collections</span>
            <h2 class="section-title">Furniture for Every Room</h2>
            <p class="section-subtitle">Explore our carefully curated collections designed to bring comfort and style to your home</p>
        </div>
        <div class="categories-grid">
            <div class="category-card animate-on-scroll">
                <img src="[images.unsplash.com](https://images.unsplash.com/photo-1505693416388-ac5ce068fe85?w=600&q=80)" alt="Bedroom furniture">
                <div class="category-overlay">
                    <h3>Beds & Bedroom</h3>
                    <p>Comfortable beds, wardrobes, and bedroom sets for restful nights</p>
                    <span class="category-link">
                        Explore Collection
                        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M5 12h14M12 5l7 7-7 7"/>
                        </svg>
                    </span>
                </div>
            </div>
            <div class="category-card animate-on-scroll">
                <img src="[images.unsplash.com](https://images.unsplash.com/photo-1555041469-a586c61ea9bc?w=600&q=80)" alt="Living room sofa">
                <div class="category-overlay">
                    <h3>Sofas & Seating</h3>
                    <p>Stylish sofas, settees, and armchairs for your living space</p>
                    <span class="category-link">
                        Explore Collection
                        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M5 12h14M12 5l7 7-7 7"/>
                        </svg>
                    </span>
                </div>
            </div>
            <div class="category-card animate-on-scroll">
                <img src="[images.unsplash.com](https://images.unsplash.com/photo-1617806118233-18e1de247200?w=600&q=80)" alt="Dining furniture">
                <div class="category-overlay">
                    <h3>Dining & Tables</h3>
                    <p>Beautiful dining sets and tables for memorable meals</p>
                    <span class="category-link">
                        Explore Collection
                        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M5 12h14M12 5l7 7-7 7"/>
                        </svg>
                    </span>
                </div>
            </div>
            <div class="category-card animate-on-scroll">
                <img src="[images.unsplash.com](https://images.unsplash.com/photo-1595428774223-ef52624120d2?w=600&q=80)" alt="Home accessories">
                <div class="category-overlay">
                    <h3>Chairs & More</h3>
                    <p>Accent chairs, futons, and tableware to complete your home</p>
                    <span class="category-link">
                        Explore Collection
                        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M5 12h14M12 5l7 7-7 7"/>
                        </svg>
                    </span>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Products Section -->
    <section class="products" id="products">
        <div class="section-header">
            <span class="section-label">Featured Products</span>
            <h2 class="section-title">Popular Picks</h2>
            <p class="section-subtitle">Our customers' favourites — quality furniture at unbeatable prices</p>
        </div>
        <div class="products-grid">
            <div class="product-card animate-on-scroll">
                <div class="product-image">
                    <img src="[images.unsplash.com](https://images.unsplash.com/photo-1493663284031-b7e3aefcae8e?w=600&q=80)" alt="Modern grey sofa">
                    <span class="product-badge">Best Seller</span>
                </div>
                <div class="product-info">
                    <span class="product-category">Sofas</span>
                    <h3>Modern 3-Seater Fabric Sofa</h3>
                    <div class="product-price">
                        <span class="current">£549</span>
                        <span class="original">£749</span>
                    </div>
                </div>
            </div>
            <div class="product-card animate-on-scroll">
                <div class="product-image">
                    <img src="[images.unsplash.com](https://images.unsplash.com/photo-1505693314120-0d443867891c?w=600&q=80)" alt="Wooden bed frame">
                </div>
                <div class="product-info">
                    <span class="product-category">Beds</span>
                    <h3>Oak Wood King Size Bed Frame</h3>
                    <div class="product-price">
                        <span class="current">£399</span>
                    </div>
                </div>
            </div>
            <div class="product-card animate-on-scroll">
                <div class="product-image">
                    <img src="[images.unsplash.com](https://images.unsplash.com/photo-1555041469-a586c61ea9bc?w=600&q=80)" alt="Velvet armchair">
                    <span class="product-badge sale">Sale</span>
                </div>
                <div class="product-info">
                    <span class="product-category">Chairs</span>
                    <h3>Velvet Accent Armchair</h3>
                    <div class="product-price">
                        <span class="current">£199</span>
                        <span class="original">£279</span>
                    </div>
                </div>
            </div>
            <div class="product-card animate-on-scroll">
                <div class="product-image">
                    <img src="[images.unsplash.com](https://images.unsplash.com/photo-1617806118233-18e1de247200?w=600&q=80)" alt="Dining table set">
                </div>
                <div class="product-info">
                    <span class="product-category">Dining</span>
                    <h3>6-Seater Dining Table Set</h3>
                    <div class="product-price">
                        <span class="current">£649</span>
                    </div>
                </div>
            </div>
            <div class="product-card animate-on-scroll">
                <div class="product-image">
                    <img src="[images.unsplash.com](https://images.unsplash.com/photo-1556909114-f6e7ad7d3136?w=600&q=80)" alt="Wardrobe">
                    <span class="product-badge">New</span>
                </div>
                <div class="product-info">
                    <span class="product-category">Storage</span>
                    <h3>3-Door Mirrored Wardrobe</h3>
                    <div class="product-price">
                        <span class="current">£449</span>
                    </div>
                </div>
            </div>
            <div class="product-card animate-on-scroll">
                <div class="product-image">
                    <img src="[images.unsplash.com](https://images.unsplash.com/photo-1518455027359-f3f8164ba6bd?w=600&q=80)" alt="Coffee table">
                </div>
                <div class="product-info">
                    <span class="product-category">Tables</span>
                    <h3>Glass Top Coffee Table</h3>
                    <div class="product-price">
                        <span class="current">£149</span>
                        <span class="original">£199</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <div class="section-header">
            <span class="section-label">Why Choose Us</span>
            <h2 class="section-title">Services That Make the Difference</h2>
            <p class="section-subtitle">We go above and beyond to ensure your furniture shopping experience is exceptional</p>
        </div>
        <div class="services-grid">
            <div class="service-card animate-on-scroll">
                <div class="service-icon">
                    <svg viewBox="0 0 24 24"><path d="M18 18.5c.83 0 1.5-.67 1.5-1.5s-.67-1.5-1.5-1.5-1.5.67-1.5 1.5.67 1.5 1.5 1.5zM19.5 9.5l1.9 2.5H19v2.5h3.5v3c0 .55-.45 1-1 1h-1c0 1.1-.9 2-2 2s-2-.9-2-2H9c0 1.1-.9 2-2 2s-2-.9-2-2H4c-.55 0-1-.45-1-1V6c0-1.1.9-2 2-2h11v5.5h3.5zM7 18.5c.83 0 1.5-.67 1.5-1.5s-.67-1.5-1.5-1.5-1.5.67-1.5 1.5.67 1.5 1.5 1.5z"/></svg>
                </div>
                <h3>Home Delivery</h3>
                <p>Convenient delivery service to bring your furniture right to your doorstep across Hayes and surrounding areas.</p>
            </div>
            <div class="service-card animate-on-scroll">
                <div class="service-icon">
                    <svg viewBox="0 0 24 24"><path d="M11.8 10.9c-2.27-.59-3-1.2-3-2.15 0-1.09 1.01-1.85 2.7-1.85 1.78 0 2.44.85 2.5 2.1h2.21c-.07-1.72-1.12-3.3-3.21-3.81V3h-3v2.16c-1.94.42-3.5 1.68-3.5 3.61 0 2.31 1.91 3.46 4.7 4.13 2.5.6 3 1.48 3 2.41 0 .69-.49 1.79-2.7 1.79-2.06 0-2.87-.92-2.98-2.1h-2.2c.12 2.19 1.76 3.42 3.68 3.83V21h3v-2.15c1.95-.37 3.5-1.5 3.5-3.55 0-2.84-2.43-3.81-4.7-4.4z"/></svg>
                </div>
                <h3>Best Prices</h3>
                <p>Factory direct pricing means you get the best value. No middleman, no markup — just great furniture at honest prices.</p>
            </div>
            <div class="service-card animate-on-scroll">
                <div class="service-icon">
                    <svg viewBox="0 0 24 24"><path d="M12 1L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-4zm-2 16l-4-4 1.41-1.41L10 14.17l6.59-6.59L18 9l-8 8z"/></svg>
                </div>
                <h3>Quality Assured</h3>
                <p>Every piece is carefully selected and inspected. We partner only with trusted manufacturers who share our quality standards.</p>
            </div>
            <div class="service-card animate-on-scroll">
                <div class="service-icon">
                    <svg viewBox="0 0 24 24"><path d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm.5-13H11v6l5.25 3.15.75-1.23-4.5-2.67z"/></svg>
                </div>
                <h3>Extended Hours</h3>
                <p>Open 7 days a week with convenient hours. Visit us when it suits you — we're here to help you find the perfect piece.</p>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="testimonials">
        <div class="section-header">
            <span class="section-label">Customer Reviews</span>
            <h2 class="section-title">What Our Customers Say</h2>
            <p class="section-subtitle">Don't just take our word for it — hear from our happy customers</p>
        </div>
        <div class="testimonials-slider">
            <div class="testimonial-card animate-on-scroll">
                <div class="testimonial-quote">
                    <svg viewBox="0 0 24 24"><path d="M6 17h3l2-4V7H5v6h3zm8 0h3l2-4V7h-6v6h3z"/></svg>
                </div>
                <div class="testimonial-stars">
                    <svg viewBox="0 0 24 24"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
                    <svg viewBox="0 0 24 24"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
                    <svg viewBox="0 0 24 24"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
                    <svg viewBox="0 0 24 24"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
                    <svg viewBox="0 0 24 24"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
                </div>
                <p class="testimonial-text">"A great shop — best deals, great value for money. Very helpful and friendly staff. Everything you need for your house is all under one roof. Excellent delivery service too!"</p>
                <div class="testimonial-author">
                    <div class="testimonial-info">
                        <h4>Paul M.</h4>
                        <p>Harrow</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <div class="contact-wrapper">
            <div class="contact-info animate-on-scroll">
                <h2>Visit Our Showroom</h2>
                <p>Come explore our extensive furniture collection in person. Our friendly team is ready to help you find exactly what you're looking for.</p>
                <div class="contact-details">
                    <div class="contact-item">
                        <div class="contact-item-icon">
                            <svg viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
                        </div>
                        <div>
                            <h4>Address</h4>
                            <p>108 Coldharbour Lane<br>Hayes, UB3 3HA</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-item-icon">
                            <svg viewBox="0 0 24 24"><path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/></svg>
                        </div>
                        <div>
                            <h4>Phone</h4>
                            <p><a href="tel:02085690162">020 8569 0162</a><br><a href="tel:02088483777">020 8848 3777</a></p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-item-icon">
                            <svg viewBox="0 0 24 24"><path d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm.5-13H11v6l5.25 3.15.75-1.23-4.5-2.67z"/></svg>
                        </div>
                        <div>
                            <h4>Opening Hours</h4>
                            <p>Mon–Sat: 9:00 AM – 7:00 PM<br>Sunday: 11:00 AM – 4:00 PM</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-item-icon">
                            <svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10h5v-2h-5c-4.34 0-8-3.66-8-8s3.66-8 8-8 8 3.66 8 8v1.43c0 .79-.71 1.57-1.5 1.57s-1.5-.78-1.5-1.57V12c0-2.76-2.24-5-5-5s-5 2.24-5 5 2.24 5 5 5c1.38 0 2.64-.56 3.54-1.47.65.89 1.77 1.47 2.96 1.47 1.97 0 3.5-1.6 3.5-3.57V12c0-5.52-4.48-10-10-10zm0 13c-1.66 0-3-1.34-3-3s1.34-3 3-3 3 1.34 3 3-1.34 3-3 3z"/></svg>
                        </div>
                        <div>
                            <h4>Nearest Station</h4>
                            <p>Hayes & Harlington<br>(0.45 miles)</p>
                        </div>
                    </div>
                </div>
                <div class="social-links">
                    <a href="[facebook.com](https://www.facebook.com/TheFurnitureShop108/)" target="_blank" class="social-link" aria-label="Facebook">
                        <svg viewBox="0 0 24 24"><path d="M22 12c0-5.52-4.48-10-10-10S2 6.48 2 12c0 4.84 3.44 8.87 8 9.8V15H8v-3h2V9.5C10 7.57 11.57 6 13.5 6H16v3h-2c-.55 0-1 .45-1 1v2h3v3h-3v6.95c5.05-.5 9-4.76 9-9.95z"/></svg>
                    </a>
                    <a href="[instagram.com](https://www.instagram.com/thefurnitureshop.online/)" target="_blank" class="social-link" aria-label="Instagram">
                        <svg viewBox="0 0 24 24"><path d="M7.8 2h8.4C19.4 2 22 4.6 22 7.8v8.4a5.8 5.8 0 0 1-5.8 5.8H7.8C4.6 22 2 19.4 2 16.2V7.8A5.8 5.8 0 0 1 7.8 2m-.2 2A3.6 3.6 0 0 0 4 7.6v8.8C4 18.39 5.61 20 7.6 20h8.8a3.6 3.6 0 0 0 3.6-3.6V7.6C20 5.61 18.39 4 16.4 4H7.6m9.65 1.5a1.25 1.25 0 0 1 1.25 1.25A1.25 1.25 0 0 1 17.25 8 1.25 1.25 0 0 1 16 6.75a1.25 1.25 0 0 1 1.25-1.25M12 7a5 5 0 0 1 5 5 5 5 0 0 1-5 5 5 5 0 0 1-5-5 5 5 0 0 1 5-5m0 2a3 3 0 0 0-3 3 3 3 0 0 0 3 3 3 3 0 0 0 3-3 3 3 0 0 0-3-3z"/></svg>
                    </a>
                    <a href="[google.com](https://www.google.com/maps/place/The+Furniture+Shop+Hayes/)" target="_blank" class="social-link" aria-label="Google Maps">
                        <svg viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
                    </a>
                </div>
            </div>
            <div class="contact-form-wrapper animate-on-scroll">
                <form class="contact-form" id="contactForm">
                    <h3>Send Us a Message</h3>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="name">Your Name</label>
                            <input type="text" id="name" name="name" required placeholder="John Smith">
                        </div>
                        <div class="form-group">
                            <label for="phone">Phone Number</label>
                            <input type="tel" id="phone" name="phone" placeholder="07123 456789">
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="email">Email Address</label>
                        <input type="email" id="email" name="email" required placeholder="john@example.com">
                    </div>
                    <div class="form-group">
                        <label for="interest">I'm Interested In</label>
                        <select id="interest" name="interest">
                            <option value="">Select a category</option>
                            <option value="sofas">Sofas & Seating</option>
                            <option value="beds">Beds & Bedroom</option>
                            <option value="dining">Dining & Tables</option>
                            <option value="storage">Storage & Wardrobes</option>
                            <option value="other">Other / General Enquiry</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="message">Your Message</label>
                        <textarea id="message" name="message" required placeholder="Tell us what you're looking for..."></textarea>
                    </div>
                    <button type="submit" class="btn-submit">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Map Section -->
    <div class="map-section">
        <iframe src="[google.com](https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2483.845!2d-0.4173032!3d51.5091951!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x487672837f6eef3d%3A0x7c2308e93cbc05c5!2sThe%20Furniture%20Shop%20Hayes!5e0!3m2!1sen!2suk!4v1620000000000!5m2!1sen!2suk)" allowfullscreen="" loading="lazy" title="The Furniture Shop Hayes location map"></iframe>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-grid">
            <div class="footer-brand">
                <h3>The Furniture Shop</h3>
                <p>Serving Hayes and the surrounding areas since 1996. Quality furniture, factory-direct prices, and exceptional customer service — that's our promise to you.</p>
                <div class="social-links">
                    <a href="[facebook.com](https://www.facebook.com/TheFurnitureShop108/)" target="_blank" class="social-link" aria-label="Facebook">
                        <svg viewBox="0 0 24 24"><path d="M22 12c0-5.52-4.48-10-10-10S2 6.48 2 12c0 4.84 3.44 8.87 8 9.8V15H8v-3h2V9.5C10 7.57 11.57 6 13.5 6H16v3h-2c-.55 0-1 .45-1 1v2h3v3h-3v6.95c5.05-.5 9-4.76 9-9.95z"/></svg>
                    </a>
                    <a href="[instagram.com](https://www.instagram.com/thefurnitureshop.online/)" target="_blank" class="social-link" aria-label="Instagram">
                        <svg viewBox="0 0 24 24"><path d="M7.8 2h8.4C19.4 2 22 4.6 22 7.8v8.4a5.8 5.8 0 0 1-5.8 5.8H7.8C4.6 22 2 19.4 2 16.2V7.8A5.8 5.8 0 0 1 7.8 2m-.2 2A3.6 3.6 0 0 0 4 7.6v8.8C4 18.39 5.61 20 7.6 20h8.8a3.6 3.6 0 0 0 3.6-3.6V7.6C20 5.61 18.39 4 16.4 4H7.6m9.65 1.5a1.25 1.25 0 0 1 1.25 1.25A1.25 1.25 0 0 1 17.25 8 1.25 1.25 0 0 1 16 6.75a1.25 1.25 0 0 1 1.25-1.25M12 7a5 5 0 0 1 5 5 5 5 0 0 1-5 5 5 5 0 0 1-5-5 5 5 0 0 1 5-5m0 2a3 3 0 0 0-3 3 3 3 0 0 0 3 3 3 3 0 0 0 3-3 3 3 0 0 0-3-3z"/></svg>
                    </a>
                </div>
            </div>
            <div class="footer-column">
                <h4>Quick Links</h4>
                <ul class="footer-links">
                    <li><a href="#about">About Us</a></li>
                    <li><a href="#categories">Collections</a></li>
                    <li><a href="#products">Products</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h4>Categories</h4>
                <ul class="footer-links">
                    <li><a href="#categories">Beds & Bedroom</a></li>
                    <li><a href="#categories">Sofas & Seating</a></li>
                    <li><a href="#categories">Dining & Tables</a></li>
                    <li><a href="#categories">Chairs & Futons</a></li>
                    <li><a href="#categories">Tableware</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h4>Opening Hours</h4>
                <div class="footer-hours">
                    <p><span>Monday</span><span>9AM – 7PM</span></p>
                    <p><span>Tuesday</span><span>9AM – 7PM</span></p>
                    <p><span>Wednesday</span><span>9AM – 7PM</span></p>
                    <p><span>Thursday</span><span>9AM – 7PM</span></p>
                    <p><span>Friday</span><span>9AM – 7PM</span></p>
                    <p><span>Saturday</span><span>9AM – 7PM</span></p>
                    <p><span>Sunday</span><span>11AM – 4PM</span></p>
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <p>© 2024 The Furniture Shop Hayes. All rights reserved.</p>
            <div class="footer-bottom-links">
                <a href="#">Privacy Policy</a>
                <a href="#">Terms of Service</a>
            </div>
        </div>
    </footer>

    <script>
        // Navbar scroll effect
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Mobile menu toggle
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const navLinks = document.getElementById('navLinks');
        
        mobileMenuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Animate on scroll
        const animateOnScroll = () => {
            const elements = document.querySelectorAll('.animate-on-scroll');
            elements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                if (elementTop < windowHeight - 100) {
                    element.classList.add('animated');
                }
            });
        };

        window.addEventListener('scroll', animateOnScroll);
        window.addEventListener('load', animateOnScroll);

        // Form submission (demo)
        document.getElementById('contactForm').addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Thank you for your message! We will get back to you soon.');
            e.target.reset();
        });
    </script>
</body>
</html>

