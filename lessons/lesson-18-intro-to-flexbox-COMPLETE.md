# Lesson 18: Introduction to Flexbox - Modern Layout Magic
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Understand Flexbox as a one-dimensional layout system
- Master all flex container properties (display, direction, justify, align, wrap, gap)
- Apply flex item properties (grow, shrink, basis, order, align-self)
- Create responsive navigation bars with Flexbox
- Build card layouts that adapt to screen size
- Center content perfectly in any direction
- Replace float-based layouts with modern Flexbox
- Debug common Flexbox issues using browser DevTools
- Combine Flexbox with other CSS properties effectively

### Materials Needed
- Text editor with syntax highlighting
- Web browser with Flexbox DevTools
- Projector for demonstrations
- Flexbox axis diagram (main/cross)
- Property reference sheets
- Playing cards (for physical demonstration)
- Rubber bands or string (to show flex/stretch)
- Sticky notes for properties
- Sample layouts to recreate

### Key Vocabulary with Definitions
- **Flexbox**: One-dimensional layout method for rows or columns
- **Flex Container**: Parent element with display: flex
- **Flex Items**: Direct children of flex container
- **Main Axis**: Primary axis (horizontal by default)
- **Cross Axis**: Perpendicular to main axis
- **Justify**: Alignment along main axis
- **Align**: Alignment along cross axis
- **Flex-grow**: How much item grows
- **Flex-shrink**: How much item shrinks
- **Flex-basis**: Initial size before growing/shrinking

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding Flexbox Fundamentals (5 minutes)

**Teacher Script:**
"Imagine you have a box of toys that need to be arranged on a shelf. Flexbox is like having a smart shelf that can automatically arrange your toys in a line - spacing them out evenly, centering them, or pushing them to the edges. It works in one direction at a time - either horizontally like a bookshelf, or vertically like a tower!"

**[CREATE new file: flexbox-demo.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Flexbox Mastery</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            padding: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }
        
        .demo-section {
            background: white;
            padding: 20px;
            margin-bottom: 30px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }
        
        h2 {
            margin-bottom: 15px;
            color: #333;
        }
        
        /* Visual helpers */
        .flex-container {
            border: 3px dashed #3498db;
            padding: 10px;
            background: #ecf0f1;
            margin-bottom: 20px;
        }
        
        .flex-item {
            background: #3498db;
            color: white;
            padding: 20px;
            margin: 5px;
            text-align: center;
            font-weight: bold;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <h1 style="color: white; text-align: center; margin-bottom: 30px;">
        🎯 Flexbox Layout System
    </h1>
    
    <!-- Basic Flex Container -->
    <div class="demo-section">
        <h2>1. Basic Flexbox</h2>
        <div class="flex-demo-1">
            <div class="flex-item">Item 1</div>
            <div class="flex-item">Item 2</div>
            <div class="flex-item">Item 3</div>
        </div>
    </div>
    
    <!-- Direction Examples -->
    <div class="demo-section">
        <h2>2. Flex Direction</h2>
        <div class="flex-demo-2">
            <div class="flex-item">First</div>
            <div class="flex-item">Second</div>
            <div class="flex-item">Third</div>
        </div>
    </div>
    
    <!-- Justify Content -->
    <div class="demo-section">
        <h2>3. Justify Content (Main Axis)</h2>
        <div class="flex-demo-3">
            <div class="flex-item">A</div>
            <div class="flex-item">B</div>
            <div class="flex-item">C</div>
        </div>
    </div>
    
    <!-- Align Items -->
    <div class="demo-section">
        <h2>4. Align Items (Cross Axis)</h2>
        <div class="flex-demo-4">
            <div class="flex-item" style="height: 50px;">Short</div>
            <div class="flex-item" style="height: 100px;">Tall</div>
            <div class="flex-item" style="height: 75px;">Medium</div>
        </div>
    </div>
</body>
</html>
```

**[DEMONSTRATE the transformation from block to flex]**

```css
/* BEFORE FLEXBOX - The Old Way */
.old-way {
    /* Items stack vertically */
    /* Hard to center */
    /* Float nightmares */
    /* Clearfix hacks */
}

.old-way-item {
    float: left; /* Ugh, floats! */
    width: 33.33333%; /* Math! */
    /* Vertical centering? Good luck! */
}

/* AFTER FLEXBOX - The Modern Way! */
.flex-demo-1 {
    display: flex; /* Magic starts here! */
    /* That's it! Items now flow horizontally */
}

/* What display: flex does:
   1. Creates flex container
   2. Direct children become flex items
   3. Items lay out in a row (default)
   4. Items stretch to fill container height
   5. Items shrink if needed
*/
```

### Flex Container Properties Explained (5 minutes)

**[DEMONSTRATE each property with live changes]**

```css
/* FLEX DIRECTION - Control the main axis */
.flex-demo-2 {
    display: flex;
    flex-direction: row;        /* → Default: left to right */
    /* flex-direction: row-reverse;    ← Right to left */
    /* flex-direction: column;         ↓ Top to bottom */
    /* flex-direction: column-reverse; ↑ Bottom to top */
    
    /* This changes what "main axis" means! */
    /* row = horizontal main axis */
    /* column = vertical main axis */
}

/* JUSTIFY-CONTENT - Position along MAIN axis */
.flex-demo-3 {
    display: flex;
    min-height: 150px;
    
    /* Where items go on main axis: */
    justify-content: flex-start;    /* |■■■      | Default */
    /* justify-content: center;        |   ■■■   | Centered */
    /* justify-content: flex-end;      |      ■■■| End */
    /* justify-content: space-between; |■   ■   ■| No edge gaps */
    /* justify-content: space-around;  | ■  ■  ■ | Equal gaps */
    /* justify-content: space-evenly;  | ■  ■  ■ | Even gaps */
}

/* ALIGN-ITEMS - Position along CROSS axis */
.flex-demo-4 {
    display: flex;
    height: 150px;
    
    /* Where items go on cross axis: */
    align-items: stretch;    /* Default - fill height */
    /* align-items: flex-start;  Top aligned */
    /* align-items: center;      Middle aligned */
    /* align-items: flex-end;    Bottom aligned */
    /* align-items: baseline;    Text baseline aligned */
}

/* FLEX-WRAP - Allow multiple lines */
.flex-wrap-demo {
    display: flex;
    flex-wrap: nowrap;  /* Default - single line, items shrink */
    /* flex-wrap: wrap;      Multiple lines as needed */
    /* flex-wrap: wrap-reverse; Multiple lines, reversed */
}

/* GAP - Modern spacing (bye bye margins!) */
.flex-gap-demo {
    display: flex;
    gap: 20px;           /* Space between all items */
    /* gap: 10px 20px;      row-gap column-gap */
    /* No more margin hacks! */
}

/* ALIGN-CONTENT - Multiple lines alignment */
.flex-align-content {
    display: flex;
    flex-wrap: wrap;
    height: 300px;
    align-content: flex-start;    /* Lines at top */
    /* align-content: center;        Lines centered */
    /* align-content: space-between; Lines spread out */
}
```

### Flex Item Properties Deep Dive (5 minutes)

**[DEMONSTRATE with interactive examples]**

```css
/* FLEX ITEM PROPERTIES - Control individual items */

/* FLEX-GROW - How much to grow */
.grow-demo {
    display: flex;
    gap: 10px;
}

.grow-demo .item-1 {
    flex-grow: 0;  /* Don't grow (default) */
    background: #e74c3c;
}

.grow-demo .item-2 {
    flex-grow: 1;  /* Take 1 share of space */
    background: #3498db;
}

.grow-demo .item-3 {
    flex-grow: 2;  /* Take 2 shares of space */
    background: #2ecc71;
}
/* Result: Item 3 grows twice as much as Item 2 */

/* FLEX-SHRINK - How much to shrink */
.shrink-demo {
    display: flex;
    width: 300px; /* Force shrinking */
}

.shrink-demo .no-shrink {
    flex-shrink: 0;    /* Won't shrink */
    width: 200px;
    background: #e74c3c;
}

.shrink-demo .can-shrink {
    flex-shrink: 1;    /* Will shrink (default) */
    width: 200px;
    background: #3498db;
}

/* FLEX-BASIS - Starting size */
.basis-demo {
    display: flex;
}

.basis-demo .item {
    flex-basis: 200px;  /* Start at 200px */
    /* flex-basis: 25%;    Or use percentage */
    /* flex-basis: auto;   Use content size (default) */
    /* flex-basis: 0;      Start from nothing */
}

/* THE FLEX SHORTHAND - Most powerful! */
.flex-shorthand {
    display: flex;
}

.flex-shorthand .item {
    /* flex: grow shrink basis; */
    flex: 1 1 200px;  /* Can grow, can shrink, start at 200px */
    
    /* Common patterns: */
    /* flex: 1;          Equal columns (1 1 0) */
    /* flex: 0 0 200px;  Fixed 200px width */
    /* flex: 1 0 200px;  Min 200px, can grow */
    /* flex: 0 1 auto;   Default (0 1 auto) */
}

/* ALIGN-SELF - Override container's align-items */
.align-self-demo {
    display: flex;
    align-items: center;
    height: 200px;
}

.align-self-demo .special {
    align-self: flex-start;  /* This one goes to top */
    /* While others stay centered */
}

/* ORDER - Rearrange without changing HTML */
.order-demo {
    display: flex;
}

.order-demo .item-1 { order: 3; }  /* Shows third */
.order-demo .item-2 { order: 1; }  /* Shows first */
.order-demo .item-3 { order: 2; }  /* Shows second */
/* Default order is 0 */
```

---

## PART 2: WE DO (Guided Practice) - 15 minutes

### Activity 1: Build a Responsive Navigation Bar (7 minutes)

**Teacher Instructions:**
1. Create a navigation together step-by-step
2. Show how Flexbox replaces float layouts
3. Add responsive behavior
4. Discuss accessibility

**[BUILD TOGETHER - Type along with students]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Flexbox Navigation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            background: #f4f4f4;
        }
        
        /* Step 1: Basic nav container */
        .navbar {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 1rem 2rem;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        /* Step 2: Make it flex! */
        .navbar {
            display: flex;
            justify-content: space-between; /* Logo left, menu right */
            align-items: center; /* Vertically center everything */
        }
        
        /* Step 3: Style the logo */
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: white;
            text-decoration: none;
        }
        
        .logo:hover {
            transform: scale(1.05);
            transition: transform 0.3s ease;
        }
        
        /* Step 4: Style the menu */
        .nav-menu {
            display: flex;  /* Nested flexbox! */
            list-style: none;
            gap: 2rem;  /* Modern spacing */
        }
        
        /* Step 5: Style menu items */
        .nav-item {
            position: relative;
        }
        
        .nav-link {
            color: white;
            text-decoration: none;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            transition: all 0.3s ease;
        }
        
        .nav-link:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-2px);
        }
        
        /* Step 6: Active state */
        .nav-link.active {
            background: rgba(255,255,255,0.3);
        }
        
        /* Step 7: Mobile menu button (hidden on desktop) */
        .menu-toggle {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        /* Step 8: Responsive design */
        @media (max-width: 768px) {
            .navbar {
                flex-wrap: wrap;
            }
            
            .nav-menu {
                flex-direction: column;
                width: 100%;
                display: none; /* Hidden by default on mobile */
                margin-top: 1rem;
            }
            
            .nav-menu.active {
                display: flex; /* Show when active */
            }
            
            .menu-toggle {
                display: block; /* Show hamburger on mobile */
            }
        }
    </style>
</head>
<body>
    <nav class="navbar">
        <a href="/" class="logo">FlexNav</a>
        
        <button class="menu-toggle" onclick="toggleMenu()">☰</button>
        
        <ul class="nav-menu" id="navMenu">
            <li class="nav-item">
                <a href="#" class="nav-link active">Home</a>
            </li>
            <li class="nav-item">
                <a href="#" class="nav-link">About</a>
            </li>
            <li class="nav-item">
                <a href="#" class="nav-link">Services</a>
            </li>
            <li class="nav-item">
                <a href="#" class="nav-link">Portfolio</a>
            </li>
            <li class="nav-item">
                <a href="#" class="nav-link">Contact</a>
            </li>
        </ul>
    </nav>
    
    <script>
        function toggleMenu() {
            const menu = document.getElementById('navMenu');
            menu.classList.toggle('active');
        }
    </script>
</body>
</html>
```

**Key Teaching Points:**
1. "Notice how we nest flexbox containers"
2. "Gap property replaces margin hacks"
3. "Justify-content handles horizontal spacing"
4. "Align-items handles vertical alignment"
5. "Flex-wrap enables responsive behavior"

### Activity 2: Create a Card Layout System (8 minutes)

**Teacher Instructions:**
1. Build flexible card grid together
2. Show grow/shrink in action
3. Make cards equal height
4. Add responsive breakpoints

**[CREATE together - students follow along]**

```css
/* Card Layout System with Flexbox */

/* Container for cards */
.card-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    padding: 20px;
    justify-content: center; /* Center when not full row */
}

/* Individual card */
.card {
    flex: 1 1 300px; /* Magic line! */
    /* grow: yes, shrink: yes, basis: 300px */
    /* This means: be 300px, but grow/shrink as needed */
    
    max-width: 400px; /* Don't get too big */
    background: white;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
    
    /* Card is also a flex container! */
    display: flex;
    flex-direction: column;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 12px rgba(0,0,0,0.15);
}

/* Card image */
.card-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
}

/* Card content */
.card-content {
    padding: 20px;
    flex-grow: 1; /* Take remaining space */
    display: flex;
    flex-direction: column;
}

.card-title {
    font-size: 1.5rem;
    margin-bottom: 10px;
    color: #333;
}

.card-text {
    flex-grow: 1; /* Push buttons to bottom */
    color: #666;
    line-height: 1.6;
}

/* Card actions */
.card-actions {
    display: flex;
    gap: 10px;
    margin-top: 20px;
}

.card-button {
    flex: 1; /* Equal width buttons */
    padding: 10px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s ease;
}

.card-button.primary {
    background: #3498db;
    color: white;
}

.card-button.secondary {
    background: #ecf0f1;
    color: #333;
}

.card-button:hover {
    transform: scale(1.05);
}

/* Responsive adjustments */
@media (max-width: 768px) {
    .card {
        flex: 1 1 100%; /* Full width on mobile */
    }
}

@media (min-width: 769px) and (max-width: 1024px) {
    .card {
        flex: 0 1 calc(50% - 10px); /* Two columns on tablet */
    }
}

@media (min-width: 1025px) {
    .card {
        flex: 0 1 calc(33.333% - 14px); /* Three columns on desktop */
    }
}
```

---

## PART 3: YOU DO (Independent Practice) - 15 minutes

### Individual Challenge: Complete Layout System (15 minutes)

**Student Instructions:**
"Create a complete webpage layout using ONLY Flexbox! Build a photo portfolio site with header, sidebar, main content, and footer - all with Flexbox!"

**Challenge Requirements:**
```
□ Sticky header with flexbox navigation
□ Sidebar with vertical menu (flex-direction: column)
□ Main content area with card grid
□ Footer that sticks to bottom (min-height technique)
□ All cards equal height
□ Responsive at 3 breakpoints
□ Center at least one element perfectly
□ Use flex-grow for flexible sections
□ Use gap instead of margins
□ Order property for mobile layout
```

**Starter Template:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Flexbox Portfolio Challenge</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        /* TODO: Your Flexbox CSS Here */
        
        /* Challenge 1: Full page layout */
        body {
            /* Make body a flex container */
            /* Direction? */
            /* Minimum height? */
        }
        
        /* Challenge 2: Header with nav */
        .header {
            /* Flexbox properties? */
        }
        
        .nav {
            /* How to space items? */
        }
        
        /* Challenge 3: Main layout with sidebar */
        .main-wrapper {
            /* Flex and grow? */
        }
        
        .sidebar {
            /* Fixed width or flex? */
        }
        
        .content {
            /* How to take remaining space? */
        }
        
        /* Challenge 4: Card grid */
        .portfolio-grid {
            /* Wrap? Gap? Justify? */
        }
        
        .portfolio-card {
            /* Flex shorthand? */
        }
        
        /* Challenge 5: Sticky footer */
        .footer {
            /* How to stick to bottom? */
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="logo">Portfolio</div>
        <nav class="nav">
            <a href="#">Home</a>
            <a href="#">Work</a>
            <a href="#">About</a>
            <a href="#">Contact</a>
        </nav>
    </header>
    
    <!-- Main Content -->
    <div class="main-wrapper">
        <!-- Sidebar -->
        <aside class="sidebar">
            <h3>Categories</h3>
            <ul class="category-list">
                <li>Photography</li>
                <li>Design</li>
                <li>Illustration</li>
                <li>Web Dev</li>
            </ul>
        </aside>
        
        <!-- Content Area -->
        <main class="content">
            <h1>My Work</h1>
            <div class="portfolio-grid">
                <!-- Create 6 cards -->
                <div class="portfolio-card">
                    <img src="https://via.placeholder.com/300x200" alt="Project">
                    <h3>Project 1</h3>
                    <p>Description here</p>
                    <button>View More</button>
                </div>
                <!-- Add 5 more cards... -->
            </div>
        </main>
    </div>
    
    <!-- Footer -->
    <footer class="footer">
        <p>&copy; 2024 My Portfolio</p>
        <div class="social-links">
            <a href="#">Twitter</a>
            <a href="#">GitHub</a>
            <a href="#">LinkedIn</a>
        </div>
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

/* Challenge 1: Full page layout */
body {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    font-family: 'Segoe UI', Arial, sans-serif;
    background: #f5f5f5;
}

/* Challenge 2: Header with nav */
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.logo {
    font-size: 1.5rem;
    font-weight: bold;
}

.nav {
    display: flex;
    gap: 2rem;
}

.nav a {
    color: white;
    text-decoration: none;
    padding: 0.5rem 1rem;
    border-radius: 5px;
    transition: background 0.3s;
}

.nav a:hover {
    background: rgba(255,255,255,0.2);
}

/* Challenge 3: Main layout with sidebar */
.main-wrapper {
    display: flex;
    flex: 1; /* Take remaining space */
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
    padding: 2rem;
    gap: 2rem;
}

.sidebar {
    flex: 0 0 200px; /* Fixed width */
    background: white;
    padding: 1.5rem;
    border-radius: 10px;
    height: fit-content;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.sidebar h3 {
    margin-bottom: 1rem;
    color: #333;
}

.category-list {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    list-style: none;
}

.category-list li {
    padding: 0.5rem;
    cursor: pointer;
    border-radius: 5px;
    transition: background 0.3s;
}

.category-list li:hover {
    background: #f0f0f0;
}

.content {
    flex: 1; /* Take remaining space */
}

.content h1 {
    margin-bottom: 2rem;
    color: #333;
}

/* Challenge 4: Card grid */
.portfolio-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
    justify-content: center;
}

.portfolio-card {
    flex: 1 1 300px; /* Flexible cards */
    max-width: 350px;
    background: white;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    transition: transform 0.3s;
    
    /* Card is also flex container */
    display: flex;
    flex-direction: column;
}

.portfolio-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 12px rgba(0,0,0,0.15);
}

.portfolio-card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}

.portfolio-card h3 {
    padding: 1rem 1rem 0.5rem;
    color: #333;
}

.portfolio-card p {
    padding: 0 1rem;
    color: #666;
    flex: 1; /* Push button to bottom */
}

.portfolio-card button {
    margin: 1rem;
    padding: 0.75rem;
    background: #667eea;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background 0.3s;
}

.portfolio-card button:hover {
    background: #764ba2;
}

/* Challenge 5: Sticky footer */
.footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.5rem 2rem;
    background: #333;
    color: white;
    margin-top: auto; /* Push to bottom */
}

.social-links {
    display: flex;
    gap: 1.5rem;
}

.social-links a {
    color: white;
    text-decoration: none;
    transition: color 0.3s;
}

.social-links a:hover {
    color: #667eea;
}

/* Responsive Design */
@media (max-width: 768px) {
    .main-wrapper {
        flex-direction: column;
    }
    
    .sidebar {
        flex: 1 1 auto;
        order: 2; /* Move below content on mobile */
    }
    
    .content {
        order: 1;
    }
    
    .portfolio-card {
        flex: 1 1 100%;
    }
    
    .nav {
        flex-direction: column;
        gap: 0.5rem;
    }
    
    .footer {
        flex-direction: column;
        gap: 1rem;
    }
}
```

---

## Assessment and Wrap-Up (5 minutes)

### Quick Flexbox Quiz
**Teacher asks, students code the answer:**

1. "How do you center a div perfectly?"
   ```css
   .container {
       display: flex;
       justify-content: center;
       align-items: center;
   }
   ```

2. "Make three equal columns?"
   ```css
   .column { flex: 1; }
   ```

3. "Push last item to the right?"
   ```css
   .last-item { margin-left: auto; }
   ```

### Visual Check
"Show me your portfolio grid - do all cards have equal height?"

---

## Common Student Mistakes & Solutions

### Mistake 1: Applying flex to wrong element
**Problem:** Properties don't work
**Fix:** Flex properties go on container OR items
```css
/* WRONG */
.container {
    align-self: center; /* Item property on container! */
}

/* RIGHT */
.container {
    align-items: center; /* Container property */
}
```

### Mistake 2: Forgetting display: flex
**Problem:** Nothing happens
**Fix:** Always start with display: flex
```css
.container {
    display: flex; /* Required! */
    justify-content: center;
}
```

### Mistake 3: Not understanding axes
**Problem:** Alignment confusion
**Fix:** Remember direction changes axes
```css
.row {
    flex-direction: row;
    justify-content: center; /* Horizontal */
    align-items: center;     /* Vertical */
}

.column {
    flex-direction: column;
    justify-content: center; /* Now vertical! */
    align-items: center;     /* Now horizontal! */
}
```

### Mistake 4: Fighting default stretch
**Problem:** Items unexpectedly tall
**Fix:** Change align-items
```css
.container {
    align-items: flex-start; /* Don't stretch */
}
```

---

## Homework Assignment

### Create a Complete Dashboard Layout
Using ONLY Flexbox, build a dashboard with:

1. **Fixed header** with logo and user menu
2. **Collapsible sidebar** with navigation
3. **Main content area** with statistics cards
4. **Data table** with flexible columns
5. **Footer** that stays at bottom
6. **Responsive** at mobile, tablet, desktop

### Bonus Challenges
- Add a search bar that expands on focus
- Create a notification badge system
- Build a timeline with alternating items
- Make cards flip on hover

### Resources
- [Flexbox Froggy](https://flexboxfroggy.com) - Practice game
- [Flexbox Defense](http://www.flexboxdefense.com) - Tower defense game
- [CSS-Tricks Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- MDN Flexbox Documentation

---

## Next Lesson Preview
"Next time, we'll learn CSS Grid - Flexbox's powerful 2D cousin that lets us create magazine-style layouts!"
