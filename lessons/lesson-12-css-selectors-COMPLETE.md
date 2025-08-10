# Lesson 12: CSS Selectors and Properties - Targeting Elements Like a Pro
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Master basic CSS selectors (element, class, ID)
- Use advanced selectors (descendant, child, sibling)
- Understand specificity and the cascade
- Combine multiple selectors effectively
- Use pseudo-classes (:hover, :active, :focus)
- Apply attribute selectors
- Group selectors for efficiency
- Debug selector conflicts using DevTools

### Materials Needed
- Text editor with syntax highlighting
- Web browser with developer tools
- Projector for demonstrations
- Printed CSS selector cheat sheet
- Sample HTML file with various elements
- Selector practice worksheet
- Colored markers for specificity exercise

### Key Vocabulary with Definitions
- **Selector**: Pattern that targets HTML elements
- **Class selector**: Targets elements with specific class (.classname)
- **ID selector**: Targets element with specific ID (#idname)
- **Specificity**: Which CSS rule wins when multiple apply
- **Descendant**: Element inside another element
- **Pseudo-class**: Targets element states (:hover)
- **Universal selector**: Targets all elements (*)
- **Combinator**: Combines selectors (space, >, +, ~)
- **Attribute selector**: Targets elements with specific attributes
- **Cascade**: Order in which styles are applied

---
## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding Selector Types (5 minutes)

**Teacher Script:**
"Imagine you're a teacher calling on students. You could say 'Everyone stand up' (element selector), 'Students wearing red stand up' (class selector), or 'Sarah, stand up' (ID selector). CSS selectors work the same way - they tell the browser which elements to style!"

**[CREATE new file: selectors-demo.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>CSS Selectors Demo</title>
    <style>
        /* We'll add our CSS here */
    </style>
</head>
<body>
    <h1 id="main-title">CSS Selectors Masterclass</h1>
    
    <nav>
        <ul class="menu">
            <li><a href="#" class="active">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>
    
    <main>
        <section class="intro">
            <h2>Welcome</h2>            <p class="highlight">This is a highlighted paragraph.</p>
            <p>This is a normal paragraph.</p>
        </section>
        
        <section class="content">
            <h2>Learn More</h2>
            <p>Content goes here with <span class="important">important text</span>.</p>
            <button type="button" class="btn primary">Click Me</button>
            <button type="button" class="btn secondary">Or Me</button>
        </section>
    </main>
    
    <footer id="page-footer">
        <p>Copyright 2024</p>
    </footer>
</body>
</html>
```

### Basic Selectors Explained (5 minutes)

**[ADD CSS demonstrations - explain each as you type]**

```css
/* 1. ELEMENT SELECTOR - Targets ALL elements of that type */
p {
    line-height: 1.6;
    color: #333;
}
/* This styles EVERY paragraph on the page */

/* 2. CLASS SELECTOR - Targets elements with that class */
.highlight {    background-color: yellow;
    padding: 2px 5px;
}
/* Use: class="highlight" in HTML */

/* 3. ID SELECTOR - Targets ONE specific element */
#main-title {
    color: #2c3e50;
    text-align: center;
    border-bottom: 3px solid #3498db;
}
/* Use: id="main-title" in HTML - only ONE per page! */

/* 4. UNIVERSAL SELECTOR - Targets EVERYTHING */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
/* Resets default styles for ALL elements */

/* 5. MULTIPLE CLASSES - Element with BOTH classes */
.btn.primary {
    background-color: #3498db;
    color: white;
}
/* Targets: class="btn primary" (element has BOTH) */

/* 6. GROUPING SELECTORS - Apply same styles */
h1, h2, h3 {
    font-family: 'Georgia', serif;
    margin-bottom: 10px;
}/* Styles ALL three heading types */
```

### Advanced Selectors & Combinators (5 minutes)

**[DEMONSTRATE each with visual results]**

```css
/* 7. DESCENDANT SELECTOR (space) - Element inside another */
nav a {
    text-decoration: none;
    color: #555;
}
/* Targets: ALL links inside nav (any level deep) */

/* 8. CHILD SELECTOR (>) - DIRECT children only */
nav > ul {
    list-style: none;
}
/* Targets: ul that's a DIRECT child of nav */

/* 9. ADJACENT SIBLING (+) - Next element */
h2 + p {
    font-size: 1.2em;
    font-weight: bold;
}
/* Targets: p that comes RIGHT AFTER h2 */

/* 10. GENERAL SIBLING (~) - All following siblings */
h2 ~ p {
    margin-left: 20px;
}
/* Targets: ALL p elements after h2 (same level) */

/* 11. ATTRIBUTE SELECTORS - Based on attributes */input[type="text"] {
    border: 2px solid #ddd;
    padding: 5px;
}
/* Targets: input elements with type="text" */

a[href^="https"] {
    color: green;
}
/* Targets: links starting with https */

/* 12. PSEUDO-CLASSES - Element states */
a:hover {
    color: #e74c3c;
    text-decoration: underline;
}
/* When mouse hovers over link */

button:active {
    transform: scale(0.95);
}
/* When button is being clicked */

input:focus {
    outline: 2px solid #3498db;
    background-color: #f0f8ff;
}
/* When input is selected/focused */

li:first-child {
    font-weight: bold;
}
/* First li in its parent */

li:nth-child(even) {    background-color: #f0f0f0;
}
/* Every even-numbered li */
```

**SPECIFICITY - The CSS Power Ranking:**

"Think of specificity like a scoring system. Higher score wins!"

```css
/* Specificity Score (0-0-0-0) = inline-id-class-element */

/* Score: 0-0-0-1 (1 element) */
p { color: blue; }

/* Score: 0-0-1-0 (1 class) */
.highlight { color: red; }

/* Score: 0-1-0-0 (1 ID) */
#special { color: green; }

/* Score: 0-0-1-1 (1 class + 1 element) */
p.highlight { color: orange; }

/* Score: 0-1-1-0 (1 ID + 1 class) */
#special.highlight { color: purple; }

/* Inline styles: 1-0-0-0 (highest!) */
/* <p style="color: black;"> wins over everything */
```

---

## PART 2: WE DO (Guided Practice) - 15 minutes

### Activity 1: Selector Challenge Game (8 minutes)
**Teacher Instructions:**
1. Display HTML structure on projector
2. Give selector challenges one by one
3. Students write selectors on paper/whiteboard
4. Reveal answer and test together

**[PROJECT this HTML structure]**

```html
<div class="container">
    <header id="top">
        <h1 class="logo">My Site</h1>
        <nav class="main-nav">
            <ul>
                <li><a href="#" class="active">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#" class="external">Blog</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <article class="post featured">
            <h2>First Post</h2>
            <p class="intro">Introduction paragraph.</p>
            <p>Regular paragraph.</p>
            <button class="btn btn-primary">Read More</button>
        </article>
        
        <article class="post">
            <h2>Second Post</h2>
            <p>Another paragraph.</p>
        </article>    </main>
    
    <footer>
        <p>Copyright <span class="year">2024</span></p>
    </footer>
</div>
```

**SELECTOR CHALLENGES - Students Try First:**

1. **"Select the logo heading"**
   - Students write their answer
   - Answer: `.logo` or `h1.logo` or `#top h1`

2. **"Select all links in the navigation"**
   - Students write their answer
   - Answer: `nav a` or `.main-nav a`

3. **"Select only the active navigation link"**
   - Students write their answer
   - Answer: `.active` or `a.active` or `nav .active`

4. **"Select the first paragraph in each article"**
   - Students write their answer
   - Answer: `article p:first-of-type`

5. **"Select the featured article's heading"**
   - Students write their answer
   - Answer: `.featured h2` or `article.featured h2`

6. **"Select buttons with BOTH btn and btn-primary classes"**
   - Students write their answer
   - Answer: `.btn.btn-primary`
7. **"Select paragraphs that come right after h2"**
   - Students write their answer
   - Answer: `h2 + p`

8. **"Select the copyright year span"**
   - Students write their answer
   - Answer: `.year` or `footer .year` or `span.year`

### Activity 2: Specificity Battle (7 minutes)

**Teacher Instructions:**
1. Show conflicting CSS rules
2. Students calculate specificity scores
3. Predict which style wins
4. Test in browser to confirm

**[EVERYONE PARTICIPATES]**

```css
/* ROUND 1: Which color wins for <p class="text">? */
p { color: blue; }                    /* Score: 0-0-0-1 */
.text { color: red; }                 /* Score: 0-0-1-0 */
p.text { color: green; }              /* Score: 0-0-1-1 */
/* WINNER: green (highest score: 0-0-1-1) */

/* ROUND 2: Which wins for <div id="box" class="highlight">? */
div { background: white; }            /* Score: 0-0-0-1 */
.highlight { background: yellow; }    /* Score: 0-0-1-0 */
#box { background: blue; }            /* Score: 0-1-0-0 */
div#box.highlight { background: red; }/* Score: 0-1-1-1 *//* WINNER: red (highest score: 0-1-1-1) */

/* ROUND 3: Which wins for <a class="link special" href="#">? */
a { color: black; }                   /* Score: 0-0-0-1 */
.link { color: blue; }                /* Score: 0-0-1-0 */
.special { color: purple; }           /* Score: 0-0-1-0 */
.link.special { color: orange; }      /* Score: 0-0-2-0 */
a.link.special { color: brown; }      /* Score: 0-0-2-1 */
/* WINNER: brown (highest score: 0-0-2-1) */
```

**Quick Specificity Calculator:**
- Count IDs: ×100
- Count classes: ×10
- Count elements: ×1
- Add them up!
- Inline style: ×1000 (always wins!)

---

## PART 3: YOU DO (Independent Practice) - 15 minutes

### Individual Challenge: Selector Mastery Page (15 minutes)

**Student Instructions:**
"Create a webpage that demonstrates your mastery of CSS selectors! Style different elements using various selector types."

**HTML Starter Template:**
```html
<!DOCTYPE html>
<html lang="en">
<head>    <meta charset="UTF-8">
    <title>CSS Selector Practice</title>
    <style>
        /* YOUR CSS GOES HERE */
        
        /* REQUIREMENT 1: Universal reset */
        
        /* REQUIREMENT 2: Style all paragraphs */
        
        /* REQUIREMENT 3: Style elements with class "special" */
        
        /* REQUIREMENT 4: Style the element with id "unique" */
        
        /* REQUIREMENT 5: Style links inside nav */
        
        /* REQUIREMENT 6: Style hover states */
        
        /* REQUIREMENT 7: First and last child */
        
        /* REQUIREMENT 8: Adjacent siblings */
        
        /* REQUIREMENT 9: Multiple classes */
        
        /* REQUIREMENT 10: Attribute selectors */
        
    </style>
</head>
<body>
    <header id="unique">
        <h1>CSS Selector Showcase</h1>
        <nav>
            <ul class="menu">
                <li><a href="#section1">Section 1</a></li>                <li><a href="#section2">Section 2</a></li>
                <li><a href="#section3" class="external">External Link</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <section id="section1">
            <h2>First Section</h2>
            <p class="special">This paragraph has the special class.</p>
            <p>This is a regular paragraph after the heading.</p>
            <p>Another regular paragraph.</p>
        </section>
        
        <section id="section2" class="featured">
            <h2>Second Section</h2>
            <p>First paragraph in second section.</p>
            <div class="box special">
                <p>Paragraph inside a div with multiple classes.</p>
                <button type="button" class="btn primary">Primary Button</button>
                <button type="button" class="btn secondary">Secondary Button</button>
            </div>
        </section>
        
        <section id="section3">
            <h2>Form Section</h2>
            <form>
                <input type="text" placeholder="Text input">
                <input type="email" placeholder="Email input">
                <input type="submit" value="Submit">            </form>
        </section>
    </main>
    
    <footer>
        <p>Created by <span class="author">Your Name</span></p>
    </footer>
</body>
</html>
```

**Requirements Checklist:**
```css
□ Universal selector (*) - Reset margins/padding
□ Element selector - Style all p tags
□ Class selector - Style .special class
□ ID selector - Style #unique element
□ Descendant selector - Style nav a
□ Child selector (>) - Style direct children
□ Adjacent sibling (+) - Style element after h2
□ Pseudo-class :hover - Add hover effects
□ Pseudo-class :first-child - Style first item
□ Pseudo-class :last-child - Style last item
□ Multiple classes - Style .btn.primary
□ Attribute selector - Style input[type="email"]
□ Grouped selectors - Style h1, h2, h3 together
□ :focus pseudo-class - Style focused inputs
□ nth-child() - Style alternating elements
```

**CSS Solution Guide (for teacher reference):**
```css
/* Complete CSS Solution */
/* 1. Universal reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* 2. Element selector */
p {
    line-height: 1.6;
    margin-bottom: 10px;
}

/* 3. Class selector */
.special {
    background-color: #fffacd;
    padding: 5px;
    border-left: 3px solid #ffd700;
}

/* 4. ID selector */
#unique {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 20px;
}

/* 5. Descendant selector */
nav a {
    color: white;
    text-decoration: none;
    padding: 5px 10px;
}

/* 6. Child selector */section > h2 {
    color: #2c3e50;
    border-bottom: 2px solid #3498db;
}

/* 7. Adjacent sibling */
h2 + p {
    font-size: 1.1em;
    font-style: italic;
}

/* 8. Hover effects */
a:hover {
    background-color: rgba(255,255,255,0.2);
    border-radius: 3px;
}

button:hover {
    transform: scale(1.05);
    cursor: pointer;
}

/* 9. First and last child */
li:first-child {
    font-weight: bold;
}

li:last-child {
    border-right: 2px solid white;
}

/* 10. Multiple classes */
.btn.primary {
    background-color: #3498db;
    color: white;    padding: 10px 20px;
    border: none;
}

.btn.secondary {
    background-color: #95a5a6;
    color: white;
    padding: 10px 20px;
    border: none;
}

/* 11. Attribute selectors */
input[type="email"] {
    border: 2px solid #3498db;
    padding: 5px;
}

input[type="submit"] {
    background-color: #27ae60;
    color: white;
    padding: 8px 15px;
    border: none;
}

/* 12. Focus state */
input:focus {
    outline: 3px solid #f39c12;
    background-color: #fff9e6;
}

/* 13. nth-child for alternating styles */
li:nth-child(even) {
    background-color: rgba(0,0,0,0.1);
}
```
---

## Assessment and Wrap-Up (5 minutes)

### Quick Selector Quiz
**Teacher asks, students answer:**
1. "How do you select all div elements?" → `div`
2. "How do you select elements with class 'box'?" → `.box`
3. "How do you select the element with id 'header'?" → `#header`
4. "What's more specific: .class or #id?" → `#id`
5. "How do you select links on hover?" → `a:hover`

### Specificity Challenge
"Calculate the specificity score:"
- `p` → 0-0-0-1
- `.highlight` → 0-0-1-0
- `#main p.text` → 0-1-1-1
- `nav ul li a.active` → 0-0-1-4

---

## Common Student Mistakes & Solutions

### Mistake 1: Forgetting the dot for classes
**Student writes:** `highlight { color: yellow; }`
**Fix:** `.highlight { color: yellow; }`
**Remember:** Classes need dots!

### Mistake 2: Using # for classes or . for IDs
**Student writes:** `#highlight` (for class="highlight")
**Fix:** `.highlight`
**Remember:** # = ID, . = class
### Mistake 3: Space matters in selectors
**Student writes:** `p .highlight` (space between)
**Means:** Elements with .highlight INSIDE p
**Probably wanted:** `p.highlight` (no space)
**Means:** p elements WITH class highlight

### Mistake 4: Over-specific selectors
**Student writes:** `body main section div p.text`
**Better:** `.text` or `p.text`
**Tip:** Keep selectors as simple as possible!

### Mistake 5: Wrong pseudo-class syntax
**Student writes:** `a.hover` or `a-hover`
**Fix:** `a:hover`
**Remember:** Pseudo-classes use colon!

---

## Homework Assignment

### Task: Selector Playground
Create a "Selector Showcase" page demonstrating mastery:

**Requirements:**
1. Create an HTML page with diverse elements:
   - Navigation menu with dropdowns
   - Article sections with headings
   - Forms with various input types
   - Lists (ordered and unordered)
   - Tables with headers and data
   - Footer with links

2. Style using EVERY selector type learned:   - At least 5 element selectors
   - At least 5 class selectors
   - At least 2 ID selectors
   - 3+ descendant selectors
   - 2+ child selectors
   - 2+ adjacent sibling selectors
   - 5+ pseudo-classes
   - 2+ attribute selectors
   - Multiple class combinations
   - Grouped selectors

3. Add comments explaining each selector

**Bonus Challenges:**
- Use `:nth-child(odd/even)` for zebra striping
- Style `:first-letter` and `:first-line`
- Use `:not()` selector
- Create a pure CSS dropdown menu
- Style `:visited` links differently

---

## Extension Activities

### For Fast Finishers:
1. **CSS Diner Game**
   - Play flukeout.github.io
   - Complete all 32 levels
   - Screenshot completion

2. **Specificity Calculator**
   - Build a specificity calculator
   - User inputs selector
   - Shows score breakdown
3. **Selector Challenge Cards**
   - Create flashcards
   - Selector on front
   - Explanation on back

---

## Teacher Notes & Tips

### Preparation:
- Set up selector game website
- Print selector cheat sheets
- Prepare specificity examples
- Test all code examples

### During Class:
- Use analogies (calling on students)
- Show DevTools selector testing
- Emphasize specificity importance
- Let students discover patterns

### Differentiation:
- **Struggling:** Provide selector reference sheet
- **Advanced:** Introduce :not(), :nth-of-type()
- **Visual:** Color-code selector parts
- **Kinesthetic:** Physical specificity cards

### Assessment Rubric (10 points):
- Uses 5+ selector types: 3 points
- Correct syntax: 2 points
- Demonstrates specificity: 2 points
- Pseudo-classes work: 2 points
- Code organization: 1 point

---

## Resources & References

### Online Tools:- **CSS Diner:** flukeout.github.io
- **Specificity Calculator:** specificity.keegan.st
- **CSS Selector Tester:** css-tricks.com/examples/SelectorTest
- **MDN Selectors:** developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors

### Quick Reference:
```css
/* BASIC SELECTORS */
*                  /* Universal */
element            /* Type/Element */
.class             /* Class */
#id                /* ID */

/* COMBINATORS */
A B                /* Descendant */
A > B              /* Child */
A + B              /* Adjacent sibling */
A ~ B              /* General sibling */

/* PSEUDO-CLASSES */
:hover             /* Mouse over */
:active            /* Being clicked */
:focus             /* Has focus */
:first-child       /* First child */
:last-child        /* Last child */
:nth-child(n)      /* Nth child */

/* ATTRIBUTE SELECTORS */
[attr]             /* Has attribute */
[attr="value"]     /* Exact value */
[attr^="start"]    /* Starts with */
[attr$="end"]      /* Ends with */
[attr*="contains"] /* Contains */
```
---

## Success Criteria Checklist

Students have mastered this lesson when they can:
- [ ] Write element, class, and ID selectors correctly
- [ ] Use descendant and child selectors appropriately
- [ ] Apply pseudo-classes for interactive states
- [ ] Calculate specificity scores
- [ ] Combine multiple selectors effectively
- [ ] Use attribute selectors
- [ ] Debug selector conflicts
- [ ] Group selectors for efficiency
- [ ] Explain selector relationships
- [ ] Choose appropriate selectors for tasks

---

## Next Lesson Preview
"Next class, we'll make your websites beautiful with colors, custom fonts, and advanced text styling! You'll learn about color theory, Google Fonts, and typography principles that make text both beautiful and readable."

## Key Takeaways
1. **Selectors target elements** - Be specific but not too specific
2. **Specificity matters** - ID > Class > Element
3. **Combinators show relationships** - Parent, child, sibling
4. **Pseudo-classes add interactivity** - :hover, :focus, :active
5. **Keep selectors simple** - Easier to maintain and understand

---

*End of Lesson 12: CSS Selectors and Properties*