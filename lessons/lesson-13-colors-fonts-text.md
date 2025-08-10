# Lesson 13: Colors, Fonts, and Text Styling

## Duration: 45-50 minutes

### Learning Objectives
- Master different color formats in CSS
- Implement custom fonts and font stacks
- Style text for readability and design
- Understand web-safe fonts vs custom fonts

### Materials Needed
- Color picker tool
- Font specimen sheet
- Google Fonts guide

### Lesson Outline

#### Color in CSS (15 minutes)

1. **Color Formats**
   ```css
   /* Named colors */
   color: red;
   color: darkblue;
   
   /* Hexadecimal */
   color: #FF0000;     /* Red */
   color: #F00;        /* Shorthand */
   color: #333333;     /* Dark gray */
   
   /* RGB */
   color: rgb(255, 0, 0);      /* Red */
   color: rgb(51, 51, 51);     /* Dark gray */
   
   /* RGBA (with transparency) */
   color: rgba(255, 0, 0, 0.5); /* 50% transparent red */
   
   /* HSL (Hue, Saturation, Lightness) */
   color: hsl(0, 100%, 50%);    /* Red */
   ```
2. **Where to Use Colors**
   ```css
   /* Text color */
   color: #333;
   
   /* Backgrounds */
   background-color: #f0f0f0;
   
   /* Borders */
   border-color: #ccc;
   
   /* Box shadows */
   box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
   ```

3. **Color Best Practices**
   - Ensure sufficient contrast (WCAG AA: 4.5:1)
   - Use a consistent color palette
   - Limit to 3-5 main colors
   - Consider color blindness

#### Typography (15 minutes)

1. **Font Families**
   ```css
   /* Generic font families */
   font-family: serif;        /* Times, Georgia */
   font-family: sans-serif;   /* Arial, Helvetica */
   font-family: monospace;    /* Courier, Consolas */
   
   /* Font stacks */
   font-family: Georgia, 'Times New Roman', serif;
   font-family: 'Helvetica Neue', Arial, sans-serif;
   
   /* System fonts */
   font-family: -apple-system, BlinkMacSystemFont, 
                'Segoe UI', Roboto, sans-serif;
   ```
2. **Using Google Fonts**
   ```html
   <!-- In HTML head -->
   <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&display=swap" rel="stylesheet">
   ```
   
   ```css
   /* In CSS */
   body {
       font-family: 'Open Sans', sans-serif;
   }
   ```

3. **Font Properties**
   ```css
   /* Size */
   font-size: 16px;           /* Pixels */
   font-size: 1.2em;          /* Relative to parent */
   font-size: 1.2rem;         /* Relative to root */
   
   /* Weight */
   font-weight: normal;       /* 400 */
   font-weight: bold;         /* 700 */
   font-weight: 300;          /* Light */
   font-weight: 900;          /* Black */
   
   /* Style */
   font-style: normal;
   font-style: italic;
   
   /* Shorthand */
   font: italic bold 16px/1.5 Arial, sans-serif;
   ```

#### Text Styling (10 minutes)

1. **Text Properties**
   ```css
   /* Alignment */
   text-align: left;
   text-align: center;
   text-align: right;
   text-align: justify;
   /* Decoration */
   text-decoration: none;
   text-decoration: underline;
   text-decoration: line-through;
   
   /* Transformation */
   text-transform: uppercase;
   text-transform: lowercase;
   text-transform: capitalize;
   
   /* Spacing */
   letter-spacing: 2px;
   word-spacing: 5px;
   line-height: 1.6;          /* Recommended 1.5-1.7 */
   
   /* Indentation */
   text-indent: 2em;
   
   /* Shadow */
   text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
   ```

#### Hands-On: Typography Makeover (8 minutes)

Students style a blog post with:
```css
/* Base typography */
body {
    font-family: 'Georgia', serif;
    font-size: 18px;
    line-height: 1.6;
    color: #333;
}

h1 {
    font-family: 'Arial', sans-serif;
    font-size: 2.5rem;
    color: #2c3e50;
    text-align: center;
    margin-bottom: 1rem;
}

.intro {
    font-size: 1.2em;
    font-style: italic;
    color: #666;
}

/* Links */
a {
    color: #3498db;
    text-decoration: none;
}

a:hover {
    text-decoration: underline;
}
### Practice Activity (2 minutes)

Create a color palette and typography system:
1. Choose 3-5 colors for your site
2. Select 2 Google Fonts (heading + body)
3. Create text styles for h1-h3 and paragraphs
4. Style links with hover states

### Homework Assignment

1. **Color Scheme Development**
   - Create a cohesive 5-color palette
   - Include primary, secondary, and neutral colors
   - Test color contrast for accessibility

2. **Typography System**
   - Implement Google Fonts on your site
   - Create consistent heading hierarchy
   - Style paragraphs for readability
   - Add special styles for quotes or emphasis

3. **Style Guide Page**
   - Create `style-guide.html`
   - Show all colors with hex codes
   - Display all heading levels
   - Show link states and text styles

### Assessment Criteria
- Proper color format usage: 2 points
- Accessible color contrast: 2 points
- Font implementation: 2 points
- Text styling variety: 2 points
- Overall design cohesion: 2 points
- Total: 10 points
### Typography Tips

1. **Readability First**
   - Body text: 16px minimum
   - Line height: 1.5-1.7
   - Line length: 45-75 characters
   - Sufficient contrast

2. **Font Pairing**
   - Serif + Sans-serif
   - Don't use more than 2-3 fonts
   - Ensure fonts complement each other
   - Consider font weights available

3. **Performance**
   - Limit Google Font weights
   - Use system fonts when possible
   - Consider font loading strategies

### Common Mistakes
- Too many fonts (more than 3)
- Poor color contrast
- Tiny text (under 14px)
- Forgetting fallback fonts
- Overusing text effects
- Inconsistent sizing

### Teacher Notes
- Show contrast checking tools
- Demonstrate Google Fonts interface
- Discuss readability vs. design
- Show examples of good typography
- Let students explore font pairings
- Emphasize accessibility

### Resources
- Google Fonts: fonts.google.com
- Color contrast checker: webaim.org/resources/contrastchecker
- Type Scale: type-scale.com
- Font Pair: fontpair.co
- Adobe Color: color.adobe.com