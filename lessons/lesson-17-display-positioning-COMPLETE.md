# Lesson 17: Display Properties and Positioning - Controlling Element Flow
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Understand and use all display property values
- Master position properties (static, relative, absolute, fixed, sticky)
- Control element stacking with z-index
- Create overlays and modals with positioning
- Build fixed headers and sticky sidebars
- Understand normal document flow
- Remove elements from flow when needed
- Create complex layouts combining display and position

### Materials Needed
- Text editor with syntax highlighting
- Web browser with developer tools
- Projector for demonstrations
- Display property reference sheet
- Position property diagrams
- Sticky notes (for physical demonstration)
- Sample layouts showing different techniques
- Z-index stacking examples

### Key Vocabulary with Definitions
- **Display**: How element generates boxes
- **Block**: Full width, stacks vertically
- **Inline**: Flows with text, no width/height
- **Inline-block**: Inline but accepts dimensions
- **None**: Removes from document
- **Static**: Default position in flow
- **Relative**: Positioned relative to normal position
- **Absolute**: Positioned relative to positioned parent
- **Fixed**: Positioned relative to viewport
- **Sticky**: Hybrid of relative and fixed
- **Z-index**: Stacking order of elements

---
## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding Display Properties (5 minutes)

**Teacher Script:**
"Think of display properties like different types of Lego blocks. Some take up a whole row (block), some sit next to each other (inline), and some can do both (inline-block). Position properties are like instructions for where to place these blocks - follow the rules (static) or break free (absolute)!"

**[CREATE new file: display-position-demo.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Display & Position Mastery</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            padding-top: 80px; /* Space for fixed header */
            background: #f5f5f5;
            min-height: 200vh; /* For scroll demonstration */
        }
        
        .demo-section {
            background: white;            padding: 20px;
            margin-bottom: 30px;
            border-radius: 8px;
        }
    </style>
</head>
<body>
    <!-- Fixed Header -->
    <header class="fixed-header">
        <h1>Display & Position Demo</h1>
    </header>
    
    <!-- Display Properties -->
    <div class="demo-section">
        <h2>Display Properties</h2>
        <div class="display-block">Block Element</div>
        <span class="display-inline">Inline 1</span>
        <span class="display-inline">Inline 2</span>
        <div class="display-inline-block">Inline-Block</div>
        <div class="display-none">Hidden Element</div>
        <div class="display-flex">Flex Container</div>
    </div>
    
    <!-- Position Properties -->
    <div class="demo-section position-container">
        <h2>Position Properties</h2>
        <div class="position-static">Static (default)</div>
        <div class="position-relative">Relative Position</div>
        <div class="position-absolute">Absolute Position</div>
        <div class="position-sticky">Sticky Position</div>    </div>
    
    <!-- Z-Index Stacking -->
    <div class="demo-section">
        <h2>Z-Index Stacking</h2>
        <div class="stack-container">
            <div class="stack-1">Layer 1 (z-index: 1)</div>
            <div class="stack-2">Layer 2 (z-index: 2)</div>
            <div class="stack-3">Layer 3 (z-index: 3)</div>
        </div>
    </div>
</body>
</html>
```

**[DEMONSTRATE display properties]**

```css
/* DISPLAY PROPERTIES EXPLAINED */

/* 1. BLOCK - Takes full width, stacks vertically */
.display-block {
    display: block;
    background: #3498db;
    color: white;
    padding: 10px;
    margin-bottom: 10px;
    /* Accepts width, height, margin, padding */
}

/* Block elements: div, p, h1-h6, section, article, etc. */

/* 2. INLINE - Flows with text, no dimensions */
.display-inline {    display: inline;
    background: #e74c3c;
    color: white;
    padding: 5px 10px;
    margin: 5px; /* Only horizontal margin works properly */
    /* CANNOT set width or height! */
    /* Vertical padding/margin behaves strangely */
}

/* Inline elements: span, a, strong, em, etc. */

/* 3. INLINE-BLOCK - Best of both worlds */
.display-inline-block {
    display: inline-block;
    background: #9b59b6;
    color: white;
    padding: 10px 20px;
    margin: 10px;
    width: 150px; /* CAN set dimensions! */
    height: 50px;
    vertical-align: top; /* Aligns with other inline elements */
}

/* 4. NONE - Completely removes element */
.display-none {
    display: none; /* Gone from document */
    /* Different from visibility: hidden (keeps space) */
}

/* 5. FLEX - Modern layout (covered in detail later) */
.display-flex {
    display: flex;    gap: 10px;
    background: #16a085;
    padding: 10px;
}

/* Visibility vs Display */
.invisible {
    visibility: hidden; /* Space remains, just invisible */
}

.removed {
    display: none; /* Space gone, element removed */
}
```

### Position Properties Explained (5 minutes)

**[DEMONSTRATE position values]**

```css
/* POSITION PROPERTIES - Where elements go */

/* 1. STATIC - Default, follows normal flow */
.position-static {
    position: static;
    /* top, right, bottom, left DON'T work */
    background: #95a5a6;
    padding: 10px;
    margin-bottom: 10px;
}

/* 2. RELATIVE - Relative to normal position */
.position-relative {
    position: relative;    top: 20px;    /* Moves 20px down from normal */
    left: 30px;   /* Moves 30px right from normal */
    background: #f39c12;
    padding: 10px;
    /* Original space is preserved! */
}

/* 3. ABSOLUTE - Relative to positioned parent */
.position-container {
    position: relative; /* Creates positioning context */
    height: 300px;
    border: 2px dashed #34495e;
}

.position-absolute {
    position: absolute;
    top: 50px;
    right: 20px;
    background: #e74c3c;
    color: white;
    padding: 10px;
    /* Removed from normal flow! */
    /* Positioned relative to .position-container */
}

/* 4. FIXED - Relative to viewport */
.fixed-header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background: #2c3e50;    color: white;
    padding: 20px;
    z-index: 1000;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    /* Stays in place when scrolling */
}

/* 5. STICKY - Hybrid of relative and fixed */
.position-sticky {
    position: sticky;
    top: 100px; /* Sticks 100px from top when scrolling */
    background: #27ae60;
    color: white;
    padding: 10px;
    /* Acts relative until scroll threshold, then fixed */
}

/* Common positioning patterns */
.centered-absolute {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    /* Perfect centering */
}

.full-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;    background: rgba(0,0,0,0.8);
    /* Covers entire viewport */
}
```

### Z-Index and Stacking Context (5 minutes)

**[DEMONSTRATE stacking order]**

```css
/* Z-INDEX - Control stacking order */

.stack-container {
    position: relative;
    height: 200px;
}

.stack-1 {
    position: absolute;
    top: 20px;
    left: 20px;
    width: 150px;
    height: 100px;
    background: #3498db;
    z-index: 1;
}

.stack-2 {
    position: absolute;
    top: 40px;
    left: 40px;
    width: 150px;
    height: 100px;
    background: #e74c3c;
    z-index: 2; /* On top of stack-1 */}

.stack-3 {
    position: absolute;
    top: 60px;
    left: 60px;
    width: 150px;
    height: 100px;
    background: #f39c12;
    z-index: 3; /* On top of everything */
}

/* Z-index rules:
   - Only works on positioned elements (not static)
   - Higher number = higher in stack
   - Can be negative
   - Creates stacking context */

/* Stacking context trap */
.parent-context {
    position: relative;
    z-index: 1; /* Creates new stacking context */
}

.child-high-z {
    position: absolute;
    z-index: 9999; /* Still below elements outside parent! */
}
```

---

## PART 2: WE DO (Guided Practice) - 15 minutes

### Activity 1: Build a Modal Overlay (7 minutes)
**Teacher Instructions:**
1. Create a modal system together
2. Apply positioning for overlay and content
3. Handle z-index stacking
4. Make it responsive

**[BUILD TOGETHER]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Modal System</title>
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
        
        /* Page content */
        .page-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .open-modal-btn {            padding: 10px 20px;
            background: #3498db;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        
        /* Modal overlay */
        .modal-overlay {
            display: none; /* Hidden by default */
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.7);
            z-index: 1000;
        }
        
        /* Show modal */
        .modal-overlay.active {
            display: block;
        }
        
        /* Modal content */
        .modal-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);            background: white;
            padding: 30px;
            border-radius: 10px;
            width: 90%;
            max-width: 500px;
            max-height: 90vh;
            overflow-y: auto;
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #eee;
        }
        
        .close-btn {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: #999;
        }
        
        .close-btn:hover {
            color: #333;
        }
    </style>
</head>
<body>    <div class="page-content">
        <h1>Page with Modal</h1>
        <button class="open-modal-btn">Open Modal</button>
        <p>Lorem ipsum content...</p>
    </div>
    
    <div class="modal-overlay" id="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2>Modal Title</h2>
                <button class="close-btn">&times;</button>
            </div>
            <div class="modal-body">
                <p>Modal content goes here!</p>
            </div>
        </div>
    </div>
</body>
</html>
```

**Key Discussion Points:**
1. Why use fixed positioning for overlay?
2. How does transform center the modal?
3. Why high z-index value?
4. What happens without overflow-y: auto?

### Activity 2: Sticky Navigation System (8 minutes)

**Teacher Instructions:**
1. Create navigation that becomes sticky
2. Add visual feedback when stuck3. Handle different scroll scenarios
4. Discuss browser support

**[CREATE TOGETHER]**

```css
/* Sticky Navigation System */
.site-header {
    background: white;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.site-nav {
    position: sticky;
    top: 0;
    background: #34495e;
    z-index: 100;
    transition: all 0.3s ease;
}

/* Visual feedback when stuck */
.site-nav.is-stuck {
    box-shadow: 0 2px 10px rgba(0,0,0,0.2);
    background: #2c3e50;
}

.nav-list {
    display: flex;
    list-style: none;
    padding: 0;
    margin: 0;
}

.nav-item {    flex: 1;
}

.nav-link {
    display: block;
    padding: 15px 20px;
    color: white;
    text-decoration: none;
    text-align: center;
    transition: background 0.3s;
}

.nav-link:hover {
    background: rgba(255,255,255,0.1);
}

/* Sticky sidebar pattern */
.layout-with-sidebar {
    display: flex;
    gap: 30px;
    max-width: 1200px;
    margin: 0 auto;
}

.sidebar {
    width: 300px;
    position: sticky;
    top: 20px;
    height: fit-content;
}

.main-content {
    flex: 1;
    min-height: 150vh; /* For scroll demo */}
```

---

## PART 3: YOU DO (Independent Practice) - 15 minutes

### Individual Challenge: Interactive Layout System (15 minutes)

**Student Instructions:**
"Create a complex layout using display and position properties. Build an interactive page with fixed header, sticky sidebar, modal popups, and tooltips!"

**HTML Starter Template:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Display & Position Mastery</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: Arial, sans-serif;
            background: #f5f5f5;
            min-height: 200vh; /* For scroll testing */
        }
        
        /* TODO: Your CSS here */
        
        /* Challenge 1: Fixed header */        .header {
            /* TODO: Fix to top of viewport */
        }
        
        /* Challenge 2: Sticky sidebar */
        .sidebar {
            /* TODO: Sticky positioning */
        }
        
        /* Challenge 3: Dropdown menu */
        .dropdown {
            /* TODO: Position dropdown content */
        }
        
        /* Challenge 4: Tooltip on hover */
        .tooltip {
            /* TODO: Position tooltip */
        }
        
        /* Challenge 5: Floating action button */
        .fab {
            /* TODO: Fixed position bottom-right */
        }
        
        /* Challenge 6: Card with badge */
        .card {
            /* TODO: Position badge absolutely */
        }
    </style>
</head>
<body>
    <!-- Fixed Header -->
    <header class="header">        <div class="header-content">
            <h1>My Website</h1>
            <nav class="main-nav">
                <div class="dropdown">
                    <button class="dropdown-btn">Menu</button>
                    <div class="dropdown-content">
                        <a href="#">Option 1</a>
                        <a href="#">Option 2</a>
                        <a href="#">Option 3</a>
                    </div>
                </div>
            </nav>
        </div>
    </header>
    
    <!-- Main Layout -->
    <div class="layout">
        <!-- Sticky Sidebar -->
        <aside class="sidebar">
            <h2>Sidebar</h2>
            <ul>
                <li>Link 1</li>
                <li>Link 2</li>
                <li>Link 3</li>
            </ul>
        </aside>
        
        <!-- Main Content -->
        <main class="content">
            <!-- Cards with badges -->
            <div class="card">
                <span class="badge">New</span>                <h3>Card Title</h3>
                <p>Card content goes here.</p>
            </div>
            
            <!-- Element with tooltip -->
            <div class="has-tooltip">
                Hover for info
                <span class="tooltip">This is a tooltip!</span>
            </div>
        </main>
    </div>
    
    <!-- Floating Action Button -->
    <button class="fab">+</button>
    
    <!-- Modal (hidden by default) -->
    <div class="modal">
        <div class="modal-content">
            <h2>Modal Title</h2>
            <p>Modal content</p>
        </div>
    </div>
</body>
</html>
```

**Requirements Checklist:**
```
□ Fixed header that stays on scroll
□ Sticky sidebar that follows scroll
□ Dropdown menu with absolute positioning
□ Tooltip appears on hover
□ Floating action button (FAB) fixed bottom-right□ Card badges positioned absolutely
□ Modal overlay with centered content
□ Use appropriate z-index values
□ Mix display properties correctly
□ Elements don't overlap incorrectly
□ Responsive behavior maintained
□ Smooth transitions on interactions
□ Dropdown closes when not hovered
□ Tooltip follows cursor (bonus)
□ Page remains scrollable
```

**CSS Solution (for teacher reference):**
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Arial, sans-serif;
    background: #f5f5f5;
    padding-top: 60px; /* Space for fixed header */
    min-height: 200vh;
}

/* Challenge 1: Fixed header */
.header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;    background: #2c3e50;
    color: white;
    padding: 15px 20px;
    z-index: 1000;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.header-content {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Challenge 3: Dropdown menu */
.dropdown {
    position: relative;
    display: inline-block;
}

.dropdown-btn {
    background: #3498db;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

.dropdown-content {
    display: none;
    position: absolute;    top: 100%;
    right: 0;
    background: white;
    min-width: 160px;
    box-shadow: 0 8px 16px rgba(0,0,0,0.1);
    border-radius: 5px;
    overflow: hidden;
    z-index: 1;
}

.dropdown:hover .dropdown-content {
    display: block;
}

.dropdown-content a {
    display: block;
    padding: 12px 16px;
    color: #333;
    text-decoration: none;
    transition: background 0.3s;
}

.dropdown-content a:hover {
    background: #f1f1f1;
}

/* Main layout */
.layout {
    max-width: 1200px;
    margin: 20px auto;
    display: flex;
    gap: 30px;
    padding: 0 20px;}

/* Challenge 2: Sticky sidebar */
.sidebar {
    position: sticky;
    top: 80px; /* Below fixed header */
    width: 250px;
    height: fit-content;
    background: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.sidebar h2 {
    margin-bottom: 15px;
    color: #333;
}

.sidebar ul {
    list-style: none;
}

.sidebar li {
    padding: 10px 0;
    border-bottom: 1px solid #eee;
    cursor: pointer;
}

.sidebar li:hover {
    color: #3498db;
}

/* Main content area */.content {
    flex: 1;
}

/* Challenge 6: Card with badge */
.card {
    position: relative;
    background: white;
    padding: 20px;
    border-radius: 10px;
    margin-bottom: 20px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.badge {
    position: absolute;
    top: -10px;
    right: -10px;
    background: #e74c3c;
    color: white;
    padding: 5px 10px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: bold;
}

/* Challenge 4: Tooltip */
.has-tooltip {
    position: relative;
    display: inline-block;
    background: #3498db;
    color: white;
    padding: 10px 20px;    border-radius: 5px;
    cursor: pointer;
    margin: 20px 0;
}

.tooltip {
    display: none;
    position: absolute;
    bottom: 125%;
    left: 50%;
    transform: translateX(-50%);
    background: #333;
    color: white;
    padding: 8px 12px;
    border-radius: 5px;
    white-space: nowrap;
    z-index: 10;
}

.tooltip::after {
    content: '';
    position: absolute;
    top: 100%;
    left: 50%;
    transform: translateX(-50%);
    border: 5px solid transparent;
    border-top-color: #333;
}

.has-tooltip:hover .tooltip {
    display: block;
}

/* Challenge 5: Floating Action Button */.fab {
    position: fixed;
    bottom: 30px;
    right: 30px;
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: #e74c3c;
    color: white;
    border: none;
    font-size: 24px;
    cursor: pointer;
    box-shadow: 0 4px 12px rgba(0,0,0,0.3);
    transition: transform 0.3s;
    z-index: 999;
}

.fab:hover {
    transform: scale(1.1);
}

/* Modal overlay */
.modal {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.8);
    z-index: 2000;
}

.modal-content {    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    padding: 30px;
    border-radius: 10px;
    max-width: 500px;
    width: 90%;
}
```

---

## Assessment and Wrap-Up (5 minutes)

### Quick Display & Position Quiz
**Teacher asks, students respond:**

1. "What's the difference between display: none and visibility: hidden?"
   → none removes from document, hidden keeps space

2. "Which position value is needed for z-index to work?"
   → Any except static (relative, absolute, fixed, sticky)

3. "How do you center an absolute element?"
   → top: 50%, left: 50%, transform: translate(-50%, -50%)

4. "When would you use position: sticky?"
   → Navigation bars, sidebars, table headers

### Layout Check
"Show me your dropdown menu - does it appear above other content?"

---
## Common Student Mistakes & Solutions

### Mistake 1: Z-index not working
**Issue:** Element won't go on top despite high z-index
**Fix:** Element needs position (not static)
```css
.element {
    position: relative; /* or absolute, fixed, sticky */
    z-index: 999;
}
```

### Mistake 2: Absolute positioning chaos
**Problem:** Element appears in wrong place
**Fix:** Parent needs position: relative
```css
.parent {
    position: relative; /* Creates positioning context */
}
.child {
    position: absolute;
    top: 0;
    right: 0;
}
```

### Mistake 3: Fixed element covers content
**Issue:** Fixed header hides page content
**Fix:** Add padding to body
```css
body {
    padding-top: 60px; /* Height of fixed header */
}
```

### Mistake 4: Sticky not working
**Problem:** Position: sticky doesn't stick**Fix:** Check parent overflow and height
```css
/* Parent must not have overflow: hidden */
/* Element needs top/bottom value */
.sticky-element {
    position: sticky;
    top: 20px; /* Required! */
}
```

### Mistake 5: Display inline-block gaps
**Issue:** Unwanted space between inline-block elements
**Fix:** Remove whitespace or use flexbox
```css
/* Option 1: No whitespace in HTML */
/* Option 2: */
.parent {
    font-size: 0; /* Remove space */
}
.child {
    font-size: 16px; /* Reset font */
}
```

---

## Homework Assignment

### Task: Interactive Dashboard Layout
Create a complex dashboard with multiple positioned elements:

**Page Requirements:**
1. **Fixed Header Bar**
   - Logo and navigation
   - User menu dropdown (absolute)
   - Search bar with results overlay

2. **Sticky Sidebar Navigation**   - Collapsible menu items
   - Sticks below header
   - Active state indicators

3. **Dashboard Cards**
   - Statistics with badges (absolute)
   - Hover tooltips
   - Action buttons
   - Progress indicators

4. **Modal System**
   - Multiple modal types
   - Centered content
   - Close button (fixed in modal)
   - Background overlay

5. **Floating Elements**
   - Chat widget (fixed bottom-right)
   - Notification toasts (fixed top-right)
   - Back-to-top button (shows on scroll)

**Technical Requirements:**
- Use all display values (block, inline, inline-block, none, flex)
- Implement all position values (static, relative, absolute, fixed, sticky)
- Create proper z-index stacking (document your layers)
- Build dropdown menus with hover states
- Add smooth transitions for all interactions
- Make tooltips follow cursor (bonus)
- Ensure mobile responsiveness
- No overlapping bugs

**Bonus Challenges:**
- Create sliding side panel
- Build multi-level dropdown
- Add parallax scrolling effect
- Create draggable elements- Implement keyboard navigation

---

## Extension Activities

### For Fast Finishers:
1. **Position Playground**
   - Interactive demo of all position values
   - Visual representation of document flow
   - Z-index layer viewer

2. **Layout Pattern Library**
   - Create 10 common layout patterns
   - Document when to use each
   - Include responsive versions

3. **CSS Animation with Position**
   - Animate position changes
   - Create sliding panels
   - Build carousel with positioning

---

## Teacher Notes & Tips

### Preparation:
- Set up examples of each position type
- Prepare z-index stacking demos
- Have real website examples ready
- Test sticky positioning browser support

### During Class:
- Use physical props to demonstrate stacking
- Show document flow with and without positioning
- Emphasize when to use each position value
- Debug z-index issues together

### Differentiation:
- **Struggling:** Start with display, then simple positioning
- **Advanced:** Introduce transform3d, will-change- **Visual:** Use colored overlays to show layers
- **Kinesthetic:** Physical cards for stacking order

### Assessment Rubric (10 points):
- Display properties used correctly: 2 points
- Position values appropriate: 2 points
- Z-index stacking logical: 2 points
- Layout functions properly: 2 points
- Responsive behavior: 1 point
- Code organization: 1 point

---

## Resources & References

### Online Tools:
- **Position Playground:** codepen.io/chriscoyier/pen/JpiaVo
- **Z-Index Visualizer:** thesitewizard.com/css/z-index.shtml
- **Display Property Guide:** css-tricks.com/almanac/properties/d/display
- **Position Guide:** developer.mozilla.org/en-US/docs/Web/CSS/position

### Quick Reference:
```css
/* DISPLAY VALUES */
display: block;         /* Full width, new line */
display: inline;        /* Inline with text */
display: inline-block;  /* Inline but with dimensions */
display: none;          /* Remove from document */
display: flex;          /* Flexbox container */
display: grid;          /* Grid container */

/* POSITION VALUES */
position: static;       /* Default, in flow */position: relative;     /* Relative to normal position */
position: absolute;     /* Relative to positioned parent */
position: fixed;        /* Relative to viewport */
position: sticky;       /* Hybrid relative/fixed */

/* POSITIONING PROPERTIES */
top: 20px;
right: 20px;
bottom: 20px;
left: 20px;

/* Z-INDEX */
z-index: 1;            /* Stacking order */
z-index: -1;           /* Behind default layer */
z-index: 9999;         /* Very high layer */

/* COMMON PATTERNS */
/* Center absolute element */
position: absolute;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);

/* Full screen overlay */
position: fixed;
top: 0;
left: 0;
right: 0;
bottom: 0;
```

---

## Success Criteria Checklist
Students have mastered this lesson when they can:
- [ ] Use appropriate display values for elements
- [ ] Apply position properties correctly
- [ ] Create overlays and modals
- [ ] Build sticky navigation
- [ ] Control z-index stacking
- [ ] Center elements with positioning
- [ ] Remove elements from document flow
- [ ] Create dropdown menus
- [ ] Build tooltips and popovers
- [ ] Debug positioning issues

---

## Next Lesson Preview
"Next class, we'll explore Flexbox - a powerful modern layout system that makes creating flexible, responsive layouts much easier than traditional positioning!"

## Key Takeaways
1. **Display controls box generation** - Block vs inline vs inline-block
2. **Position controls placement** - Static vs relative vs absolute vs fixed vs sticky
3. **Z-index needs positioning** - Won't work on static elements
4. **Absolute needs positioned parent** - Or it uses viewport
5. **Fixed and sticky are powerful** - For persistent UI elements

## Vocabulary Review
- **Display**: How elements generate boxes
- **Position**: Where elements are placed
- **Static**: Default position in flow
- **Relative**: Offset from normal position
- **Absolute**: Relative to positioned ancestor
- **Fixed**: Relative to viewport
- **Sticky**: Switches between relative and fixed
- **Z-index**: Stacking order control
- **Document flow**: Normal element layout

---

*End of Lesson 17: Display Properties and Positioning*