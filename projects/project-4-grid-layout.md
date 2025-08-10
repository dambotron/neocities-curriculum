# Project 4: Modern Layout Challenge - Magazine/Blog Design

## Project Overview
Create a sophisticated magazine-style website or blog using CSS Grid and Flexbox to achieve complex, professional layouts that adapt beautifully to any screen size.

## Duration: 2-3 class periods

## Learning Objectives
- Master CSS Grid for complex layouts
- Combine Grid and Flexbox effectively
- Create asymmetric, creative designs
- Implement auto-responsive layouts
- Use modern CSS features
- Design content-first layouts

## Project Requirements

### Technical Requirements

1. **CSS Grid Implementation**
   - Main layout using CSS Grid
   - Use grid-template-areas for at least one section
   - Implement auto-fit or auto-fill
   - Use fr units and minmax()
   - Create overlapping elements
   - Minimum 3 different grid layouts

2. **Flexbox Integration**
   - Navigation using Flexbox
   - Card components with Flexbox
   - Footer layout with Flexbox
   - Combine with Grid where appropriate

3. **Required Sections**
   - Masthead/Header with navigation
   - Featured article (hero) section
   - Article grid with varied sizes
   - Sidebar with widgets
   - Photo gallery or portfolio grid
   - Newsletter signup section
   - Multi-column footer

4. **Layout Features**
   - Asymmetric article layout
   - Magazine-style text columns
   - Pull quotes
   - Image galleries
   - Advertisement placements
   - Related articles section

### Design Requirements
- Professional typography
- Clear visual hierarchy
- Consistent spacing using gap
- Creative use of white space
- Modern, clean aesthetic
- Print-inspired design elements

### Responsive Requirements
- NO media queries for main grid (use auto-fit/auto-fill)
- Graceful degradation on mobile
- Maintain readability at all sizes
- Images scale appropriately

## Grading Rubric

### Grid Mastery (30 points)
- **Excellent (26-30)**: Creative, complex grids, perfect implementation
- **Good (21-25)**: Good use of Grid, minor issues
- **Satisfactory (15-20)**: Basic Grid usage, some mistakes
- **Needs Improvement (0-14)**: Poor Grid implementation

### Layout Creativity (25 points)
- **Excellent (22-25)**: Unique, professional, magazine-quality
- **Good (18-21)**: Creative layout, good visual interest
- **Satisfactory (13-17)**: Standard layout, lacks creativity
- **Needs Improvement (0-12)**: Basic or broken layout

### Flexbox Integration (20 points)
- **Excellent (18-20)**: Perfect Grid/Flexbox combination
- **Good (15-17)**: Good integration, minor issues
- **Satisfactory (11-14)**: Basic integration
- **Needs Improvement (0-10)**: Poor or no integration

### Code Quality (25 points)
- **Excellent (22-25)**: Clean, efficient, well-organized
- **Good (18-21)**: Good organization, minor issues
- **Satisfactory (13-17)**: Works but inefficient
- **Needs Improvement (0-12)**: Messy, hard to maintain

## Starter Code

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modern Magazine</title>
    <style>
        /* Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        /* CSS Variables */
        :root {
            --primary-color: #2c3e50;
            --accent-color: #e74c3c;
            --text-color: #333;
            --light-bg: #ecf0f1;
            --gap: 1.5rem;
        }
        
        body {
            font-family: Georgia, serif;
            line-height: 1.6;
            color: var(--text-color);
        }
        
        /* Main Grid Container */
        .magazine-layout {
            display: grid;
            grid-template-columns: repeat(12, 1fr);
            grid-auto-rows: minmax(100px, auto);
            gap: var(--gap);
            max-width: 1400px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        /* Grid Areas Template Example */
        .header {
            grid-column: 1 / -1;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        /* Feature Article Example */
        .feature-article {
            grid-column: 1 / 9;
            grid-row: span 3;
        }
        
        /* Sidebar Example */
        .sidebar {
            grid-column: 9 / -1;
            grid-row: span 3;
        }
        
        /* Article Grid */
        .article-grid {
            grid-column: 1 / -1;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: var(--gap);
        }
        
        /* Your additional styles here */
        
    </style>
</head>
<body>
    <div class="magazine-layout">
        <!-- Build your magazine layout -->
    </div>
</body>
</html>
```

## Required Components

### 1. Masthead
- Logo/Title
- Navigation menu
- Search bar
- Date/Issue number

### 2. Featured Article
- Large hero image
- Headline
- Excerpt
- Author byline
- Read time

### 3. Article Cards (minimum 6)
- Varied sizes (some span 2 columns)
- Images
- Headlines
- Categories
- Excerpts

### 4. Sidebar Widgets
- Popular articles
- Newsletter signup
- Social media links
- Advertisement
- Categories/Tags

### 5. Photo Gallery
- Grid of images
- Captions
- Lightbox effect (bonus)

### 6. Footer
- Multiple columns
- Links
- Copyright
- Social icons

## Creative Challenges

### Layout Ideas
1. **Newspaper Style**: Multi-column text flow
2. **Pinterest Style**: Masonry layout
3. **Card Overlap**: Elements that break the grid
4. **Asymmetric**: Intentionally unbalanced design
5. **Mondrian**: Colored blocks inspired by art

### Advanced Features (Bonus)
- Sticky sidebar that follows scroll
- CSS-only image carousel
- Expandable article cards
- Filter system for articles
- Dark mode toggle
- Print stylesheet
- CSS counters for numbering
- Custom properties for theming

## Resources
- [Grid by Example](https://gridbyexample.com)
- [CSS Grid Garden](https://cssgridgarden.com)
- [Flexbox Froggy](https://flexboxfroggy.com)
- [Magazine Layout Inspiration](https://www.awwwards.com)
- [Lorem Picsum](https://picsum.photos) for placeholder images

## Tips for Success
1. Sketch your layout on paper first
2. Use Firefox Grid Inspector
3. Start with mobile, enhance with Grid
4. Name your grid lines for clarity
5. Use grid-template-areas for complex sections
6. Don't overuse Grid - sometimes Flexbox is better
7. Test with different content lengths
8. Consider readability and scan patterns

## Submission Requirements
1. All HTML/CSS files
2. At least 6 article entries with real content
3. Images (optimized and attributed)
4. README with:
   - Magazine/Blog concept
   - Target audience
   - Grid techniques used
   - Challenges overcome
   - What you learned
5. Live deployment link

## Assessment Criteria
- Creative use of CSS Grid
- Professional appearance
- Clean, maintainable code
- Responsive without media queries
- Effective Grid/Flexbox combination
- Visual hierarchy and typography
- Overall user experience
