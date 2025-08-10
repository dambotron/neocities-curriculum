# Lesson 13: Colors, Fonts, and Text Styling - Making Text Beautiful
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Use different color formats (names, hex, RGB, HSL)
- Apply colors to text and backgrounds effectively
- Import and use Google Fonts
- Style text with various properties (size, weight, style, decoration)
- Control text alignment and spacing
- Create readable typography with proper line height
- Implement text shadows and effects
- Understand color contrast for accessibility

### Materials Needed
- Text editor with syntax highlighting
- Web browser with developer tools
- Projector for demonstrations
- Color wheel/palette printout
- Google Fonts website access
- Contrast checker tool
- Typography examples (good and bad)
- Color blindness simulator (optional)

### Key Vocabulary with Definitions
- **Hex color**: Six-digit code representing colors (#RRGGBB)
- **RGB**: Red, Green, Blue color values (0-255)
- **HSL**: Hue, Saturation, Lightness color model
- **Typography**: Art and technique of arranging text
- **Font family**: Type of font (serif, sans-serif, etc.)
- **Font weight**: Thickness of text (bold, normal, light)
- **Line height**: Space between lines of text
- **Letter spacing**: Space between letters
- **Text shadow**: Shadow effect behind text
- **Web fonts**: Custom fonts loaded from internet

---
## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding Color Formats (5 minutes)

**Teacher Script:**
"Colors on the web are like paint - but instead of mixing physical paint, we're mixing light! We have several ways to tell the browser what color we want."

**[CREATE new file: colors-fonts-demo.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Colors and Typography Demo</title>
    <style>
        /* We'll add our styles here */
    </style>
</head>
<body>
    <h1>Color and Typography Masterclass</h1>
    
    <section class="color-demo">
        <h2>Color Formats</h2>
        <p class="color-name">Color by name</p>
        <p class="color-hex">Hexadecimal color</p>
        <p class="color-rgb">RGB color</p>
        <p class="color-hsl">HSL color</p>
        <p class="color-alpha">Colors with transparency</p>
    </section>
    
    <section class="font-demo">
        <h2>Typography Examples</h2>        <p class="serif">Serif fonts have decorative strokes</p>
        <p class="sans-serif">Sans-serif fonts are clean and modern</p>
        <p class="monospace">Monospace fonts have equal spacing</p>
        <p class="custom-font">Custom fonts from Google Fonts!</p>
    </section>
</body>
</html>
```

**[DEMONSTRATE each color format]**

```css
/* COLOR FORMATS - All these create the same blue! */

/* 1. COLOR NAMES - Easy but limited (140 colors) */
.color-name {
    color: blue;
    background-color: lightblue;
}

/* 2. HEXADECIMAL - Most common format */
.color-hex {
    color: #0000FF;        /* Full blue */
    background-color: #ADD8E6; /* Light blue */
}
/* How it works:
   #RRGGBB
   RR = Red (00-FF)
   GG = Green (00-FF)  
   BB = Blue (00-FF)
   00 = none, FF = maximum */

/* 3. RGB - Red, Green, Blue (0-255) */.color-rgb {
    color: rgb(0, 0, 255);           /* Blue */
    background-color: rgb(173, 216, 230); /* Light blue */
}

/* 4. HSL - Hue, Saturation, Lightness */
.color-hsl {
    color: hsl(240, 100%, 50%);      /* Blue */
    background-color: hsl(195, 53%, 79%); /* Light blue */
}
/* How it works:
   Hue = Color wheel position (0-360°)
   Saturation = Color intensity (0-100%)
   Lightness = Brightness (0-100%) */

/* 5. COLORS WITH TRANSPARENCY (Alpha) */
.color-alpha {
    /* RGBA - Red, Green, Blue, Alpha */
    background-color: rgba(0, 0, 255, 0.5); /* 50% transparent blue */
    
    /* HSLA - Hue, Saturation, Lightness, Alpha */
    border: 5px solid hsla(240, 100%, 50%, 0.7); /* 70% opaque blue */
    
    /* Hex with alpha (newer) */
    color: #0000FF80; /* 50% transparent blue */
}
```

### Typography and Font Properties (5 minutes)

**[DEMONSTRATE font properties]**
```css
/* FONT FAMILIES - Different font types */
.serif {
    font-family: Georgia, 'Times New Roman', serif;
    /* Fallback fonts if first isn't available */
}

.sans-serif {
    font-family: Arial, Helvetica, sans-serif;
}

.monospace {
    font-family: 'Courier New', Courier, monospace;
}

/* FONT PROPERTIES */
h1 {
    /* Size */
    font-size: 36px;              /* Pixels */
    /* font-size: 2em; */         /* Relative to parent */
    /* font-size: 2rem; */        /* Relative to root */
    
    /* Weight */
    font-weight: bold;            /* Or: 700 */
    /* font-weight: normal; */    /* Or: 400 */
    /* font-weight: 300; */       /* Light */
    
    /* Style */
    font-style: italic;           /* Or: normal, oblique */
    
    /* Decoration */
    text-decoration: underline;   /* Or: none, overline, line-through */    
    /* Transform */
    text-transform: uppercase;    /* Or: lowercase, capitalize */
    
    /* Alignment */
    text-align: center;          /* Or: left, right, justify */
}

/* TEXT SPACING */
p {
    /* Line height (space between lines) */
    line-height: 1.6;            /* 1.6 times font size */
    
    /* Letter spacing */
    letter-spacing: 1px;         /* Space between letters */
    
    /* Word spacing */
    word-spacing: 2px;           /* Space between words */
    
    /* Indentation */
    text-indent: 20px;           /* First line indent */
}

/* TEXT EFFECTS */
.fancy-text {
    /* Text shadow: x-offset y-offset blur color */
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
    
    /* Multiple shadows! */
    text-shadow: 
        1px 1px 2px red,
        -1px -1px 2px blue;
}```

### Using Google Fonts (5 minutes)

**[DEMONSTRATE live on fonts.google.com]**

"Let's get some beautiful free fonts!"

**Step 1: Visit Google Fonts**
1. Go to fonts.google.com
2. Browse or search for fonts
3. Click on a font to preview
4. Click "Select this style"

**Step 2: Get the embed code**
```html
<!-- Add to HTML <head> -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
```

**Step 3: Use in CSS**
```css
body {
    font-family: 'Roboto', sans-serif;
}

/* Use different weights */
h1 {
    font-family: 'Roboto', sans-serif;
    font-weight: 700; /* Bold version */
}

p {    font-family: 'Roboto', sans-serif;
    font-weight: 300; /* Light version */
}
```

---

## PART 2: WE DO (Guided Practice) - 15 minutes

### Activity 1: Create a Color Palette Together (7 minutes)

**Teacher Instructions:**
1. Open a color palette generator (coolors.co)
2. Create a 5-color palette together
3. Apply colors to a sample page
4. Test color contrast

**[EVERYONE FOLLOWS ALONG]**

**Step 1: Choose a color scheme**
```css
/* Our Custom Color Palette */
:root {
    /* Define CSS variables for colors */
    --primary-color: #2C3E50;    /* Dark blue-gray */
    --secondary-color: #E74C3C;  /* Red accent */
    --text-color: #34495E;       /* Dark gray text */
    --background-color: #ECF0F1; /* Light gray background */
    --accent-color: #3498DB;     /* Bright blue */
}

/* Use the variables */
body {
    background-color: var(--background-color);    color: var(--text-color);
}

h1 {
    color: var(--primary-color);
}

a {
    color: var(--accent-color);
}

.highlight {
    background-color: var(--secondary-color);
    color: white;
}
```

**Step 2: Test different combinations**
"Let's try these combinations and check if they're readable!"

```css
/* GOOD CONTRAST - Easy to read */
.good-contrast {
    background-color: #FFFFFF;
    color: #000000;
    /* Contrast ratio: 21:1 - Perfect! */
}

/* BAD CONTRAST - Hard to read */
.bad-contrast {
    background-color: #FFFF00;
    color: #FFFFFF;
    /* Contrast ratio: 1.07:1 - Fails accessibility! */
}

/* ACCESSIBLE CONTRAST */.accessible {
    background-color: #2C3E50;
    color: #FFFFFF;
    /* Contrast ratio: 12.6:1 - Passes AAA standard! */
}
```

**Accessibility Standards:**
- Normal text: 4.5:1 minimum (AA)
- Large text: 3:1 minimum (AA)
- Enhanced: 7:1 for AAA compliance

### Activity 2: Typography Makeover (8 minutes)

**Teacher Instructions:**
1. Start with poorly styled text
2. Transform it together step by step
3. Explain each improvement

**[PROJECT this starter code]**

```html
<!-- BAD Typography Example -->
<style>
    /* DON'T DO THIS */
    .bad-text {
        font-family: 'Comic Sans MS';
        font-size: 10px;
        line-height: 1;
        color: yellow;
        background-color: lime;
        text-align: justify;
        letter-spacing: 5px;
    }
</style>
<article class="bad-text">
    <h1>This Text is Hard to Read!</h1>
    <p>The quick brown fox jumps over the lazy dog. This classic sentence contains every letter of the alphabet.</p>
</article>
```

**[TRANSFORM together to GOOD typography]**

```html
<!-- Link Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">

<style>
    /* GOOD Typography */
    .good-text {
        /* Professional font pairing */
        font-family: 'Open Sans', sans-serif;
        
        /* Readable size */
        font-size: 16px;
        
        /* Comfortable line spacing */
        line-height: 1.6;
        
        /* High contrast colors */
        color: #2C3E50;
        background-color: #FFFFFF;
        
        /* Natural alignment */
        text-align: left;
        
        /* Normal letter spacing */        letter-spacing: normal;
        
        /* Comfortable reading width */
        max-width: 600px;
        margin: 0 auto;
        padding: 20px;
    }
    
    .good-text h1 {
        /* Display font for headings */
        font-family: 'Playfair Display', serif;
        font-size: 36px;
        font-weight: 700;
        margin-bottom: 20px;
        color: #1A1A1A;
    }
    
    .good-text p {
        margin-bottom: 15px;
        text-indent: 20px;
    }
</style>
```

**Typography Best Practices:**
1. **Font Size:** 16px minimum for body text
2. **Line Height:** 1.5-1.8 for readability
3. **Line Length:** 45-75 characters ideal
4. **Contrast:** Dark text on light background
5. **Font Pairing:** One serif + one sans-serif
6. **Hierarchy:** Clear size differences

---
## PART 3: YOU DO (Independent Practice) - 15 minutes

### Individual Challenge: Design a Magazine Article (15 minutes)

**Student Instructions:**
"Create a beautifully styled magazine article page using colors, custom fonts, and professional typography!"

**HTML Starter Template:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Magazine Article - [Your Topic]</title>
    
    <!-- TODO: Add Google Fonts links here -->
    
    <style>
        /* TODO: Define your color palette */
        :root {
            --primary-color: ;
            --secondary-color: ;
            --text-color: ;
            --background-color: ;
            --accent-color: ;
        }
        
        /* TODO: Style the article */
        
    </style>
</head>
<body>
    <article class="magazine-article">
        <header class="article-header">            <h1 class="article-title">The Art of [Your Topic]</h1>
            <p class="article-subtitle">Exploring the fascinating world of [subtopic]</p>
            <p class="article-meta">
                By <span class="author">[Your Name]</span> | 
                <time>March 15, 2024</time> | 
                <span class="read-time">5 min read</span>
            </p>
        </header>
        
        <section class="article-content">
            <p class="lead-paragraph">
                This is your lead paragraph. It should be slightly larger and draw the reader in with compelling text about your topic.
            </p>
            
            <p>
                Regular paragraph text goes here. Add interesting content about your chosen topic. Make sure to have enough text to demonstrate your typography skills.
            </p>
            
            <blockquote class="pull-quote">
                "An inspiring quote related to your topic that stands out visually."
                <cite>- Famous Person</cite>
            </blockquote>
            
            <h2>Subheading for New Section</h2>
            <p>
                More content here. Remember to maintain consistent styling throughout while creating visual hierarchy.
            </p>
                        <h3>Smaller Subheading</h3>
            <p>
                Additional paragraph demonstrating the hierarchy of your typography system.
            </p>
            
            <p class="conclusion">
                A concluding paragraph that wraps up your article nicely.
            </p>
        </section>
        
        <footer class="article-footer">
            <p class="tags">Tags: <span class="tag">Design</span> <span class="tag">Typography</span> <span class="tag">Web</span></p>
        </footer>
    </article>
</body>
</html>
```

**Requirements Checklist:**
```css
□ Define 5-color palette using CSS variables
□ Use 2+ Google Fonts (heading + body)
□ Style all heading levels (h1, h2, h3)
□ Set readable body text (16px+, line-height 1.5+)
□ Create visual hierarchy with font sizes
□ Style the lead paragraph differently
□ Make pull quote stand out
□ Add text shadow to main title
□ Use different font weights
□ Style metadata (author, date) uniquely
□ Create hover effects for tags□ Ensure AA contrast ratio (4.5:1)
□ Add appropriate letter/word spacing
□ Use text-transform creatively
□ Maximum 65-75 characters per line
```

**CSS Solution Guide (for teacher reference):**
```css
/* Import Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Merriweather:wght@300;700;900&family=Open+Sans:wght@400;600&display=swap');

/* Color Palette */
:root {
    --primary-color: #2C3E50;
    --secondary-color: #E74C3C;
    --text-color: #34495E;
    --background-color: #FAFAFA;
    --accent-color: #3498DB;
}

/* Base Styles */
body {
    font-family: 'Open Sans', sans-serif;
    font-size: 16px;
    line-height: 1.7;
    color: var(--text-color);
    background-color: var(--background-color);
    margin: 0;
    padding: 0;
}

.magazine-article {    max-width: 700px;
    margin: 40px auto;
    padding: 20px;
    background: white;
    box-shadow: 0 0 20px rgba(0,0,0,0.1);
}

/* Typography - Headings */
.article-title {
    font-family: 'Merriweather', serif;
    font-size: 48px;
    font-weight: 900;
    color: var(--primary-color);
    text-align: center;
    margin-bottom: 10px;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
    letter-spacing: -1px;
}

.article-subtitle {
    font-size: 20px;
    color: var(--accent-color);
    text-align: center;
    font-weight: 300;
    font-style: italic;
    margin-bottom: 20px;
}

.article-meta {
    text-align: center;
    color: #7F8C8D;
    font-size: 14px;    text-transform: uppercase;
    letter-spacing: 1px;
    border-bottom: 2px solid var(--accent-color);
    padding-bottom: 20px;
    margin-bottom: 30px;
}

.author {
    font-weight: 600;
    color: var(--primary-color);
}

/* Body Text */
.lead-paragraph {
    font-size: 20px;
    line-height: 1.8;
    color: var(--primary-color);
    font-weight: 300;
    margin-bottom: 25px;
    text-indent: 0;
}

.lead-paragraph::first-letter {
    font-size: 72px;
    font-weight: 700;
    float: left;
    line-height: 60px;
    padding-right: 8px;
    margin-top: -3px;
    font-family: 'Merriweather', serif;
    color: var(--secondary-color);
}

p {    margin-bottom: 20px;
    text-align: justify;
    text-indent: 20px;
}

h2 {
    font-family: 'Merriweather', serif;
    font-size: 32px;
    font-weight: 700;
    color: var(--primary-color);
    margin: 30px 0 15px 0;
}

h3 {
    font-family: 'Merriweather', serif;
    font-size: 24px;
    font-weight: 600;
    color: var(--primary-color);
    margin: 25px 0 10px 0;
}

/* Pull Quote */
.pull-quote {
    font-family: 'Merriweather', serif;
    font-size: 24px;
    font-style: italic;
    color: var(--accent-color);
    border-left: 4px solid var(--secondary-color);
    padding-left: 20px;
    margin: 30px 0;
    background: linear-gradient(to right, rgba(52, 152, 219, 0.05), transparent);
}

.pull-quote cite {    display: block;
    text-align: right;
    font-size: 18px;
    color: var(--text-color);
    margin-top: 10px;
}

/* Tags */
.tags {
    margin-top: 30px;
    padding-top: 20px;
    border-top: 1px solid #E0E0E0;
}

.tag {
    display: inline-block;
    background: var(--accent-color);
    color: white;
    padding: 5px 15px;
    border-radius: 20px;
    font-size: 12px;
    margin-right: 10px;
    transition: all 0.3s ease;
}

.tag:hover {
    background: var(--secondary-color);
    transform: translateY(-2px);
    box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}
```

---

## Assessment and Wrap-Up (5 minutes)
### Quick Color & Typography Check
"Show me your article! Let's check:"
1. Can you read the text easily?
2. Do your colors work well together?
3. Is there clear hierarchy?
4. Are your fonts loading correctly?
5. Does it look professional?

### Exit Ticket Questions:
1. Name three color formats in CSS
2. What's the minimum contrast ratio for accessibility?
3. How do you import Google Fonts?
4. What's a good line-height for body text?
5. What property creates space between letters?

---

## Common Student Mistakes & Solutions

### Mistake 1: Too Many Fonts
**Student uses:** 5 different Google Fonts
**Fix:** Limit to 2-3 fonts maximum
**Rule:** One for headings, one for body

### Mistake 2: Poor Color Contrast
**Student writes:** Light gray text on white
**Fix:** Check contrast ratio (WebAIM tool)
**Standard:** 4.5:1 minimum for normal text

### Mistake 3: Forgetting Font Fallbacks
**Student writes:** `font-family: 'Roboto';`
**Fix:** `font-family: 'Roboto', sans-serif;`**Always:** Include fallback fonts

### Mistake 4: Tiny Font Sizes
**Student writes:** `font-size: 12px;`
**Fix:** Minimum 16px for body text
**Why:** Accessibility and readability

### Mistake 5: Wrong Color Format
**Student writes:** `color: #GGG;`
**Fix:** Hex uses 0-9 and A-F only
**Correct:** `color: #777;` or `#777777;`

---

## Homework Assignment

### Task: Personal Brand Style Guide
Create a comprehensive style guide for your personal brand:

**Requirements:**
1. **Color Palette Page**
   - 5-color scheme with hex, RGB, and HSL values
   - Show each color in swatches
   - Demonstrate color combinations
   - Include contrast ratios

2. **Typography Showcase**
   - Import 2-3 Google Fonts
   - Show complete type scale (h1-h6, p, etc.)
   - Demonstrate different weights
   - Show italic and bold variations
   - Include optimal line-height examples

3. **Text Effects Gallery**   - Create 5 different text shadows
   - Show text decorations
   - Demonstrate text transforms
   - Create gradient text (research how!)

4. **Real-World Application**
   - Apply style guide to existing HTML page
   - Create dark mode version
   - Ensure accessibility standards

**Bonus Challenges:**
- Create color variables with CSS custom properties
- Add @font-face for custom font file
- Create text animation on hover
- Build contrast checker tool
- Design colorblind-friendly palette

---

## Extension Activities

### For Fast Finishers:
1. **Font Pairing Challenge**
   - Research font pairing rules
   - Create 5 professional combinations
   - Explain why they work

2. **Color Theory Deep Dive**
   - Learn about color harmony
   - Create monochromatic scheme
   - Build complementary palette
   - Try split-complementary

3. **Typography Poster**
   - Design typographic poster
   - Use only text as design   - Show font personality

---

## Teacher Notes & Tips

### Preparation:
- Bookmark font and color tools
- Prepare contrast examples
- Test Google Fonts loading
- Have backup fonts ready

### During Class:
- Show real website examples
- Emphasize readability over style
- Discuss accessibility importance
- Let students explore fonts

### Differentiation:
- **Struggling:** Provide color palette templates
- **Advanced:** Introduce variable fonts, CSS gradients
- **Visual:** Use color wheel, typography specimens
- **Kinesthetic:** Physical color cards activity

### Assessment Rubric (10 points):
- Color palette defined: 2 points
- Google Fonts implemented: 2 points
- Typography hierarchy: 2 points
- Readability/contrast: 2 points
- Creative design: 1 point
- Code organization: 1 point

---

## Resources & References

### Color Tools:
- **Adobe Color:** color.adobe.com
- **Coolors:** coolors.co- **Contrast Checker:** webaim.org/resources/contrastchecker
- **Color Hunt:** colorhunt.co
- **Accessible Colors:** accessible-colors.com

### Typography Resources:
- **Google Fonts:** fonts.google.com
- **Font Pair:** fontpair.co
- **Type Scale:** type-scale.com
- **Font Squirrel:** fontsquirrel.com
- **Typography Handbook:** typographyhandbook.com

### Quick Reference:
```css
/* COLOR FORMATS */
color: red;                    /* Named */
color: #FF0000;               /* Hex */
color: rgb(255, 0, 0);        /* RGB */
color: hsl(0, 100%, 50%);     /* HSL */
color: rgba(255, 0, 0, 0.5);  /* RGB + Alpha */

/* FONT PROPERTIES */
font-family: 'Font Name', fallback;
font-size: 16px | 1em | 1rem;
font-weight: 400 | 700 | bold;
font-style: normal | italic;
line-height: 1.5;
letter-spacing: 1px;
word-spacing: 2px;
text-transform: uppercase;
text-align: left | center | right;
text-decoration: underline;
text-shadow: x y blur color;```

---

## Success Criteria Checklist

Students have mastered this lesson when they can:
- [ ] Use multiple color formats (hex, RGB, HSL)
- [ ] Apply colors with proper contrast
- [ ] Import and use Google Fonts
- [ ] Create typographic hierarchy
- [ ] Set appropriate font sizes and line heights
- [ ] Apply text decorations and effects
- [ ] Use text shadows effectively
- [ ] Implement CSS color variables
- [ ] Ensure text accessibility
- [ ] Pair fonts professionally

---

## Next Lesson Preview
"Next class, we'll dive into the CSS Box Model - the foundation of all layouts! You'll learn how margin, padding, and borders work together to create space and structure in your designs."

## Key Takeaways
1. **Colors have multiple formats** - Choose based on needs
2. **Contrast matters** - 4.5:1 minimum for accessibility
3. **Typography creates hierarchy** - Guide the reader's eye
4. **Less is more** - Limit fonts and colors
5. **Test readability** - If it's hard to read, it's bad design

## Vocabulary Review
- **Hex color**: #RRGGBB format
- **RGB**: Red, Green, Blue values
- **HSL**: Hue, Saturation, Lightness
- **Typography**: Art of arranging text
- **Font weight**: Thickness of text
- **Line height**: Space between lines
- **Contrast ratio**: Difference between colors
- **Web fonts**: Custom fonts from internet
- **Fallback fonts**: Backup font choices

---

*End of Lesson 13: Colors, Fonts, and Text Styling*