# Lesson 16: Working with Dimensions - Sizing Elements Like a Pro
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Set width and height using different units (px, %, em, rem, vh, vw)
- Use min/max width and height for responsive design
- Understand the difference between content and viewport sizing
- Control overflow behavior when content exceeds dimensions
- Maintain aspect ratios responsively
- Apply object-fit to images and videos
- Create fluid and fixed layouts
- Debug dimension-related issues

### Materials Needed
- Text editor with syntax highlighting
- Web browser with developer tools
- Projector for demonstrations
- Responsive design examples
- Unit conversion reference sheet
- Sample images of different sizes
- Mobile device or browser device emulator
- Ruler/measuring tape for visual demos

### Key Vocabulary with Definitions
- **Fixed dimensions**: Specific size in pixels
- **Fluid dimensions**: Percentage-based sizing
- **Viewport units**: Size relative to browser window
- **Min-width/height**: Minimum allowed size
- **Max-width/height**: Maximum allowed size
- **Overflow**: What happens when content is too big
- **Aspect ratio**: Width to height relationship
- **Object-fit**: How images fill containers
- **Responsive**: Adapts to different screen sizes
- **Intrinsic sizing**: Based on content size

---
## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding Dimension Units (5 minutes)

**Teacher Script:**
"Think of CSS dimensions like choosing a picture frame. You can pick an exact size (fixed), make it fit the wall (percentage), or make it adjust to the room size (viewport units). Each choice creates different behaviors!"

**[CREATE new file: dimensions-demo.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>CSS Dimensions Mastery</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            background: #f5f5f5;
        }
        
        .demo-container {
            background: white;
            padding: 20px;
            margin-bottom: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }    </style>
</head>
<body>
    <h1>Dimensions in CSS</h1>
    
    <!-- Unit Demonstrations -->
    <div class="demo-container">
        <h2>Unit Types</h2>
        <div class="fixed-width">Fixed Width (300px)</div>
        <div class="percent-width">Percentage Width (50%)</div>
        <div class="viewport-width">Viewport Width (80vw)</div>
        <div class="em-width">Em Width (20em)</div>
        <div class="rem-width">Rem Width (25rem)</div>
    </div>
    
    <!-- Min/Max Demonstrations -->
    <div class="demo-container">
        <h2>Min/Max Constraints</h2>
        <div class="min-max-demo">Responsive with limits</div>
        <div class="max-only">Max width only</div>
        <div class="min-only">Min width only</div>
    </div>
    
    <!-- Overflow Examples -->
    <div class="demo-container">
        <h2>Overflow Behavior</h2>
        <div class="overflow-visible">Visible overflow content...</div>
        <div class="overflow-hidden">Hidden overflow content...</div>
        <div class="overflow-scroll">Scroll overflow content...</div>
        <div class="overflow-auto">Auto overflow content...</div>    </div>
</body>
</html>
```

**[DEMONSTRATE dimension units with detailed explanations]**

```css
/* 1. FIXED DIMENSIONS - Exact pixel values */
.fixed-width {
    width: 300px;  /* Always 300 pixels wide */
    height: 100px; /* Always 100 pixels tall */
    background: #3498db;
    color: white;
    padding: 10px;
    margin-bottom: 10px;
}

/* When to use fixed:
   - Logos with specific size
   - Icons that shouldn't scale
   - Sidebar with exact width */

/* 2. PERCENTAGE DIMENSIONS - Relative to parent */
.percent-width {
    width: 50%;    /* 50% of parent container */
    height: 100px; /* Height often fixed when width is % */
    background: #e74c3c;
    color: white;
    padding: 10px;
    margin-bottom: 10px;
}

/* Important: % height needs parent with defined height! */
.parent-with-height {    height: 400px; /* Parent needs height for child % height */
}

.child-percent-height {
    height: 50%; /* Now this works! */
}

/* 3. VIEWPORT UNITS - Relative to browser window */
.viewport-width {
    width: 80vw;   /* 80% of viewport width */
    height: 20vh;  /* 20% of viewport height */
    background: #9b59b6;
    color: white;
    padding: 10px;
    margin-bottom: 10px;
}

/* Viewport unit types:
   vw = viewport width (1vw = 1% of viewport width)
   vh = viewport height (1vh = 1% of viewport height)
   vmin = smaller of vw or vh
   vmax = larger of vw or vh */

/* Creative viewport uses */
.full-screen-hero {
    width: 100vw;
    height: 100vh;  /* Full screen section */
}

.square-responsive {
    width: 50vmin;
    height: 50vmin; /* Always square, responsive */
}
/* 4. EM UNITS - Relative to parent font-size */
.em-width {
    width: 20em;    /* 20 times parent font-size */
    font-size: 16px;
    padding: 0.5em; /* Padding scales with font-size */
    background: #16a085;
    color: white;
    margin-bottom: 10px;
}

/* 5. REM UNITS - Relative to root font-size */
.rem-width {
    width: 25rem;   /* 25 times root (html) font-size */
    padding: 1rem;  /* Consistent across site */
    background: #f39c12;
    color: white;
}

/* REM vs EM:
   rem = predictable, based on root
   em = cascades, can compound */
```

### Min/Max Constraints (5 minutes)

**[DEMONSTRATE responsive constraints]**

```css
/* MIN AND MAX WIDTH - The responsive sweet spot */
.min-max-demo {
    width: 90%;           /* Fluid width */
    max-width: 1200px;    /* But never larger than 1200px */
    min-width: 300px;     /* And never smaller than 300px */    margin: 0 auto;      /* Center it */
    padding: 20px;
    background: #34495e;
    color: white;
}

/* Common responsive pattern */
.responsive-container {
    width: 100%;
    max-width: 960px;
    margin: 0 auto;
    padding: 0 20px;
}

/* MIN HEIGHT - Ensure minimum space */
.min-height-card {
    min-height: 200px;    /* At least 200px tall */
    /* Content can make it taller */
}

/* MAX HEIGHT with scroll */
.max-height-list {
    max-height: 400px;    /* Never taller than 400px */
    overflow-y: auto;     /* Scroll if needed */
}

/* Responsive images */
.responsive-image {
    width: 100%;          /* Fill container width */
    max-width: 100%;      /* But not larger than actual size */
    height: auto;         /* Maintain aspect ratio */
}

/* Fluid typography with limits */.fluid-text {
    font-size: calc(1rem + 1vw);
    font-size: clamp(1rem, 2vw, 2rem); /* Modern way: min, preferred, max */
}
```

### Overflow and Object-Fit (5 minutes)

**[DEMONSTRATE overflow behaviors]**

```css
/* OVERFLOW PROPERTIES - Control content that's too big */

/* Visible - Default, content spills out */
.overflow-visible {
    width: 200px;
    height: 100px;
    overflow: visible; /* Default */
    background: #ecf0f1;
    border: 2px solid #95a5a6;
}

/* Hidden - Clips overflow */
.overflow-hidden {
    width: 200px;
    height: 100px;
    overflow: hidden; /* Cuts off excess */
    background: #ecf0f1;
    border: 2px solid #95a5a6;
}

/* Scroll - Always show scrollbars */
.overflow-scroll {
    width: 200px;
    height: 100px;    overflow: scroll; /* Scrollbars always visible */
    background: #ecf0f1;
    border: 2px solid #95a5a6;
}

/* Auto - Scrollbars only when needed */
.overflow-auto {
    width: 200px;
    height: 100px;
    overflow: auto; /* Smart scrollbars */
    background: #ecf0f1;
    border: 2px solid #95a5a6;
}

/* Overflow X and Y separately */
.overflow-separate {
    overflow-x: hidden;  /* No horizontal scroll */
    overflow-y: auto;    /* Vertical scroll if needed */
}

/* Text overflow with ellipsis */
.text-overflow {
    width: 200px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis; /* Shows ... */
}

/* OBJECT-FIT - How images fill containers */
.image-container {
    width: 300px;
    height: 200px;
    border: 2px solid #3498db;}

.image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Fills container, crops if needed */
}

/* Object-fit values:
   fill = Stretches to fill (default, can distort)
   contain = Fits entire image, may have space
   cover = Fills container, may crop
   none = Original size, may overflow
   scale-down = Smaller of none or contain */

/* ASPECT RATIO TECHNIQUES */
/* Padding hack for responsive aspect ratios */
.aspect-ratio-16-9 {
    position: relative;
    padding-bottom: 56.25%; /* 9/16 = 0.5625 */
    height: 0;
}

.aspect-ratio-16-9 > * {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

/* Modern aspect-ratio property */
.modern-aspect {    aspect-ratio: 16 / 9; /* Simpler, newer way */
    width: 100%;
    background: #3498db;
}
```

---

## PART 2: WE DO (Guided Practice) - 15 minutes

### Activity 1: Responsive Card Builder (7 minutes)

**Teacher Instructions:**
1. Build a responsive card system together
2. Apply different dimension strategies
3. Test at different screen sizes
4. Fix overflow issues as they arise

**[PROJECT and BUILD TOGETHER]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Responsive Card System</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: Arial, sans-serif;
            background: #f0f0f0;
            padding: 20px;        }
        
        /* Card container with responsive grid */
        .card-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        /* Individual card with constraints */
        .card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            min-height: 350px;  /* Minimum height */
            display: flex;
            flex-direction: column;
        }
        
        /* Image with aspect ratio */
        .card-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            object-fit: cover;
        }
        
        /* Content with flexible height */
        .card-content {            padding: 20px;
            flex: 1;  /* Takes remaining space */
        }
        
        .card-title {
            font-size: clamp(1.2rem, 2vw, 1.5rem); /* Responsive font */
            margin-bottom: 10px;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
        }
        
        .card-description {
            color: #666;
            line-height: 1.6;
            max-height: 100px;
            overflow: hidden;
            position: relative;
        }
        
        /* Fade out effect for long text */
        .card-description::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 30px;
            background: linear-gradient(transparent, white);
        }
        
        .card-footer {            padding: 15px 20px;
            border-top: 1px solid #eee;
        }
        
        .card-button {
            width: 100%;
            padding: 10px;
            background: #3498db;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="card-container">
        <div class="card">
            <div class="card-image"></div>
            <div class="card-content">
                <h3 class="card-title">Responsive Card Title That Might Be Long</h3>
                <p class="card-description">
                    This card demonstrates responsive dimensions. The content adapts
                    to different screen sizes while maintaining readability and proper
                    proportions. Extra text gets hidden with a fade effect.
                </p>
            </div>
            <div class="card-footer">
                <button class="card-button">Read More</button>
            </div>
        </div>        <!-- Repeat cards to see grid behavior -->
    </div>
</body>
</html>
```

**Discussion Points:**
1. Why use minmax() in grid?
2. How does flex: 1 work?
3. What happens without min-height?
4. Why clamp() for font-size?
5. How to handle text overflow?

### Activity 2: Dimension Calculator Challenge (8 minutes)

**Teacher Instructions:**
1. Present dimension scenarios
2. Students calculate final sizes
3. Test predictions in browser
4. Discuss why results occur

**[EVERYONE CALCULATES]**

```css
/* Scenario 1: What's the final width? */
.parent-1 {
    width: 800px;
    padding: 20px;
}

.child-1 {
    width: 50%;
    max-width: 500px;
    padding: 10px;
    border: 2px solid black;
    box-sizing: border-box;
}
/* Answer: 400px (50% of 800px, under max-width limit) */
/* Scenario 2: Viewport units */
/* Browser window: 1920px wide, 1080px tall */
.element-2 {
    width: 50vw;
    height: 25vh;
    max-width: 800px;
    min-height: 200px;
}
/* Answer: Width = 800px (50vw = 960px, but max-width limits)
           Height = 270px (25vh = 270px, above min-height) */

/* Scenario 3: Em vs Rem */
html { font-size: 16px; }
.parent-3 { font-size: 20px; }
.child-3 {
    font-size: 24px;
    width: 10em;    /* Based on element's font-size */
    height: 10rem;  /* Based on root font-size */
}
/* Answer: Width = 240px (10 × 24px)
           Height = 160px (10 × 16px) */

/* Scenario 4: Percentage height issue */
.parent-4 {
    /* No height defined */
}
.child-4 {
    height: 50%; /* What happens? */
}
/* Answer: Doesn't work! Parent needs defined height */```

---

## PART 3: YOU DO (Independent Practice) - 15 minutes

### Individual Challenge: Responsive Gallery System (15 minutes)

**Student Instructions:**
"Create a responsive gallery that works perfectly on all screen sizes. Use various dimension techniques to ensure optimal viewing experience."

**HTML Starter Template:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Responsive Gallery Challenge</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: Arial, sans-serif;
            background: #f5f5f5;
        }
        
        /* TODO: Your CSS here */
        
        /* Challenge 1: Hero section with viewport height */
        .hero {
            /* TODO: Full viewport height with max limit */        }
        
        /* Challenge 2: Responsive container */
        .container {
            /* TODO: Fluid width with min/max constraints */
        }
        
        /* Challenge 3: Gallery grid */
        .gallery {
            /* TODO: Responsive grid with minimum item size */
        }
        
        /* Challenge 4: Gallery items with aspect ratio */
        .gallery-item {
            /* TODO: Maintain 1:1 aspect ratio */
        }
        
        /* Challenge 5: Modal with max dimensions */
        .modal {
            /* TODO: Centered modal with size limits */
        }
        
        /* Challenge 6: Sidebar with fixed/fluid behavior */
        .sidebar {
            /* TODO: Fixed width on desktop, full on mobile */
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <h1>Responsive Gallery</h1>
        <p>Adapts to any screen size</p>    </section>
    
    <!-- Main Container -->
    <div class="container">
        <!-- Sidebar -->
        <aside class="sidebar">
            <h2>Categories</h2>
            <ul>
                <li>Nature</li>
                <li>Architecture</li>
                <li>People</li>
                <li>Animals</li>
            </ul>
        </aside>
        
        <!-- Gallery Grid -->
        <main class="gallery">
            <div class="gallery-item">
                <img src="placeholder.jpg" alt="Gallery image 1">
                <div class="overlay">Image 1</div>
            </div>
            <div class="gallery-item">
                <img src="placeholder.jpg" alt="Gallery image 2">
                <div class="overlay">Image 2</div>
            </div>
            <!-- Add more items -->
        </main>
    </div>
    
    <!-- Modal -->
    <div class="modal">
        <div class="modal-content">            <h3>Image Preview</h3>
            <img src="placeholder.jpg" alt="Full size">
            <button class="close">Close</button>
        </div>
    </div>
</body>
</html>
```

**Requirements Checklist:**
```
□ Hero section uses vh units with max-height
□ Container has fluid width with min/max
□ Gallery uses responsive grid
□ Gallery items maintain aspect ratio
□ Images use object-fit appropriately
□ Modal has maximum dimensions
□ Sidebar switches between fixed and fluid
□ Text has overflow handling
□ Use clamp() for at least one property
□ Include responsive padding/margins
□ Test at 320px, 768px, 1920px widths
□ No horizontal scroll at any size
□ Images don't distort
□ Content remains readable
□ Smooth transitions between sizes
```

**CSS Solution (for teacher reference):**
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;}

body {
    font-family: 'Segoe UI', Arial, sans-serif;
    background: #f5f5f5;
    line-height: 1.6;
}

/* Challenge 1: Hero with viewport height */
.hero {
    height: 100vh;
    max-height: 800px;
    min-height: 400px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 20px;
}

.hero h1 {
    font-size: clamp(2rem, 5vw, 4rem);
    margin-bottom: 1rem;
}

.hero p {
    font-size: clamp(1rem, 2vw, 1.5rem);
}

/* Challenge 2: Responsive container */.container {
    width: 90%;
    max-width: 1400px;
    min-width: 320px;
    margin: 2rem auto;
    padding: 0 1rem;
    display: flex;
    gap: 2rem;
}

/* Challenge 6: Sidebar responsive behavior */
.sidebar {
    width: 250px;
    min-width: 200px;
    background: white;
    padding: 1.5rem;
    border-radius: 10px;
    height: fit-content;
    position: sticky;
    top: 20px;
}

.sidebar h2 {
    margin-bottom: 1rem;
    color: #333;
}

.sidebar ul {
    list-style: none;
}

.sidebar li {
    padding: 0.5rem 0;
    border-bottom: 1px solid #eee;    cursor: pointer;
    transition: color 0.3s;
}

.sidebar li:hover {
    color: #667eea;
}

/* Challenge 3: Gallery grid */
.gallery {
    flex: 1;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 1.5rem;
    align-content: start;
}

/* Challenge 4: Gallery items with aspect ratio */
.gallery-item {
    position: relative;
    width: 100%;
    padding-bottom: 100%; /* 1:1 aspect ratio */
    background: white;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    cursor: pointer;
    transition: transform 0.3s;
}

.gallery-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 12px rgba(0, 0, 0, 0.15);}

.gallery-item img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.gallery-item .overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: linear-gradient(transparent, rgba(0, 0, 0, 0.7));
    color: white;
    padding: 1rem;
    transform: translateY(100%);
    transition: transform 0.3s;
}

.gallery-item:hover .overlay {
    transform: translateY(0);
}

/* Challenge 5: Modal with max dimensions */
.modal {
    display: none; /* Hidden by default */
    position: fixed;
    top: 0;
    left: 0;    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0.8);
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
}

.modal-content {
    background: white;
    width: 90%;
    max-width: 800px;
    max-height: 90vh;
    overflow-y: auto;
    border-radius: 10px;
    padding: 2rem;
    position: relative;
}

.modal-content img {
    width: 100%;
    height: auto;
    max-height: 60vh;
    object-fit: contain;
    margin: 1rem 0;
}

.modal-content .close {
    position: absolute;
    top: 1rem;
    right: 1rem;
    padding: 0.5rem 1rem;
    background: #e74c3c;    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

/* Responsive adjustments */
@media (max-width: 768px) {
    .container {
        flex-direction: column;
    }
    
    .sidebar {
        width: 100%;
        position: static;
    }
    
    .gallery {
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    }
    
    .hero {
        height: 70vh;
    }
}

@media (max-width: 480px) {
    .gallery {
        grid-template-columns: 1fr;
    }
    
    .modal-content {
        padding: 1rem;
    }
}```

---

## Assessment and Wrap-Up (5 minutes)

### Quick Dimension Quiz
**Teacher asks, students answer:**

1. "What's the difference between vw and %?"
   → vw = viewport width, % = parent element width

2. "When would you use max-width?"
   → To prevent content from getting too wide on large screens

3. "What happens with height: 100% if parent has no height?"
   → It doesn't work! Needs defined parent height

4. "What's object-fit: cover do?"
   → Fills container, crops if needed, maintains aspect ratio

### Responsive Check
"Resize your browser window - does your gallery adapt smoothly?"

---

## Common Student Mistakes & Solutions

### Mistake 1: Height percentage not working
**Student writes:** `height: 100%;` with no parent height
**Fix:** Parent needs defined height or use vh units
```css
/* Parent needs height */
.parent { height: 400px; }
.child { height: 50%; } /* Now works */
```

### Mistake 2: Images stretching**Problem:** Images distort when resized
**Fix:** Use object-fit or maintain aspect ratio
```css
img {
    width: 100%;
    height: auto; /* Maintains aspect ratio */
    /* OR */
    object-fit: cover; /* Crops to fit */
}
```

### Mistake 3: Overflow issues ignored
**Problem:** Content spills out, breaks layout
**Fix:** Always handle overflow
```css
.container {
    overflow: hidden; /* or auto, or scroll */
}
```

### Mistake 4: Not testing responsive sizes
**Issue:** Looks good on desktop, broken on mobile
**Fix:** Test at multiple breakpoints (320px, 768px, 1024px, 1920px)

### Mistake 5: Using only fixed units
**Problem:** Not responsive
**Fix:** Mix units appropriately
```css
/* Good mix */
width: 90%;
max-width: 1200px;
min-width: 320px;
padding: clamp(1rem, 3vw, 2rem);
```
---

## Homework Assignment

### Task: Responsive Portfolio Layout
Create a complete portfolio website with intelligent dimension handling:

**Page Requirements:**
1. **Landing Hero**
   - Full viewport height with maximum
   - Responsive typography using clamp()
   - Background image with object-fit

2. **Project Grid**
   - Responsive columns (1-4 based on width)
   - Minimum item width of 250px
   - Maintain 16:9 aspect ratio for images
   - Hover effects changing dimensions

3. **About Section**
   - Maximum readable width (65ch)
   - Responsive padding using calc()
   - Image that never exceeds 400px

4. **Skills Bar Chart**
   - Percentage-based widths
   - Animated width on scroll
   - Labels with text-overflow

5. **Contact Form**
   - Maximum width of 600px
   - Inputs with min/max constraints
   - Textarea with max-height and scroll

**Technical Requirements:**- Use all unit types (px, %, em, rem, vw, vh)
- Implement min/max for 5+ elements
- Use clamp() for responsive values
- Handle overflow in 3 different ways
- Apply object-fit to all images
- Create 2+ aspect ratio containers
- No horizontal scroll at any viewport size
- Test and document at 5 breakpoints

**Bonus Challenges:**
- Implement container queries (new CSS feature)
- Create fluid typography scale
- Build responsive spacing system
- Add viewport-based animations
- Create picture element for art direction

---

## Extension Activities

### For Fast Finishers:
1. **Dimension Calculator Tool**
   - Build interactive unit converter
   - Show live preview of dimensions
   - Compare different units

2. **Responsive Tester**
   - Create device frame previews
   - Show dimension values live
   - Test common breakpoints

3. **Aspect Ratio Gallery**
   - Build gallery with different ratios
   - 1:1, 16:9, 4:3, 21:9
   - Smooth transitions between ratios
---

## Teacher Notes & Tips

### Preparation:
- Set up browser with device emulator
- Prepare dimension comparison charts
- Test responsive examples at all sizes
- Have calculator ready for conversions

### During Class:
- Show real website responsive behavior
- Use browser zoom to demonstrate units
- Draw diagrams for aspect ratios
- Emphasize mobile-first thinking

### Differentiation:
- **Struggling:** Start with fixed, then percentage
- **Advanced:** Introduce CSS custom properties for dimensions
- **Visual:** Use colored boxes to show dimensions
- **Kinesthetic:** Physical objects for aspect ratios

### Assessment Rubric (10 points):
- Responsive dimensions: 3 points
- Min/max usage: 2 points
- Unit variety: 2 points
- Overflow handling: 1 point
- Aspect ratios: 1 point
- Testing/documentation: 1 point

---

## Resources & References

### Online Tools:
- **Responsive Viewer:** responsiveviewer.org- **Viewport Calculator:** viewportsizes.com
- **Aspect Ratio Calculator:** aspectratiocalculator.com
- **CSS Units Guide:** developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units

### Quick Reference:
```css
/* DIMENSION UNITS */
width: 300px;        /* Fixed pixels */
width: 50%;         /* Percentage of parent */
width: 20em;        /* Relative to font-size */
width: 20rem;       /* Relative to root font-size */
width: 50vw;        /* 50% of viewport width */
width: 50vh;        /* 50% of viewport height */
width: 50vmin;      /* 50% of smaller viewport dimension */
width: 50vmax;      /* 50% of larger viewport dimension */

/* CONSTRAINTS */
min-width: 200px;   /* Minimum width */
max-width: 1200px;  /* Maximum width */
min-height: 100px;  /* Minimum height */
max-height: 500px;  /* Maximum height */

/* OVERFLOW */
overflow: visible;   /* Default, content spills */
overflow: hidden;    /* Clips content */
overflow: scroll;    /* Always show scrollbars */
overflow: auto;      /* Scrollbars when needed */

/* OBJECT-FIT */
object-fit: fill;    /* Stretch to fill */
object-fit: contain; /* Fit entire image */object-fit: cover;   /* Fill container, crop */
object-fit: none;    /* Original size */
object-fit: scale-down; /* Smaller of none or contain */
```

---

## Success Criteria Checklist

Students have mastered this lesson when they can:
- [ ] Use appropriate units for different scenarios
- [ ] Apply min/max constraints effectively
- [ ] Create responsive dimensions
- [ ] Handle overflow properly
- [ ] Maintain aspect ratios
- [ ] Use viewport units correctly
- [ ] Apply object-fit to images
- [ ] Mix units for optimal responsiveness
- [ ] Debug dimension issues
- [ ] Test at multiple viewport sizes

---

## Next Lesson Preview
"Next class, we'll explore display properties and positioning - learning how to control element flow, stack elements, and create complex layouts with position properties!"

## Key Takeaways
1. **Different units for different needs** - px for fixed, % for fluid, vw/vh for viewport
2. **Min/max creates boundaries** - Fluid within limits
3. **Overflow must be handled** - Don't let content break layouts
4. **Test at all sizes** - Mobile, tablet, desktop, and beyond
5. **Mix units wisely** - Combine for best responsiveness

---

*End of Lesson 16: Working with Dimensions*