HTML
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Auto-Responsive Image Gallery</title>
    <meta name="description" content="An auto-responsive image gallery built using CSS Grid and auto-fit minmax.">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header class="site-header">
        <h1>Developer Gallery & Projects</h1>
        <p>An auto-responsive image gallery that dynamically adjusts columns based on viewport width.</p>
    </header>

    <main class="main-container">
        <section class="gallery-grid">
            <!-- Gallery Item 1 -->
            <div class="gallery-item">
                <img src="images/gallery-1.jpg" alt="Modern Workspace Setup" class="gallery-image">
                <div class="gallery-overlay">
                    <h3>Workspace Setup</h3>
                </div>
            </div>

            <!-- Gallery Item 2 -->
            <div class="gallery-item">
                <img src="images/gallery-2.jpg" alt="Coding on Dual Monitors" class="gallery-image">
                <div class="gallery-overlay">
                    <h3>Dual Monitor Dev</h3>
                </div>
            </div>

            <!-- Gallery Item 3 -->
            <div class="gallery-item">
                <img src="images/gallery-3.jpg" alt="Mechanical Keyboard Close-up" class="gallery-image">
                <div class="gallery-overlay">
                    <h3>Mechanical Keyboard</h3>
                </div>
            </div>

            <!-- Gallery Item 4 -->
            <div class="gallery-item">
                <img src="images/gallery-4.jpg" alt="Code on Screen" class="gallery-image">
                <div class="gallery-overlay">
                    <h3>Clean Code</h3>
                </div>
            </div>

            <!-- Gallery Item 5 -->
            <div class="gallery-item">
                <img src="images/gallery-5.jpg" alt="Hackathon Collaboration" class="gallery-image">
                <div class="gallery-overlay">
                    <h3>Hackathon Team</h3>
                </div>
            </div>

            <!-- Gallery Item 6 -->
            <div class="gallery-item">
                <img src="images/gallery-6.jpg" alt="Minimalist Desk Setup" class="gallery-image">
                <div class="gallery-overlay">
                    <h3>Minimal Desk</h3>
                </div>
            </div>

            <!-- Gallery Item 7 -->
            <div class="gallery-item">
                <img src="images/gallery-7.jpg" alt="Server Rack & Networking" class="gallery-image">
                <div class="gallery-overlay">
                    <h3>Server Infrastructure</h3>
                </div>
            </div>

            <!-- Gallery Item 8 -->
            <div class="gallery-item">
                <img src="images/gallery-8.jpg" alt="Coffee and Code" class="gallery-image">
                <div class="gallery-overlay">
                    <h3>Coffee & Code</h3>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 Atim Akhtar. All rights reserved.</p>
    </footer>
</body>
</html>
CSS
/* style.css */
:root {
    --primary-color: #0284c7;
    --secondary-color: #0f172a;
    --bg-color: #f8fafc;
    --surface-color: #ffffff;
    --text-color: #334155;
    --text-muted: #64748b;
    --border-color: #e2e8f0;
    
    --space-md: 16px;
    --space-xl: 32px;
    
    --radius-lg: 12px;
    --shadow-sm: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    --shadow-md: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-color);
    line-height: 1.6;
}

.site-header {
    background-color: var(--secondary-color);
    color: var(--surface-color);
    text-align: center;
    padding: 3rem var(--space-xl);
}

.site-header h1 {
    font-size: 2rem;
    margin-bottom: 0.5rem;
}

.site-header p {
    color: #94a3b8;
    font-size: 1.1rem;
}

.main-container {
    max-width: 1300px;
    margin: 3rem auto;
    padding: 0 var(--space-xl);
}

/* Auto-Responsive CSS Grid Gallery */
.gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: var(--space-xl);
}

.gallery-item {
    position: relative;
    background-color: var(--surface-color);
    border: 1px solid var(--border-color);
    border-radius: var(--radius-lg);
    overflow: hidden;
    box-shadow: var(--shadow-sm);
    height: 240px;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.gallery-item:hover {
    transform: translateY(-5px);
    box-shadow: var(--shadow-md);
}

.gallery-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition: transform 0.3s ease;
}

.gallery-item:hover .gallery-image {
    transform: scale(1.05);
}

.gallery-overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: linear-gradient(to top, rgba(15, 23, 42, 0.85), transparent);
    color: var(--surface-color);
    padding: 1.25rem var(--space-md) var(--space-md) var(--space-md);
    opacity: 0;
    transition: opacity 0.3s ease;
    display: flex;
    align-items: flex-end;
}

.gallery-item:hover .gallery-overlay {
    opacity: 1;
}

.gallery-overlay h3 {
    font-size: 1.1rem;
    font-weight: 600;
}

footer {
    text-align: center;
    padding: 2rem;
    color: var(--text-muted);
    font-size: 0.875rem;
    border-top: 1px solid var(--border-color);
    margin-top: 4rem;
    background-color: var(--surface-color);
}