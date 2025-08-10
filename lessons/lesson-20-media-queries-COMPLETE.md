# Lesson 20: Media Queries Mastery - Advanced Responsive Techniques
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Master all media query syntax and operators
- Use advanced media features (hover, pointer, any-hover, any-pointer)
- Implement container queries for component-based design
- Create print stylesheets
- Handle device orientation changes
- Support user preferences (dark mode, reduced motion, high contrast)
- Combine multiple media queries effectively
- Debug media queries with DevTools
- Write efficient, maintainable media query code
- Understand media query best practices and anti-patterns

### Materials Needed
- Browser with latest CSS support
- DevTools with media query inspector
- Multiple devices for testing
- Print preview capability
- Accessibility testing tools
- Media query reference sheet
- Component examples
- Performance testing tools

### Key Vocabulary with Definitions
- **Media Query**: Conditional CSS rules
- **Media Type**: Screen, print, speech, all
- **Media Feature**: Testable characteristic (width, hover)
- **Breakpoint**: Point where layout changes
- **Container Query**: Query based on container size
- **Logical Operators**: and, or, not, only
- **Range Syntax**: New comparison operators
- **User Preference**: System settings queries
- **Feature Query**: Test for CSS support

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Media Query Fundamentals Review & Advanced Syntax (5 minutes)

**Teacher Script:**
"Think of media queries as smart filters for your CSS. Like a bouncer at a club checking IDs - 'Are you wide enough? Can you hover? Do you prefer dark mode?' Only the CSS that passes the test gets applied!"

**[CREATE new file: media-queries-advanced.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Advanced Media Queries</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: system-ui, -apple-system, sans-serif;
            padding: 2rem;
            transition: all 0.3s ease;
        }
        
        .demo-container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .info-panel {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 2rem;
            border-radius: 10px;
            margin-bottom: 2rem;
        }
        
        .info-panel h1 {
            margin-bottom: 1rem;
        }
        
        .current-state {
            font-family: monospace;
            background: rgba(0,0,0,0.2);
            padding: 1rem;
            border-radius: 5px;
            margin-top: 1rem;
        }
    </style>
</head>
<body>
    <div class="demo-container">
        <div class="info-panel">
            <h1>Advanced Media Queries Demo</h1>
            <p>This page adapts to your device capabilities and preferences!</p>
            <div class="current-state" id="state">
                <!-- JavaScript will update this -->
            </div>
        </div>
        
        <div class="feature-grid">
            <div class="feature-card">
                <h2>Responsive</h2>
                <p>Adapts to screen size</p>
            </div>
            <div class="feature-card">
                <h2>Adaptive</h2>
                <p>Detects device capabilities</p>
            </div>
            <div class="feature-card">
                <h2>Accessible</h2>
                <p>Respects user preferences</p>
            </div>
        </div>
    </div>
</body>
</html>
```

**[EXPLAIN all media query syntaxes]**

```css
/* MEDIA QUERY SYNTAX EVOLUTION */

/* 1. CLASSIC SYNTAX (Still works!) */
@media screen and (min-width: 768px) {
    /* Tablet and up */
}

@media (max-width: 767px) {
    /* Mobile only */
}

/* 2. MODERN RANGE SYNTAX (Level 4) */
@media (width >= 768px) {
    /* Same as min-width: 768px but clearer! */
}

@media (768px <= width <= 1024px) {
    /* Between tablet and desktop */
    /* Much cleaner than: */
    /* @media (min-width: 768px) and (max-width: 1024px) */
}

@media (width < 768px) {
    /* Mobile only */
}

/* 3. LOGICAL OPERATORS */

/* AND - All conditions must be true */
@media (min-width: 768px) and (orientation: landscape) {
    /* Tablet or larger IN landscape */
}

/* OR (comma-separated) */
@media (max-width: 768px), (orientation: portrait) {
    /* Mobile OR portrait orientation */
}

/* NOT - Inverts the query */
@media not print {
    /* Everything except print */
}

/* ONLY - Hides from old browsers */
@media only screen and (min-width: 768px) {
    /* Modern browsers only */
}

/* 4. MEDIA TYPES */
@media screen { /* Screens (default) */ }
@media print { /* When printing */ }
@media speech { /* Screen readers */ }
@media all { /* Everything */ }

/* 5. ADVANCED MEDIA FEATURES */

/* Aspect Ratio */
@media (aspect-ratio: 16/9) {
    /* Exactly 16:9 */
}

@media (min-aspect-ratio: 16/9) {
    /* Wider than 16:9 */
}

/* Resolution (Retina displays) */
@media (min-resolution: 2dppx) {
    /* High DPI screens */
}

@media (-webkit-min-device-pixel-ratio: 2) {
    /* Older Safari syntax */
}

/* Color capabilities */
@media (color) {
    /* Has color screen */
}

@media (monochrome) {
    /* Black and white only */
}

@media (color-gamut: p3) {
    /* Wide color gamut support */
}
```

### Advanced Interaction Media Queries (5 minutes)

**[DEMONSTRATE interaction detection]**

```css
/* INTERACTION MEDIA QUERIES - Detect input methods */

/* 1. HOVER CAPABILITY */
@media (hover: hover) {
    /* Can hover precisely (mouse/trackpad) */
    .button:hover {
        transform: scale(1.1);
        background: linear-gradient(45deg, #667eea, #764ba2);
    }
    
    .card:hover {
        box-shadow: 0 10px 30px rgba(0,0,0,0.2);
    }
}

@media (hover: none) {
    /* Cannot hover (touchscreen) */
    .button:active {
        transform: scale(0.95);
    }
    
    /* Make touch targets bigger */
    .button {
        min-height: 44px;
        min-width: 44px;
    }
}

/* 2. ANY-HOVER - Any input device can hover */
@media (any-hover: hover) {
    /* At least one input can hover */
    /* Laptop with touchscreen - mouse can hover */
}

@media (any-hover: none) {
    /* No input devices can hover */
    /* Phone/tablet only */
}

/* 3. POINTER PRECISION */
@media (pointer: coarse) {
    /* Imprecise pointer (finger) */
    .small-button {
        padding: 12px 24px; /* Bigger touch target */
        font-size: 16px;
    }
    
    .checkbox {
        width: 24px;
        height: 24px;
    }
}

@media (pointer: fine) {
    /* Precise pointer (mouse) */
    .small-button {
        padding: 6px 12px; /* Can be smaller */
        font-size: 14px;
    }
    
    .checkbox {
        width: 16px;
        height: 16px;
    }
}

@media (pointer: none) {
    /* No pointer (keyboard only) */
    :focus {
        outline: 3px solid #667eea;
        outline-offset: 2px;
    }
}

/* 4. ANY-POINTER - Any available pointer */
@media (any-pointer: coarse) {
    /* Has touchscreen available */
}

@media (any-pointer: fine) {
    /* Has mouse available */
}

/* 5. COMBINING FOR DEVICE DETECTION */

/* Desktop with mouse */
@media (hover: hover) and (pointer: fine) {
    .desktop-only {
        display: block;
    }
}

/* Mobile/Tablet */
@media (hover: none) and (pointer: coarse) {
    .mobile-only {
        display: block;
    }
}

/* Laptop with touchscreen */
@media (hover: hover) and (any-pointer: coarse) {
    .hybrid-device {
        display: block;
    }
}
```

### User Preference Queries (5 minutes)

**[SHOW preference-based adaptations]**

```css
/* USER PREFERENCE MEDIA QUERIES */

/* 1. COLOR SCHEME PREFERENCE */
@media (prefers-color-scheme: dark) {
    :root {
        --bg-color: #1a1a1a;
        --text-color: #f0f0f0;
        --card-bg: #2c2c2c;
        --border-color: #404040;
    }
    
    body {
        background: var(--bg-color);
        color: var(--text-color);
    }
    
    .card {
        background: var(--card-bg);
        border: 1px solid var(--border-color);
    }
    
    img {
        opacity: 0.8; /* Dim images in dark mode */
    }
    
    /* Invert certain graphics */
    .icon {
        filter: invert(1);
    }
}

@media (prefers-color-scheme: light) {
    :root {
        --bg-color: #ffffff;
        --text-color: #333333;
        --card-bg: #f8f9fa;
        --border-color: #dee2e6;
    }
}

/* System that supports both */
@media (prefers-color-scheme: no-preference) {
    /* User hasn't set preference */
}

/* 2. REDUCED MOTION */
@media (prefers-reduced-motion: reduce) {
    /* User prefers less animation */
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
        scroll-behavior: auto !important;
    }
    
    .parallax {
        transform: none !important;
    }
    
    .auto-play-video {
        display: none;
    }
}

@media (prefers-reduced-motion: no-preference) {
    /* Animations are OK */
    .hero {
        animation: fadeInUp 1s ease-out;
    }
    
    .card {
        transition: transform 0.3s ease;
    }
    
    html {
        scroll-behavior: smooth;
    }
}

/* 3. HIGH CONTRAST */
@media (prefers-contrast: high) {
    /* User wants high contrast */
    body {
        background: white;
        color: black;
    }
    
    .button {
        border: 2px solid black;
        font-weight: bold;
    }
    
    a {
        color: #0000EE;
        text-decoration: underline;
    }
}

@media (prefers-contrast: low) {
    /* User wants low contrast */
    body {
        background: #f5f5f5;
        color: #666;
    }
}

/* 4. REDUCED TRANSPARENCY */
@media (prefers-reduced-transparency: reduce) {
    /* User prefers opaque backgrounds */
    .glass-effect {
        backdrop-filter: none;
        background: rgba(255, 255, 255, 1);
    }
    
    .modal-overlay {
        background: black;
    }
}

/* 5. FORCED COLORS (Windows High Contrast) */
@media (forced-colors: active) {
    .button {
        border: 1px solid;
    }
}

/* 6. INVERTED COLORS */
@media (inverted-colors: inverted) {
    img, video {
        filter: invert(1);
    }
}

/* 7. SCRIPTING SUPPORT */
@media (scripting: none) {
    /* JavaScript disabled */
    .requires-js {
        display: none;
    }
    
    .no-js-fallback {
        display: block;
    }
}

@media (scripting: enabled) {
    /* JavaScript enabled */
    .js-enhanced {
        display: block;
    }
}
```

---

## PART 2: WE DO (Guided Practice) - 15 minutes

### Activity 1: Build an Adaptive Component System (7 minutes)

**Teacher Instructions:**
1. Create components that adapt to capabilities
2. Implement user preference support
3. Add print styles
4. Test with DevTools

**[BUILD TOGETHER]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adaptive Components</title>
    <style>
        /* CSS Variables for theming */
        :root {
            --primary: #667eea;
            --secondary: #764ba2;
            --bg: #ffffff;
            --text: #333333;
            --card-bg: #f8f9fa;
            --shadow: 0 4px 6px rgba(0,0,0,0.1);
            --transition: 0.3s ease;
        }
        
        /* Dark mode variables */
        @media (prefers-color-scheme: dark) {
            :root {
                --bg: #1a1a1a;
                --text: #f0f0f0;
                --card-bg: #2c2c2c;
                --shadow: 0 4px 6px rgba(0,0,0,0.3);
            }
        }
        
        /* Base styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: system-ui, -apple-system, sans-serif;
            background: var(--bg);
            color: var(--text);
            line-height: 1.6;
            transition: background var(--transition), color var(--transition);
        }
        
        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        /* Header */
        .header {
            text-align: center;
            margin-bottom: 3rem;
        }
        
        h1 {
            font-size: clamp(1.5rem, 5vw, 3rem);
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1rem;
        }
        
        /* Adaptive Button Component */
        .button {
            display: inline-block;
            padding: 0.75rem 1.5rem;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            border: none;
            cursor: pointer;
            transition: transform var(--transition);
        }
        
        /* Mouse hover only */
        @media (hover: hover) and (pointer: fine) {
            .button:hover {
                transform: translateY(-2px) scale(1.05);
                box-shadow: 0 6px 20px rgba(102, 126, 234, 0.4);
            }
        }
        
        /* Touch devices */
        @media (pointer: coarse) {
            .button {
                min-height: 44px;
                min-width: 44px;
                padding: 1rem 2rem;
                font-size: 1.1rem;
            }
            
            .button:active {
                transform: scale(0.95);
            }
        }
        
        /* Reduced motion */
        @media (prefers-reduced-motion: reduce) {
            .button {
                transition: none;
            }
            
            .button:hover {
                transform: none;
            }
        }
        
        /* Card Grid */
        .card-grid {
            display: grid;
            gap: 2rem;
            margin-top: 3rem;
        }
        
        /* Mobile first */
        .card-grid {
            grid-template-columns: 1fr;
        }
        
        /* Tablet */
        @media (width >= 768px) {
            .card-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        /* Desktop */
        @media (width >= 1024px) {
            .card-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }
        
        /* Wide screens */
        @media (width >= 1440px) {
            .card-grid {
                grid-template-columns: repeat(4, 1fr);
            }
        }
        
        /* Card Component */
        .card {
            background: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform var(--transition), box-shadow var(--transition);
        }
        
        .card-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
        }
        
        .card-content {
            padding: 1.5rem;
        }
        
        .card-title {
            font-size: 1.25rem;
            margin-bottom: 0.5rem;
        }
        
        .card-text {
            opacity: 0.8;
            margin-bottom: 1rem;
        }
        
        /* Hover effects for mouse users only */
        @media (hover: hover) {
            .card:hover {
                transform: translateY(-5px);
                box-shadow: 0 8px 16px rgba(0,0,0,0.2);
            }
        }
        
        /* High contrast mode */
        @media (prefers-contrast: high) {
            .card {
                border: 2px solid currentColor;
            }
            
            .button {
                border: 2px solid white;
                font-weight: 900;
            }
        }
        
        /* Print Styles */
        @media print {
            /* Remove unnecessary elements */
            .no-print,
            .button,
            .navigation {
                display: none !important;
            }
            
            /* Reset colors for print */
            * {
                background: white !important;
                color: black !important;
            }
            
            /* Page setup */
            @page {
                margin: 2cm;
                size: A4;
            }
            
            /* Ensure text is readable */
            body {
                font-size: 12pt;
                line-height: 1.5;
            }
            
            h1 {
                font-size: 18pt;
                page-break-after: avoid;
            }
            
            .card {
                page-break-inside: avoid;
                border: 1px solid #ccc;
                margin-bottom: 1cm;
            }
            
            /* Show URLs for links */
            a[href]:after {
                content: " (" attr(href) ")";
            }
            
            /* Remove shadows and effects */
            .card {
                box-shadow: none !important;
                transform: none !important;
            }
        }
        
        /* Orientation Changes */
        @media (orientation: landscape) {
            .hero {
                min-height: 100vh;
                display: flex;
                align-items: center;
                justify-content: center;
            }
        }
        
        @media (orientation: portrait) {
            .hero {
                min-height: 50vh;
                padding: 2rem 1rem;
            }
        }
        
        /* Feature Detection with @supports */
        @supports (backdrop-filter: blur(10px)) {
            .glass-card {
                background: rgba(255, 255, 255, 0.1);
                backdrop-filter: blur(10px);
            }
        }
        
        @supports not (backdrop-filter: blur(10px)) {
            .glass-card {
                background: rgba(255, 255, 255, 0.95);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header class="header">
            <h1>Adaptive Component System</h1>
            <p>Components that adapt to your device and preferences</p>
            <button class="button">Interactive Button</button>
        </header>
        
        <main class="card-grid">
            <article class="card">
                <div class="card-image"></div>
                <div class="card-content">
                    <h2 class="card-title">Adaptive Card</h2>
                    <p class="card-text">This card adapts to hover capability, color scheme, and screen size.</p>
                    <button class="button">Action</button>
                </div>
            </article>
            
            <!-- Add more cards -->
        </main>
    </div>
    
    <script>
        // Display current media query states
        function checkMediaQueries() {
            const checks = {
                'Dark Mode': window.matchMedia('(prefers-color-scheme: dark)').matches,
                'Can Hover': window.matchMedia('(hover: hover)').matches,
                'Touch Device': window.matchMedia('(pointer: coarse)').matches,
                'Reduced Motion': window.matchMedia('(prefers-reduced-motion: reduce)').matches,
                'High Contrast': window.matchMedia('(prefers-contrast: high)').matches,
                'Landscape': window.matchMedia('(orientation: landscape)').matches
            };
            
            console.table(checks);
        }
        
        checkMediaQueries();
        window.addEventListener('resize', checkMediaQueries);
    </script>
</body>
</html>
```

### Activity 2: Container Queries Implementation (8 minutes)

**Teacher Instructions:**
1. Explain container queries vs media queries
2. Build component-based responsive design
3. Show isolation benefits
4. Demonstrate reusability

**[CREATE TOGETHER - Latest CSS feature]**

```css
/* CONTAINER QUERIES - Component-based responsive design */

/* Define container */
.card-container {
    container-type: inline-size;
    container-name: card;
}

/* Alternative shorthand */
.widget-container {
    container: widget / inline-size;
}

/* Query the container, not viewport! */
@container card (min-width: 400px) {
    .card {
        display: flex;
        flex-direction: row;
    }
    
    .card-image {
        width: 40%;
    }
    
    .card-content {
        width: 60%;
    }
}

@container card (min-width: 600px) {
    .card {
        grid-template-columns: 1fr 2fr;
    }
    
    .card-title {
        font-size: 1.5rem;
    }
}

/* Container query units */
.responsive-text {
    /* cqw = container query width */
    font-size: clamp(1rem, 5cqw, 2rem);
    
    /* cqh = container query height */
    padding: 2cqh;
    
    /* cqi = container query inline */
    /* cqb = container query block */
    /* cqmin = smaller of cqi/cqb */
    /* cqmax = larger of cqi/cqb */
}

/* Named containers */
@container widget (min-width: 300px) {
    .widget-content {
        display: grid;
        grid-template-columns: 1fr 1fr;
    }
}

/* Combining with media queries */
@media (min-width: 768px) {
    @container card (min-width: 400px) {
        /* Tablet + large card container */
    }
}

/* Style queries (experimental) */
@container style(--theme: dark) {
    .themed-component {
        background: black;
        color: white;
    }
}
```

---

## PART 3: YOU DO (Independent Practice) - 15 minutes

### Individual Challenge: Multi-Device Experience (15 minutes)

**Student Instructions:**
"Create a webpage that provides optimal experience for every device type and user preference. Use advanced media queries to handle all scenarios!"

**Requirements Checklist:**
```
□ Mobile-first responsive design
□ Dark mode support
□ Reduced motion support
□ High contrast mode support
□ Print stylesheet
□ Hover states for mouse only
□ Touch-friendly for touch devices
□ Landscape vs portrait layouts
□ Container queries for components
□ Feature detection with @supports
□ Proper breakpoints (320px to 1920px)
□ Retina display support
□ Forced colors support
□ Orientation change handling
□ JavaScript fallback for no-JS
```

**Starter Template:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Media Query Challenge</title>
    <style>
        /* TODO: Your advanced media queries */
        
        /* Variables for theming */
        :root {
            /* Light mode defaults */
        }
        
        /* TODO: Dark mode */
        @media (prefers-color-scheme: dark) {
            
        }
        
        /* TODO: Mobile first layout */
        
        /* TODO: Tablet breakpoint */
        
        /* TODO: Desktop breakpoint */
        
        /* TODO: Hover capability detection */
        
        /* TODO: Touch device optimization */
        
        /* TODO: Reduced motion */
        
        /* TODO: Print styles */
        
        /* TODO: Container queries */
        
        /* TODO: High contrast */
        
        /* TODO: Orientation */
    </style>
</head>
<body>
    <!-- Build your adaptive interface -->
</body>
</html>
```

**Full Solution (for teacher reference):**
```css
/* Complete Advanced Media Query Solution */

/* CSS Variables */
:root {
    /* Light mode (default) */
    --bg-primary: #ffffff;
    --bg-secondary: #f8f9fa;
    --text-primary: #212529;
    --text-secondary: #6c757d;
    --accent: #0066cc;
    --border: #dee2e6;
    --shadow: 0 2px 4px rgba(0,0,0,0.1);
    --radius: 8px;
    --transition: 0.3s ease;
}

/* Dark Mode Support */
@media (prefers-color-scheme: dark) {
    :root {
        --bg-primary: #1a1a1a;
        --bg-secondary: #2c2c2c;
        --text-primary: #f0f0f0;
        --text-secondary: #adb5bd;
        --accent: #4dabf7;
        --border: #495057;
        --shadow: 0 2px 8px rgba(0,0,0,0.3);
    }
    
    img {
        opacity: 0.9;
    }
    
    /* Invert logos */
    .logo {
        filter: invert(1) hue-rotate(180deg);
    }
}

/* Base Styles - Mobile First */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
    background: var(--bg-primary);
    color: var(--text-primary);
    line-height: 1.6;
    font-size: 16px;
    transition: background-color var(--transition), color var(--transition);
}

/* Container */
.container {
    width: 100%;
    padding: 1rem;
}

/* Typography - Fluid */
h1 {
    font-size: clamp(1.5rem, 5vw, 3rem);
    line-height: 1.2;
    margin-bottom: 1rem;
}

h2 {
    font-size: clamp(1.25rem, 4vw, 2rem);
    margin-bottom: 0.75rem;
}

p {
    font-size: clamp(1rem, 2vw, 1.125rem);
    color: var(--text-secondary);
    margin-bottom: 1rem;
}

/* Layout Grid - Mobile First */
.grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1rem;
}

/* Components */
.card {
    background: var(--bg-secondary);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 1.5rem;
    box-shadow: var(--shadow);
    transition: transform var(--transition), box-shadow var(--transition);
}

.button {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    background: var(--accent);
    color: white;
    border: none;
    border-radius: var(--radius);
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    text-decoration: none;
    transition: all var(--transition);
}

/* Touch Device Optimization */
@media (pointer: coarse) {
    .button {
        min-height: 44px;
        min-width: 44px;
        padding: 1rem 2rem;
    }
    
    .clickable {
        min-height: 44px;
    }
    
    /* Larger form elements */
    input, select, textarea {
        min-height: 44px;
        font-size: 16px; /* Prevent zoom on iOS */
    }
}

/* Mouse/Trackpad Hover Effects */
@media (hover: hover) and (pointer: fine) {
    .button:hover {
        transform: translateY(-2px);
        box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        background: color-mix(in srgb, var(--accent) 85%, black);
    }
    
    .card:hover {
        transform: translateY(-4px);
        box-shadow: 0 8px 16px rgba(0,0,0,0.15);
    }
    
    a:hover {
        text-decoration: underline;
    }
}

/* Tablet Breakpoint */
@media (width >= 768px) {
    .container {
        padding: 2rem;
        max-width: 1200px;
        margin: 0 auto;
    }
    
    .grid {
        grid-template-columns: repeat(2, 1fr);
        gap: 1.5rem;
    }
    
    .sidebar-layout {
        display: grid;
        grid-template-columns: 250px 1fr;
        gap: 2rem;
    }
}

/* Desktop Breakpoint */
@media (width >= 1024px) {
    .grid {
        grid-template-columns: repeat(3, 1fr);
        gap: 2rem;
    }
    
    .hero {
        min-height: 70vh;
        display: flex;
        align-items: center;
    }
}

/* Large Desktop */
@media (width >= 1440px) {
    .grid {
        grid-template-columns: repeat(4, 1fr);
    }
    
    .container {
        max-width: 1400px;
    }
}

/* Ultra Wide */
@media (width >= 1920px) {
    body {
        font-size: 18px;
    }
    
    .container {
        max-width: 1800px;
    }
}

/* Reduced Motion */
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
        scroll-behavior: auto !important;
    }
    
    .parallax {
        transform: none !important;
    }
    
    .carousel {
        scroll-snap-type: none !important;
    }
}

/* High Contrast Mode */
@media (prefers-contrast: high) {
    :root {
        --bg-primary: white;
        --bg-secondary: white;
        --text-primary: black;
        --text-secondary: black;
        --accent: #0000ff;
        --border: black;
    }
    
    * {
        border-width: 2px !important;
    }
    
    .button {
        border: 2px solid black !important;
        font-weight: 900;
    }
    
    a {
        text-decoration: underline !important;
        text-decoration-thickness: 2px !important;
    }
}

/* Forced Colors (Windows High Contrast) */
@media (forced-colors: active) {
    .button {
        border: 1px solid;
    }
    
    .card {
        border: 1px solid;
    }
}

/* Orientation Handling */
@media (orientation: landscape) {
    .mobile-hero {
        display: grid;
        grid-template-columns: 1fr 1fr;
        min-height: 100vh;
    }
}

@media (orientation: portrait) {
    .mobile-hero {
        min-height: 50vh;
        text-align: center;
    }
}

/* Retina Displays */
@media (-webkit-min-device-pixel-ratio: 2),
       (min-resolution: 192dpi) {
    .logo {
        background-image: url('logo@2x.png');
        background-size: contain;
    }
    
    /* Thinner borders on retina */
    .card {
        border-width: 0.5px;
    }
}

/* Print Styles */
@media print {
    /* Hide non-content elements */
    nav, .sidebar, .ads, .no-print, 
    .button, footer, .social-links {
        display: none !important;
    }
    
    /* Reset colors */
    * {
        background: white !important;
        color: black !important;
        box-shadow: none !important;
        text-shadow: none !important;
    }
    
    /* Page setup */
    @page {
        margin: 2cm;
        size: A4;
    }
    
    /* Typography for print */
    body {
        font-family: Georgia, serif;
        font-size: 12pt;
        line-height: 1.5;
    }
    
    h1 { font-size: 24pt; }
    h2 { font-size: 18pt; }
    h3 { font-size: 14pt; }
    
    /* Prevent breaks */
    h1, h2, h3, h4, h5, h6 {
        page-break-after: avoid;
    }
    
    img, figure {
        page-break-inside: avoid;
    }
    
    /* Show URLs */
    a[href]:after {
        content: " (" attr(href) ")";
    }
    
    /* Expand abbreviations */
    abbr[title]:after {
        content: " (" attr(title) ")";
    }
}

/* Container Queries */
.card-wrapper {
    container-type: inline-size;
    container-name: card;
}

@container card (min-width: 400px) {
    .card {
        display: grid;
        grid-template-columns: 150px 1fr;
        gap: 1rem;
    }
    
    .card-title {
        font-size: 1.5rem;
    }
}

@container card (min-width: 600px) {
    .card {
        grid-template-columns: 200px 1fr;
    }
    
    .card-actions {
        display: flex;
        gap: 1rem;
    }
}

/* Feature Detection */
@supports (backdrop-filter: blur(10px)) {
    .modal-overlay {
        background: rgba(0, 0, 0, 0.3);
        backdrop-filter: blur(10px);
    }
}

@supports not (backdrop-filter: blur(10px)) {
    .modal-overlay {
        background: rgba(0, 0, 0, 0.8);
    }
}

@supports (display: grid) {
    .layout {
        display: grid;
    }
}

@supports not (display: grid) {
    .layout {
        display: flex;
        flex-wrap: wrap;
    }
}

/* No JavaScript Fallback */
@media (scripting: none) {
    .requires-js {
        display: none;
    }
    
    .no-js-message {
        display: block;
        padding: 1rem;
        background: #fff3cd;
        border: 1px solid #ffc107;
        color: #856404;
    }
    
    details {
        /* Use details/summary for accordions */
        border: 1px solid var(--border);
        padding: 1rem;
        margin-bottom: 1rem;
    }
}
```

---

## Assessment and Wrap-Up (5 minutes)

### Quick Media Query Challenge
**Teacher provides scenarios, students write queries:**

1. "Target only iPads in landscape"
   ```css
   @media (min-width: 768px) and (max-width: 1024px) 
          and (orientation: landscape) { }
   ```

2. "Apply styles only if user can hover precisely"
   ```css
   @media (hover: hover) and (pointer: fine) { }
   ```

3. "Dark mode with reduced motion"
   ```css
   @media (prefers-color-scheme: dark) and 
          (prefers-reduced-motion: reduce) { }
   ```

---

## Common Student Mistakes & Solutions

### Mistake 1: Wrong operator precedence
**Problem:** Query doesn't work as expected
**Fix:** Use parentheses for clarity
```css
/* Confusing */
@media screen and (min-width: 768px) or (orientation: landscape)

/* Clear */
@media screen and ((min-width: 768px) or (orientation: landscape))
```

### Mistake 2: Forgetting fallbacks
**Problem:** Site breaks on older browsers
**Fix:** Progressive enhancement
```css
/* Provide fallback first */
.container { display: flex; }

/* Then enhance */
@supports (display: grid) {
    .container { display: grid; }
}
```

### Mistake 3: Too many breakpoints
**Problem:** Maintenance nightmare
**Fix:** Use fluid design, fewer breakpoints
```css
/* Instead of 10 breakpoints, use fluid units */
font-size: clamp(1rem, 2vw, 1.5rem);
```

---

## Homework Assignment

### Create an Adaptive News Website
Build a news site that adapts to every scenario:

1. **Device adaptation** - Desktop, tablet, mobile
2. **Capability detection** - Mouse vs touch
3. **User preferences** - Dark mode, reduced motion, high contrast
4. **Print version** - Clean, readable printout
5. **Container queries** - For article cards
6. **Performance** - Lazy load images on slow connections

### Bonus Challenges:
- Add offline support detection
- Implement language-based layouts (LTR/RTL)
- Create TV/large screen layout
- Add voice assistant optimizations

---

## Next Lesson Preview
"Next time, we'll master CSS Grid - the ultimate tool for complex two-dimensional layouts!"
