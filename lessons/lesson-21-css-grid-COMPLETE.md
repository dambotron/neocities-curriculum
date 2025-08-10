# Lesson 21: CSS Grid - Two-Dimensional Layout Mastery
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Understand CSS Grid as a two-dimensional layout system
- Create grid containers and define grid tracks
- Place items using grid lines and areas
- Master grid-template properties (columns, rows, areas)
- Use auto-fit and auto-fill for responsive grids
- Implement grid gap and alignment properties
- Create complex magazine-style layouts
- Combine Grid with Flexbox effectively
- Build responsive layouts without media queries
- Debug grids using browser DevTools

### Materials Needed
- Browser with Grid DevTools
- Grid inspector tools
- Graph paper for sketching
- Layout examples (magazines, newspapers)
- Grid terminology reference sheet
- CSS Grid Garden game
- Real-world layout challenges
- Performance monitoring tools

### Key Vocabulary with Definitions
- **Grid Container**: Parent element with display: grid
- **Grid Item**: Direct children of grid container
- **Grid Line**: Dividing lines that create grid structure
- **Grid Track**: Space between two grid lines (row or column)
- **Grid Cell**: Single unit of the grid
- **Grid Area**: Rectangle of one or more cells
- **Grid Gap**: Space between tracks
- **Fr Unit**: Fractional unit (portion of available space)
- **Explicit Grid**: Defined rows/columns
- **Implicit Grid**: Auto-created rows/columns

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding CSS Grid Fundamentals (5 minutes)

**Teacher Script:**
"Imagine you're designing a newspaper layout. You need columns for articles, rows for sections, and some content spans multiple columns. That's CSS Grid! It's like having a perfect graph paper where you can place content exactly where you want it in both directions - not just left-to-right like Flexbox."

**[CREATE new file: css-grid-demo.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Grid Mastery</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', system-ui, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 2rem;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }
        
        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 2rem;
            font-size: 2.5rem;
        }
        
        /* Grid Demo Sections */
        .demo-section {
            margin-bottom: 3rem;
            padding: 1.5rem;
            background: #f8f9fa;
            border-radius: 8px;
        }
        
        .demo-section h2 {
            color: #667eea;
            margin-bottom: 1rem;
        }
        
        /* Visual grid items */
        .grid-item {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 1rem;
            text-align: center;
            border-radius: 5px;
            font-weight: bold;
            display: flex;
            align-items: center;
            justify-content: center;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🎯 CSS Grid Layout System</h1>
        
        <!-- Basic Grid -->
        <div class="demo-section">
            <h2>1. Basic Grid</h2>
            <div class="basic-grid">
                <div class="grid-item">1</div>
                <div class="grid-item">2</div>
                <div class="grid-item">3</div>
                <div class="grid-item">4</div>
                <div class="grid-item">5</div>
                <div class="grid-item">6</div>
            </div>
        </div>
        
        <!-- Template Areas -->
        <div class="demo-section">
            <h2>2. Grid Template Areas</h2>
            <div class="area-grid">
                <div class="grid-item header">Header</div>
                <div class="grid-item sidebar">Sidebar</div>
                <div class="grid-item main">Main Content</div>
                <div class="grid-item footer">Footer</div>
            </div>
        </div>
        
        <!-- Responsive Grid -->
        <div class="demo-section">
            <h2>3. Auto-Responsive Grid</h2>
            <div class="auto-grid">
                <div class="grid-item">Auto</div>
                <div class="grid-item">Responsive</div>
                <div class="grid-item">Grid</div>
                <div class="grid-item">Layout</div>
                <div class="grid-item">Magic</div>
            </div>
        </div>
    </div>
</body>
</html>
```

**[DEMONSTRATE Grid basics]**

```css
/* CSS GRID FUNDAMENTALS */

/* 1. CREATING A GRID */
.basic-grid {
    display: grid; /* Creates grid container */
    
    /* Define columns */
    grid-template-columns: 200px 200px 200px;
    /* OR using repeat */
    grid-template-columns: repeat(3, 200px);
    /* OR using fractions */
    grid-template-columns: 1fr 1fr 1fr;
    /* OR mixed units */
    grid-template-columns: 200px 1fr 200px;
    
    /* Define rows */
    grid-template-rows: 100px 100px;
    /* OR auto rows */
    grid-auto-rows: 100px;
    
    /* Gap between items */
    gap: 1rem; /* Same as grid-gap */
    /* OR different gaps */
    row-gap: 1rem;
    column-gap: 2rem;
}

/* 2. THE FR UNIT - Fractional Unit */
.fraction-grid {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
    /* First: 1 part, Middle: 2 parts, Last: 1 part */
    /* If container is 1000px: 250px, 500px, 250px */
}

/* 3. REPEAT FUNCTION */
.repeat-grid {
    display: grid;
    /* Simple repeat */
    grid-template-columns: repeat(4, 1fr);
    
    /* Repeat pattern */
    grid-template-columns: repeat(3, 1fr 2fr);
    /* Creates: 1fr 2fr 1fr 2fr 1fr 2fr */
    
    /* Auto-fill - Create as many columns as fit */
    grid-template-columns: repeat(auto-fill, 200px);
    
    /* Auto-fit - Same but collapse empty columns */
    grid-template-columns: repeat(auto-fit, 200px);
}

/* 4. MINMAX FUNCTION */
.flexible-grid {
    display: grid;
    /* Columns at least 200px, max 1fr */
    grid-template-columns: repeat(3, minmax(200px, 1fr));
    
    /* Responsive without media queries! */
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
}

/* 5. GRID LINES */
.line-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 100px);
}

.span-item {
    /* Place using line numbers */
    grid-column-start: 1;
    grid-column-end: 3;
    /* OR shorthand */
    grid-column: 1 / 3;
    
    /* Span multiple cells */
    grid-column: span 2;
    grid-row: span 2;
    
    /* Negative line numbers (from end) */
    grid-column: 1 / -1; /* Full width */
}
```

### Grid Template Areas - Visual Layout (5 minutes)

**[DEMONSTRATE template areas]**

```css
/* GRID TEMPLATE AREAS - Visual ASCII Art! */

.area-grid {
    display: grid;
    grid-template-columns: 200px 1fr;
    grid-template-rows: auto 1fr auto;
    gap: 1rem;
    min-height: 400px;
    
    /* Define areas visually! */
    grid-template-areas:
        "header  header"
        "sidebar main"
        "footer  footer";
}

/* Assign items to areas */
.header {
    grid-area: header;
    background: #e74c3c;
}

.sidebar {
    grid-area: sidebar;
    background: #3498db;
}

.main {
    grid-area: main;
    background: #2ecc71;
}

.footer {
    grid-area: footer;
    background: #f39c12;
}

/* Complex magazine layout */
.magazine-layout {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(4, minmax(100px, auto));
    gap: 1rem;
    grid-template-areas:
        "hero    hero    hero    sidebar"
        "hero    hero    hero    ad1"
        "article article article ad2"
        "foot    foot    foot    foot";
}

/* Responsive areas with media queries */
@media (max-width: 768px) {
    .area-grid {
        grid-template-columns: 1fr;
        grid-template-areas:
            "header"
            "main"
            "sidebar"
            "footer";
    }
}

/* Named lines for precision */
.named-line-grid {
    display: grid;
    grid-template-columns: 
        [sidebar-start] 200px 
        [sidebar-end main-start] 1fr 
        [main-end];
    grid-template-rows:
        [header-start] auto
        [header-end content-start] 1fr
        [content-end footer-start] auto
        [footer-end];
}

.placed-item {
    grid-column: sidebar-start / main-end;
    grid-row: header-start / content-end;
}
```

### Advanced Grid Techniques (5 minutes)

**[DEMONSTRATE advanced features]**

```css
/* ADVANCED GRID TECHNIQUES */

/* 1. AUTO-FIT vs AUTO-FILL */
.auto-fill-demo {
    display: grid;
    /* Creates empty columns if space available */
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    /* Container 1000px, items 200px = 5 columns (some empty) */
}

.auto-fit-demo {
    display: grid;
    /* Expands items to fill space */
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    /* Container 1000px, 3 items = 3 columns (expanded) */
}

/* 2. GRID AUTO FLOW */
.auto-flow-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-flow: row;    /* Default - fill by rows */
    /* grid-auto-flow: column;  Fill by columns */
    /* grid-auto-flow: dense;   Fill gaps */
    grid-auto-flow: row dense; /* Combine */
}

/* 3. ALIGNMENT IN GRID */
.aligned-grid {
    display: grid;
    grid-template-columns: repeat(3, 100px);
    grid-template-rows: repeat(2, 100px);
    height: 400px;
    
    /* Align all items (like flexbox) */
    justify-items: center;  /* Horizontal in cell */
    align-items: center;    /* Vertical in cell */
    /* Shorthand */
    place-items: center center;
    
    /* Align the grid itself */
    justify-content: center; /* Horizontal in container */
    align-content: center;   /* Vertical in container */
    /* Shorthand */
    place-content: center center;
}

/* Individual item alignment */
.special-item {
    justify-self: end;
    align-self: start;
    /* Shorthand */
    place-self: start end;
}

/* 4. SUBGRID (When supported) */
.parent-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
}

.child-grid {
    display: grid;
    grid-column: span 2;
    /* Inherit parent's grid */
    grid-template-columns: subgrid;
}

/* 5. MASONRY LAYOUT (Experimental) */
.masonry-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-template-rows: masonry; /* When supported */
}

/* 6. RESPONSIVE WITHOUT MEDIA QUERIES */
.responsive-grid {
    display: grid;
    /* The holy grail of responsive */
    grid-template-columns: 
        repeat(auto-fit, minmax(min(100%, 300px), 1fr));
    gap: 1rem;
}

/* 7. LAYERING WITH GRID */
.layered-grid {
    display: grid;
    grid-template: 1fr / 1fr;
}

.layered-grid > * {
    grid-area: 1 / 1; /* All items in same cell */
}

.background-layer {
    z-index: 1;
}

.content-layer {
    z-index: 2;
}

.overlay-layer {
    z-index: 3;
}
```

---

## PART 2: WE DO (Guided Practice) - 15 minutes

### Activity 1: Build a Dashboard Layout (7 minutes)

**Teacher Instructions:**
1. Create a complex dashboard layout together
2. Use grid-template-areas for clarity
3. Make it responsive
4. Show DevTools grid inspector

**[BUILD TOGETHER]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grid Dashboard</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: system-ui, -apple-system, sans-serif;
            background: #f0f2f5;
            min-height: 100vh;
        }
        
        /* Dashboard Container */
        .dashboard {
            display: grid;
            grid-template-columns: 250px 1fr;
            grid-template-rows: 60px 1fr;
            grid-template-areas:
                "sidebar header"
                "sidebar main";
            height: 100vh;
        }
        
        /* Header */
        .header {
            grid-area: header;
            background: white;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: flex;
            align-items: center;
            padding: 0 2rem;
            justify-content: space-between;
        }
        
        .header h1 {
            font-size: 1.5rem;
            color: #333;
        }
        
        .user-menu {
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        
        .avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea, #764ba2);
        }
        
        /* Sidebar */
        .sidebar {
            grid-area: sidebar;
            background: #2c3e50;
            color: white;
            padding: 1rem;
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            padding: 1rem;
            margin-bottom: 2rem;
            text-align: center;
            background: rgba(255,255,255,0.1);
            border-radius: 8px;
        }
        
        .nav-item {
            padding: 1rem;
            margin-bottom: 0.5rem;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        .nav-item:hover {
            background: rgba(255,255,255,0.1);
        }
        
        .nav-item.active {
            background: #3498db;
        }
        
        /* Main Content Area */
        .main {
            grid-area: main;
            padding: 2rem;
            overflow-y: auto;
        }
        
        /* Stats Grid */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }
        
        .stat-card {
            background: white;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: grid;
            gap: 0.5rem;
        }
        
        .stat-label {
            color: #6c757d;
            font-size: 0.875rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        
        .stat-value {
            font-size: 2rem;
            font-weight: bold;
            color: #333;
        }
        
        .stat-change {
            font-size: 0.875rem;
            color: #28a745;
        }
        
        .stat-change.negative {
            color: #dc3545;
        }
        
        /* Content Grid */
        .content-grid {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 2rem;
        }
        
        .chart-container {
            background: white;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            min-height: 400px;
        }
        
        .activity-feed {
            background: white;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        
        .activity-item {
            padding: 1rem;
            border-bottom: 1px solid #e9ecef;
            display: grid;
            grid-template-columns: 40px 1fr;
            gap: 1rem;
            align-items: start;
        }
        
        .activity-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: #e9ecef;
            display: grid;
            place-items: center;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .dashboard {
                grid-template-columns: 1fr;
                grid-template-rows: 60px 1fr;
                grid-template-areas:
                    "header"
                    "main";
            }
            
            .sidebar {
                display: none;
                position: fixed;
                left: 0;
                top: 60px;
                bottom: 0;
                width: 250px;
                z-index: 1000;
            }
            
            .sidebar.active {
                display: block;
            }
            
            .content-grid {
                grid-template-columns: 1fr;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
        }
        
        /* Advanced Grid Features */
        .data-table {
            display: grid;
            grid-template-columns: 
                50px 
                minmax(150px, 2fr) 
                repeat(3, minmax(100px, 1fr)) 
                100px;
            background: white;
            border-radius: 10px;
            overflow: hidden;
            margin-top: 2rem;
        }
        
        .table-header {
            background: #f8f9fa;
            padding: 1rem;
            font-weight: bold;
            color: #6c757d;
            border-bottom: 2px solid #e9ecef;
        }
        
        .table-row {
            display: contents; /* Magic! */
        }
        
        .table-row:hover > * {
            background: #f8f9fa;
        }
        
        .table-cell {
            padding: 1rem;
            border-bottom: 1px solid #e9ecef;
            display: flex;
            align-items: center;
        }
    </style>
</head>
<body>
    <div class="dashboard">
        <!-- Header -->
        <header class="header">
            <h1>Dashboard</h1>
            <div class="user-menu">
                <span>John Doe</span>
                <div class="avatar"></div>
            </div>
        </header>
        
        <!-- Sidebar -->
        <aside class="sidebar">
            <div class="logo">GridApp</div>
            <nav>
                <div class="nav-item active">📊 Dashboard</div>
                <div class="nav-item">📈 Analytics</div>
                <div class="nav-item">👥 Users</div>
                <div class="nav-item">📦 Products</div>
                <div class="nav-item">⚙️ Settings</div>
            </nav>
        </aside>
        
        <!-- Main Content -->
        <main class="main">
            <!-- Stats Cards -->
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-label">Total Revenue</div>
                    <div class="stat-value">$45,231</div>
                    <div class="stat-change">+12.5% from last month</div>
                </div>
                <div class="stat-card">
                    <div class="stat-label">Active Users</div>
                    <div class="stat-value">8,549</div>
                    <div class="stat-change">+5.2% from last month</div>
                </div>
                <div class="stat-card">
                    <div class="stat-label">Conversion Rate</div>
                    <div class="stat-value">3.24%</div>
                    <div class="stat-change negative">-0.5% from last month</div>
                </div>
                <div class="stat-card">
                    <div class="stat-label">Avg. Order Value</div>
                    <div class="stat-value">$142</div>
                    <div class="stat-change">+8.1% from last month</div>
                </div>
            </div>
            
            <!-- Content Grid -->
            <div class="content-grid">
                <div class="chart-container">
                    <h2>Revenue Overview</h2>
                    <p>Chart would go here</p>
                </div>
                <div class="activity-feed">
                    <h2>Recent Activity</h2>
                    <div class="activity-item">
                        <div class="activity-icon">🛒</div>
                        <div>
                            <strong>New order #1234</strong>
                            <div>2 minutes ago</div>
                        </div>
                    </div>
                    <div class="activity-item">
                        <div class="activity-icon">👤</div>
                        <div>
                            <strong>New user registered</strong>
                            <div>15 minutes ago</div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Data Table -->
            <div class="data-table">
                <div class="table-header">#</div>
                <div class="table-header">Product</div>
                <div class="table-header">Price</div>
                <div class="table-header">Stock</div>
                <div class="table-header">Sales</div>
                <div class="table-header">Action</div>
                
                <div class="table-row">
                    <div class="table-cell">1</div>
                    <div class="table-cell">Product A</div>
                    <div class="table-cell">$99</div>
                    <div class="table-cell">45</div>
                    <div class="table-cell">234</div>
                    <div class="table-cell">
                        <button>Edit</button>
                    </div>
                </div>
            </div>
        </main>
    </div>
</body>
</html>
```

### Activity 2: Magazine Layout with Grid (8 minutes)

**Teacher Instructions:**
1. Create a complex magazine layout
2. Use spanning and areas
3. Show different content arrangements
4. Implement auto-flow for articles

**[CREATE magazine layout together]**

```css
/* Magazine Layout with CSS Grid */

.magazine {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    grid-auto-rows: minmax(100px, auto);
    gap: 1.5rem;
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
}

/* Feature Article - Spans 8 columns, 4 rows */
.feature-article {
    grid-column: span 8;
    grid-row: span 4;
    background: linear-gradient(135deg, #667eea, #764ba2);
    color: white;
    padding: 3rem;
    display: grid;
    align-content: end;
}

/* Sidebar Ad - Spans 4 columns, 2 rows */
.sidebar-ad {
    grid-column: span 4;
    grid-row: span 2;
    background: #f8f9fa;
    padding: 1.5rem;
    text-align: center;
}

/* Regular Articles */
.article {
    grid-column: span 4;
    grid-row: span 3;
    background: white;
    padding: 1.5rem;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

/* Quote Block */
.quote {
    grid-column: span 6;
    grid-row: span 2;
    background: #2c3e50;
    color: white;
    padding: 2rem;
    display: grid;
    place-items: center;
    font-size: 1.5rem;
    font-style: italic;
}

/* Image Gallery */
.gallery {
    grid-column: span 12;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1rem;
}

/* Breaking layout rules */
.overlap-element {
    grid-column: 7 / 11;
    grid-row: 3 / 5;
    z-index: 10;
    background: rgba(255,255,255,0.95);
    box-shadow: 0 10px 30px rgba(0,0,0,0.2);
}
```

---

## PART 3: YOU DO (Independent Practice) - 15 minutes

### Individual Challenge: Portfolio Grid Layout (15 minutes)

**Student Instructions:**
"Create a creative portfolio layout using CSS Grid. Build something unique that showcases Grid's power - think outside the box!"

**Requirements Checklist:**
```
□ Use display: grid
□ Define explicit grid with template
□ Use grid-template-areas for at least one section
□ Implement auto-fit or auto-fill
□ Use fr units effectively
□ Span items across multiple cells
□ Create a responsive layout (no media queries preferred)
□ Use minmax() for flexibility
□ Implement proper alignment
□ Layer elements using grid
□ Use grid-auto-flow for dynamic content
□ Combine Grid with Flexbox where appropriate
□ Create an asymmetric layout
□ Use named grid lines (bonus)
□ Implement subgrid if supported (bonus)
```

**Starter Template:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grid Portfolio Challenge</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        /* TODO: Your Grid Layout */
        
        .portfolio {
            /* Create your grid container */
        }
        
        /* TODO: Grid areas */
        
        /* TODO: Responsive without media queries */
        
        /* TODO: Creative spanning */
        
    </style>
</head>
<body>
    <div class="portfolio">
        <!-- Build your creative layout -->
    </div>
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

body {
    font-family: 'Segoe UI', system-ui, sans-serif;
    background: #0a0a0a;
    color: white;
    min-height: 100vh;
}

/* Creative Portfolio Grid */
.portfolio {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    grid-auto-rows: 80px;
    gap: 2px;
    max-width: 1400px;
    margin: 0 auto;
    padding: 2rem;
    background: #111;
}

/* Hero Section */
.hero {
    grid-column: 1 / -1;
    grid-row: span 6;
    background: linear-gradient(135deg, #667eea, #764ba2);
    display: grid;
    place-items: center;
    text-align: center;
    padding: 3rem;
    position: relative;
    overflow: hidden;
}

.hero::before {
    content: '';
    position: absolute;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle, transparent, rgba(0,0,0,0.5));
    animation: pulse 3s ease-in-out infinite;
}

@keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.1); }
}

.hero h1 {
    font-size: clamp(2rem, 5vw, 4rem);
    z-index: 1;
    position: relative;
}

/* Project Grid */
.projects {
    grid-column: 1 / -1;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1rem;
    padding: 2rem 0;
}

.project {
    aspect-ratio: 1;
    background: #1a1a1a;
    border: 1px solid #333;
    display: grid;
    place-items: center;
    transition: all 0.3s ease;
    cursor: pointer;
    position: relative;
    overflow: hidden;
}

.project:hover {
    transform: scale(1.05);
    border-color: #667eea;
    z-index: 10;
}

.project::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, transparent, #667eea);
    opacity: 0;
    transition: opacity 0.3s;
}

.project:hover::before {
    opacity: 0.3;
}

/* Featured Project */
.featured {
    grid-column: 2 / 8;
    grid-row: span 5;
    background: linear-gradient(135deg, #e74c3c, #c0392b);
    padding: 2rem;
    display: grid;
    align-content: end;
}

/* Info Cards */
.info-card {
    background: #1a1a1a;
    border: 1px solid #333;
    padding: 1.5rem;
    display: grid;
    gap: 0.5rem;
}

.info-card:nth-child(odd) {
    grid-column: span 4;
    grid-row: span 3;
}

.info-card:nth-child(even) {
    grid-column: span 3;
    grid-row: span 4;
}

/* Skills Grid */
.skills {
    grid-column: 9 / -1;
    grid-row: span 5;
    background: #1a1a1a;
    padding: 1.5rem;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
}

.skill {
    background: #0a0a0a;
    padding: 1rem;
    text-align: center;
    border-radius: 8px;
    border: 1px solid #333;
}

/* Timeline */
.timeline {
    grid-column: 1 / -1;
    grid-row: span 3;
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 1rem;
    padding: 2rem 0;
}

.timeline-item {
    background: #1a1a1a;
    padding: 1rem;
    text-align: center;
    border-left: 3px solid #667eea;
    position: relative;
}

.timeline-item::before {
    content: '';
    position: absolute;
    left: -8px;
    top: 50%;
    width: 12px;
    height: 12px;
    background: #667eea;
    border-radius: 50%;
}

/* Contact Section */
.contact {
    grid-column: 1 / -1;
    grid-row: span 4;
    background: linear-gradient(135deg, #2c3e50, #34495e);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    padding: 3rem;
}

.contact-info {
    display: grid;
    gap: 1rem;
    align-content: center;
}

.contact-form {
    display: grid;
    gap: 1rem;
}

.form-group {
    display: grid;
    gap: 0.5rem;
}

.form-group input,
.form-group textarea {
    background: rgba(255,255,255,0.1);
    border: 1px solid rgba(255,255,255,0.2);
    padding: 0.75rem;
    color: white;
    border-radius: 4px;
}

/* Floating Elements */
.floating-badge {
    grid-column: 11 / -1;
    grid-row: 8 / 10;
    background: #f39c12;
    color: #000;
    display: grid;
    place-items: center;
    font-weight: bold;
    border-radius: 50%;
    z-index: 20;
    animation: float 3s ease-in-out infinite;
}

@keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
}

/* Responsive adjustments */
@media (max-width: 768px) {
    .portfolio {
        grid-template-columns: repeat(6, 1fr);
        grid-auto-rows: 60px;
    }
    
    .featured {
        grid-column: 1 / -1;
    }
    
    .skills {
        grid-column: 1 / -1;
    }
    
    .contact {
        grid-template-columns: 1fr;
    }
}

/* Print styles */
@media print {
    .portfolio {
        display: block;
    }
    
    .project {
        page-break-inside: avoid;
    }
}
```

---

## Assessment and Wrap-Up (5 minutes)

### Quick Grid Challenge
**Teacher provides layout, students write grid code:**

1. "Create a 3x3 grid with 1rem gap"
   ```css
   display: grid;
   grid-template-columns: repeat(3, 1fr);
   grid-template-rows: repeat(3, 1fr);
   gap: 1rem;
   ```

2. "Make header span full width"
   ```css
   .header { grid-column: 1 / -1; }
   ```

3. "Responsive grid without media queries"
   ```css
   grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
   ```

### Visual Check
"Open DevTools Grid inspector - show me your grid lines!"

---

## Common Student Mistakes & Solutions

### Mistake 1: Forgetting display: grid
**Problem:** Nothing happens
**Fix:** Always start with display: grid
```css
.container {
    display: grid; /* Required! */
    grid-template-columns: 1fr 1fr;
}
```

### Mistake 2: Direct children only
**Problem:** Nested elements don't follow grid
**Fix:** Only direct children are grid items
```css
/* Only immediate children become grid items */
.grid > div { /* Direct children */ }
.grid div { /* All descendants - won't work as expected */ }
```

### Mistake 3: Fr units confusion
**Problem:** Unexpected sizing
**Fix:** Fr is remaining space after fixed units
```css
/* 200px taken first, then remaining split */
grid-template-columns: 200px 1fr 2fr;
```

### Mistake 4: Line numbers off by one
**Problem:** Items not placed correctly
**Fix:** Lines start at 1, not 0
```css
/* 3 columns = 4 lines (1,2,3,4) */
.item { grid-column: 1 / 4; /* Spans 3 columns */ }
```

### Mistake 5: Auto-fit vs auto-fill confusion
**Problem:** Wrong responsive behavior
**Fix:** Understand the difference
```css
/* auto-fill: keeps empty columns */
/* auto-fit: collapses empty columns */
```

---

## Homework Assignment

### Create a News Website Layout
Build a complete news site using CSS Grid:

1. **Header** with logo and navigation
2. **Featured story** that spans multiple columns
3. **Article grid** with varied sizes
4. **Sidebar** with ads and widgets
5. **Image gallery** section
6. **Footer** with multiple columns

### Requirements:
- Use grid-template-areas for main layout
- Implement auto-fit for article cards
- No media queries for main responsiveness
- Use subgrid if browser supports
- Layer elements creatively
- Mix Grid and Flexbox appropriately

### Bonus Challenges:
- Add a masonry-style photo section
- Create a calendar widget with Grid
- Build a pricing table with Grid
- Implement a chess board layout

---

## Resources
- [CSS Grid Garden](https://cssgridgarden.com) - Interactive game
- [Grid by Example](https://gridbyexample.com) - Rachel Andrew's examples
- [CSS Grid Generator](https://cssgrid-generator.netlify.app)
- Firefox Grid Inspector (best DevTools for Grid)
- [Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

---

## Next Lesson Preview
"Next time, we'll bring your sites to life with CSS animations and transitions - make things move, bounce, and delight your users!"
