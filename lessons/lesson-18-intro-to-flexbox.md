# Lesson 18: Introduction to Flexbox

## Duration: 45-50 minutes

### Learning Objectives
- Understand what Flexbox is and when to use it
- Master flex container properties
- Learn flex item properties
- Create flexible layouts

### Materials Needed
- Flexbox cheat sheet
- Practice exercises handout
- Visual diagrams

### Lesson Outline

#### Introduction to Flexbox (10 minutes)

1. **What is Flexbox?**
   - Flexible Box Layout
   - One-dimensional layout method
   - Makes alignment and distribution easy
   - Replaces floats and positioning hacks

2. **Flex Container vs Flex Items**
   ```css
   /* Container */
   .container {
       display: flex;
   }
   
   /* Items are direct children */
   .container > div {
       /* These are flex items */
   }
   ```

3. **Main Axis vs Cross Axis**
   - Main axis: primary direction (horizontal by default)
   - Cross axis: perpendicular to main
#### Flex Container Properties (15 minutes)

1. **display: flex**
   ```css
   .container {
       display: flex; /* or inline-flex */
   }
   ```

2. **flex-direction**
   ```css
   .container {
       flex-direction: row;        /* default */
       flex-direction: column;     /* vertical */
       flex-direction: row-reverse;
       flex-direction: column-reverse;
   }
   ```

3. **justify-content** (main axis)
   ```css
   .container {
       justify-content: flex-start;  /* default */
       justify-content: center;
       justify-content: flex-end;
       justify-content: space-between;
       justify-content: space-around;
       justify-content: space-evenly;
   }
   ```

4. **align-items** (cross axis)
   ```css
   .container {
       align-items: stretch;    /* default */
       align-items: center;
       align-items: flex-start;
       align-items: flex-end;
       align-items: baseline;
   }
   ```
5. **flex-wrap**
   ```css
   .container {
       flex-wrap: nowrap;   /* default - single line */
       flex-wrap: wrap;     /* multiple lines */
       flex-wrap: wrap-reverse;
   }
   ```

6. **gap** (spacing between items)
   ```css
   .container {
       gap: 20px;           /* all directions */
       gap: 10px 20px;      /* row-gap column-gap */
   }
   ```

#### Hands-On: Navigation Bar (15 minutes)

Create a responsive navigation using Flexbox:

```html
<nav class="navbar">
    <div class="logo">My Site</div>
    <ul class="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
</nav>
```

```css
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #333;
    padding: 1rem;
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 2rem;
    margin: 0;
    padding: 0;
}
.nav-links a {
    color: white;
    text-decoration: none;
}
```

#### Flex Item Properties (8 minutes)

1. **flex-grow**
   ```css
   .item {
       flex-grow: 1; /* Grows to fill space */
   }
   ```

2. **flex-shrink**
   ```css
   .item {
       flex-shrink: 0; /* Won't shrink */
   }
   ```

3. **flex-basis**
   ```css
   .item {
       flex-basis: 200px; /* Starting size */
   }
   ```

4. **Shorthand**
   ```css
   .item {
       flex: 1 1 200px; /* grow shrink basis */
       flex: 1;         /* Common: equal columns */
   }
   ```

### Practice Exercises (5 minutes)

1. **Card Layout**: Create 3 equal-width cards
2. **Centered Content**: Center a div both ways
3. **Sidebar Layout**: Fixed sidebar, flexible content
4. **Footer**: Stick footer to bottom
### Common Flexbox Patterns

#### Center Everything
```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}
```

#### Equal Height Columns
```css
.row {
    display: flex;
}
.column {
    flex: 1;
    padding: 1rem;
}
```

#### Push Item to End
```css
.nav {
    display: flex;
}
.nav-item:last-child {
    margin-left: auto;
}
```

### Homework Assignment
1. Convert your navigation to use Flexbox
2. Create a photo gallery with Flexbox
3. Build a card layout for your projects
4. Make a footer that stays at bottom
5. Experiment with different justify-content values

### Assessment Checklist
- Uses display: flex correctly
- Understands main vs cross axis
- Can center items
- Creates responsive layouts
- Proper use of flex properties

### Common Mistakes
- Forgetting display: flex on container
- Applying flex properties to wrong element
- Not understanding axis directions
- Over-complicating simple layouts

### Resources
- Flexbox Froggy (game): flexboxfroggy.com
- CSS-Tricks Flexbox Guide
- MDN Flexbox Documentation