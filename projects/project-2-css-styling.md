# Project 2: Style Your Personal Website with CSS

## Project Duration: 2-3 class periods

### Project Overview
Transform your HTML-only website from Project 1 into a beautifully styled, modern website using CSS. This project demonstrates your ability to separate content from presentation and create visually appealing web pages.

### Project Requirements

#### Technical Requirements

1. **External Stylesheet**
   - Create a comprehensive styles.css file
   - Link to all HTML pages
   - No inline styles (except for special cases)
   - Organized with comments

2. **Required CSS Implementations**
   - Custom color scheme (minimum 5 colors)
   - Typography styling (fonts, sizes, weights)
   - Navigation menu styling
   - Image styling and borders
   - Spacing with margin and padding
   - Background colors/images
   - Hover effects on links
   - Styled lists
   - Table styling

3. **Layout Requirements**
   - Centered content wrapper
   - Consistent header/footer styling
   - Proper spacing between elements
   - Responsive images (max-width: 100%)
   - Navigation that looks like a real menu
### Design Requirements

#### Color Scheme
- Choose a cohesive color palette
- Primary color for headers
- Secondary color for accents
- Background colors
- Text colors with good contrast
- Link colors (normal, hover, visited)

#### Typography
- Choose appropriate fonts
- Establish hierarchy with font sizes
- Use font weights effectively
- Ensure readability
- Consistent line-height

#### Navigation Design
- Horizontal or vertical menu
- Clear hover states
- Active page indication
- Visually separated from content
- Professional appearance

#### Visual Enhancements
- Rounded corners where appropriate
- Box shadows for depth
- Consistent spacing
- Styled form elements
- Custom bullet points (optional)
- Background patterns/gradients (optional)
### Grading Rubric (100 points)

#### CSS Technical Skills (35 points)
- [ ] External stylesheet properly linked (5 pts)
- [ ] Valid CSS syntax throughout (5 pts)
- [ ] Minimum 50 CSS rules (10 pts)
- [ ] Proper use of selectors (5 pts)
- [ ] Organized with comments (5 pts)
- [ ] No inline styles (5 pts)

#### Design & Aesthetics (35 points)
- [ ] Cohesive color scheme (10 pts)
- [ ] Professional typography (10 pts)
- [ ] Attractive navigation (10 pts)
- [ ] Consistent spacing (5 pts)

#### Required Elements (20 points)
- [ ] All links styled with hover (5 pts)
- [ ] Images properly styled (5 pts)
- [ ] Lists customized (5 pts)
- [ ] Table styling if present (5 pts)

#### Creativity & Polish (10 points)
- [ ] Goes beyond requirements (5 pts)
- [ ] Shows design thinking (5 pts)

### Required CSS Properties
Must use at least once:
- font-family, font-size, font-weight
- color, background-color
- margin, padding
- border, border-radius
- text-align, line-height
- display, width, max-width
- :hover pseudo-class
### Example CSS Structure
```css
/* ===== RESET & BASE STYLES ===== */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
}

/* ===== LAYOUT ===== */
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* ===== NAVIGATION ===== */
nav {
    background-color: #2c3e50;
    padding: 1rem 0;
}

/* ===== TYPOGRAPHY ===== */
h1, h2, h3 {
    margin-bottom: 1rem;
    color: #2c3e50;
}

/* Continue with more styles... */
```

### Project Tips
1. Start with a CSS reset
2. Use a consistent naming convention
3. Group related styles together
4. Test on different screen sizes
5. Use browser DevTools to experiment
6. Get feedback on color choices
### Submission Requirements
1. Updated website live on Neocities
2. All CSS in external stylesheet
3. Project reflection document including:
   - Your design inspiration
   - Challenges you faced
   - What you're most proud of
   - What you would improve

### Extension Challenges
- Add CSS animations
- Create a print stylesheet
- Implement a dark mode toggle
- Use CSS Grid for layout
- Add custom fonts from Google Fonts
- Create CSS art or shapes

### Design Resources
- **Color Palettes**: coolors.co, color.adobe.com
- **Fonts**: fonts.google.com
- **Inspiration**: awwwards.com, css-tricks.com
- **Icons**: fontawesome.com (basic icons)

### Common CSS Mistakes to Avoid
- Forgetting units (px, %, em)
- Over-specific selectors
- Not testing hover states
- Poor color contrast
- Inconsistent spacing
- Fighting default styles instead of resetting

### Timeline
- **Day 1**: Plan design, create color scheme, start CSS
- **Day 2**: Complete styling, test all pages
- **Day 3**: Polish, debug, and submit

Remember: Good design takes time. Start simple and build up!