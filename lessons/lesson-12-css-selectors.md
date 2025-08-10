# Lesson 12: CSS Selectors and Properties

## Duration: 45-50 minutes

### Learning Objectives
- Master different types of CSS selectors
- Understand selector specificity
- Learn to combine selectors
- Practice targeting specific elements

### Materials Needed
- Selector practice worksheet
- HTML file with various elements
- CSS selector game link

### Lesson Outline

#### Review of Basic Selectors (5 minutes)

1. **Element Selectors**
   ```css
   p { }     /* All paragraphs */
   h1 { }    /* All h1 elements */
   div { }   /* All divs */
   ```

2. **Class Selectors**
   ```css
   .classname { }      /* Elements with class="classname" */
   .red-text { }       /* Elements with class="red-text" */
   ```

3. **ID Selectors**
   ```css
   #idname { }         /* Element with id="idname" */
   #header { }         /* Element with id="header" */
   ```
#### Advanced Selectors (15 minutes)

1. **Descendant Selectors**
   ```css
   /* Any p inside a div */
   div p { }
   
   /* Any a inside nav */
   nav a { }
   
   /* Can be multiple levels deep */
   article section p { }
   ```

2. **Child Selectors**
   ```css
   /* Direct children only */
   div > p { }
   
   /* Direct li children of ul */
   ul > li { }
   ```

3. **Multiple Selectors**
   ```css
   /* Apply same styles to multiple */
   h1, h2, h3 {
       color: navy;
   }
   
   /* Multiple classes on same element */
   .red.bold { }  /* Has BOTH classes */
   ```

4. **Attribute Selectors**
   ```css
   /* Elements with specific attributes */
   img[alt] { }               /* Has alt attribute */
   a[href="#"] { }           /* Specific value */
   a[href^="https"] { }      /* Starts with */
   a[href$=".pdf"] { }       /* Ends with */
   ```
#### Pseudo-Classes (10 minutes)

1. **Link States**
   ```css
   a:link { }       /* Unvisited links */
   a:visited { }    /* Visited links */
   a:hover { }      /* Mouse over */
   a:active { }     /* Being clicked */
   ```

2. **Structural Pseudo-Classes**
   ```css
   li:first-child { }      /* First li in parent */
   li:last-child { }       /* Last li in parent */
   li:nth-child(3) { }     /* 3rd li */
   li:nth-child(odd) { }   /* Odd items */
   li:nth-child(even) { }  /* Even items */
   ```

3. **Other Useful Pseudo-Classes**
   ```css
   input:focus { }         /* When selected */
   input:disabled { }      /* Disabled inputs */
   p:not(.special) { }     /* p without class special */
   ```

#### Specificity (8 minutes)

1. **Specificity Hierarchy**
   - Inline styles: 1000 points
   - IDs: 100 points
   - Classes: 10 points
   - Elements: 1 point

2. **Calculating Specificity**
   ```css
   p { }                  /* 0-0-1 = 1 */
   .class { }             /* 0-1-0 = 10 */
   #id { }                /* 1-0-0 = 100 */
   div p.class { }        /* 0-1-2 = 12 */
   #id .class p { }       /* 1-1-1 = 111 */
   ```
#### Hands-On Practice (10 minutes)

Create a test HTML file with various elements:
```html
<div id="container">
    <nav>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li class="active"><a href="#">Services</a></li>
        </ul>
    </nav>
    <main>
        <h1>Welcome</h1>
        <p class="intro">First paragraph</p>
        <p>Second paragraph</p>
        <section class="highlight important">
            <h2>Featured</h2>
            <p>Content here</p>
        </section>
    </main>
</div>
```

**Challenge: Style the following**
1. Make the nav links blue, but red on hover
2. Style only the first paragraph after any h1
3. Make the active nav item bold
4. Style elements with both highlight AND important classes
5. Make every other list item have a gray background

### Practice Game (2 minutes)
Introduce CSS Diner game for homework practice

### Homework Assignment
1. Complete 15 levels of CSS Diner (flukeout.github.io)
2. Create a "selector playground" page with:
   - Examples of all selector types learned
   - Comments explaining each selector
   - Creative styling using combinations
3. Style your existing pages using advanced selectors
### Common Selector Patterns

```css
/* Navigation styling */
nav ul li a { }
nav ul li a:hover { }
nav ul li.active a { }

/* Form styling */
input[type="text"],
input[type="email"] {
    /* Shared styles */
}

/* Table striping */
tr:nth-child(even) {
    background-color: #f2f2f2;
}

/* First letter styling */
p:first-child:first-letter {
    font-size: 2em;
}
```

### Assessment Criteria
- Correctly uses element selectors: 2 points
- Proper use of classes and IDs: 2 points
- Combines selectors effectively: 3 points
- Uses pseudo-classes: 2 points
- Understands specificity: 1 point
- Total: 10 points

### Common Mistakes
- Over-using ID selectors
- Making selectors too specific
- Not understanding cascade order
- Forgetting about inheritance
- Using inline styles unnecessarily

### Teacher Notes
- Use browser DevTools to show selector matching
- Demonstrate specificity conflicts
- Show real-world examples
- Let students experiment with selector combinations
- Emphasize best practices over complexity

### Extension Activities
- Research CSS combinators (+, ~)
- Explore :nth-child() formulas
- Learn about :root and CSS variables
- Try the "30 CSS Selectors" challenge