# Lesson 20: Media Queries and Responsive Design

## Duration: 45-50 minutes

### Learning Objectives
- Understand responsive web design principles
- Write media queries for different screen sizes
- Create mobile-first designs
- Test responsive layouts

### Materials Needed
- Multiple devices or browser DevTools
- Responsive design examples
- Breakpoint reference sheet

### Lesson Outline

#### Introduction to Responsive Design (10 minutes)

1. **Why Responsive Design?**
   - Multiple device sizes
   - Better user experience
   - Google prioritizes mobile-friendly sites
   - One codebase for all devices

2. **Key Concepts**
   - Fluid grids
   - Flexible images
   - Media queries
   - Mobile-first approach

3. **Viewport Meta Tag**
   ```html
   <!-- Required in HTML head -->
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```
#### Media Query Syntax (15 minutes)

1. **Basic Syntax**
   ```css
   @media (max-width: 768px) {
       /* Styles for screens 768px and smaller */
   }
   
   @media (min-width: 769px) {
       /* Styles for screens 769px and larger */
   }
   ```

2. **Common Breakpoints**
   ```css
   /* Mobile phones */
   @media (max-width: 480px) { }
   
   /* Tablets */
   @media (min-width: 481px) and (max-width: 768px) { }
   
   /* Small laptops */
   @media (min-width: 769px) and (max-width: 1024px) { }
   
   /* Desktops */
   @media (min-width: 1025px) { }
   ```

3. **Mobile-First Approach**
   ```css
   /* Base styles (mobile) */
   .container {
       width: 100%;
       padding: 10px;
   }
   
   /* Tablet and up */
   @media (min-width: 768px) {
       .container {
           width: 750px;
           margin: 0 auto;
       }
   }
   
   /* Desktop and up */
   @media (min-width: 1024px) {
       .container {
           width: 960px;
       }
   }
   ```
#### Responsive Design Patterns (10 minutes)

1. **Responsive Navigation**
   ```css
   /* Mobile - Vertical menu */
   nav ul {
       flex-direction: column;
   }
   
   /* Desktop - Horizontal menu */
   @media (min-width: 768px) {
       nav ul {
           flex-direction: row;
       }
   }
   ```

2. **Flexible Images**
   ```css
   img {
       max-width: 100%;
       height: auto;
   }
   ```

3. **Responsive Typography**
   ```css
   /* Base size */
   body {
       font-size: 16px;
   }
   
   /* Larger screens */
   @media (min-width: 768px) {
       body {
           font-size: 18px;
       }
   }
   
   /* Using relative units */
   h1 {
       font-size: 2rem;  /* Scales with root */
   }
   ```
#### Hands-On: Responsive Gallery (12 minutes)

Create a responsive image gallery:

```html
<div class="gallery">
    <div class="gallery-item">
        <img src="image1.jpg" alt="Image 1">
    </div>
    <div class="gallery-item">
        <img src="image2.jpg" alt="Image 2">
    </div>
    <!-- More items... -->
</div>
```

```css
/* Mobile - 1 column */
.gallery {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
}

.gallery-item {
    width: 100%;
}

/* Tablet - 2 columns */
@media (min-width: 768px) {
    .gallery-item {
        width: calc(50% - 5px);
    }
}

/* Desktop - 3 columns */
@media (min-width: 1024px) {
    .gallery-item {
        width: calc(33.333% - 7px);
    }
}
```

#### Testing Responsive Design (3 minutes)

1. Browser DevTools responsive mode
2. Resize browser window
3. Test on actual devices
4. Check all breakpoints
### Practice Exercise

Create a responsive layout with:
1. Header that stacks on mobile
2. Two-column layout on desktop
3. Single column on mobile
4. Responsive font sizes

### Homework Assignment

1. **Make Your Site Responsive**
   - Add viewport meta tag
   - Create at least 3 media queries
   - Test on phone, tablet, desktop sizes
   - Make navigation mobile-friendly

2. **Responsive Components**
   - Gallery adapts to screen size
   - Text is readable on all devices
   - Images scale properly
   - No horizontal scrolling

3. **Advanced Challenge**
   - Create a hamburger menu for mobile
   - Use CSS Grid with media queries
   - Add print styles

### Common Responsive Patterns

```css
/* Hide/Show elements */
.desktop-only {
    display: none;
}

@media (min-width: 768px) {
    .desktop-only {
        display: block;
    }
    .mobile-only {
        display: none;
    }
}

/* Flexible containers */
.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
}
```
### Assessment Criteria
- Viewport meta tag present: 2 points
- Correct media query syntax: 3 points
- Appropriate breakpoints: 2 points
- Mobile-friendly design: 2 points
- No horizontal scroll: 1 point
- Total: 10 points

### Best Practices
1. Start with mobile design
2. Use min-width for mobile-first
3. Test on real devices when possible
4. Keep breakpoints consistent
5. Don't forget landscape orientation
6. Consider touch targets (44px minimum)

### Common Mistakes
- Forgetting viewport meta tag
- Too many breakpoints
- Pixel-perfect attempts
- Not testing enough
- Fixed widths on mobile
- Text too small on mobile

### Teacher Notes
- Show examples of responsive sites
- Demonstrate DevTools device mode
- Discuss mobile-first benefits
- Let students test each other's sites
- Show how to check mobile-friendliness
- Emphasize content prioritization

### Resources
- Chrome DevTools device mode
- ResponsiveDesign.is
- Mobile-Friendly Test (Google)
- Common device dimensions reference
- Responsive design patterns gallery