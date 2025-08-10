# Lesson 5: Creating Links and Navigation
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Create links to external websites, internal pages, and email addresses
- Build a navigation menu that works across multiple pages
- Use anchor links to jump to sections within the same page
- Understand absolute vs relative paths
- Apply link attributes like target="_blank" appropriately
- Style link states (preview for CSS)

### Materials Needed
- Text editor with multiple files open
- Web browser with tabs
- Projector for demonstrations
- Sample multi-page website files (provided)
- Printed diagram of file structure
- Students' existing HTML files from previous lessons

### Key Vocabulary with Definitions
- **Hyperlink**: Clickable text or element that navigates to another location
- **URL**: Uniform Resource Locator - complete web address
- **Absolute Path**: Full URL including protocol (https://example.com)
- **Relative Path**: Path relative to current file location
- **Anchor**: Link that jumps to a specific part of a page
- **Navigation**: Menu system for moving between pages
- **Protocol**: The method of transfer (http://, https://, mailto:)
- **Target Attribute**: Specifies where to open the linked document

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding How Links Work (5 minutes)

**Teacher Script:**
"Links are what make the World Wide Web a WEB! Without links, websites would be isolated islands. Today, you'll connect your pages into a real website!"
**[CREATE new file: links-demo.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Links and Navigation Demo</title>
</head>
<body>
    <h1>Types of Links</h1>
```

**"The Anchor Tag Anatomy:"**
```html
<a href="destination">Clickable Text</a>
```

"Let's break this down:
- `<a>` = Anchor tag (creates the link)
- `href` = Hypertext REFerence (where it goes)
- `destination` = URL, file path, or special value
- `Clickable Text` = What users see and click
- `</a>` = Closing anchor tag

Think of it like a portal: href is the destination, the text is the door!"

### All Types of Links (10 minutes)

**[TYPE and explain each type]**

```html
    <h2>1. External Links (to other websites)</h2>
    <p>Visit <a href="https://www.google.com">Google</a> to search.</p>
    <p>Learn at <a href="https://www.w3schools.com">W3Schools</a>.</p>
```
"External links MUST include the protocol (https:// or http://). Without it, the browser thinks it's a file on YOUR site!"

```html
    <h2>2. Internal Links (to your own pages)</h2>
    <p>Go to my <a href="about.html">About Page</a>.</p>
    <p>See my <a href="contact.html">Contact Info</a>.</p>
    <p>Return to <a href="index.html">Homepage</a>.</p>
```"Internal links use RELATIVE paths - just the filename if it's in the same folder!"

```html
    <h2>3. Email Links</h2>
    <p>Email me at <a href="mailto:student@school.edu">student@school.edu</a></p>
    <p>Contact support: <a href="mailto:help@example.com?subject=Help%20Request">Send Help Request</a></p>
```
"The mailto: protocol opens the user's email program! You can even pre-fill the subject line!"

```html
    <h2>4. Phone Links (for mobile)</h2>
    <p>Call us: <a href="tel:+1-555-123-4567">(555) 123-4567</a></p>
    <p>Text us: <a href="sms:+15551234567">Send SMS</a></p>
```
"On mobile devices, tel: opens the phone app, sms: opens texting!"

```html
    <h2>5. Download Links</h2>
    <a href="resume.pdf" download>Download My Resume (PDF)</a>
    <a href="photo.jpg" download="vacation-photo.jpg">Download Photo</a>
```
"The download attribute forces download instead of opening in browser!"

```html
    <h2>6. Anchor Links (same page jumping)</h2>
    <p>Jump to <a href="#section2">Section 2</a></p>
    <p>Go to <a href="#footer">Bottom of Page</a></p>
    
    <!-- Later in the page: -->
    <h2 id="section2">Section 2</h2>
    <p>You jumped here!</p>
    
    <footer id="footer">
        <p>This is the footer</p>
    </footer>
```
"The # symbol means 'find an ID on THIS page'. The ID is the landing spot!"
```html
    <h2>7. Link Attributes</h2>
    <!-- Open in new tab -->
    <p><a href="https://google.com" target="_blank">Opens in New Tab</a></p>
    
    <!-- With title (tooltip on hover) -->
    <p><a href="about.html" title="Learn more about me">About (hover for tooltip)</a></p>
    
    <!-- Relationship attribute -->
    <p><a href="https://sketchy-site.com" target="_blank" rel="noopener noreferrer">Secure External Link</a></p>
```
"Important attributes:
- `target="_blank"` = Opens in new tab (use sparingly!)
- `title` = Shows tooltip on hover
- `rel="noopener noreferrer"` = Security for target="_blank" links"

```html
    <h2>8. Special Link Types</h2>
    <!-- Link that does nothing (placeholder) -->
    <a href="#">Placeholder Link</a>
    
    <!-- JavaScript link (we won't use these) -->
    <a href="javascript:void(0)">Does Nothing</a>
    
    <!-- Link to top of page -->
    <a href="#top">Back to Top</a> <!-- Works without an ID! -->
</body>
</html>
```

**[SAVE and DEMONSTRATE each link type in browser]**

"Watch how each link behaves differently:
- External links leave your site (that's why some use target="_blank")
- Internal links stay on your site
- Anchor links don't reload the page, just scroll
- Email links open mail programs"

---
## PART 2: WE DO (Guided Practice) - 20 minutes

### Building a Navigation Menu Together (10 minutes)

**Teacher Script:**
"Every website needs navigation! Let's build a menu that works across ALL your pages. This is the most important skill today!"

**Step 1: Plan Our Site Structure**
"First, let's map out our website:
```
my-website/
├── index.html (Homepage)
├── about.html (About Me)
├── projects.html (My Projects)
├── contact.html (Contact Info)
└── gallery.html (Photo Gallery)
```
Everyone write this down - this is your site map!"

**Step 2: Create the Navigation HTML**

"Open your index.html and let's add navigation at the top of the body:"

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Home | My Portfolio Site</title>
</head>
<body>
    <!-- Navigation Menu -->
    <nav>
        <a href="index.html">Home</a> | 
        <a href="about.html">About</a> | 
        <a href="projects.html">Projects</a> | 
        <a href="gallery.html">Gallery</a> | 
        <a href="contact.html">Contact</a>
    </nav>
    
    <h1>Welcome to My Portfolio</h1>
    <p>This is my homepage with working navigation!</p>
```"Notice:
- We use `<nav>` tag - semantic HTML for navigation!
- Pipes | separate links (we'll make this prettier with CSS later)
- Even on homepage, we include the Home link
- All links are relative paths (just filenames)"

**Step 3: Copy Navigation to All Pages**

"Now the CRITICAL step - this EXACT navigation goes on EVERY page:"

```html
<!-- about.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About | My Portfolio Site</title>
</head>
<body>
    <!-- SAME Navigation Menu -->
    <nav>
        <a href="index.html">Home</a> | 
        <a href="about.html">About</a> | 
        <a href="projects.html">Projects</a> | 
        <a href="gallery.html">Gallery</a> | 
        <a href="contact.html">Contact</a>
    </nav>
    
    <h1>About Me</h1>
    <p>Learn more about my journey...</p>
```

"CHECKPOINT: Everyone add this navigation to at least 2 pages. Test that links work!"

**Common Navigation Patterns:**
```html
<!-- Horizontal with spacing -->
<nav>
    <a href="index.html">Home</a> &nbsp;&nbsp;
    <a href="about.html">About</a> &nbsp;&nbsp;
    <a href="contact.html">Contact</a>
</nav>
<!-- Using bullets -->
<nav>
    • <a href="index.html">Home</a>
    • <a href="about.html">About</a>
    • <a href="contact.html">Contact</a>
</nav>

<!-- Using list (semantic but needs CSS later) -->
<nav>
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

### Creating Anchor Links (10 minutes)

"Now let's make a single page with a table of contents that jumps to sections!"

**Step 4: Build a Page with Anchors**

"Create a new file called `blog.html`:"

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Blog | Portfolio Site</title>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <a href="index.html">Home</a> | 
        <a href="about.html">About</a> | 
        <a href="blog.html">Blog</a> | 
        <a href="contact.html">Contact</a>
    </nav>
    
    <h1>My Web Development Blog</h1>
    
    <!-- Table of Contents with Anchor Links -->
    <h2>Table of Contents</h2>
    <ul>
        <li><a href="#post1">My First Website</a></li>        <li><a href="#post2">Learning HTML</a></li>
        <li><a href="#post3">CSS Excitement</a></li>
        <li><a href="#resources">Helpful Resources</a></li>
    </ul>
    
    <hr>
    
    <!-- Blog Posts with IDs for anchors -->
    <article id="post1">
        <h2>My First Website</h2>
        <p><small>Posted: January 10, 2024</small></p>
        <p>Today I created my first website! It was amazing to see my HTML come to life...</p>
        <p>Lorem ipsum dolor sit amet... (add more content so scrolling works)</p>
        <p><a href="#top">↑ Back to top</a></p>
    </article>
    
    <hr>
    
    <article id="post2">
        <h2>Learning HTML</h2>
        <p><small>Posted: January 12, 2024</small></p>
        <p>HTML is easier than I thought! Today I learned about links and navigation...</p>
        <p>Lorem ipsum dolor sit amet... (add more content)</p>
        <p><a href="#top">↑ Back to top</a></p>
    </article>
    
    <hr>
    
    <article id="post3">
        <h2>CSS Excitement</h2>
        <p><small>Posted: January 15, 2024</small></p>
        <p>Can't wait to start CSS next week and make everything beautiful...</p>
        <p>Lorem ipsum dolor sit amet... (add more content)</p>
        <p><a href="#top">↑ Back to top</a></p>
    </article>
    
    <hr>
    
    <section id="resources">
        <h2>Helpful Resources</h2>        <ul>
            <li><a href="https://www.w3schools.com" target="_blank" rel="noopener">W3Schools</a> - Great tutorials</li>
            <li><a href="https://developer.mozilla.org" target="_blank" rel="noopener">MDN Web Docs</a> - Detailed reference</li>
            <li><a href="https://codepen.io" target="_blank" rel="noopener">CodePen</a> - Practice coding</li>
        </ul>
        <p><a href="#top">↑ Back to top</a></p>
    </section>
    
    <footer>
        <p>&copy; 2024 My Blog | <a href="mailto:student@school.edu">Email Me</a></p>
    </footer>
</body>
</html>
```

**Teacher Script:**
"See how anchor links work:
1. The link has `href="#something"`
2. An element has `id="something"`
3. Click the link = jump to that ID
4. No page reload - just scrolling!
5. Back to top links make long pages user-friendly"

---

## PART 3: YOU DO (Independent Practice) - 10 minutes

### Student Activity: Create a Complete Multi-Page Website

**Instructions:**
"Build a 3-page website with working navigation and various link types. You have 10 minutes!"

**Required Tasks:**
1. ✅ Create three files: home.html, portfolio.html, resources.html
2. ✅ Add identical navigation menu to ALL three pages
3. ✅ Include at least 3 external links (use target="_blank" appropriately)
4. ✅ Add an email link with pre-filled subject
5. ✅ Create anchor links on at least one page
6. ✅ Include a "Back to Top" link on long pages
7. ✅ Add title attributes for accessibility
8. ✅ Use semantic `<nav>` tags
9. ✅ Test ALL links work correctly10. ✅ Upload to Neocities and verify links work online

**Bonus Challenges:**
- Add breadcrumb navigation (Home > Projects > Project 1)
- Create a sitemap page with links to everything
- Add social media links with icons (we'll style later)
- Make a "skip to content" accessibility link

### Complete Solution Example:

**File 1: home.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Home | Student Portfolio</title>
</head>
<body>
    <!-- Skip to content for accessibility -->
    <a href="#main" style="position: absolute; left: -9999px;">Skip to main content</a>
    
    <!-- Main Navigation -->
    <nav>
        <a href="home.html" title="Homepage">Home</a> | 
        <a href="portfolio.html" title="View my work">Portfolio</a> | 
        <a href="resources.html" title="Helpful links">Resources</a>
    </nav>
    
    <main id="main">
        <h1>Welcome to My Portfolio Site</h1>
        <p>Hi! I'm a web development student learning HTML and CSS.</p>
        
        <h2>Quick Links</h2>
        <ul>
            <li><a href="portfolio.html#websites">My Websites</a></li>
            <li><a href="portfolio.html#projects">Class Projects</a></li>
            <li><a href="resources.html#tutorials">Learning Resources</a></li>
        </ul>        
        <h2>Contact Me</h2>
        <p>
            Email: <a href="mailto:student@school.edu?subject=Portfolio%20Feedback" 
                     title="Send me an email">student@school.edu</a><br>
            Phone: <a href="tel:+15551234567" title="Call me">(555) 123-4567</a><br>
            GitHub: <a href="https://github.com" target="_blank" 
                      rel="noopener noreferrer" title="View my code (opens in new tab)">@mystudentname</a>
        </p>
    </main>
    
    <footer>
        <p>&copy; 2024 Student Name | <a href="#top">Back to top</a></p>
    </footer>
</body>
</html>
```

**File 2: portfolio.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio | Student Portfolio</title>
</head>
<body>
    <!-- Main Navigation (SAME on every page) -->
    <nav>
        <a href="home.html" title="Homepage">Home</a> | 
        <a href="portfolio.html" title="View my work">Portfolio</a> | 
        <a href="resources.html" title="Helpful links">Resources</a>
    </nav>
    
    <h1>My Portfolio</h1>
    
    <!-- Page Navigation -->
    <h2>Jump to Section</h2>
    <ul>
        <li><a href="#websites">Websites I've Built</a></li>
        <li><a href="#projects">Class Projects</a></li>        <li><a href="#experiments">Experiments</a></li>
    </ul>
    
    <hr>
    
    <section id="websites">
        <h2>Websites I've Built</h2>
        <ul>
            <li><a href="recipe.html">Recipe Collection</a> - My first HTML project</li>
            <li><a href="blog.html">Personal Blog</a> - Thoughts on learning to code</li>
            <li><a href="tribute.html">Tribute Page</a> - Honoring my favorite author</li>
        </ul>
        <p><a href="#top">↑ Top</a></p>
    </section>
    
    <section id="projects">
        <h2>Class Projects</h2>
        <ul>
            <li><strong>Week 1:</strong> <a href="about.html">About Me Page</a></li>
            <li><strong>Week 2:</strong> <a href="contact.html">Contact Form</a></li>
            <li><strong>Week 3:</strong> <a href="gallery.html">Photo Gallery</a></li>
        </ul>
        <p><a href="#top">↑ Top</a></p>
    </section>
    
    <section id="experiments">
        <h2>Code Experiments</h2>
        <p>Check out my coding experiments on 
           <a href="https://codepen.io" target="_blank" rel="noopener noreferrer">CodePen</a> 
           <small>(opens in new tab)</small></p>
        <p><a href="#top">↑ Top</a></p>
    </section>
    
    <footer>
        <p>&copy; 2024 | <a href="home.html">Home</a> | 
           <a href="mailto:student@school.edu">Contact</a></p>
    </footer>
</body>
</html>
```
**File 3: resources.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resources | Student Portfolio</title>
</head>
<body>
    <!-- Main Navigation (SAME on every page) -->
    <nav>
        <a href="home.html" title="Homepage">Home</a> | 
        <a href="portfolio.html" title="View my work">Portfolio</a> | 
        <a href="resources.html" title="Helpful links">Resources</a>
    </nav>
    
    <h1>Web Development Resources</h1>
    <p>My collection of helpful links for learning web development.</p>
    
    <section id="tutorials">
        <h2>Learning Websites</h2>
        <ul>
            <li>
                <a href="https://www.w3schools.com" target="_blank" rel="noopener noreferrer">
                    W3Schools
                </a> - Interactive tutorials and references
            </li>
            <li>
                <a href="https://developer.mozilla.org" target="_blank" rel="noopener noreferrer">
                    MDN Web Docs
                </a> - Comprehensive documentation
            </li>
            <li>
                <a href="https://www.freecodecamp.org" target="_blank" rel="noopener noreferrer">
                    freeCodeCamp
                </a> - Free coding bootcamp
            </li>
            <li>
                <a href="https://css-tricks.com" target="_blank" rel="noopener noreferrer">
                    CSS-Tricks
                </a> - CSS tips and techniques
            </li>
        </ul>    </section>
    
    <section id="tools">
        <h2>Development Tools</h2>
        <ul>
            <li>
                <a href="https://code.visualstudio.com/" target="_blank" rel="noopener noreferrer">
                    VS Code
                </a> - Free code editor
            </li>
            <li>
                <a href="https://validator.w3.org/" target="_blank" rel="noopener noreferrer">
                    HTML Validator
                </a> - Check your HTML for errors
            </li>
            <li>
                <a href="https://jsfiddle.net/" target="_blank" rel="noopener noreferrer">
                    JSFiddle
                </a> - Online code playground
            </li>
        </ul>
    </section>
    
    <section id="inspiration">
        <h2>Design Inspiration</h2>
        <ul>
            <li><a href="https://dribbble.com" target="_blank" rel="noopener noreferrer">Dribbble</a></li>
            <li><a href="https://www.awwwards.com" target="_blank" rel="noopener noreferrer">Awwwards</a></li>
            <li><a href="https://codepen.io" target="_blank" rel="noopener noreferrer">CodePen</a></li>
        </ul>
    </section>
    
    <section>
        <h2>Need Help?</h2>
        <p>Feel free to <a href="mailto:student@school.edu?subject=Web%20Dev%20Question&body=Hi!%20I%20have%20a%20question%20about...">
           email me with questions</a>!</p>
    </section>
    
    <footer>
        <p>&copy; 2024 | <a href="#top">Back to top</a> | 
           <a href="home.html">Return Home</a></p>
    </footer>
</body>
</html>
```
---

## Assessment & Closing (5 minutes)

### Exit Ticket Questions

1. **What's the difference between absolute and relative paths?**
   - Answer: Absolute paths include the full URL with protocol (https://example.com/page.html), relative paths are relative to the current file location (page.html or ../folder/page.html)

2. **Write the HTML for a link that opens Google in a new tab:**
   - Answer: `<a href="https://google.com" target="_blank" rel="noopener noreferrer">Google</a>`

3. **How do you create an email link with the subject "Hello"?**
   - Answer: `<a href="mailto:email@example.com?subject=Hello">Email me</a>`

4. **What HTML creates an anchor link to jump to an element with id="footer"?**
   - Answer: `<a href="#footer">Go to footer</a>`

5. **Why should navigation be identical on every page?**
   - Answer: Consistency helps users know where they are and how to navigate your site. It's a fundamental principle of good web design.

### Success Criteria Checklist
- [ ] Created working navigation on multiple pages (3 pts)
- [ ] Used both internal and external links correctly (2 pts)
- [ ] Implemented anchor links with IDs (2 pts)
- [ ] Added appropriate link attributes (2 pts)
- [ ] Used semantic nav tags (1 pt)
- [ ] All links tested and working (3 pts)
- [ ] Included email/phone links (2 pts)
- [ ] Used title attributes for accessibility (2 pts)
- [ ] Proper use of target="_blank" with rel attribute (3 pts)
**Total: ___/20 points**

### Homework Assignment

**Create a "Sitemap" Page (`sitemap.html`):**
Requirements:
1. Create a comprehensive sitemap showing ALL pages on your site
2. Organize links hierarchically (main pages, sub-pages)
3. Include at least 8 internal links
4. Add 5 external resource links
5. Create a "breadcrumb" trail (Home > Current Page)
6. Include both text and email contact links
7. Add a search engine link that searches your site
8. Use nested lists to show site structure

**Homework Solution Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sitemap | My Portfolio Site</title>
</head>
<body>
    <!-- Breadcrumb Navigation -->
    <p><a href="index.html">Home</a> &gt; Sitemap</p>
    
    <h1>Complete Site Map</h1>
    <p>All pages and resources on this website:</p>
    
    <h2>Main Pages</h2>
    <ul>
        <li><a href="index.html">Homepage</a>
            <ul>
                <li><a href="index.html#welcome">Welcome Section</a></li>
                <li><a href="index.html#featured">Featured Work</a></li>
            </ul>
        </li>
        <li><a href="about.html">About Me</a>
            <ul>
                <li><a href="about.html#bio">Biography</a></li>
                <li><a href="about.html#skills">Skills</a></li>
                <li><a href="about.html#education">Education</a></li>
            </ul>        </li>
        <li><a href="portfolio.html">Portfolio</a>
            <ul>
                <li><a href="project1.html">Project 1: Recipe Site</a></li>
                <li><a href="project2.html">Project 2: Blog</a></li>
                <li><a href="project3.html">Project 3: Gallery</a></li>
            </ul>
        </li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
    
    <h2>Resources</h2>
    <ul>
        <li>Learning: <a href="https://w3schools.com" target="_blank">W3Schools</a></li>
        <li>Reference: <a href="https://developer.mozilla.org" target="_blank">MDN</a></li>
        <li>Practice: <a href="https://codepen.io" target="_blank">CodePen</a></li>
        <li>Validation: <a href="https://validator.w3.org" target="_blank">W3C Validator</a></li>
        <li>Search this site: <a href="https://www.google.com/search?q=site:yourusername.neocities.org" 
                                target="_blank">Google Site Search</a></li>
    </ul>
    
    <h2>Contact Methods</h2>
    <ul>
        <li>Email: <a href="mailto:student@school.edu">student@school.edu</a></li>
        <li>Phone: <a href="tel:+15551234567">(555) 123-4567</a></li>
    </ul>
</body>
</html>
```

---

## Teacher Notes & Tips

### Common Student Errors:
1. **Forgetting https://** - External links won't work without protocol
2. **Wrong slash direction** - Using backslash \ instead of forward slash /
3. **Broken relative paths** - Not understanding file locations
4. **Missing closing </a> tags** - Makes entire page clickable
5. **Spaces in filenames** - Use hyphens or underscores instead6. **Not testing links** - Always click every link to verify
7. **Inconsistent navigation** - Must be identical on all pages
8. **Missing rel="noopener noreferrer"** - Security issue with target="_blank"

### Differentiation Strategies:

**For Struggling Students:**
- Provide a navigation template to copy
- Show folder structure visually
- Practice with just two pages first
- Use absolute URLs initially, then teach relative

**For Advanced Students:**
- Create dropdown navigation (preview of CSS)
- Add breadcrumb navigation
- Implement skip navigation for accessibility
- Create a JavaScript-free mobile menu

### Time Management:
- 0-5 min: Review and check homework
- 5-15 min: I DO link types demonstration
- 15-25 min: WE DO navigation building
- 25-35 min: WE DO anchor links
- 35-45 min: YOU DO multi-page site
- 45-50 min: Assessment and homework

### Key Teaching Points:
- **Navigation consistency** is crucial for usability
- **Relative vs absolute** paths - draw folder diagram
- **Anchor links** don't reload the page
- **Target="_blank"** should be used sparingly (accessibility)
- **Email links** can include subject and body

### Troubleshooting Guide:
- **Links not working**: Check for typos in href
- **Page not found**: Verify file exists and spelling matches
- **Anchor not jumping**: Ensure ID exists and matches exactly
- **External link opens in same tab**: Add target="_blank"
- **Email link not working**: User might not have email client configured
### Extension Activities:
1. Create a navigation bar that highlights the current page
2. Build a "Web Ring" linking to classmates' sites
3. Add social media links with icons (preview of images)
4. Create a JavaScript-free dropdown menu using CSS (advanced)

### Real-World Applications:
- Every website needs navigation
- Email signatures use mailto links
- Table of contents in documentation uses anchors
- Social media sites open external links in new tabs
- Accessibility requires skip navigation links

### Resources for Teachers:
- Link Best Practices: https://www.nngroup.com/articles/guidelines-for-visualizing-links/
- Navigation Patterns: https://www.smashingmagazine.com/2017/05/building-navigation/
- Accessibility: https://webaim.org/techniques/hypertext/
- URL Structure: https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL

### Quick Reference for Board:
```
LINK FORMULA:
<a href="destination">Clickable Text</a>

LINK TYPES:
External: https://website.com
Internal: page.html
Email: mailto:email@example.com
Phone: tel:+1234567890
Anchor: #section-id
Download: add download attribute

IMPORTANT ATTRIBUTES:
target="_blank" (new tab)
rel="noopener noreferrer" (security)
title="Description" (tooltip)
download (force download)
```

### Safety Note:
Remind students to never link to inappropriate content and to be cautious about linking to external sites they haven't verified.

**End of Lesson 5**