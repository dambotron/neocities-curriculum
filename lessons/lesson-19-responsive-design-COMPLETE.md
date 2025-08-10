# Lesson 19: Responsive Web Design - One Site for All Devices
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Understand the mobile-first design philosophy
- Set up proper viewport meta tags
- Create fluid layouts with relative units
- Master media queries for different screen sizes
- Build responsive images and videos
- Implement responsive typography
- Design touch-friendly interfaces
- Test responsiveness effectively
- Use CSS Grid and Flexbox for responsive layouts
- Handle responsive navigation patterns

### Materials Needed
- Multiple devices or browser DevTools
- Responsive design testing tools
- Viewport size reference chart
- Common breakpoint guidelines
- Mobile-first design examples
- Touch target size guidelines
- Performance testing tools
- Real phones/tablets if available

### Key Vocabulary with Definitions
- **Responsive Design**: Adapts to any screen size
- **Viewport**: Visible area of webpage
- **Media Query**: CSS rules for specific conditions
- **Breakpoint**: Screen size where layout changes
- **Mobile-First**: Design for mobile, enhance for desktop
- **Fluid Layout**: Uses relative units (%, em, rem)
- **Fixed Layout**: Uses absolute units (px)
- **Retina Display**: High pixel density screens
- **Touch Target**: Clickable area for fingers

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding Responsive Design (5 minutes)

**Teacher Script:**
"Imagine you're designing a shirt that needs to fit a baby, a teenager, and a basketball player - all with the same piece of fabric! That's responsive design. One website that stretches, shrinks, and rearranges itself to look perfect on any device - from a tiny phone to a giant TV!"

**[CREATE new file: responsive-demo.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!-- CRITICAL: Viewport meta tag for mobile -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Design Mastery</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        /* Mobile-First Base Styles */
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
            line-height: 1.6;
            color: #333;
            background: #f4f4f4;
        }
        
        /* Fluid Typography */
        h1 {
            font-size: clamp(1.5rem, 5vw, 3rem);
            /* Min size, preferred size, max size */
        }
        
        p {
            font-size: clamp(1rem, 2vw, 1.25rem);
        }
        
        /* Container with max-width */
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Responsive Design Demo</h1>
        <p>This content adapts to your screen size!</p>
        
        <!-- Mobile-First Content -->
        <div class="hero">
            <h2>Mobile-First Approach</h2>
            <p>We design for mobile, then enhance for larger screens.</p>
        </div>
        
        <!-- Responsive Grid -->
        <div class="grid">
            <div class="card">Card 1</div>
            <div class="card">Card 2</div>
            <div class="card">Card 3</div>
            <div class="card">Card 4</div>
        </div>
        
        <!-- Responsive Image -->
        <figure class="image-container">
            <img src="https://via.placeholder.com/800x400" 
                 alt="Responsive image">
            <figcaption>Images scale with container</figcaption>
        </figure>
    </div>
</body>
</html>
```

**[EXPLAIN viewport and units]**

```css
/* RESPONSIVE UNITS EXPLAINED */

/* 1. VIEWPORT UNITS - Based on browser window */
.viewport-units {
    width: 100vw;  /* 100% of viewport width */
    height: 100vh; /* 100% of viewport height */
    padding: 5vmin; /* 5% of smaller dimension */
    margin: 5vmax;  /* 5% of larger dimension */
}

/* 2. RELATIVE UNITS - Based on other elements */
.relative-units {
    font-size: 1rem;    /* Relative to root (html) font-size */
    padding: 1em;       /* Relative to element's font-size */
    width: 50%;         /* Relative to parent width */
    max-width: 100%;    /* Never exceed parent */
}

/* 3. FLEXIBLE IMAGES - Scale properly */
img {
    max-width: 100%;    /* Never exceed container */
    height: auto;       /* Maintain aspect ratio */
    display: block;     /* Remove bottom gap */
}

/* 4. RESPONSIVE TYPOGRAPHY */
html {
    font-size: 16px; /* Base size */
}

/* Fluid typography with clamp() */
.fluid-text {
    /* clamp(minimum, preferred, maximum) */
    font-size: clamp(1rem, 2.5vw, 2rem);
    /* Starts at 1rem, grows with viewport, caps at 2rem */
}

/* Old way (still works) */
.old-fluid {
    font-size: calc(1rem + 1vw);
    /* Combines fixed and fluid */
}
```

### Media Queries Deep Dive (5 minutes)

**[DEMONSTRATE different media queries]**

```css
/* MEDIA QUERIES - The responsive magic! */

/* Mobile First Approach (Recommended) */
/* Start with mobile styles, add complexity */

/* Base styles (Mobile) */
.grid {
    display: grid;
    grid-template-columns: 1fr; /* Single column */
    gap: 1rem;
}

/* Tablet styles (768px and up) */
@media (min-width: 768px) {
    .grid {
        grid-template-columns: repeat(2, 1fr); /* 2 columns */
    }
    
    .container {
        padding: 2rem;
    }
}

/* Desktop styles (1024px and up) */
@media (min-width: 1024px) {
    .grid {
        grid-template-columns: repeat(3, 1fr); /* 3 columns */
    }
    
    .sidebar {
        display: block; /* Show sidebar on desktop */
    }
}

/* Large desktop (1440px and up) */
@media (min-width: 1440px) {
    .grid {
        grid-template-columns: repeat(4, 1fr); /* 4 columns */
    }
}

/* COMMON BREAKPOINTS */
/* 
   320px  - Small phones
   375px  - iPhone size
   768px  - Tablets
   1024px - Small laptops
   1440px - Desktops
   1920px - Large screens
*/

/* ADVANCED MEDIA QUERIES */

/* Orientation */
@media (orientation: landscape) {
    .hero {
        height: 100vh; /* Full height in landscape */
    }
}

@media (orientation: portrait) {
    .hero {
        height: 50vh; /* Half height in portrait */
    }
}

/* High resolution screens */
@media (-webkit-min-device-pixel-ratio: 2),
       (min-resolution: 192dpi) {
    /* Retina display styles */
    .logo {
        background-image: url('logo@2x.png');
        background-size: contain;
    }
}

/* Hover capability (desktop vs touch) */
@media (hover: hover) {
    /* Has precise hover (desktop) */
    .button:hover {
        transform: scale(1.1);
    }
}

@media (hover: none) {
    /* Touch device - no hover */
    .button:active {
        transform: scale(0.95);
    }
}

/* Print styles */
@media print {
    .no-print {
        display: none;
    }
    
    body {
        font-size: 12pt;
        color: black;
        background: white;
    }
}

/* Combining queries */
@media (min-width: 768px) and (max-width: 1023px) {
    /* Tablet only styles */
}

/* Dark mode */
@media (prefers-color-scheme: dark) {
    body {
        background: #1a1a1a;
        color: #f0f0f0;
    }
}
```

### Responsive Patterns (5 minutes)

**[SHOW common responsive patterns]**

```css
/* RESPONSIVE NAVIGATION */
.nav {
    /* Mobile: Hamburger menu */
    position: fixed;
    top: 0;
    left: -100%;
    width: 80%;
    height: 100vh;
    background: white;
    transition: left 0.3s;
}

.nav.active {
    left: 0;
}

.hamburger {
    display: block;
    cursor: pointer;
}

@media (min-width: 768px) {
    /* Desktop: Horizontal nav */
    .nav {
        position: static;
        width: auto;
        height: auto;
        display: flex;
    }
    
    .hamburger {
        display: none;
    }
}

/* RESPONSIVE GRID PATTERNS */

/* Auto-fit grid (no media queries!) */
.auto-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1rem;
    /* Automatically adjusts columns based on space */
}

/* Flexbox responsive */
.flex-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
}

.flex-item {
    flex: 1 1 300px; /* Responsive without media queries */
}

/* RESPONSIVE TABLES */
.table-container {
    overflow-x: auto; /* Horizontal scroll on small screens */
}

table {
    min-width: 600px; /* Force horizontal scroll */
}

/* Or convert to cards on mobile */
@media (max-width: 767px) {
    table, thead, tbody, th, td, tr {
        display: block;
    }
    
    thead tr {
        display: none; /* Hide header */
    }
    
    tr {
        margin-bottom: 1rem;
        border: 1px solid #ddd;
    }
    
    td {
        position: relative;
        padding-left: 50%;
    }
    
    td:before {
        content: attr(data-label);
        position: absolute;
        left: 1rem;
        font-weight: bold;
    }
}

/* RESPONSIVE IMAGES */

/* Basic responsive image */
img {
    max-width: 100%;
    height: auto;
}

/* Art direction with picture element */
/* HTML:
<picture>
    <source media="(min-width: 768px)" srcset="desktop.jpg">
    <source media="(min-width: 480px)" srcset="tablet.jpg">
    <img src="mobile.jpg" alt="Responsive image">
</picture>
*/

/* Background images */
.hero {
    background-image: url('mobile-hero.jpg');
    background-size: cover;
    background-position: center;
}

@media (min-width: 768px) {
    .hero {
        background-image: url('desktop-hero.jpg');
    }
}
```

---

## PART 2: WE DO (Guided Practice) - 15 minutes

### Activity 1: Build a Responsive Card Layout (7 minutes)

**Teacher Instructions:**
1. Start with mobile layout
2. Add tablet breakpoint
3. Add desktop breakpoint
4. Test with DevTools

**[BUILD TOGETHER]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Cards</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: system-ui, -apple-system, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 1rem;
        }
        
        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        h1 {
            color: white;
            text-align: center;
            margin-bottom: 2rem;
            font-size: clamp(1.5rem, 5vw, 3rem);
        }
        
        /* Mobile First: Single column */
        .card-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1rem;
        }
        
        .card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-5px);
        }
        
        .card-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }
        
        .card-content {
            padding: 1.5rem;
        }
        
        .card-title {
            font-size: clamp(1.25rem, 3vw, 1.5rem);
            margin-bottom: 0.5rem;
            color: #333;
        }
        
        .card-text {
            color: #666;
            line-height: 1.6;
            margin-bottom: 1rem;
        }
        
        .card-button {
            display: inline-block;
            padding: 0.75rem 1.5rem;
            background: #667eea;
            color: white;
            text-decoration: none;
            border-radius: 6px;
            transition: background 0.3s;
            
            /* Touch-friendly size */
            min-height: 44px; /* iOS guideline */
            min-width: 44px;
        }
        
        .card-button:hover {
            background: #764ba2;
        }
        
        /* Tablet: 2 columns */
        @media (min-width: 768px) {
            .card-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 1.5rem;
            }
            
            .container {
                padding: 2rem;
            }
            
            .card-image {
                height: 250px;
            }
        }
        
        /* Desktop: 3 columns */
        @media (min-width: 1024px) {
            .card-grid {
                grid-template-columns: repeat(3, 1fr);
                gap: 2rem;
            }
            
            .card-image {
                height: 200px;
            }
        }
        
        /* Large screens: 4 columns */
        @media (min-width: 1440px) {
            .card-grid {
                grid-template-columns: repeat(4, 1fr);
            }
        }
        
        /* Accessibility: Reduced motion */
        @media (prefers-reduced-motion: reduce) {
            .card {
                transition: none;
            }
        }
        
        /* Dark mode support */
        @media (prefers-color-scheme: dark) {
            body {
                background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            }
            
            .card {
                background: #2c2c2c;
                color: #f0f0f0;
            }
            
            .card-title {
                color: #f0f0f0;
            }
            
            .card-text {
                color: #ccc;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Responsive Card Layout</h1>
        <div class="card-grid">
            <!-- Card 1 -->
            <article class="card">
                <img src="https://via.placeholder.com/400x250" 
                     alt="Card image" 
                     class="card-image">
                <div class="card-content">
                    <h2 class="card-title">Card Title One</h2>
                    <p class="card-text">
                        This card adapts beautifully to any screen size.
                        Notice how the layout changes as you resize!
                    </p>
                    <a href="#" class="card-button">Learn More</a>
                </div>
            </article>
            
            <!-- Repeat for more cards -->
            <!-- Students add 3 more cards -->
        </div>
    </div>
</body>
</html>
```

### Activity 2: Responsive Navigation Menu (8 minutes)

**Teacher Instructions:**
1. Create hamburger for mobile
2. Horizontal nav for desktop
3. Add smooth transitions
4. Make it accessible

**[CREATE TOGETHER]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Navigation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: system-ui, -apple-system, sans-serif;
        }
        
        /* Header */
        .header {
            background: #2c3e50;
            color: white;
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
        }
        
        /* Mobile First: Hidden menu */
        .nav-menu {
            position: fixed;
            left: -100%;
            top: 60px;
            width: 100%;
            height: calc(100vh - 60px);
            background: #34495e;
            transition: left 0.3s ease;
            display: flex;
            flex-direction: column;
            padding: 2rem;
        }
        
        .nav-menu.active {
            left: 0;
        }
        
        .nav-link {
            color: white;
            text-decoration: none;
            padding: 1rem;
            font-size: 1.1rem;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            transition: background 0.3s;
        }
        
        .nav-link:hover {
            background: rgba(255,255,255,0.1);
        }
        
        /* Hamburger Menu */
        .hamburger {
            display: flex;
            flex-direction: column;
            cursor: pointer;
            background: none;
            border: none;
            padding: 0;
        }
        
        .hamburger span {
            width: 25px;
            height: 3px;
            background: white;
            margin: 3px 0;
            transition: 0.3s;
        }
        
        /* Hamburger animation */
        .hamburger.active span:nth-child(1) {
            transform: rotate(-45deg) translate(-5px, 6px);
        }
        
        .hamburger.active span:nth-child(2) {
            opacity: 0;
        }
        
        .hamburger.active span:nth-child(3) {
            transform: rotate(45deg) translate(-5px, -6px);
        }
        
        /* Tablet and up */
        @media (min-width: 768px) {
            .nav-menu {
                position: static;
                width: auto;
                height: auto;
                background: transparent;
                flex-direction: row;
                padding: 0;
                left: 0;
            }
            
            .nav-link {
                border: none;
                padding: 0.5rem 1rem;
                margin: 0 0.5rem;
                border-radius: 4px;
            }
            
            .hamburger {
                display: none;
            }
        }
        
        /* Content */
        .content {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }
        
        h1 {
            font-size: clamp(1.5rem, 5vw, 3rem);
            margin-bottom: 1rem;
        }
        
        p {
            line-height: 1.6;
            margin-bottom: 1rem;
        }
    </style>
</head>
<body>
    <header class="header">
        <nav class="nav-container">
            <div class="logo">ResponsiveNav</div>
            
            <button class="hamburger" id="hamburger" aria-label="Menu">
                <span></span>
                <span></span>
                <span></span>
            </button>
            
            <div class="nav-menu" id="navMenu">
                <a href="#" class="nav-link">Home</a>
                <a href="#" class="nav-link">About</a>
                <a href="#" class="nav-link">Services</a>
                <a href="#" class="nav-link">Portfolio</a>
                <a href="#" class="nav-link">Contact</a>
            </div>
        </nav>
    </header>
    
    <main class="content">
        <h1>Responsive Design</h1>
        <p>Resize your browser to see the navigation transform!</p>
        <p>On mobile, click the hamburger menu to reveal navigation.</p>
    </main>
    
    <script>
        const hamburger = document.getElementById('hamburger');
        const navMenu = document.getElementById('navMenu');
        
        hamburger.addEventListener('click', () => {
            hamburger.classList.toggle('active');
            navMenu.classList.toggle('active');
        });
        
        // Close menu when clicking a link
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', () => {
                hamburger.classList.remove('active');
                navMenu.classList.remove('active');
            });
        });
    </script>
</body>
</html>
```

---

## PART 3: YOU DO (Independent Practice) - 15 minutes

### Individual Challenge: Complete Responsive Website (15 minutes)

**Student Instructions:**
"Create a fully responsive landing page with hero, features, testimonials, and footer. Must work perfectly from 320px to 1920px!"

**Requirements Checklist:**
```
□ Mobile-first approach
□ At least 3 breakpoints
□ Responsive navigation
□ Fluid typography (clamp or calc)
□ Responsive images
□ Touch-friendly buttons (44px minimum)
□ Grid or flexbox layout
□ No horizontal scroll at any size
□ Readable at all sizes
□ Proper viewport meta tag
□ Hover states for desktop only
□ Print styles (bonus)
□ Dark mode support (bonus)
□ Reduced motion support (bonus)
```

**Starter Template:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!-- TODO: Add viewport meta tag -->
    <title>Responsive Challenge</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        /* TODO: Mobile-first styles */
        
        /* Hero Section */
        .hero {
            /* Make it responsive */
        }
        
        /* Features Grid */
        .features {
            /* Single column on mobile */
            /* 2 columns on tablet */
            /* 3 columns on desktop */
        }
        
        /* Testimonials */
        .testimonials {
            /* Responsive cards */
        }
        
        /* TODO: Media queries */
        
        /* Tablet */
        @media (min-width: 768px) {
            
        }
        
        /* Desktop */
        @media (min-width: 1024px) {
            
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <header>
        <nav>
            <!-- TODO: Responsive nav -->
        </nav>
    </header>
    
    <!-- Hero -->
    <section class="hero">
        <h1>Welcome to Our Site</h1>
        <p>Make this fully responsive!</p>
        <button>Get Started</button>
    </section>
    
    <!-- Features -->
    <section class="features">
        <h2>Our Features</h2>
        <div class="feature-grid">
            <!-- Add feature cards -->
        </div>
    </section>
    
    <!-- Testimonials -->
    <section class="testimonials">
        <h2>What People Say</h2>
        <div class="testimonial-grid">
            <!-- Add testimonials -->
        </div>
    </section>
    
    <!-- Footer -->
    <footer>
        <!-- TODO: Responsive footer -->
    </footer>
</body>
</html>
```

**Full Solution (for teacher reference):**
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Base styles (Mobile first) */
body {
    font-family: system-ui, -apple-system, sans-serif;
    line-height: 1.6;
    color: #333;
}

/* Typography */
h1 {
    font-size: clamp(1.75rem, 5vw, 3.5rem);
    line-height: 1.2;
}

h2 {
    font-size: clamp(1.5rem, 4vw, 2.5rem);
    margin-bottom: 1rem;
}

p {
    font-size: clamp(1rem, 2vw, 1.125rem);
}

/* Container */
.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 1rem;
}

/* Navigation - Mobile */
.header {
    background: #fff;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    position: sticky;
    top: 0;
    z-index: 1000;
}

.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
}

.logo {
    font-size: 1.5rem;
    font-weight: bold;
    color: #667eea;
}

.nav-menu {
    display: none;
    position: fixed;
    top: 60px;
    left: 0;
    right: 0;
    background: white;
    flex-direction: column;
    padding: 1rem;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.nav-menu.active {
    display: flex;
}

.nav-link {
    padding: 0.75rem;
    text-decoration: none;
    color: #333;
    border-bottom: 1px solid #eee;
}

.hamburger {
    display: block;
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
}

.hamburger span {
    display: block;
    width: 25px;
    height: 3px;
    background: #333;
    margin: 5px 0;
    transition: 0.3s;
}

/* Hero - Mobile */
.hero {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 3rem 1rem;
    text-align: center;
    min-height: 50vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.hero p {
    margin: 1rem 0 2rem;
    opacity: 0.9;
}

.btn {
    display: inline-block;
    padding: 1rem 2rem;
    background: white;
    color: #667eea;
    text-decoration: none;
    border-radius: 50px;
    font-weight: bold;
    min-height: 44px;
    transition: transform 0.3s;
}

/* Features - Mobile */
.features {
    padding: 3rem 1rem;
    background: #f8f9fa;
}

.features h2 {
    text-align: center;
    color: #333;
}

.feature-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.5rem;
    margin-top: 2rem;
}

.feature-card {
    background: white;
    padding: 1.5rem;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    text-align: center;
}

.feature-icon {
    font-size: 3rem;
    margin-bottom: 1rem;
}

/* Testimonials - Mobile */
.testimonials {
    padding: 3rem 1rem;
}

.testimonials h2 {
    text-align: center;
}

.testimonial-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.5rem;
    margin-top: 2rem;
}

.testimonial-card {
    background: white;
    padding: 1.5rem;
    border-radius: 10px;
    border-left: 4px solid #667eea;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.testimonial-text {
    font-style: italic;
    margin-bottom: 1rem;
}

.testimonial-author {
    font-weight: bold;
    color: #667eea;
}

/* Footer - Mobile */
.footer {
    background: #2c3e50;
    color: white;
    padding: 2rem 1rem;
    text-align: center;
}

.footer-content {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}

.footer-section h3 {
    margin-bottom: 0.5rem;
}

.footer-links {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

.footer-links a {
    color: #ecf0f1;
    text-decoration: none;
}

/* Tablet Styles */
@media (min-width: 768px) {
    .container {
        padding: 2rem;
    }
    
    .nav-menu {
        display: flex;
        position: static;
        flex-direction: row;
        padding: 0;
        box-shadow: none;
        gap: 1rem;
    }
    
    .nav-link {
        border: none;
        padding: 0.5rem 1rem;
        border-radius: 5px;
        transition: background 0.3s;
    }
    
    .nav-link:hover {
        background: #f0f0f0;
    }
    
    .hamburger {
        display: none;
    }
    
    .hero {
        min-height: 60vh;
        padding: 4rem 2rem;
    }
    
    .feature-grid {
        grid-template-columns: repeat(2, 1fr);
        gap: 2rem;
    }
    
    .testimonial-grid {
        grid-template-columns: repeat(2, 1fr);
    }
    
    .footer-content {
        flex-direction: row;
        justify-content: space-around;
        text-align: left;
    }
    
    .footer-links {
        flex-direction: row;
        gap: 1rem;
    }
}

/* Desktop Styles */
@media (min-width: 1024px) {
    .hero {
        min-height: 70vh;
        padding: 5rem 2rem;
    }
    
    .feature-grid {
        grid-template-columns: repeat(3, 1fr);
    }
    
    .testimonial-grid {
        grid-template-columns: repeat(3, 1fr);
    }
    
    .btn:hover {
        transform: scale(1.05);
    }
    
    .feature-card {
        transition: transform 0.3s;
    }
    
    .feature-card:hover {
        transform: translateY(-5px);
    }
}

/* Large Desktop */
@media (min-width: 1440px) {
    .feature-grid {
        grid-template-columns: repeat(4, 1fr);
    }
}

/* Print Styles */
@media print {
    .header, .footer, .hamburger {
        display: none;
    }
    
    body {
        font-size: 12pt;
        line-height: 1.5;
        color: black;
    }
    
    .hero {
        background: none;
        color: black;
    }
}

/* Dark Mode */
@media (prefers-color-scheme: dark) {
    body {
        background: #1a1a1a;
        color: #f0f0f0;
    }
    
    .header {
        background: #2c2c2c;
    }
    
    .feature-card,
    .testimonial-card {
        background: #2c2c2c;
        color: #f0f0f0;
    }
}

/* Reduced Motion */
@media (prefers-reduced-motion: reduce) {
    * {
        animation: none !important;
        transition: none !important;
    }
}
```

---

## Assessment and Wrap-Up (5 minutes)

### Quick Responsive Quiz
**Teacher asks:**

1. "What's the viewport meta tag?"
   → `<meta name="viewport" content="width=device-width, initial-scale=1.0">`

2. "Mobile-first means?"
   → Start with mobile styles, enhance for larger screens

3. "Common breakpoints?"
   → 768px (tablet), 1024px (desktop)

4. "How to make images responsive?"
   → `max-width: 100%; height: auto;`

### Device Testing
"Open DevTools, show me your site at iPhone, iPad, and desktop sizes!"

---

## Common Student Mistakes & Solutions

### Mistake 1: Forgetting viewport meta
**Problem:** Site looks tiny on mobile
**Fix:** Add viewport meta tag
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Mistake 2: Desktop-first approach
**Problem:** Too much overriding in media queries
**Fix:** Start mobile, add complexity
```css
/* Mobile first */
.element { /* Simple mobile styles */ }
@media (min-width: 768px) { /* Add complexity */ }
```

### Mistake 3: Fixed widths
**Problem:** Horizontal scroll on mobile
**Fix:** Use max-width and relative units
```css
/* Bad */
.container { width: 1200px; }

/* Good */
.container { 
    width: 90%;
    max-width: 1200px;
}
```

### Mistake 4: Small touch targets
**Problem:** Hard to tap on mobile
**Fix:** Minimum 44px for touch
```css
.button {
    min-height: 44px;
    min-width: 44px;
    padding: 12px 24px;
}
```

### Mistake 5: Not testing actual devices
**Problem:** Looks good in DevTools, broken on phone
**Fix:** Test on real devices or use online tools

---

## Homework Assignment

### Build a Responsive Portfolio Site
Create your personal portfolio that includes:

1. **Responsive navigation** with hamburger menu
2. **Hero section** with background image
3. **About section** with responsive text
4. **Project grid** that adapts to screen size
5. **Contact form** that's touch-friendly
6. **Footer** with social links

### Requirements:
- Works from 320px to 1920px
- At least 4 breakpoints
- Uses modern CSS (Grid, Flexbox, clamp)
- Passes Google Mobile-Friendly Test
- No horizontal scroll at any size
- All images optimized and responsive

### Bonus Features:
- Dark mode support
- Animated hamburger menu
- Smooth scroll behavior
- Loading performance optimization

---

## Resources
- [Google Mobile-Friendly Test](https://search.google.com/test/mobile-friendly)
- [Responsive Web Design Checker](https://responsivedesignchecker.com)
- [Can I Use](https://caniuse.com) - Browser support
- Chrome DevTools Device Mode
- [A Complete Guide to CSS Media Queries](https://css-tricks.com/a-complete-guide-to-css-media-queries/)

---

## Next Lesson Preview
"Next time, we'll dive into CSS Grid - the two-dimensional layout system that makes complex layouts simple!"
