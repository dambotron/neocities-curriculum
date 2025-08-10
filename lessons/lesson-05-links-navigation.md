# Lesson 5: Creating Links and Navigation

## Duration: 45-50 minutes

### Learning Objectives
- Create different types of hyperlinks
- Build site navigation
- Understand relative vs absolute paths
- Create email and anchor links

### Materials Needed
- Multiple HTML files from previous lessons
- Navigation examples
- Path diagram handout

### Lesson Outline

#### Introduction to Links (10 minutes)

1. **The Anchor Tag**
   ```html
   <a href="destination">Link Text</a>
   ```
   - `href` = hypertext reference
   - Link text is what users click

2. **Types of Links**
   - Internal (to your own pages)
   - External (to other websites)
   - Email links
   - Anchor links (within same page)

#### Internal Links (10 minutes)

1. **Relative Paths**
   ```html
   <!-- Link to page in same folder -->
   <a href="about.html">About Me</a>
   
   <!-- Link to homepage -->
   <a href="index.html">Home</a>
   ```
2. **Folder Structure**
   ```html
   <!-- Link to page in subfolder -->
   <a href="projects/project1.html">Project 1</a>
   
   <!-- Link to parent folder -->
   <a href="../index.html">Back to Home</a>
   ```

#### External Links (8 minutes)

1. **Absolute URLs**
   ```html
   <a href="https://www.google.com">Google</a>
   <a href="https://neocities.org">Neocities</a>
   ```

2. **Opening in New Tab**
   ```html
   <a href="https://www.example.com" target="_blank">Opens in new tab</a>
   ```
   - Use sparingly
   - Good for external links
   - Keeps your site open

#### Special Links (7 minutes)

1. **Email Links**
   ```html
   <a href="mailto:student@school.edu">Email Me</a>
   ```

2. **Anchor Links**
   ```html
   <!-- Create anchor point -->
   <h2 id="section1">Section 1</h2>
   
   <!-- Link to anchor -->
   <a href="#section1">Go to Section 1</a>
   ```
#### Hands-On: Creating Navigation (12 minutes)

Students add navigation to all their pages:

```html
<nav>
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="favorites.html">Favorites</a></li>
        <li><a href="recipe.html">Recipe</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

**Steps:**
1. Add the navigation code to index.html
2. Copy the same navigation to all other pages
3. Test all links work correctly
4. Style with inline CSS (preview of next month):
   ```html
   <nav style="background-color: #f0f0f0; padding: 10px;">
   ```

#### Best Practices (3 minutes)
- Use descriptive link text (not "click here")
- Check all links work
- Be consistent with navigation
- Consider accessibility
- Use relative paths for internal links
### Practice Activity: Link Scavenger Hunt (5 minutes)

Create a `links.html` page with:
1. 5 external links to educational websites
2. Links to all your internal pages
3. An email link
4. 3 anchor links within the page
5. At least one link that opens in a new tab

### Homework Assignment

1. **Update All Pages**
   - Add consistent navigation to every page
   - Ensure all links work correctly
   - Add a footer with copyright and email link

2. **Create a Resources Page**
   - List helpful websites for learning HTML
   - Include brief descriptions
   - Organize with headings and lists
   - All external links open in new tabs

### Assessment Rubric
- Working navigation on all pages: 4 points
- Correct use of relative paths: 2 points
- External links properly formatted: 2 points
- Special links (email/anchor): 1 point
- Link text is descriptive: 1 point
- Total: 10 points

### Common Issues
- Broken links (wrong paths)
- Missing closing tags
- Forgetting http:// or https://
- Navigation not consistent across pages
- Using spaces in filenames

### Teacher Notes
- Demo the difference between relative and absolute paths
- Show what happens with broken links
- Discuss when to use target="_blank"
- Emphasize testing all links before submitting