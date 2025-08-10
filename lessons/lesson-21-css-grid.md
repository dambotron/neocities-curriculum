# Lesson 21: CSS Grid Layout

## Duration: 45-50 minutes

### Learning Objectives
- Understand CSS Grid concepts
- Create grid containers and items
- Use grid lines and areas
- Build complex layouts easily

### Materials Needed
- Grid visualization tools
- Layout examples
- Grid garden game link

### Lesson Outline

#### Introduction to CSS Grid (10 minutes)

1. **What is CSS Grid?**
   - Two-dimensional layout system
   - Rows AND columns
   - More powerful than Flexbox for layouts
   - Works great with Flexbox

2. **Grid Terminology**
   - Grid Container (parent)
   - Grid Items (children)
   - Grid Lines
   - Grid Tracks (rows/columns)
   - Grid Cells
   - Grid Areas

3. **When to Use Grid vs Flexbox**
   - Grid: Overall page layout
   - Flexbox: Components and alignment
   - Can use both together!
#### Basic Grid Properties (15 minutes)

1. **Creating a Grid Container**
   ```css
   .container {
       display: grid;
       /* or display: inline-grid; */
   }
   ```

2. **Defining Columns and Rows**
   ```css
   .container {
       display: grid;
       
       /* 3 columns of equal width */
       grid-template-columns: 1fr 1fr 1fr;
       
       /* Different sized columns */
       grid-template-columns: 200px 1fr 100px;
       
       /* Using repeat */
       grid-template-columns: repeat(3, 1fr);
       
       /* Rows */
       grid-template-rows: 100px 200px auto;
       
       /* Gap between items */
       gap: 20px;
       /* or */
       row-gap: 10px;
       column-gap: 20px;
   }
   ```

3. **Grid Item Placement**
   ```css
   .item {
       /* Span multiple columns */
       grid-column: 1 / 3;  /* Start at 1, end at 3 */
       
       /* Span multiple rows */
       grid-row: 1 / 4;
       
       /* Shorthand */
       grid-area: 1 / 1 / 3 / 3;
   }
   ```
#### Named Grid Areas (10 minutes)

1. **Template Areas**
   ```css
   .container {
       display: grid;
       grid-template-columns: 200px 1fr 200px;
       grid-template-rows: auto 1fr auto;
       grid-template-areas:
           "header header header"
           "sidebar main aside"
           "footer footer footer";
       gap: 20px;
   }
   
   .header { grid-area: header; }
   .sidebar { grid-area: sidebar; }
   .main { grid-area: main; }
   .aside { grid-area: aside; }
   .footer { grid-area: footer; }
   ```

#### Hands-On: Magazine Layout (12 minutes)

Create a responsive magazine-style layout:

```html
<div class="magazine">
    <header class="header">
        <h1>My Magazine</h1>
    </header>
    <nav class="nav">Navigation</nav>
    <main class="content">
        <article>Main Article</article>
    </main>
    <aside class="sidebar">Related Stories</aside>
    <footer class="footer">Footer Info</footer>
</div>
```
```css
/* Mobile Layout */
.magazine {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-areas:
        "header"
        "nav"
        "content"
        "sidebar"
        "footer";
    gap: 20px;
    padding: 20px;
}

/* Tablet and Desktop */
@media (min-width: 768px) {
    .magazine {
        grid-template-columns: 200px 1fr 200px;
        grid-template-rows: auto auto 1fr auto;
        grid-template-areas:
            "header header header"
            "nav nav nav"
            "sidebar content content"
            "footer footer footer";
    }
}

/* Style grid items */
.header { 
    grid-area: header;
    background: #333;
    color: white;
    padding: 20px;
}

.nav { 
    grid-area: nav;
    background: #666;
    color: white;
    padding: 10px;
}

.content { 
    grid-area: content;
    min-height: 300px;
}

.sidebar { 
    grid-area: sidebar;
    background: #f0f0f0;
    padding: 20px;
}

.footer { 
    grid-area: footer;
    background: #333;
    color: white;
    padding: 20px;
    text-align: center;
}
```
#### Advanced Grid Features (3 minutes)

1. **Auto-Fit and Auto-Fill**
   ```css
   /* Responsive columns without media queries */
   .grid {
       display: grid;
       grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
       gap: 20px;
   }
   ```

2. **Alignment**
   ```css
   .container {
       justify-items: center;  /* Horizontal alignment */
       align-items: center;    /* Vertical alignment */
   }
   ```

### Practice Exercise

Create a photo gallery with:
1. Responsive grid layout
2. Some images span 2 columns
3. Feature image spans 2x2 grid
4. No media queries needed

### Homework Assignment

1. **Convert a Page to Grid**
   - Choose your most complex page
   - Redesign using CSS Grid
   - Make it responsive
   - Use named grid areas

2. **Grid Challenges**
   - Complete CSS Grid Garden game
   - Create a dashboard layout
   - Build a calendar grid
   - Make a pricing table with Grid
### Common Grid Patterns

```css
/* Card Grid */
.cards {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 20px;
}

/* Holy Grail Layout */
.page {
    display: grid;
    grid-template: 
        "header header header" auto
        "nav main aside" 1fr
        "footer footer footer" auto
        / 200px 1fr 200px;
    min-height: 100vh;
}

/* Image Gallery with Feature */
.gallery {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

.featured {
    grid-column: span 2;
    grid-row: span 2;
}
```

### Assessment Criteria
- Creates grid container: 2 points
- Defines columns/rows: 3 points
- Uses gap property: 1 point
- Implements grid areas: 2 points
- Responsive grid: 2 points
- Total: 10 points

### Teacher Notes
- Use Firefox Grid Inspector
- Show real website grids
- Compare with Flexbox
- Let students experiment
- Emphasize simplicity

### Resources
- CSS Grid Garden: cssgridgarden.com
- Grid by Example: gridbyexample.com
- CSS-Tricks Complete Guide
- MDN Grid Documentation