# markethub
all in one market
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MarketHub</title>
    <style>
        body {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            line-height: 1.6;
            color: #0F1111;
            background-color: #f5f5f5;
            min-height: 100vh;
        }

        * {
            box-sizing: border-box;
        }

        /* Header - Amazon Style */
        .header {
            background-color: #232F3E;
            color: white;
            padding: 0.5rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-top {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 1rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #FF9900;
            text-decoration: none;
        }

        .header-icons {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .header-icons a {
            color: white;
            text-decoration: none;
            font-size: 0.9rem;
            position: relative;
        }

        .cart-icon {
            position: relative;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #FF9900;
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.7rem;
            font-weight: bold;
        }

        /* Search Bar */
        .search-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1rem;
            display: flex;
            align-items: center;
            background-color: white;
            margin-top: 0.5rem;
        }

        .search-select {
            background: #f3f3f3;
            border: 1px solid #ddd;
            padding: 0.5rem;
            border-radius: 4px 0 0 4px;
            font-size: 0.9rem;
        }

        .search-input {
            flex: 1;
            padding: 0.7rem;
            border: none;
            font-size: 1rem;
            outline: none;
        }

        .search-btn {
            background: #FF9900;
            color: white;
            border: none;
            padding: 0.7rem 1rem;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
            font-size: 1rem;
        }

        .search-btn:hover {
            background: #e68900;
        }

        /* Departments Navigation */
        .departments {
            background-color: #232F3E;
            color: white;
            padding: 0.5rem 0;
        }

        .departments-nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            list-style: none;
            margin: 0;
            padding: 0 1rem;
            gap: 2rem;
        }

        .departments-nav a {
            color: white;
            text-decoration: none;
            font-size: 0.9rem;
            padding: 0.5rem 0;
            transition: color 0.3s;
        }

        .departments-nav a:hover {
            color: #FF9900;
        }

        /* Main Content */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .page {
            display: none;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 2rem;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(10px);
        }

        .page.active {
            display: block;
        }

        .page-title {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: #333;
            text-align: center;
        }

        .page-subtitle {
            font-size: 1.2rem;
            color: #666;
            text-align: center;
            margin-bottom: 3rem;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 4rem 0;
            color: white;
            background: linear-gradient(135deg, #232F3E 0%, #131921 100%);
            border-radius: 10px;
            margin-bottom: 2rem;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .cta-btn {
            padding: 1rem 2rem;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .cta-btn:hover {
            background: white;
            color: #667eea;
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        /* Product Grid */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .product-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(45deg, #f0f0f0, #e0e0e0);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3.5rem;
            color: #999;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .product-price {
            font-size: 1.4rem;
            font-weight: bold;
            color: #B12704;
            margin-bottom: 0.5rem;
        }

        .product-description {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .product-rating {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .stars {
            color: #ffc107;
        }

        .btn {
            background: #FF9900;
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            width: 100%;
        }

        .btn:hover {
            background: #e68900;
            transform: translateY(-2px);
        }

        .btn-secondary {
            background: #28a745;
        }

        .btn-secondary:hover {
            background: #218838;
        }

        .btn-warning {
            background: #ffc107;
            color: #333;
        }

        .btn-warning:hover {
            background: #e0a800;
        }

        /* Used Items Cards */
        .used-item-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .used-item-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .item-header {
            padding: 1rem 1.5rem;
            background: linear-gradient(135deg, #28a745, #20c997);
            color: white;
        }

        .item-category {
            font-size: 0.9rem;
            opacity: 0.9;
            margin-bottom: 0.5rem;
        }

        .item-condition {
            display: inline-block;
            background: rgba(255, 255, 255, 0.2);
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            margin-top: 0.5rem;
        }

        /* Repair Service Cards */
        .repair-card {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border-left: 5px solid #ffc107;
        }

        .repair-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .repair-status {
            display: inline-block;
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .status-pending {
            background: #fff3cd;
            color: #856404;
        }

        .status-progress {
            background: #d1ecf1;
            color: #0c5460;
        }

        .status-completed {
            background: #d4edda;
            color: #155724;
        }

        /* Footer */
        .footer {
            background: rgba(0, 0, 0, 0.8);
            color: white;
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 1rem;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: white;
            text-decoration: none;
            opacity: 0.8;
            transition: opacity 0.3s ease;
        }

        .footer-links a:hover {
            opacity: 1;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-container {
                flex-direction: column;
                gap: 1rem;
                padding: 0 1rem;
            }

            .nav-links {
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .container {
                padding: 1rem;
            }

            .product-grid {
                grid-template-columns: 1fr;
            }

            .page-title {
                font-size: 2rem;
            }
        }

        @media (max-width: 480px) {
            .nav-links {
                flex-direction: column;
                text-align: center;
            }

            .hero {
                padding: 2rem 0;
            }

            .hero h1 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <div class="header-top">
            <a href="#" class="logo" onclick="showCategoryPage('home')">MarketHub</a>
            <div class="header-icons">
                <a href="#" onclick="showCategoryPage('login')" id="account-link">Hello, Sign in<br><span style="font-weight: bold;">Account & Lists</span></a>
                <a href="#" onclick="showCategoryPage('cart')" class="cart-icon">🛒 Cart <span class="cart-count" id="cart-count">0</span></a>
            </div>
        </div>
        <div class="search-container">
            <select class="search-select">
                <option>All</option>
                <option>Electronics</option>
                <option>Books</option>
                <option>Fiction</option>
                <option>Non-Fiction</option>
                <option>Biographies</option>
                <option>Clothing</option>
                <option>Home</option>
            </select>
            <input type="text" class="search-input" placeholder="Search Amazon">
            <button class="search-btn">🔍</button>
        </div>
    </header>

    <nav class="departments">
        <ul class="departments-nav">
            <li><a href="#" onclick="showCategoryPage('home')">Home</a></li>
            <li><a href="#" onclick="showCategoryPage('products', 'All')">Today's Deals</a></li>
            <li><a href="#" onclick="showCategoryPage('products', 'Electronics')">Electronics</a></li>
            <li><a href="#" onclick="showCategoryPage('products', 'Books')">Books</a></li>
            <li><a href="#" onclick="showCategoryPage('products', 'Clothing')">Fashion</a></li>
            <li><a href="#" onclick="showCategoryPage('used-items', 'All')">Sell</a></li>
            <li><a href="#" onclick="showCategoryPage('repair', 'All')">Services</a></li>
        </ul>
    </nav>

    <div class="container">
        <div id="home" class="page active">
            <div class="hero">
                <h1>Welcome to MarketHub</h1>
                <p>Your one-stop destination for buying, selling, and repairing</p>
                <div class="cta-buttons">
                    <a href="#" onclick="showCategoryPage('products', 'All')" class="cta-btn">🛍️ Shop Products</a>
                    <a href="#" onclick="showCategoryPage('used-items', 'All')" class="cta-btn">💱 Sell Items</a>
                    <a href="#" onclick="showCategoryPage('repair', 'All')" class="cta-btn">🔧 Repair Services</a>
                </div>
            </div>

            <section style="margin: 3rem 0;">
                <h2 style="font-size: 2rem; margin-bottom: 1rem; color: #333; text-align: center;">Today's Deals</h2>
                <div class="product-grid">
                    <div class="product-card" data-category="Electronics">
                        <div class="product-image">📱</div>
                        <div class="product-info">
                            <h3 class="product-title">Smartphone Pro Max</h3>
                            <div class="product-price" style="text-decoration: line-through; color: #666;">$999.99</div>
                            <div class="product-price">$899.99 <span style="color: #B12704; font-size: 0.9rem;">(10% off)</span></div>
                            <p class="product-description">Latest flagship smartphone with advanced camera system.</p>
                            <button class="btn">Add to Cart</button>
                        </div>
                    </div>
                    <div class="product-card" data-category="Electronics">
                        <div class="product-image">🎧</div>
                        <div class="product-info">
                            <h3 class="product-title">Wireless Headphones</h3>
                            <div class="product-price" style="text-decoration: line-through; color: #666;">$249.99</div>
                            <div class="product-price">$199.99 <span style="color: #B12704; font-size: 0.9rem;">(20% off)</span></div>
                            <p class="product-description">Premium noise-canceling headphones with 30-hour battery.</p>
                            <button class="btn">Add to Cart</button>
                        </div>
                    </div>
                    <div class="product-card" data-category="Books">
                        <div class="product-image">📚</div>
                        <div class="product-info">
                            <h3 class="product-title">The Daily Stoic</h3>
                            <div class="product-price" style="text-decoration: line-through; color: #666;">$19.99</div>
                            <div class="product-price">$14.99 <span style="color: #B12704; font-size: 0.9rem;">(25% off)</span></div>
                            <p class="product-description">A guide to the good life by Ryan Holiday.</p>
                            <button class="btn">Add to Cart</button>
                        </div>
                    </div>
                    <div class="product-card" data-category="Clothing">
                        <div class="product-image">👕</div>
                        <div class="product-info">
                            <h3 class="product-title">Designer Casual Shirt</h3>
                            <div class="product-price" style="text-decoration: line-through; color: #666;">$49.99</div>
                            <div class="product-price">$34.99 <span style="color: #B12704; font-size: 0.9rem;">(30% off)</span></div>
                            <p class="product-description">Comfortable cotton shirt for everyday wear.</p>
                            <button class="btn">Add to Cart</button>
                        </div>
                    </div>
                    <div class="product-card" data-category="Electronics">
                        <div class="product-image">⌚</div>
                        <div class="product-info">
                            <h3 class="product-title">Smart Watch Series X</h3>
                            <div class="product-price" style="text-decoration: line-through; color: #666;">$399.99</div>
                            <div class="product-price">$349.99 <span style="color: #B12704; font-size: 0.9rem;">(12% off)</span></div>
                            <p class="product-description">Advanced fitness tracking and health monitoring.</p>
                            <button class="btn">Add to Cart</button>
                        </div>
                    </div>
                    <div class="product-card" data-category="Home">
                        <div class="product-image">☕</div>
                        <div class="product-info">
                            <h3 class="product-title">Ceramic Coffee Mug</h3>
                            <div class="product-price" style="text-decoration: line-through; color: #666;">$15.99</div>
                            <div class="product-price">$11.99 <span style="color: #B12704; font-size: 0.9rem;">(25% off)</span></div>
                            <p class="product-description">High-quality mug for your morning coffee.</p>
                            <button class="btn">Add to Cart</button>
                        </div>
                    </div>
                    <div class="product-card" data-category="Books">
                        <div class="product-image">📚</div>
                        <div class="product-info">
                            <h3 class="product-title">The Psychology of Money</h3>
                            <div class="product-price" style="text-decoration: line-through; color: #666;">$22.00</div>
                            <div class="product-price">$18.70 <span style="color: #B12704; font-size: 0.9rem;">(15% off)</span></div>
                            <p class="product-description">Timeless lessons on wealth, greed, and happiness.</p>
                            <button class="btn">Add to Cart</button>
                        </div>
                    </div>
                    <div class="product-card" data-category="Clothing">
                        <div class="product-image">👖</div>
                        <div class="product-info">
                            <h3 class="product-title">Slim Fit Jeans</h3>
                            <div class="product-price" style="text-decoration: line-through; color: #666;">$59.99</div>
                            <div class="product-price">$41.99 <span style="color: #B12704; font-size: 0.9rem;">(30% off)</span></div>
                            <p class="product-description">Classic denim jeans with a modern slim-fit cut.</p>
                            <button class="btn">Add to Cart</button>
                        </div>
                    </div>
                </div>
            </section>

            <section style="margin: 3rem 0;">
                <h2 style="font-size: 2rem; margin-bottom: 1rem; color: #333; text-align: center;">Shop by Category</h2>
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 1rem; margin-top: 2rem;">
                    <div style="text-align: center; padding: 1rem; background: white; border-radius: 10px; box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); cursor: pointer;" onclick="showCategoryPage('products', 'Electronics')">
                        <div style="font-size: 3rem; margin-bottom: 0.5rem;">📱</div>
                        <h3 style="font-size: 1rem; color: #333;">Electronics</h3>
                    </div>
                    <div style="text-align: center; padding: 1rem; background: white; border-radius: 10px; box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); cursor: pointer;" onclick="showCategoryPage('products', 'Clothing')">
                        <div style="font-size: 3rem; margin-bottom: 0.5rem;">👕</div>
                        <h3 style="font-size: 1rem; color: #333;">Fashion</h3>
                    </div>
                    <div style="text-align: center; padding: 1rem; background: white; border-radius: 10px; box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); cursor: pointer;" onclick="showCategoryPage('products', 'Home')">
                        <div style="font-size: 3rem; margin-bottom: 0.5rem;">🏠</div>
                        <h3 style="font-size: 1rem; color: #333;">Home & Garden</h3>
                    </div>
                    <div style="text-align: center; padding: 1rem; background: white; border-radius: 10px; box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); cursor: pointer;" onclick="showCategoryPage('products', 'Books')">
                        <div style="font-size: 3rem; margin-bottom: 0.5rem;">📚</div>
                        <h3 style="font-size: 1rem; color: #333;">Books</h3>
                    </div>
                    <div style="text-align: center; padding: 1rem; background: white; border-radius: 10px; box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); cursor: pointer;" onclick="showCategoryPage('used-items', 'All')">
                        <div style="font-size: 3rem; margin-bottom: 0.5rem;">💱</div>
                        <h3 style="font-size: 1rem; color: #333;">Sell Items</h3>
                    </div>
                    <div style="text-align: center; padding: 1rem; background: white; border-radius: 10px; box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); cursor: pointer;" onclick="showCategoryPage('repair', 'All')">
                        <div style="font-size: 3rem; margin-bottom: 0.5rem;">🔧</div>
                        <h3 style="font-size: 1rem; color: #333;">Repair Services</h3>
                    </div>
                </div>
            </section>
        </div>

        <div id="products" class="page">
            <h2 class="page-title">🛍️ Buy Products</h2>
            <p class="page-subtitle">Discover amazing products at great prices</p>
            
            <div class="product-grid">
                <div class="product-card" data-category="Electronics">
                    <div class="product-image">📱</div>
                    <div class="product-info">
                        <h3 class="product-title">Smartphone Pro Max</h3>
                        <div class="product-price">$899.99</div>
                        <p class="product-description">Latest flagship smartphone with advanced camera system and lightning-fast performance.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.8/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Electronics">
                    <div class="product-image">💻</div>
                    <div class="product-info">
                        <h3 class="product-title">Gaming Laptop Ultra</h3>
                        <div class="product-price">$1,299.99</div>
                        <p class="product-description">High-performance gaming laptop with RTX graphics and RGB keyboard.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.9/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Electronics">
                    <div class="product-image">🎧</div>
                    <div class="product-info">
                        <h3 class="product-title">Wireless Headphones</h3>
                        <div class="product-price">$199.99</div>
                        <p class="product-description">Premium noise-canceling headphones with 30-hour battery life.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.7/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Electronics">
                    <div class="product-image">⌚</div>
                    <div class="product-info">
                        <h3 class="product-title">Smart Watch Series X</h3>
                        <div class="product-price">$349.99</div>
                        <p class="product-description">Advanced fitness tracking and health monitoring smartwatch.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.6/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Electronics">
                    <div class="product-image">📷</div>
                    <div class="product-info">
                        <h3 class="product-title">DSLR Camera Kit</h3>
                        <div class="product-price">$799.99</div>
                        <p class="product-description">Professional camera with multiple lenses and accessories included.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.8/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Electronics">
                    <div class="product-image">🎮</div>
                    <div class="product-info">
                        <h3 class="product-title">Gaming Console</h3>
                        <div class="product-price">$499.99</div>
                        <p class="product-description">Next-gen gaming console with 4K gaming and exclusive titles.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.9/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Books">
                    <div class="product-image">📖</div>
                    <div class="product-info">
                        <h3 class="product-title">The Great Gatsby</h3>
                        <div class="product-price">$12.99</div>
                        <p class="product-description">A classic American novel by F. Scott Fitzgerald about the Jazz Age and the American Dream.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.7/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Books">
                    <div class="product-image">📚</div>
                    <div class="product-info">
                        <h3 class="product-title">Sapiens: A Brief History of Humankind</h3>
                        <div class="product-price">$18.99</div>
                        <p class="product-description">An exploration of the history of humankind from the Stone Age to the modern age.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.8/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Books">
                    <div class="product-image">👤</div>
                    <div class="product-info">
                        <h3 class="product-title">Steve Jobs Biography</h3>
                        <div class="product-price">$24.99</div>
                        <p class="product-description">The definitive biography of Steve Jobs, co-founder of Apple Inc.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.6/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Books">
                    <div class="product-image">💻</div>
                    <div class="product-info">
                        <h3 class="product-title">Python Crash Course</h3>
                        <div class="product-price">$29.99</div>
                        <p class="product-description">A hands-on, project-based introduction to programming with Python.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.9/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Books">
                    <div class="product-image">💡</div>
                    <div class="product-info">
                        <h3 class="product-title">Atomic Habits</h3>
                        <div class="product-price">$15.99</div>
                        <p class="product-description">An easy and proven way to build good habits and break bad ones.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.9/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Books">
                    <div class="product-image">🔍</div>
                    <div class="product-info">
                        <h3 class="product-title">Where the Crawdads Sing</h3>
                        <div class="product-price">$14.50</div>
                        <p class="product-description">A haunting coming-of-age story and a murder mystery.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.8/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Clothing">
                    <div class="product-image">👕</div>
                    <div class="product-info">
                        <h3 class="product-title">Men's Polo Shirt</h3>
                        <div class="product-price">$25.99</div>
                        <p class="product-description">Classic fit polo shirt made from breathable cotton fabric.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.5/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Clothing">
                    <div class="product-image">👗</div>
                    <div class="product-info">
                        <h3 class="product-title">Women's Summer Dress</h3>
                        <div class="product-price">$39.99</div>
                        <p class="product-description">Lightweight and comfortable floral print summer dress.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.7/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
                <div class="product-card" data-category="Clothing">
                    <div class="product-image">👟</div>
                    <div class="product-info">
                        <h3 class="product-title">Running Sneakers</h3>
                        <div class="product-price">$79.99</div>
                        <p class="product-description">High-performance running shoes with cushioned soles.</p>
                        <div class="product-rating">
                            <span class="stars">⭐⭐⭐⭐⭐</span>
                            <span>(4.6/5)</span>
                        </div>
                        <button class="btn">Add to Cart</button>
                    </div>
                </div>
            </div>
        </div>

        <div id="used-items" class="page">
            <h2 class="page-title">💱 Sell/Exchange Used Items</h2>
            <p class="page-subtitle">Give your items a second life and earn money</p>
            
            <div class="product-grid">
                <div class="used-item-card">
                    <div class="item-header">
                        <div class="item-category">Electronics</div>
                        <h3 class="product-title">iPhone 12 - Excellent Condition</h3>
                        <div class="item-condition">Like New</div>
                    </div>
                    <div class="product-info">
                        <div class="product-price">$450.00</div>
                        <p class="product-description">Barely used iPhone 12 with original box and accessories. No scratches or damage.</p>
                        <div class="product-rating">
                            <span>📍 New York, NY</span>
                        </div>
                        <button class="btn btn-secondary">Contact Seller</button>
                    </div>
                </div>

                <div class="used-item-card">
                    <div class="item-header">
                        <div class="item-category">Furniture</div>
                        <h3 class="product-title">Vintage Leather Sofa</h3>
                        <div class="item-condition">Good</div>
                    </div>
                    <div class="product-info">
                        <div class="product-price">$300.00</div>
                        <p class="product-description">Beautiful vintage leather sofa, some wear but very comfortable. Perfect for living room.</p>
                        <div class="product-rating">
                            <span>📍 Los Angeles, CA</span>
                        </div>
                        <button class="btn btn-secondary">Contact Seller</button>
                    </div>
                </div>

                <div class="used-item-card">
                    <div class="item-header">
                        <div class="item-category">Sports</div>
                        <h3 class="product-title">Mountain Bike - Trek</h3>
                        <div class="item-condition">Very Good</div>
                    </div>
                    <div class="product-info">
                        <div class="product-price">$650.00</div>
                        <p class="product-description">Well-maintained Trek mountain bike. Recently serviced with new tires and brakes.</p>
                        <div class="product-rating">
                            <span>📍 Denver, CO</span>
                        </div>
                        <button class="btn btn-secondary">Contact Seller</button>
                    </div>
                </div>

                <div class="used-item-card">
                    <div class="item-header">
                        <div class="item-category">Books</div>
                        <h3 class="product-title">Programming Books Collection</h3>
                        <div class="item-condition">Good</div>
                    </div>
                    <div class="product-info">
                        <div class="product-price">$120.00</div>
                        <p class="product-description">Collection of 15 programming books including Python, JavaScript, and web development.</p>
                        <div class="product-rating">
                            <span>📍 Austin, TX</span>
                        </div>
                        <button class="btn btn-secondary">Contact Seller</button>
                    </div>
                </div>

                <div class="used-item-card">
                    <div class="item-header">
                        <div class="item-category">Appliances</div>
                        <h3 class="product-title">Coffee Machine - Espresso</h3>
                        <div class="item-condition">Excellent</div>
                    </div>
                    <div class="product-info">
                        <div class="product-price">$180.00</div>
                        <p class="product-description">Professional espresso machine, lightly used. Makes perfect coffee every time.</p>
                        <div class="product-rating">
                            <span>📍 Seattle, WA</span>
                        </div>
                        <button class="btn btn-secondary">Contact Seller</button>
                    </div>
                </div>

                <div class="used-item-card">
                    <div class="item-header">
                        <div class="item-category">Fashion</div>
                        <h3 class="product-title">Designer Handbag</h3>
                        <div class="item-condition">Like New</div>
                    </div>
                    <div class="product-info">
                        <div class="product-price">$280.00</div>
                        <p class="product-description">Authentic designer handbag, used only twice. Comes with authenticity certificate.</p>
                        <div class="product-rating">
                            <span>📍 Miami, FL</span>
                        </div>
                        <button class="btn btn-secondary">Contact Seller</button>
                    </div>
                </div>
            </div>
        </div>

        <div id="repair" class="page">
            <h2 class="page-title">🔧 Repair Services</h2>
            <p class="page-subtitle">Get your items fixed by trusted professionals</p>

            <div class="product-grid">
                <div class="repair-card">
                    <div class="repair-status status-pending">Pending Review</div>
                    <h3 class="product-title">MacBook Pro Screen Replacement</h3>
                    <p class="product-description">Cracked screen on 2019 MacBook Pro 13". Need professional screen replacement service.</p>
                    <div class="product-rating">
                        <span><strong>Estimated Cost:</strong> $280 - $350</span><br>
                        <span><strong>Repair Time:</strong> 2-3 days</span><br>
                        <span><strong>Location:</strong> San Francisco, CA</span>
                    </div>
                    <button class="btn btn-warning">Get Quote</button>
                </div>

                <div class="repair-card">
                    <div class="repair-status status-progress">In Progress</div>
                    <h3 class="product-title">Washing Machine Motor Issue</h3>
                    <p class="product-description">Washing machine making loud noises and not spinning properly. Motor needs inspection.</p>
                    <div class="product-rating">
                        <span><strong>Estimated Cost:</strong> $150 - $200</span><br>
                        <span><strong>Repair Time:</strong> 1-2 days</span><br>
                        <span><strong>Location:</strong> Chicago, IL</span>
                    </div>
                    <button class="btn btn-warning">Track Progress</button>
                </div>

                <div class="repair-card">
                    <div class="repair-status status-completed">Completed</div>
                    <h3 class="product-title">iPhone Battery Replacement</h3>
                    <p class="product-description">iPhone 11 battery draining quickly. Professional battery replacement completed successfully.</p>
                    <div class="product-rating">
                        <span><strong>Final Cost:</strong> $89</span><br>
                        <span><strong>Repair Time:</strong> Same day</span><br>
                        <span><strong>Location:</strong> Boston, MA</span>
                    </div>
                    <button class="btn btn-secondary">Leave Review</button>
                </div>

                <div class="repair-card">
                    <div class="repair-status status-pending">Pending Review</div>
                    <h3 class="product-title">Gaming Console Overheating</h3>
                    <p class="product-description">PS5 shutting down due to overheating. Needs cleaning and thermal paste replacement.</p>
                    <div class="product-rating">
                        <span><strong>Estimated Cost:</strong> $80 - $120</span><br>
                        <span><strong>Repair Time:</strong> 1 day</span><br>
                        <span><strong>Location:</strong> Phoenix, AZ</span>
                    </div>
                    <button class="btn btn-warning">Get Quote</button>
                </div>

                <div class="repair-card">
                    <div class="repair-status status-progress">In Progress</div>
                    <h3 class="product-title">Watch Band Replacement</h3>
                    <p class="product-description">Luxury watch needs new leather band. Original band is worn out and cracked.</p>
                    <div class="product-rating">
                        <span><strong>Estimated Cost:</strong> $45 - $75</span><br>
                        <span><strong>Repair Time:</strong> 2-3 hours</span><br>
                        <span><strong>Location:</strong> Las Vegas, NV</span>
                    </div>
                    <button class="btn btn-warning">Track Progress</button>
                </div>

                <div class="repair-card">
                    <div class="repair-status status-pending">Pending Review</div>
                    <h3 class="product-title">Laptop Keyboard Repair</h3>
                    <p class="product-description">Several keys not working on Dell laptop keyboard. Needs professional keyboard replacement.</p>
                    <div class="product-rating">
                        <span><strong>Estimated Cost:</strong> $120 - $180</span><br>
                        <span><strong>Repair Time:</strong> 1-2 days</span><br>
                        <span><strong>Location:</strong> Portland, OR</span>
                    </div>
                    <button class="btn btn-warning">Get Quote</button>
                </div>
            </div>
        </div>

        <div id="login" class="page">
            <h2 class="page-title">🔐 Sign In</h2>
            <p class="page-subtitle">Welcome back! Please sign in to your account.</p>

            <form class="login-form" style="max-width: 400px; margin: 0 auto;">
                <div style="margin-bottom: 1rem;">
                    <label for="email" style="display: block; margin-bottom: 0.5rem; font-weight: 600;">Email</label>
                    <input type="email" id="email" name="email" required style="width: 100%; padding: 0.8rem; border: 1px solid #ddd; border-radius: 4px; font-size: 1rem;">
                </div>
                <div style="margin-bottom: 1.5rem;">
                    <label for="password" style="display: block; margin-bottom: 0.5rem; font-weight: 600;">Password</label>
                    <input type="password" id="password" name="password" required style="width: 100%; padding: 0.8rem; border: 1px solid #ddd; border-radius: 4px; font-size: 1rem;">
                </div>
                <button type="submit" class="btn" style="width: 100%; margin-bottom: 1rem;">Sign In</button>
                <p style="text-align: center; color: #666;">Don't have an account? <a href="#" style="color: #FF9900; text-decoration: none;">Create one</a></p>
            </form>
        </div>

        <div id="cart" class="page">
            <h2 class="page-title">🛒 Shopping Cart</h2>
            <p class="page-subtitle">Review your items and proceed to checkout.</p>

            <div id="cart-items" style="margin-bottom: 2rem;">
                <p style="text-align: center; color: #666; font-size: 1.2rem;">Your cart is empty.</p>
            </div>

            <div id="cart-summary" style="max-width: 400px; margin: 0 auto; background: white; padding: 1.5rem; border-radius: 15px; box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1); display: none;">
                <h3 style="margin-bottom: 1rem; color: #333;">Order Summary</h3>
                <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
                    <span>Subtotal:</span>
                    <span id="subtotal">$0.00</span>
                </div>
                <div style="display: flex; justify-content: space-between; margin-bottom: 0.5rem;">
                    <span>Shipping:</span>
                    <span id="shipping">$0.00</span>
                </div>
                <div style="display: flex; justify-content: space-between; margin-bottom: 1rem; font-weight: bold; border-top: 1px solid #ddd; padding-top: 0.5rem;">
                    <span>Total:</span>
                    <span id="total">$0.00</span>
                </div>
                <button class="btn" style="width: 100%;">Proceed to Checkout</button>
            </div>
        </div>
    </div>

    <footer class="footer">
        <div class="footer-content">
            <div class="footer-links">
                <a href="#">About Us</a>
                <a href="#">Contact</a>
                <a href="#">Privacy Policy</a>
                <a href="#">Terms of Service</a>
                <a href="#">Help Center</a>
            </div>
            <p>&copy; 2024 MarketHub. All rights reserved. | Your trusted marketplace for buying, selling, and repairing.</p>
        </div>
    </footer>

    <script>
        // Cart functionality
        let cart = JSON.parse(localStorage.getItem('cart')) || [];
        let isLoggedIn = JSON.parse(localStorage.getItem('isLoggedIn')) || false;
        let currentUser = JSON.parse(localStorage.getItem('currentUser')) || null;

        function updateCartCount() {
            const cartCount = document.getElementById('cart-count');
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = totalItems;
        }

        function addToCart(productName, price, image) {
            const existingItem = cart.find(item => item.name === productName);
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    name: productName,
                    price: parseFloat(price.replace('$', '')),
                    image: image,
                    quantity: 1
                });
            }
            localStorage.setItem('cart', JSON.stringify(cart));
            updateCartCount();
            updateCartDisplay();
            alert(`${productName} added to cart!`);
        }

        function updateCartDisplay() {
            const cartItems = document.getElementById('cart-items');
            const cartSummary = document.getElementById('cart-summary');

            if (cart.length === 0) {
                cartItems.innerHTML = '<p style="text-align: center; color: #666; font-size: 1.2rem;">Your cart is empty.</p>';
                cartSummary.style.display = 'none';
                return;
            }

            let itemsHTML = '';
            let subtotal = 0;

            cart.forEach((item, index) => {
                const itemTotal = item.price * item.quantity;
                subtotal += itemTotal;
                itemsHTML += `
                    <div style="display: flex; align-items: center; padding: 1rem; border-bottom: 1px solid #ddd;">
                        <div style="font-size: 2rem; margin-right: 1rem;">${item.image}</div>
                        <div style="flex: 1;">
                            <h4 style="margin: 0; color: #333;">${item.name}</h4>
                            <p style="margin: 0.5rem 0; color: #666;">$${item.price.toFixed(2)} each</p>
                            <div style="display: flex; align-items: center; gap: 0.5rem;">
                                <button onclick="changeQuantity(${index}, -1)" style="padding: 0.25rem 0.5rem; border: 1px solid #ddd;">-</button>
                                <span>Qty: ${item.quantity}</span>
                                <button onclick="changeQuantity(${index}, 1)" style="padding: 0.25rem 0.5rem; border: 1px solid #ddd;">+</button>
                            </div>
                        </div>
                        <div style="font-weight: bold; color: #B12704;">$${itemTotal.toFixed(2)}</div>
                        <button onclick="removeFromCart(${index})" style="margin-left: 1rem; background: #dc3545; color: white; border: none; padding: 0.5rem; border-radius: 4px; cursor: pointer;">Remove</button>
                    </div>
                `;
            });

            cartItems.innerHTML = itemsHTML;
            cartSummary.style.display = 'block';

            const shipping = subtotal > 50 ? 0 : 9.99;
            const total = subtotal + shipping;

            document.getElementById('subtotal').textContent = `$${subtotal.toFixed(2)}`;
            document.getElementById('shipping').textContent = shipping === 0 ? 'FREE' : `$${shipping.toFixed(2)}`;
            document.getElementById('total').textContent = `$${total.toFixed(2)}`;
        }

        // Login functionality
        function updateLoginStatus() {
            const accountLink = document.getElementById('account-link');
            if (isLoggedIn && currentUser) {
                // If logged in, display the user's name and a logout option
                accountLink.innerHTML = `Hello, ${currentUser.name}<br><span style="font-weight: bold;">Account & Lists</span>`;
                accountLink.onclick = () => {
                    if (confirm('Are you sure you want to log out?')) {
                        logout();
                    }
                };
            } else {
                // If logged out, show the login prompt
                accountLink.innerHTML = `Hello, Sign in<br><span style="font-weight: bold;">Account & Lists</span>`;
                accountLink.onclick = () => showCategoryPage('login', 'All');
            }
        }

        function handleLogin(event) {
            event.preventDefault();
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;

            // Simple login validation
            if (email && password) {
                isLoggedIn = true;
                currentUser = { name: email.split('@')[0], email: email };
                localStorage.setItem('isLoggedIn', JSON.stringify(isLoggedIn));
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                updateLoginStatus();
                showCategoryPage('home', 'All');
                alert('Logged in successfully!');
            } else {
                alert('Please enter valid credentials.');
            }
        }

        function logout() {
            isLoggedIn = false;
            currentUser = null;
            cart = []; // Clear the cart on logout
            localStorage.clear();
            updateLoginStatus();
            updateCartCount();
            showCategoryPage('home', 'All');
            alert('Logged out successfully!');
        }

        function changeQuantity(index, change) {
            cart[index].quantity += change;
            if (cart[index].quantity <= 0) {
                cart.splice(index, 1);
            }
            localStorage.setItem('cart', JSON.stringify(cart));
            updateCartCount();
            updateCartDisplay();
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            localStorage.setItem('cart', JSON.stringify(cart));
            updateCartCount();
            updateCartDisplay();
        }

        function showPage(pageId) {
            // Hide all pages
            const pages = document.querySelectorAll('.page');
            pages.forEach(page => page.classList.remove('active'));

            // Show selected page
            document.getElementById(pageId).classList.add('active');

            // Update active nav link
            const navLinks = document.querySelectorAll('.departments-nav a');
            navLinks.forEach(link => link.classList.remove('active'));
            if (event && event.target) {
                event.target.classList.add('active');
            }
        }

        function showCategoryPage(pageId, category) {
            showPage(pageId);
            if (pageId === 'products') {
                filterProducts(category);
            } else if (pageId === 'cart') {
                updateCartDisplay();
            }
        }

        function filterProducts(category) {
            const productsPage = document.getElementById('products');
            const productCards = productsPage.querySelectorAll('.product-card');
            const pageTitle = productsPage.querySelector('.page-title');

            if (category === 'All') {
                pageTitle.textContent = '🛍️ Today\'s Deals';
            } else {
                pageTitle.textContent = `🛍️ Shop ${category}`;
            }

            productCards.forEach(card => {
                const productCategory = card.getAttribute('data-category');
                if (category === 'All' || productCategory === category) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        // Search functionality
        function handleSearch() {
            const searchTerm = document.querySelector('.search-input').value.toLowerCase();
            const selectedCategory = document.querySelector('.search-select').value;
            const productCards = document.querySelectorAll('#products .product-card');

            // Switch to products page
            showCategoryPage('products', selectedCategory);

            productCards.forEach(card => {
                const title = card.querySelector('.product-title').textContent.toLowerCase();
                const description = card.querySelector('.product-description').textContent.toLowerCase();
                const category = card.getAttribute('data-category');

                const matchesSearch = title.includes(searchTerm) || description.includes(searchTerm);
                const matchesCategory = selectedCategory === 'All' || category.toLowerCase() === selectedCategory.toLowerCase();

                if (matchesSearch && matchesCategory) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        // Initialize
        document.addEventListener('DOMContentLoaded', function() {
            updateCartCount();
            updateLoginStatus();

            // Add event listeners to Add to Cart buttons
            const addToCartButtons = document.querySelectorAll('.btn');
            addToCartButtons.forEach(button => {
                if (button.textContent.trim() === 'Add to Cart') {
                    button.addEventListener('click', function() {
                        const card = this.closest('.product-card');
                        const title = card.querySelector('.product-title').textContent;
                        const price = card.querySelector('.product-price').textContent;
                        const image = card.querySelector('.product-image').textContent;
                        addToCart(title, price, image);
                    });
                }
            });

            // Add login form handler
            const loginForm = document.querySelector('.login-form');
            if (loginForm) {
                loginForm.addEventListener('submit', handleLogin);
            }

            // Add search functionality
            const searchBtn = document.querySelector('.search-btn');
            const searchInput = document.querySelector('.search-input');
            const searchSelect = document.querySelector('.search-select');

            searchBtn.addEventListener('click', handleSearch);
            searchInput.addEventListener('input', handleSearch);
            searchSelect.addEventListener('change', handleSearch);
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'985a02ea90ddba20',t:'MTc1ODk2NTczMS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
