# Lesson 7: Semantic HTML5 Elements - Building Meaningful Structure
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Understand the difference between semantic and non-semantic HTML
- Use all major HTML5 semantic elements correctly
- Build a properly structured webpage using semantic elements
- Explain why semantic HTML matters for accessibility and SEO
- Convert div-based layouts to semantic HTML
- Create a blog layout using article and section elements

### Materials Needed
- Text editor with HTML5 support
- Web browser with developer tools
- Screen reader demo (optional but recommended)
- Projector for demonstrations
- Printed semantic elements reference chart
- Sample website layouts for analysis

### Key Vocabulary with Definitions
- **Semantic HTML**: HTML elements that clearly describe their meaning
- **Non-semantic**: Elements that don't describe content (div, span)
- **Header**: Introductory content or navigation
- **Nav**: Navigation links section
- **Main**: Main content of the document
- **Article**: Self-contained, independent content
- **Section**: Thematic grouping of content
- **Aside**: Content tangentially related to main content
- **Footer**: Footer for document or section
- **Accessibility**: Making web content usable by people with disabilities
- **SEO**: Search Engine Optimization
- **Document Outline**: Hierarchical structure of a webpage

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Why Semantic HTML Matters (5 minutes)

**Teacher Script:**
"Until now, we've been building websites that work, but today we'll make them MEANINGFUL. Semantic HTML is like the difference between a pile of bricks and a blueprint - both make a house, but one tells you what each part is for!"
**[CREATE two files side by side: old-way.html and semantic-way.html]**

**old-way.html (The OLD Way - Don't Do This!):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Old Way - Using Divs</title>
</head>
<body>
    <div class="header">
        <div class="nav">
            <a href="#">Home</a>
            <a href="#">About</a>
        </div>
    </div>
    
    <div class="main-content">
        <div class="article">
            <h1>Article Title</h1>
            <p>Content here...</p>
        </div>
    </div>
    
    <div class="sidebar">
        <p>Related links...</p>
    </div>
    
    <div class="footer">
        <p>Copyright 2024</p>
    </div>
</body>
</html>
```

**semantic-way.html (The NEW Way - Do This!):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Semantic Way - Using HTML5</title>
</head>
<body>
    <header>
        <nav>
            <a href="#">Home</a>
            <a href="#">About</a>        </nav>
    </header>
    
    <main>
        <article>
            <h1>Article Title</h1>
            <p>Content here...</p>
        </article>
    </main>
    
    <aside>
        <p>Related links...</p>
    </aside>
    
    <footer>
        <p>Copyright 2024</p>
    </footer>
</body>
</html>
```

**Teacher Script:**
"See the difference? The semantic version:
- **Tells browsers** what each part is
- **Helps screen readers** navigate for blind users
- **Improves SEO** - Google understands your content better
- **Makes code readable** - other developers understand immediately
- **No CSS classes needed** for basic structure!"

### All Semantic Elements Explained (10 minutes)

**[CREATE comprehensive demo: semantic-elements-demo.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>All Semantic Elements Demo</title>
</head>
<body>
    <!-- HEADER: Site/section header with intro content -->
    <header>
        <h1>My News Website</h1>
        <p>Breaking news and updates</p>
        
        <!-- NAV: Navigation links -->        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#world">World</a></li>
                <li><a href="#tech">Technology</a></li>
                <li><a href="#sports">Sports</a></li>
            </ul>
        </nav>
    </header>
    
    <!-- MAIN: The main content (only ONE per page!) -->
    <main>
        <!-- SECTION: Thematic grouping of content -->
        <section id="featured">
            <h2>Featured Stories</h2>
            
            <!-- ARTICLE: Self-contained content that makes sense alone -->
            <article>
                <header>
                    <h3>Breaking: New Discovery in Space</h3>
                    <p>By Jane Smith | <time datetime="2024-01-15">January 15, 2024</time></p>
                </header>
                
                <p>Scientists have discovered a new exoplanet that could support life...</p>
                
                <footer>
                    <p>Tags: Space, Science, Discovery</p>
                </footer>
            </article>
            
            <!-- Another ARTICLE -->
            <article>
                <header>
                    <h3>Tech Giant Announces New Product</h3>
                    <p>By John Doe | <time datetime="2024-01-14">January 14, 2024</time></p>
                </header>
                
                <p>The latest innovation in artificial intelligence was unveiled today...</p>
                
                <!-- FIGURE: Self-contained image/diagram with caption -->
                <figure>                    <img src="images/tech-product.jpg" alt="New AI device on display">
                    <figcaption>The new AI assistant device at launch event</figcaption>
                </figure>
                
                <footer>
                    <p>Related: <a href="#">Previous announcements</a></p>
                </footer>
            </article>
        </section>
        
        <!-- Another SECTION -->
        <section id="latest">
            <h2>Latest Updates</h2>
            
            <!-- Multiple articles in a section -->
            <article>
                <h3>Weather Alert</h3>
                <p>Storm warning in effect until <time datetime="2024-01-16T18:00">6 PM tomorrow</time>.</p>
            </article>
            
            <article>
                <h3>Sports Update</h3>
                <p>Local team wins championship!</p>
            </article>
        </section>
    </main>
    
    <!-- ASIDE: Related but separate content (sidebar) -->
    <aside>
        <h2>Related Links</h2>
        <nav>
            <h3>Popular Stories</h3>
            <ul>
                <li><a href="#">Yesterday's top story</a></li>
                <li><a href="#">Most read this week</a></li>
            </ul>
        </nav>
        
        <!-- SECTION inside ASIDE -->
        <section>
            <h3>Advertisement</h3>            <p>Support our journalism!</p>
        </section>
    </aside>
    
    <!-- FOOTER: Footer for document or section -->
    <footer>
        <h2>Site Information</h2>
        
        <!-- ADDRESS: Contact information -->
        <address>
            Contact us at: <a href="mailto:news@example.com">news@example.com</a><br>
            Visit us at: 123 News Street, City, State 12345
        </address>
        
        <!-- Small print in footer -->
        <p><small>&copy; 2024 News Website. All rights reserved.</small></p>
    </footer>
</body>
</html>
```

**Additional Semantic Elements:**
```html
<!-- MARK: Highlighted/marked text -->
<p>The <mark>important part</mark> is highlighted.</p>

<!-- TIME: Machine-readable date/time -->
<p>Published on <time datetime="2024-01-15T10:30">January 15 at 10:30 AM</time></p>

<!-- DETAILS & SUMMARY: Expandable content -->
<details>
    <summary>Click for more information</summary>
    <p>This content is hidden until clicked!</p>
</details>

<!-- DIALOG: Dialog box or window -->
<dialog open>
    <p>This is a dialog box!</p>
    <button>Close</button>
</dialog>

<!-- PROGRESS: Progress bar -->
<progress value="32" max="100">32%</progress>

<!-- METER: Gauge/measurement --><meter value="6" min="0" max="10">6 out of 10</meter>
```

**Teacher Script:**
"Each semantic element has a specific purpose:
- **header**: Introductory content (can have multiple)
- **nav**: Navigation links (can have multiple)
- **main**: Main content (only ONE per page!)
- **article**: Complete, independent content
- **section**: Related content grouped together
- **aside**: Sidebar, related but separate
- **footer**: Closing content (can have multiple)
- **address**: Contact information
- **time**: Machine-readable dates
- **figure/figcaption**: Images with captions"

---

## PART 2: WE DO (Guided Practice) - 20 minutes

### Building a Blog Layout Together (10 minutes)

**Teacher Script:**
"Let's build a professional blog layout using semantic HTML. This is the structure used by real blogging platforms!"

**Step 1: Create the File Structure**
"Everyone create `blog-semantic.html` and follow along:"

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="My personal blog about web development journey">
    <title>Tech Learning Blog | Student Name</title>
</head>
<body>
    <!-- Site Header -->
    <header>
        <h1>Tech Learning Journey</h1>
        <p>Documenting my path to becoming a web developer</p>
        
        <!-- Main Navigation -->        <nav aria-label="Main navigation">
            <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="blog-semantic.html">Blog</a></li>
                <li><a href="portfolio.html">Portfolio</a></li>
                <li><a href="about.html">About</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
        </nav>
    </header>
```
"Notice the aria-label - this helps screen readers understand what navigation this is!"

**Step 2: Add the Main Content Area**
```html
    <!-- Main Content -->
    <main>
        <!-- Blog Posts Section -->
        <section id="blog-posts">
            <h2>Recent Posts</h2>
            
            <!-- First Blog Post -->
            <article>
                <header>
                    <h3>My First Week Learning HTML</h3>
                    <p>Posted on <time datetime="2024-01-15">January 15, 2024</time> 
                       by <address style="display: inline;">Student Name</address></p>
                </header>
                
                <p>This week has been amazing! I learned about HTML tags, attributes, and how to structure a webpage. 
                   The most exciting part was creating my first website and seeing it live on Neocities.</p>
                
                <p>Key things I learned:</p>
                <ul>
                    <li>HTML document structure</li>
                    <li>Headings and paragraphs</li>
                    <li>Links and navigation</li>
                    <li>Adding images</li>
                </ul>
                
                <figure>                    <img src="images/first-website-screenshot.jpg" 
                         alt="Screenshot of my first HTML webpage showing header and paragraphs"
                         width="400">
                    <figcaption>My very first webpage!</figcaption>
                </figure>
                
                <footer>
                    <p>Categories: <a href="#html">HTML</a>, <a href="#beginner">Beginner</a></p>
                    <p><a href="post1.html">Read more...</a> | <a href="#comments">3 Comments</a></p>
                </footer>
            </article>
            
            <!-- Second Blog Post -->
            <article>
                <header>
                    <h3>Understanding Semantic HTML</h3>
                    <p>Posted on <time datetime="2024-01-20">January 20, 2024</time></p>
                </header>
                
                <p>Today I learned about semantic HTML5 elements. It's not just about making things work - 
                   it's about making them meaningful!</p>
                
                <blockquote>
                    "Semantic HTML is the foundation of accessible web development."
                    <cite>- Web Accessibility Guidelines</cite>
                </blockquote>
                
                <details>
                    <summary>Click to see the semantic elements I learned</summary>
                    <ul>
                        <li>header, nav, main, footer</li>
                        <li>article, section, aside</li>
                        <li>figure, figcaption</li>
                        <li>time, address, mark</li>
                    </ul>
                </details>
                
                <footer>                    <p>Categories: <a href="#html5">HTML5</a>, <a href="#semantic">Semantic</a></p>
                    <p><a href="post2.html">Read more...</a> | <a href="#comments">5 Comments</a></p>
                </footer>
            </article>
        </section>
```

**Step 3: Add Sidebar with Aside**
```html
        <!-- Blog Navigation/Archive -->
        <section id="blog-navigation">
            <h2>Browse Posts</h2>
            
            <nav aria-label="Blog archive">
                <h3>Archives</h3>
                <ul>
                    <li><a href="#jan2024">January 2024 (5 posts)</a></li>
                    <li><a href="#dec2023">December 2023 (3 posts)</a></li>
                    <li><a href="#nov2023">November 2023 (4 posts)</a></li>
                </ul>
            </nav>
        </section>
    </main>
    
    <!-- Sidebar -->
    <aside>
        <section>
            <h2>About This Blog</h2>
            <p>Follow my journey learning web development from scratch!</p>
        </section>
        
        <section>
            <h3>Categories</h3>
            <nav aria-label="Blog categories">
                <ul>
                    <li><a href="#html">HTML (8 posts)</a></li>
                    <li><a href="#css">CSS (coming soon)</a></li>
                    <li><a href="#javascript">JavaScript (future)</a></li>
                    <li><a href="#projects">Projects (2 posts)</a></li>
                </ul>            </nav>
        </section>
        
        <section>
            <h3>Recent Comments</h3>
            <article>
                <p><strong>Sarah:</strong> "Great post about semantic HTML!"</p>
                <p><small>2 hours ago on <a href="#post2">Understanding Semantic HTML</a></small></p>
            </article>
            <article>
                <p><strong>Mike:</strong> "Keep up the good work!"</p>
                <p><small>Yesterday on <a href="#post1">My First Week</a></small></p>
            </article>
        </section>
        
        <section>
            <h3>Learning Progress</h3>
            <p>Course completion:</p>
            <progress value="7" max="30">Lesson 7 of 30</progress>
        </section>
    </aside>
    
    <!-- Site Footer -->
    <footer>
        <nav aria-label="Footer navigation">
            <ul>
                <li><a href="privacy.html">Privacy Policy</a></li>
                <li><a href="terms.html">Terms of Use</a></li>
                <li><a href="sitemap.html">Sitemap</a></li>
                <li><a href="rss.xml">RSS Feed</a></li>
            </ul>
        </nav>
        
        <address>
            Contact: <a href="mailto:student@school.edu">student@school.edu</a>
        </address>
        
        <p><small>&copy; 2024 Tech Learning Blog. Built with semantic HTML5.</small></p>
    </footer>
</body>
</html>
```
### Understanding When to Use Each Element (10 minutes)

**Teacher Script:**
"Let's discuss WHEN to use each semantic element:"

**Decision Tree for Semantic Elements:**
```
Is it navigation? → <nav>
Is it the main content? → <main> (only one!)
Is it introductory? → <header>
Is it a footer? → <footer>
Is it self-contained? → <article>
Is it a thematic group? → <section>
Is it tangentially related? → <aside>
Is it contact info? → <address>
Is it an image with caption? → <figure> + <figcaption>
Is it a date/time? → <time>
```

**Common Mistakes to Avoid:**
1. "DON'T use multiple `<main>` elements - only ONE per page!"
2. "DON'T put `<header>` only at the top - articles can have headers too"
3. "DON'T use `<section>` without a heading - it needs one"
4. "DON'T use `<article>` for everything - only self-contained content"
5. "DON'T forget `<nav>` can be used multiple times"

---

## PART 3: YOU DO (Independent Practice) - 10 minutes

### Student Activity: Create a Portfolio Page with Semantic HTML

**Instructions:**
"Create a portfolio page using ALL the semantic elements we learned. Make it meaningful AND functional!"

**Required Tasks:**
1. ✅ Create `portfolio-semantic.html` with proper structure
2. ✅ Use `<header>` with site title and `<nav>` for navigation
3. ✅ Use `<main>` for primary content (only one!)
4. ✅ Create at least 3 `<article>` elements for projects
5. ✅ Use `<section>` to group related content6. ✅ Include `<aside>` with related information
7. ✅ Use `<footer>` with contact information
8. ✅ Include `<time>` elements with datetime attributes
9. ✅ Use `<figure>` and `<figcaption>` for project images
10. ✅ Add `<address>` for contact details
11. ✅ Include aria-label attributes on navigation elements
12. ✅ Use `<mark>`, `<details>`, or `<progress>` elements

**Bonus Challenges:**
- Add multiple `<nav>` elements with different aria-labels
- Use nested `<article>` elements for project updates
- Include `<dialog>` element for a modal window
- Add `<meter>` to show skill levels
- Create breadcrumb navigation using semantic markup

### Complete Solution Example:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Web development portfolio showcasing HTML5, CSS, and JavaScript projects">
    <meta name="author" content="Alex Johnson">
    <title>Portfolio | Alex Johnson - Web Developer</title>
</head>
<body>
    <!-- Site Header -->
    <header>
        <h1>Alex Johnson</h1>
        <p>Aspiring Web Developer | Creative Coder | Problem Solver</p>
        
        <!-- Main Navigation -->
        <nav aria-label="Main navigation">
            <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="portfolio-semantic.html" aria-current="page">Portfolio</a></li>
                <li><a href="blog.html">Blog</a></li>
                <li><a href="resume.html">Resume</a></li>
                <li><a href="contact.html">Contact</a></li>            </ul>
        </nav>
    </header>
    
    <!-- Main Content -->
    <main>
        <!-- Introduction Section -->
        <section id="intro">
            <h2>My Web Development Journey</h2>
            <p>Welcome to my portfolio! Here you'll find projects that showcase my growth as a web developer. 
               Each project represents a <mark>milestone in my learning journey</mark>.</p>
            <p>Started learning: <time datetime="2023-09">September 2023</time></p>
            <p>Projects completed: <meter value="8" min="0" max="10">8 out of 10 planned</meter></p>
        </section>
        
        <!-- Featured Projects Section -->
        <section id="featured-projects">
            <h2>Featured Projects</h2>
            
            <!-- Project 1 -->
            <article>
                <header>
                    <h3>Personal Blog Platform</h3>
                    <p>Completed: <time datetime="2024-01-10">January 10, 2024</time></p>
                </header>
                
                <figure>
                    <img src="images/blog-screenshot.jpg" 
                         alt="Screenshot of blog homepage showing semantic HTML5 layout"
                         width="400">
                    <figcaption>My blog built with semantic HTML5 and CSS Grid</figcaption>
                </figure>
                
                <p>A fully semantic blog platform featuring:</p>
                <ul>
                    <li>Semantic HTML5 structure</li>
                    <li>Responsive design</li>
                    <li>Accessibility features</li>
                    <li>SEO optimization</li>                </ul>
                
                <details>
                    <summary>Technical Details</summary>
                    <p>Built with: HTML5, CSS3, Vanilla JavaScript</p>
                    <p>Features: Local storage for drafts, comment system, RSS feed</p>
                    <p>Lines of code: ~500 HTML, ~800 CSS</p>
                </details>
                
                <footer>
                    <p>Technologies: HTML5, CSS3 | 
                       <a href="https://github.com/username/blog">View on GitHub</a> | 
                       <a href="https://blog-demo.netlify.app">Live Demo</a></p>
                </footer>
            </article>
            
            <!-- Project 2 -->
            <article>
                <header>
                    <h3>Restaurant Website</h3>
                    <p>Completed: <time datetime="2023-12-15">December 15, 2023</time></p>
                </header>
                
                <figure>
                    <img src="images/restaurant-site.jpg" 
                         alt="Restaurant homepage with navigation menu and food gallery"
                         width="400">
                    <figcaption>Responsive restaurant website with online menu</figcaption>
                </figure>
                
                <p>A modern restaurant website with online menu and reservation system.</p>
                
                <footer>
                    <p>Client: Local Bistro | 
                       <a href="restaurant-project.html">Case Study</a> | 
                       <a href="https://bistro-demo.netlify.app">Live Site</a></p>
                </footer>
            </article>            
            <!-- Project 3 -->
            <article>
                <header>
                    <h3>Weather Dashboard</h3>
                    <p>Completed: <time datetime="2024-01-20">January 20, 2024</time></p>
                </header>
                
                <figure>
                    <img src="images/weather-app.jpg" 
                         alt="Weather dashboard showing 5-day forecast with charts"
                         width="400">
                    <figcaption>Interactive weather dashboard using API data</figcaption>
                </figure>
                
                <p>Real-time weather application fetching data from OpenWeather API.</p>
                
                <p>Project status: <progress value="90" max="100">90% complete</progress></p>
                
                <footer>
                    <p>Technologies: HTML5, CSS3, JavaScript, API | 
                       <a href="weather-project.html">Learn More</a></p>
                </footer>
            </article>
        </section>
        
        <!-- Skills Section -->
        <section id="skills">
            <h2>Technical Skills</h2>
            
            <article>
                <h3>Languages & Technologies</h3>
                <dl>
                    <dt>HTML5</dt>
                    <dd>Semantic markup, accessibility, SEO best practices</dd>
                    <dd>Proficiency: <meter value="8" min="0" max="10">8/10</meter></dd>
                    
                    <dt>CSS3</dt>
                    <dd>Flexbox, Grid, animations, responsive design</dd>
                    <dd>Proficiency: <meter value="6" min="0" max="10">6/10</meter></dd>                    
                    <dt>JavaScript</dt>
                    <dd>DOM manipulation, ES6+, async programming</dd>
                    <dd>Proficiency: <meter value="4" min="0" max="10">4/10</meter></dd>
                </dl>
            </article>
        </section>
    </main>
    
    <!-- Sidebar -->
    <aside>
        <section>
            <h2>Quick Stats</h2>
            <ul>
                <li>Projects Completed: 8</li>
                <li>GitHub Repos: 12</li>
                <li>Certifications: 2</li>
                <li>Happy Clients: 3</li>
            </ul>
        </section>
        
        <section>
            <h3>Current Focus</h3>
            <p>Currently learning: <mark>Advanced CSS and JavaScript</mark></p>
            <p>Next project: E-commerce site with shopping cart</p>
        </section>
        
        <nav aria-label="Portfolio categories">
            <h3>Browse by Type</h3>
            <ul>
                <li><a href="#websites">Websites (5)</a></li>
                <li><a href="#apps">Web Apps (3)</a></li>
                <li><a href="#experiments">Experiments (4)</a></li>
            </ul>
        </nav>
    </aside>
    
    <!-- Site Footer -->
    <footer>
        <section>
            <h2>Get In Touch</h2>
            
            <address>                Email: <a href="mailto:alex@example.com">alex@example.com</a><br>
                Phone: <a href="tel:+15551234567">(555) 123-4567</a><br>
                Location: San Francisco, CA
            </address>
        </section>
        
        <nav aria-label="Social media links">
            <h3>Connect</h3>
            <ul>
                <li><a href="https://github.com/alexjohnson" rel="external">GitHub</a></li>
                <li><a href="https://linkedin.com/in/alexjohnson" rel="external">LinkedIn</a></li>
                <li><a href="https://codepen.io/alexjohnson" rel="external">CodePen</a></li>
                <li><a href="https://twitter.com/alexcodes" rel="external">Twitter</a></li>
            </ul>
        </nav>
        
        <p><small>&copy; 2024 Alex Johnson. Built with semantic HTML5 and lots of ☕</small></p>
    </footer>
</body>
</html>
```

---

## Assessment & Closing (5 minutes)

### Exit Ticket Questions

1. **What's the difference between `<section>` and `<article>`?**
   - Answer: `<section>` groups related content by theme, while `<article>` contains self-contained content that makes sense on its own (like a blog post or news story).

2. **How many `<main>` elements can you have per page?**
   - Answer: Only ONE `<main>` element per page - it represents the main content.

3. **Why use semantic HTML instead of just divs?**
   - Answer: Semantic HTML provides meaning to content, improves accessibility for screen readers, helps with SEO, and makes code more readable and maintainable.

4. **Write the semantic element for navigation:**
   - Answer: `<nav>`

5. **What element would you use for a blog post?**   - Answer: `<article>` because it's self-contained content that could stand alone.

### Success Criteria Checklist
- [ ] Used all major semantic elements correctly (4 pts)
- [ ] Only one `<main>` element (2 pts)
- [ ] Articles have proper structure (2 pts)
- [ ] Navigation uses `<nav>` tags (2 pts)
- [ ] Used `<time>` with datetime attribute (2 pts)
- [ ] Included `<aside>` appropriately (2 pts)
- [ ] Added aria-label for accessibility (2 pts)
- [ ] Footer contains appropriate content (2 pts)
- [ ] Code is properly structured and semantic (2 pts)
**Total: ___/20 points**

### Homework Assignment

**Create a News Website Homepage (`news-semantic.html`):**

Requirements:
1. Use proper semantic HTML5 structure throughout
2. Include a `<header>` with site title and main navigation
3. Create at least 4 news `<article>` elements with:
   - Article headers with headlines
   - Time elements with datetime attributes
   - Article footers with metadata
4. Add a `<section>` for breaking news
5. Include an `<aside>` with:
   - Weather widget section
   - Advertisement section
   - Trending topics navigation
6. Use `<figure>` and `<figcaption>` for news images
7. Add a comprehensive `<footer>` with multiple sections
8. Include at least 2 different `<nav>` elements with aria-labels
9. Use `<address>` for newsroom contact info
10. Add `<details>` and `<summary>` for expandable content

**Homework Solution Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daily News - Your Source for Breaking News</title>
</head>
<body>
    <header>
        <h1>The Daily News</h1>
        <p>Your trusted source since 2024</p>
        <nav aria-label="Main sections">
            <ul>
                <li><a href="#world">World</a></li>
                <li><a href="#local">Local</a></li>
                <li><a href="#sports">Sports</a></li>
                <li><a href="#tech">Technology</a></li>
                <li><a href="#opinion">Opinion</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <section id="breaking">
            <h2>Breaking News</h2>
            <article>
                <header>
                    <h3>Major Scientific Discovery Announced</h3>
                    <p>By Sarah Chen | <time datetime="2024-01-25T14:30">2:30 PM Today</time></p>
                </header>
                <figure>
                    <img src="images/science-news.jpg" alt="Scientists in lab examining samples" width="600">
                    <figcaption>Research team at the National Science Institute</figcaption>
                </figure>
                <p>Scientists have made a groundbreaking discovery that could change our understanding of climate change...</p>
                <details>
                    <summary>Read more details</summary>
                    <p>The research, published in Nature today, shows that...</p>
                </details>
                <footer>
                    <p>Filed under: <a href="#science">Science</a>, <a href="#climate">Climate</a></p>
                </footer>
            </article>        </section>
        
        <section id="top-stories">
            <h2>Top Stories</h2>
            <article>
                <header>
                    <h3>Local Team Wins Championship</h3>
                    <p><time datetime="2024-01-25T10:00">10:00 AM</time></p>
                </header>
                <p>In an exciting overtime victory...</p>
                <footer>
                    <p><a href="sports1.html">Full story</a> | 45 comments</p>
                </footer>
            </article>
            
            <article>
                <header>
                    <h3>New Tech Hub Opens Downtown</h3>
                    <p><time datetime="2024-01-25T09:00">9:00 AM</time></p>
                </header>
                <p>The city's economy gets a boost with...</p>
                <footer>
                    <p><a href="tech1.html">Full story</a> | 23 comments</p>
                </footer>
            </article>
        </section>
    </main>
    
    <aside>
        <section>
            <h2>Weather</h2>
            <p>Today: Sunny, 72°F</p>
            <p>Tomorrow: Partly cloudy, 68°F</p>
        </section>
        
        <section>
            <h3>Advertisement</h3>
            <p>[Ad placeholder]</p>
        </section>
        
        <nav aria-label="Trending topics">
            <h3>Trending Now</h3>            <ol>
                <li><a href="#election">Election Updates</a></li>
                <li><a href="#weather">Storm Warning</a></li>
                <li><a href="#sports">Championship Game</a></li>
            </ol>
        </nav>
    </aside>
    
    <footer>
        <section>
            <h2>About The Daily News</h2>
            <address>
                Newsroom: <a href="mailto:news@dailynews.com">news@dailynews.com</a><br>
                Main: <a href="tel:+15551234567">(555) 123-4567</a><br>
                123 News Plaza, City, State 12345
            </address>
        </section>
        
        <nav aria-label="Footer links">
            <ul>
                <li><a href="about.html">About Us</a></li>
                <li><a href="contact.html">Contact</a></li>
                <li><a href="careers.html">Careers</a></li>
                <li><a href="privacy.html">Privacy Policy</a></li>
            </ul>
        </nav>
        
        <p><small>&copy; 2024 The Daily News. All rights reserved.</small></p>
    </footer>
</body>
</html>
```

---

## Teacher Notes & Tips

### Common Student Errors:
1. **Using multiple `<main>` elements** - Emphasize only ONE per page
2. **Confusing `<section>` and `<div>`** - Section needs a heading
3. **Overusing `<article>`** - Only for self-contained content
4. **Forgetting `<nav>` can be used multiple times** - Not just for main nav
5. **Wrong element nesting** - Can't put `<header>` inside `<header>`6. **Using semantic elements without meaning** - Not every group needs `<section>`
7. **Missing aria-labels on navigation** - Important for accessibility
8. **Not using `<time>` datetime attribute** - Makes dates machine-readable

### Differentiation Strategies:

**For Struggling Students:**
- Provide a semantic elements cheat sheet
- Start with just header, main, footer
- Use color coding for different semantic elements
- Provide templates with comments explaining each element
- Pair with stronger students for practice

**For Advanced Students:**
- Research ARIA roles and landmarks
- Create a complex magazine layout
- Add microdata for rich snippets
- Implement schema.org markup
- Build an accessible skip navigation system

### Time Management:
- 0-5 min: Review homework and warm-up
- 5-15 min: I DO semantic vs non-semantic demo
- 15-25 min: WE DO blog layout creation
- 25-35 min: WE DO element decision tree
- 35-45 min: YOU DO portfolio page
- 45-50 min: Assessment and homework

### Key Teaching Points:
- **Semantic = Meaning** - Elements describe their content
- **Accessibility first** - Screen readers depend on semantic HTML
- **SEO benefits** - Search engines understand semantic structure
- **Only one `<main>`** - This is the most common mistake
- **Articles are independent** - Could be syndicated elsewhere
- **Sections need headings** - If no heading, probably use `<div>`

### Accessibility Demonstration:
If possible, demonstrate with a screen reader:
1. Show how it announces different landmarks
2. Navigate by headings
3. Jump between navigation areas
4. Show how non-semantic HTML confuses users
### Why This Matters (Real-World Applications):
- **Job Requirements**: Semantic HTML is expected in professional development
- **Legal Compliance**: Accessibility laws require semantic structure
- **Team Collaboration**: Semantic code is self-documenting
- **Future-Proofing**: New devices/browsers understand semantic HTML
- **Performance**: Search engines rank semantic sites higher

### Extension Activities:
1. Convert an existing non-semantic page to semantic HTML
2. Create a newspaper layout with multiple sections
3. Build a documentation site with proper structure
4. Add schema.org microdata to enhance SEO
5. Create an accessible form using semantic elements

### Browser Support Note:
All HTML5 semantic elements are supported in:
- Chrome 6+
- Firefox 4+
- Safari 5+
- Edge (all versions)
- Internet Explorer 9+ (with some limitations)

### Assessment Rubric:

| Element Usage | Excellent (3) | Good (2) | Needs Work (1) | Missing (0) |
|--------------|---------------|-----------|----------------|-------------|
| Main Structure | All semantic elements used correctly | Most elements correct | Some confusion | Mostly divs |
| Article/Section | Clear understanding of difference | Mostly correct usage | Some confusion | Incorrect usage |
| Navigation | Multiple nav with aria-labels | Nav elements used | Basic nav | No nav elements |
| Accessibility | All ARIA attributes included | Some ARIA usage | Minimal | None |

### Resources for Students:
- MDN Semantic Elements: https://developer.mozilla.org/en-US/docs/Glossary/Semantics
- HTML5 Doctor: http://html5doctor.com/
- WebAIM Semantic Structure: https://webaim.org/resources/htmlcheatsheet/
- Can I Use (browser support): https://caniuse.com/
### Quick Reference for Board:
```
SEMANTIC STRUCTURE:
<header> - Intro content/navigation
<nav> - Navigation links
<main> - Main content (ONLY ONE!)
<article> - Self-contained content
<section> - Thematic grouping
<aside> - Related but separate
<footer> - Footer content
<address> - Contact info
<time> - Date/time
<figure> + <figcaption> - Images

REMEMBER:
✓ Only ONE <main> per page
✓ Articles are independent
✓ Sections need headings
✓ Nav can be used multiple times
✓ Add aria-labels for accessibility
```

### Troubleshooting Guide:
- **Page structure looks wrong**: Check element nesting
- **Screen reader confused**: Add aria-labels and landmarks
- **SEO not improving**: Ensure proper heading hierarchy
- **Content not making sense**: Review article vs section usage
- **Validation errors**: Check for duplicate main elements

### Sample Semantic Structure Diagram:
```
<body>
    <header>
        <nav>Main Navigation</nav>
    </header>
    <main>
        <section>
            <article>Content 1</article>
            <article>Content 2</article>
        </section>
    </main>
    <aside>
        Sidebar content
    </aside>
    <footer>
        <nav>Footer Navigation</nav>
    </footer>
</body>
```

### Final Tip:
"When in doubt, ask yourself: Does this element describe WHAT the content is, or just HOW it looks? If it's WHAT, use semantic HTML. If it's HOW, that's for CSS!"

**End of Lesson 7**