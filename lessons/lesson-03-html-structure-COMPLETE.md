# Lesson 3: HTML Document Structure - Deep Dive
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Explain every part of a complete HTML5 document structure
- Understand and use metadata tags in the head section
- Write and understand HTML comments
- Create a reusable HTML template for future projects
- Use browser developer tools to inspect HTML structure

### Materials Needed
- Text editor (VS Code, Notepad++, or Sublime Text)
- Web browser with developer tools
- Projector for demonstrations
- Printed HTML5 structure diagram
- Students' completed homework (favorites.html) from Lesson 2

### Key Vocabulary with Definitions
- **DOCTYPE**: Document Type Declaration - tells browser which HTML version to use
- **Metadata**: Information about the webpage that isn't visible to users
- **Character Encoding**: How text characters are converted to computer code
- **Viewport**: The visible area of a webpage on a device
- **HTML Comments**: Notes in code that don't appear on the webpage
- **Root Element**: The main container for all HTML content (`<html>`)
- **Head Section**: Contains information about the document
- **Body Section**: Contains all visible content
- **Semantic**: HTML that clearly describes its meaning

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### The Complete HTML5 Structure Explained (8 minutes)

**Teacher Script:**
"Last class, we wrote basic HTML. Today, we'll understand EVERY line of a professional HTML document. This is like learning the blueprint before building a house!"
**[CREATE NEW FILE and TYPE each line with explanations]**

```html
<!DOCTYPE html>
```
**"Line 1: The DOCTYPE Declaration"**
"This is like putting a sign on your house that says 'Built in 2024 with modern materials!'
- It MUST be the very first line
- It's NOT an HTML tag (notice no closing tag)
- The 'html' part means we're using HTML5 (the newest version)
- Without this, browsers might display your page incorrectly (quirks mode)
- Fun fact: Old HTML4 had DOCTYPE declarations that were 3 lines long!"

```html
<html lang="en">
```
**"Line 2: The Root Element"**
"This is the container that holds EVERYTHING else - like the foundation and walls of your house.
- `<html>` is called the 'root' element
- `lang="en"` tells browsers and screen readers this page is in English
- Why language matters:
  - Screen readers pronounce words correctly
  - Search engines know what language to index
  - Translation tools work better
- Other language codes: 'es' (Spanish), 'fr' (French), 'zh' (Chinese)"

```html
<head>
    <meta charset="UTF-8">
```
**"Line 3-4: The Head Section Begins"**
"The head is like the control room of your webpage - users don't see it, but it controls everything!
- `<head>` contains metadata (data about data)
- `<meta charset="UTF-8">` is CRITICAL - here's why:
  - UTF-8 lets you use ANY character from ANY language
  - Includes emojis! 😀 hearts ♥ and symbols © ™
  - Without it, special characters become weird symbols like â€™ or Ã©"
```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
```
**"Line 5: The Viewport Meta Tag"**
"This is the SECRET to making websites look good on phones!
- `width=device-width`: Makes the page match the screen width
- `initial-scale=1.0`: Sets the zoom level (1.0 = 100%, no zoom)
- Without this, mobile browsers assume your site is desktop-only and zoom out
- This is called 'responsive web design' - we'll learn more in later lessons"

```html
    <meta name="description" content="A website about learning HTML">
    <meta name="keywords" content="HTML, web development, learning">
    <meta name="author" content="Your Name">
```
**"Lines 6-8: SEO and Information Meta Tags"**
"These help search engines and social media understand your page:
- `description`: Shows up in Google search results (keep under 160 characters)
- `keywords`: Helps with search (less important now, but good practice)
- `author`: Credits the creator (that's you!)"

```html
    <title>My Awesome Website - Home</title>
</head>
```
**"Lines 9-10: The Page Title"**
"The title is SUPER important - here's everywhere it appears:
- Browser tab (look up there!)
- Bookmarks/favorites
- Search engine results (the blue clickable link)
- Social media when shared
- Best practice: Put site name AND page name"

```html
<body>
    <!-- This is where all visible content goes -->
    <h1>Welcome to My Site</h1>
    <p>This is a paragraph.</p>
</body>
</html>
```**"Lines 11-16: Body and Comments"**
"Everything visible goes in the body, and comments help organize:
- `<!-- -->` creates comments (notes for developers)
- Comments are INVISIBLE on the actual webpage
- Use them to explain complex code or leave reminders"

### HTML Comments Deep Dive (7 minutes)

**[TYPE examples of comments]**

```html
<!-- This is a single line comment -->

<!-- 
    This is a
    multi-line comment
    Great for longer explanations
-->

<!-- TODO: Add more content here -->
<!-- FIXME: This section needs updating -->
<!-- NOTE: This is important -->

<!-- Navigation Section Start -->
<nav>
    <a href="home.html">Home</a>
</nav>
<!-- Navigation Section End -->

<!-- WARNING: Never put passwords or sensitive info in comments! 
     Anyone can view source and see them! -->
```

**Teacher Script:**
"Comments are like sticky notes in your code:
- They help you remember what you were thinking
- They help others understand your code
- They can temporarily 'turn off' code (commenting out)
- Professional developers use LOTS of comments
- But remember: ANYONE can see them with View Source!"

**[DEMONSTRATE: Right-click on any website → View Page Source → Find comments]**

---
## PART 2: WE DO (Guided Practice) - 20 minutes

### Creating a Professional Template Together (10 minutes)

**Teacher Script:**
"Let's build a professional HTML template you can reuse for EVERY project. Follow along with me!"

**Step 1: Create the File**
"Everyone:
1. Open your text editor
2. Create a new file
3. Save it as `template.html`
4. CHECKPOINT: Everyone saved? Show me thumbs up!"

**Step 2: Build the Structure Together**

"Type exactly what I type. I'll explain each line as we go:"

```html
<!DOCTYPE html>
<!-- 
    Website: My Personal Site
    Author: [Your Name]
    Date Created: [Today's Date]
    Description: Template for all my web pages
-->
```
"Start with DOCTYPE, then add a comment block with information about your file. Fill in your actual name and today's date!"

```html
<html lang="en">
```
"Add the html tag with language. What language code would we use for Spanish class websites? Right - 'es'!"

```html
<head>
    <!-- Character encoding for universal text support -->
    <meta charset="UTF-8">
```
"Indent with TAB. Add charset with a comment explaining why."
```html
    <!-- Mobile responsive viewport -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- SEO Meta Tags -->
    <meta name="description" content="Add page description here">
    <meta name="keywords" content="add, your, keywords, here">
    <meta name="author" content="Your Name">
    
    <!-- Page Title - Shows in browser tab -->
    <title>Page Title | Site Name</title>
    
    <!-- Future CSS link will go here -->
    <!-- <link rel="stylesheet" href="styles.css"> -->
</head>
```
"Add all the meta tags. Notice I'm adding comments for EVERYTHING - this helps you remember what each line does!"

```html
<body>
    <!-- Header Section -->
    <header>
        <h1>Page Title</h1>
        <!-- Future navigation will go here -->
    </header>
    
    <!-- Main Content Section -->
    <main>
        <p>Page content goes here.</p>
    </main>
    
    <!-- Footer Section -->
    <footer>
        <p>&copy; 2024 Your Name. All rights reserved.</p>
    </footer>
</body>
</html>
```
"The body has three sections: header, main, and footer. Notice the `&copy;` - that's an HTML entity for the © symbol!"

**Step 3: Save and Test**
"Save your file and open it in the browser. You should see a basic but professional page structure!"
### Using Browser Developer Tools (10 minutes)

**Teacher Script:**
"Professional web developers use DevTools every day. Let me show you this superpower!"

**[OPEN template.html in Chrome/Firefox]**

**Step 1: Opening DevTools**
"Three ways to open Developer Tools:
1. Right-click anywhere → Inspect
2. Press F12
3. Press Ctrl+Shift+I (Cmd+Option+I on Mac)
EVERYONE try all three methods!"

**Step 2: Exploring the Elements Panel**
"Look at the Elements panel (or Inspector in Firefox):
- See the HTML structure as a tree
- Click the arrow to expand/collapse sections
- Hover over HTML to highlight it on the page
- Notice our comments do NOT appear in the rendered page"

**Step 3: Live Editing**
"Watch this magic:
1. Double-click on the h1 text in DevTools
2. Change it to something else
3. Press Enter
4. Look at the page - it changed!
5. Refresh the page - it's back to normal!
This is ONLY temporary - great for testing!"

**Step 4: Finding Hidden Information**
"In DevTools, look at the <head> section:
- All our meta tags are there
- The title element is there
- But users never see any of this on the page!"

**Common DevTools Tips:**
- "Use the magnifying glass to select elements on the page"
- "The Styles panel shows CSS (we'll use this next week)"
- "Console panel shows errors (red text = problem in your code)"
- "Network panel shows loading (useful for images later)"
---

## PART 3: YOU DO (Independent Practice) - 10 minutes

### Student Activity: Create Your Contact Page

**Instructions:**
"Using your template.html as a starting point, create a professional contact.html page. You have 10 minutes to complete the required tasks."

**Required Tasks:**
1. ✅ Copy template.html and rename it to contact.html
2. ✅ Update the title to "Contact Me | [Your Name]'s Site"
3. ✅ Change the meta description to describe your contact page
4. ✅ Update the h1 to say "Get In Touch"
5. ✅ Add at least 3 different contact methods using appropriate HTML
6. ✅ Add comments to organize your sections
7. ✅ Include at least 3 HTML entities (&copy;, &amp;, &hearts;, etc.)
8. ✅ Add a "business hours" or "availability" section
9. ✅ Test in browser and use DevTools to inspect

**Bonus Challenges:**
- Add a comment that won't show on the page with a secret message
- Use nested comments to organize complex sections
- Add all possible meta tags we discussed
- Create sections for social media links (we'll make them work in Lesson 5)

### Complete Solution Example:

```html
<!DOCTYPE html>
<!-- 
    Page: Contact Information
    Author: Jamie Rodriguez
    Date Created: January 15, 2024
    Last Updated: January 15, 2024
    Description: How to get in touch with me
-->
<html lang="en">
<head>
    <!-- Essential Meta Tags -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">    
    <!-- SEO and Information -->
    <meta name="description" content="Contact Jamie Rodriguez - Web Development Student. Available for questions and collaboration.">
    <meta name="keywords" content="contact, email, Jamie Rodriguez, web developer, student">
    <meta name="author" content="Jamie Rodriguez">
    
    <!-- Page Title -->
    <title>Contact Me | Jamie Rodriguez's Site</title>
</head>
<body>
    <!-- Header Section -->
    <header>
        <h1>Get In Touch</h1>
        <p>I'd love to hear from you! Here's how to reach me.</p>
    </header>
    
    <!-- Main Content -->
    <main>
        <!-- Contact Methods Section -->
        <section>
            <h2>Contact Information</h2>
            <!-- Email is the preferred method -->
            <p><strong>Email:</strong> jrodriguez@lincolnhs.edu <em>(preferred)</em></p>
            <p><strong>School Phone:</strong> (555) 123-4567 ext. 2024</p>
            <p><strong>Classroom:</strong> Room 301, Computer Lab</p>
        </section>
        
        <!-- Availability Section -->
        <section>
            <h2>Availability &amp; Office Hours</h2>
            <p>I'm usually available during these times:</p>
            <p>
                <strong>Monday &ndash; Friday:</strong><br>
                Before School: 7:30 AM &ndash; 8:00 AM<br>
                Lunch: 12:00 PM &ndash; 12:30 PM<br>
                After School: 3:00 PM &ndash; 4:00 PM
            </p>
            <p><strong>Weekends:</strong> Email only &mdash; I'll respond within 24 hours</p>
        </section>        
        <!-- Social Media Section (Links not active yet) -->
        <section>
            <h2>Social Media</h2>
            <!-- We'll make these links work in Lesson 5 -->
            <p>GitHub: @jrodriguez2024</p>
            <p>LinkedIn: Jamie Rodriguez</p>
            <p>CodePen: @jr_codes</p>
        </section>
        
        <!-- Fun Section with HTML Entities -->
        <section>
            <h2>Quick Facts</h2>
            <p>Favorite Code Editor: VS Code &hearts;</p>
            <p>Favorite HTML Entity: &lt;code&gt; tags</p>
            <p>Coffee or Tea: Coffee &amp; more coffee &amp; even more coffee!</p>
            <p>Coding Playlist: Lo-fi hip hop &infin; hours</p>
        </section>
        
        <!-- Secret Message in Comment -->
        <!-- Easter Egg: If you're reading this in the source code, you found my secret! 
             Email me with the code word "INSPECTOR" for bonus points! -->
    </main>
    
    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Jamie Rodriguez. All rights reserved. Made with &hearts; and HTML.</p>
        <p><small>This site is a work in progress &hellip; check back for updates!</small></p>
    </footer>
</body>
</html>
```

---

## Assessment & Closing (5 minutes)

### Exit Ticket Questions
Students answer these questions:
1. **What does `<!DOCTYPE html>` tell the browser?**
   - Answer: It declares that this is an HTML5 document and tells the browser to use HTML5 standards for rendering.

2. **Why is `<meta charset="UTF-8">` important?**
   - Answer: It allows the page to display any character from any language, including special symbols and emojis.

3. **What's the difference between the `<head>` and `<body>` sections?**
   - Answer: The head contains metadata and information ABOUT the page (not visible), while the body contains all the visible content.

4. **Write an HTML comment that says "Navigation goes here":**
   - Answer: `<!-- Navigation goes here -->`

5. **What does the viewport meta tag do?**
   - Answer: It makes the webpage responsive by setting the width to match the device's screen width, essential for mobile viewing.

### Success Criteria Checklist
- [ ] Created valid HTML5 structure with DOCTYPE (2 pts)
- [ ] Included all required meta tags (3 pts)
- [ ] Used HTML comments appropriately (2 pts)
- [ ] Created organized sections with semantic meaning (2 pts)
- [ ] Used at least 3 HTML entities correctly (2 pts)
- [ ] Successfully used DevTools to inspect (1 pt)
- [ ] Template is reusable for future projects (3 pts)
**Total: ___/15 points**

### Homework Assignment

**Create `portfolio.html` using your template:**

Requirements:
1. Start with your template.html
2. Create a page about your future portfolio projects
3. Include:
   - Proper HTML5 structure with all meta tags
   - At least 5 HTML comments organizing sections
   - 3 different heading levels (h1, h2, h3)   - At least 5 HTML entities
   - Sections for: Introduction, Skills Learning, Future Projects, Goals
   - Custom meta description and keywords relevant to portfolio

**Homework Solution Example:**
```html
<!DOCTYPE html>
<!-- 
    Portfolio Planning Page
    Author: Student Name
    Created: January 2024
    Purpose: Planning future web development projects
-->
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="My web development portfolio planning page - future projects and goals">
    <meta name="keywords" content="portfolio, web development, HTML, CSS, projects, student">
    <meta name="author" content="Student Name">
    <title>Portfolio Planning | Student's Web Development Journey</title>
</head>
<body>
    <!-- Header -->
    <header>
        <h1>My Portfolio Planning</h1>
        <p>Building my web development skills one project at a time!</p>
    </header>
    
    <!-- Main Content -->
    <main>
        <!-- Introduction Section -->
        <section>
            <h2>Introduction</h2>
            <p>Welcome to my portfolio planning page! I'm currently learning HTML &amp; CSS.</p>
            <p>By the end of this course, I'll have 5&ndash;10 completed projects to showcase.</p>
        </section>
        
        <!-- Skills Section -->
        <section>
            <h2>Skills I'm Learning</h2>            <h3>Current Skills:</h3>
            <p>&bull; HTML5 structure &amp; semantic elements<br>
            &bull; Meta tags &amp; SEO basics<br>
            &bull; Developer tools &amp; debugging</p>
            
            <h3>Upcoming Skills:</h3>
            <p>&rarr; CSS styling &amp; layouts<br>
            &rarr; Responsive design<br>
            &rarr; Flexbox &amp; Grid</p>
        </section>
        
        <!-- Future Projects -->
        <section>
            <h2>Planned Projects</h2>
            <p>Here are the projects I'll build:</p>
            <p>1. Personal blog &mdash; Share my learning journey<br>
            2. Photo gallery &mdash; Showcase my photography<br>
            3. Recipe collection &mdash; Family favorites<br>
            4. Game reviews &mdash; My favorite games<br>
            5. Final portfolio &mdash; Professional showcase</p>
        </section>
    </main>
    
    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Student Name &hearts; Learning HTML &amp; loving it!</p>
    </footer>
</body>
</html>
```

---

## Teacher Notes & Tips

### Common Student Errors:
1. **Forgetting DOCTYPE** - Check EVERY file starts with it
2. **Wrong meta tag format** - They're self-closing, no </meta>
3. **Comments inside comments** - This breaks! Show example
4. **Missing viewport** - Their sites won't work on phones
5. **Wrong quote types** - Must use straight quotes " not curly "
### Differentiation Strategies:

**For Struggling Students:**
- Provide printed template with fill-in-the-blanks
- Highlight required vs optional elements
- Create a checklist they can check off
- Pair with stronger student for DevTools section

**For Advanced Students:**
- Research additional meta tags (Open Graph for social media)
- Add microdata or schema.org markup
- Create a template with CSS link prepared
- Explore HTML validation at validator.w3.org

### Time Management:
- 0-5 min: Review homework and warm-up
- 5-15 min: I DO demonstration
- 15-35 min: WE DO template creation
- 35-45 min: YOU DO contact page
- 45-50 min: Assessment and homework

### Key Points to Emphasize:
- DOCTYPE must be first (no blank lines before it!)
- Meta charset prevents character encoding issues
- Viewport is essential for mobile devices
- Comments help but are visible to anyone
- Templates save time and prevent errors

### Extension Ideas:
- Create templates for different page types
- Research HTML entities and create a reference sheet
- Explore other language codes beyond "en"
- Learn about Open Graph meta tags for social sharing

### Resources:
- HTML Entity Reference: https://www.w3schools.com/html/html_entities.asp
- Meta Tag Generator: https://metatags.io/
- HTML Validator: https://validator.w3.org/
- Language Codes: https://www.w3schools.com/tags/ref_language_codes.asp

**End of Lesson 3**