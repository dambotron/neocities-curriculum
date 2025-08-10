# Lesson 11: What is CSS? Linking Stylesheets

## Duration: 45-50 minutes

### Learning Objectives
- Understand what CSS is and why we use it
- Learn three ways to add CSS to HTML
- Create and link an external stylesheet
- Write basic CSS rules

### Materials Needed
- Completed HTML pages from Month 1
- CSS cheat sheet
- Color picker tool

### Lesson Outline

#### Introduction to CSS (10 minutes)

1. **What is CSS?**
   - Cascading Style Sheets
   - Separates content (HTML) from presentation (CSS)
   - Makes websites beautiful and consistent

2. **CSS Demonstration**
   - Show same HTML with different CSS files
   - Demonstrate the power of styling
   - Explain "cascading" concept

3. **Why Use CSS?**
   - Consistency across pages
   - Easier maintenance
   - Better organization
   - More control over design
#### Three Ways to Add CSS (15 minutes)

1. **Inline CSS** (Quick but not recommended)
   ```html
   <p style="color: blue; font-size: 18px;">This is blue text</p>
   ```
   - Good for testing
   - Hard to maintain
   - Overrides other styles

2. **Internal CSS** (In the head section)
   ```html
   <head>
       <style>
           p {
               color: blue;
               font-size: 18px;
           }
       </style>
   </head>
   ```
   - Good for single-page styles
   - Keeps HTML and CSS together
   - Not reusable across pages

3. **External CSS** (Separate file) - RECOMMENDED
   ```html
   <head>
       <link rel="stylesheet" href="styles.css">
   </head>
   ```
   - Best practice
   - Reusable across all pages
   - Keeps code organized
#### Hands-On: Creating styles.css (15 minutes)

1. **Create the CSS file**
   - In Neocities, create new file: `styles.css`
   - Add basic styles:

```css
/* Reset default styles */
body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
}

/* Style all headings */
h1 {
    color: #333333;
    text-align: center;
}

/* Style paragraphs */
p {
    line-height: 1.6;
    color: #666666;
}

/* Style navigation */
nav {
    background-color: #f0f0f0;
    padding: 10px;
}

nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
}

nav li {
    display: inline;
    margin-right: 20px;
}
```
2. **Link CSS to All HTML Pages**
   - Open each HTML file
   - Add in the `<head>` section:
   ```html
   <link rel="stylesheet" href="styles.css">
   ```
   - Save and upload all files
   - View the styled pages

#### CSS Syntax Review (3 minutes)

```css
selector {
    property: value;
    another-property: another-value;
}
```

- **Selector**: What to style
- **Property**: What aspect to change
- **Value**: What to change it to
- **Semicolon**: Ends each declaration

### Practice Activity (2 minutes)
Add these styles to your CSS:
1. Change the background color of the body
2. Make all links a different color
3. Center all images

### Homework Assignment
1. Link styles.css to ALL your HTML pages
2. Customize the colors to match your personality
3. Add at least 10 CSS rules
4. Style your navigation to look like a menu
5. Experiment with different fonts

### Assessment Criteria
- External stylesheet created: 3 points
- Correctly linked to HTML: 3 points
- Valid CSS syntax: 2 points
- At least 10 rules: 2 points
- Total: 10 points
### Common Mistakes
- Forgetting semicolons
- Wrong file path to CSS
- Typos in property names
- Missing closing braces }
- Using = instead of :
- Forgetting to save CSS file

### Debugging Tips
1. Check the browser developer tools
2. Look for red errors in CSS
3. Verify the link path is correct
4. Make sure CSS file is uploaded
5. Hard refresh the browser (Ctrl+F5)

### Teacher Notes
- Show before/after with CSS
- Demonstrate cascade order (inline > internal > external)
- Let students pick their own color schemes
- Encourage experimentation
- Have students help each other debug
- Show CSS validation tools

### Extension Ideas
- Research Google Fonts
- Try CSS animations (preview)
- Create multiple stylesheets
- Make a "dark mode" version

### Resources
- CSS color picker: colorpicker.me
- CSS validator: jigsaw.w3.org/css-validator
- Font combinations: fontpair.co