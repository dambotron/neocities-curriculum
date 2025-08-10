# Project 3: Responsive Business Website

## Project Overview
Create a fully responsive website for a fictional business of your choice (restaurant, gym, tech startup, etc.) that looks perfect on all devices.

## Duration: 2-3 class periods

## Learning Objectives
- Apply responsive design principles
- Use media queries effectively
- Implement mobile-first design
- Create fluid layouts with Flexbox
- Optimize images for different screen sizes
- Design touch-friendly interfaces

## Project Requirements

### Technical Requirements
1. **Mobile-First Approach**
   - Start with mobile design (320px)
   - Enhance for larger screens
   - No horizontal scrolling at any size

2. **Breakpoints** (minimum)
   - Mobile: 320px - 767px
   - Tablet: 768px - 1023px
   - Desktop: 1024px+
   - Large screens: 1440px+

3. **Required Pages**
   - Home page with hero section
   - About/Services page
   - Gallery/Portfolio page
   - Contact page with form

4. **Navigation**
   - Hamburger menu for mobile
   - Horizontal nav for desktop
   - Smooth transitions between states

5. **Components Required**
   - Responsive image gallery
   - Flexible card layout
   - Contact form
   - Footer with multiple columns

### Design Requirements
- Professional color scheme
- Readable typography at all sizes
- Touch targets minimum 44x44px
- Proper spacing and alignment
- Consistent styling throughout

### Performance Requirements
- Images optimized for web
- Proper meta viewport tag
- Fast loading times
- Smooth animations

## Grading Rubric

### Responsive Design (30 points)
- **Excellent (26-30)**: Perfect at all sizes, creative breakpoints
- **Good (21-25)**: Works well, minor issues at some sizes
- **Satisfactory (15-20)**: Basic responsiveness, some problems
- **Needs Improvement (0-14)**: Major responsive issues

### Code Quality (25 points)
- **Excellent (22-25)**: Clean, organized, well-commented
- **Good (18-21)**: Mostly clean, some organization issues
- **Satisfactory (13-17)**: Works but messy code
- **Needs Improvement (0-12)**: Poor organization, hard to read

### Design & UX (25 points)
- **Excellent (22-25)**: Professional, intuitive, beautiful
- **Good (18-21)**: Good design, minor UX issues
- **Satisfactory (13-17)**: Basic design, usable
- **Needs Improvement (0-12)**: Poor design choices

### Functionality (20 points)
- **Excellent (18-20)**: All features work perfectly
- **Good (15-17)**: Minor bugs
- **Satisfactory (11-14)**: Some features broken
- **Needs Improvement (0-10)**: Major functionality issues

## Starter Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Business Name</title>
    <style>
        /* Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        /* Mobile-First Base Styles */
        body {
            font-family: system-ui, -apple-system, sans-serif;
            line-height: 1.6;
            color: #333;
        }
        
        /* Your styles here */
        
        /* Tablet Styles */
        @media (min-width: 768px) {
            
        }
        
        /* Desktop Styles */
        @media (min-width: 1024px) {
            
        }
        
        /* Large Desktop */
        @media (min-width: 1440px) {
            
        }
    </style>
</head>
<body>
    <!-- Build your responsive website -->
</body>
</html>
```

## Resources
- [Google Mobile-Friendly Test](https://search.google.com/test/mobile-friendly)
- [Responsive Design Checker](https://responsivedesignchecker.com)
- Chrome DevTools Device Mode
- [Unsplash](https://unsplash.com) for free images

## Tips for Success
1. Start with mobile design first
2. Test frequently at different sizes
3. Use relative units (%, em, rem, vw, vh)
4. Make touch targets large enough
5. Optimize images for performance
6. Test on real devices if possible
7. Consider loading times on mobile networks
8. Ensure text remains readable

## Extension Challenges
- Add a sticky navigation
- Implement lazy loading for images
- Create a progressive web app (PWA)
- Add offline functionality
- Implement a dark mode toggle
- Add print styles
- Create custom loading animations
- Build an accessible mega-menu

## Submission Requirements
1. All HTML/CSS files
2. Images used (optimized)
3. README with:
   - Business description
   - Target audience
   - Design decisions
   - Challenges faced
   - Future improvements
4. Live link (GitHub Pages or Neocities)
