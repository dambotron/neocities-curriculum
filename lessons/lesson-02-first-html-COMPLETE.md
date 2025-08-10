# Lesson 2: Creating Your First HTML Page
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Write HTML tags with correct syntax
- Create an HTML file from scratch without a template
- Use essential HTML tags (h1-h6, p, strong, em, br)
- Upload files to their Neocities account
- Understand the difference between opening and closing tags

### Materials Needed
- Text editor installed (VS Code, Notepad++, or Sublime Text)
- Neocities account from Lesson 1
- Projector for demonstrations
- Printed HTML reference sheet (optional)
- Sample HTML file for troubleshooting

### Key Vocabulary with Definitions
- **Tag**: HTML code that tells the browser how to display content
- **Element**: A complete HTML unit (opening tag + content + closing tag)
- **Opening Tag**: Starts an HTML element, like `<p>`
- **Closing Tag**: Ends an HTML element, like `</p>`
- **Self-Closing Tag**: A tag that doesn't need a closing tag, like `<br>`
- **Attribute**: Extra information added to tags, like `lang="en"`
- **Nesting**: Putting HTML elements inside other elements

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding HTML Syntax (7 minutes)

**Teacher Script:**
"Yesterday we edited existing HTML. Today, you'll write HTML from scratch! Let me show you exactly how HTML works."

**[OPEN TEXT EDITOR on projector]**

"HTML uses a simple pattern. Watch carefully:"

**[TYPE THIS SLOWLY, explaining each character]**
```html
<tagname>Content goes here</tagname>
```

"Let's break this down:
1. `<tagname>` - This is the OPENING TAG. The angle brackets tell the browser 'Hey, here comes an instruction!'
2. `Content goes here` - This is what the user actually sees
3. `</tagname>` - This is the CLOSING TAG. The forward slash means 'I'm done with this instruction'

Think of it like a sandwich:
- Opening tag = Top piece of bread
- Content = The filling
- Closing tag = Bottom piece of bread

**Real Example:**
```html
<p>This is a paragraph.</p>
```
This tells the browser: 'Display this text as a paragraph'

**Common Beginner Mistakes I'll Help You Avoid:**
1. Forgetting the closing tag: `<p>This is wrong`
2. Wrong slash direction: `<p\>This is wrong<\p>`
3. Forgetting angle brackets: `p>This is wrong</p`
4. Mismatched tags: `<p>This is wrong</h1>`"

### Creating an HTML File from Scratch (8 minutes)

**[CREATE NEW FILE in text editor]**

"Now watch as I build a complete HTML page from nothing. I'll explain every single line:"
**[TYPE EACH LINE, explaining as you go]**

```html
<!DOCTYPE html>
```
"This tells the browser: 'I'm using modern HTML5'. Always put this first!"

```html
<html>
```
"This is the root element - everything else goes inside here."

```html
<head>
    <title>About Me</title>
</head>
```
"The head section contains information ABOUT your page. The title appears in the browser tab - look up there when I save this!"

```html
<body>
    <h1>About Me</h1>
    <p>My name is Ms. Johnson.</p>
    <p>I am learning HTML!</p>
</body>
```
"The body section contains everything VISIBLE on your page. 
- `<h1>` is the biggest heading - use it for your main title
- `<p>` creates paragraphs with space between them"

```html
</html>
```
"Close the HTML tag - we're done!"

**[SAVE FILE as teacher_demo.html and OPEN IN BROWSER]**
"Look! Our HTML became a real webpage! See how:
- The title 'About Me' appears in the browser tab
- The `<h1>` is big and bold
- The paragraphs have automatic spacing"

---

## PART 2: WE DO (Guided Practice) - 20 minutes

### Building about.html Together (12 minutes)

**Teacher Script:**
"Now let's build your about.html page together. Open your text editor and follow along with me. I'll go slowly and we'll check in frequently."

**Step 1: Create the File**
"Everyone:
1. Open your text editor
2. Click File → New File
3. Immediately save it as 'about.html' (NOT about.txt!)
4. CHECKPOINT: Everyone raise your hand when you see 'about.html' in your editor's title bar"

**Step 2: Type the Structure Together**

"Type exactly what I type. We'll go line by line:"

```html
<!DOCTYPE html>
```
"Everyone type this. D-O-C-T-Y-P-E is all capitals. Who can tell me what this line does?"
*[Wait for response]* "Right! It tells the browser we're using HTML5."

```html
<html>
```
"Add the HTML opening tag. Don't forget the angle brackets!"

```html
<head>
```
"Indent by pressing TAB once. This makes our code readable. Add the head opening tag."
```html
    <title>About Me - [Your Name]</title>
```
"Indent again with TAB. Type title tags. Put YOUR actual name, not [Your Name]!"

```html
</head>
```
"Close the head tag. Make sure the slash goes forward: /"

```html
<body>
```
"Start the body section - same indentation as head."

```html
    <h1>All About [Your Name]</h1>
```
"This is your main heading. Make it personal! You could write 'All About Sarah' or 'John's Story' - be creative!"

```html
    <p>Hi! My name is [Your Name] and I'm a student at [School Name].</p>
```
"First paragraph - introduce yourself. Include your actual school name."

```html
    <p>I am learning to build websites with HTML!</p>
```
"Second paragraph - everyone type this exactly."

```html
    <h2>My Interests</h2>
```
"Now add a smaller heading using h2. What do you think h2 means? Right - heading level 2!"

```html
    <p>I enjoy [add three things you enjoy].</p>
```
"Add a paragraph about your interests. Be specific! Instead of 'I like sports', write 'I enjoy playing basketball, watching soccer, and swimming.'"
```html
</body>
```
"Close the body tag."

```html
</html>
```
"Close the html tag. We're done typing!"

**Step 3: Save and Test Locally**
"Everyone:
1. Save your file (Ctrl+S or Cmd+S)
2. Find your file in your file explorer/finder
3. Double-click to open in your browser
4. CHECKPOINT: Raise your hand when you see your page in the browser!"

**Common Issues to Fix Together:**
- "If you see code instead of a webpage, you probably saved as .txt instead of .html"
- "If something looks wrong, let's check for missing closing tags"
- "If your title doesn't show in the tab, check your `<title>` tags"

### Adding More HTML Elements (8 minutes)

"Let's enhance our page with more HTML elements. Add these after your interests paragraph:"

**Strong and Emphasis Tags:**
```html
    <p>My <strong>favorite</strong> subject is <em>computer science</em>!</p>
```
"The `<strong>` tag makes text bold. The `<em>` tag makes text italic. Let's see the difference!"

**Line Breaks:**
```html
    <p>My contact info:<br>
    Email: student@school.edu<br>
    Class: Web Development</p>
```
"The `<br>` tag creates a line break WITHOUT starting a new paragraph. It's self-closing - no `</br>` needed!"
**Multiple Heading Levels:**
```html
    <h3>A Smaller Heading</h3>
    <p>This heading is smaller than h2.</p>
    
    <h4>Even Smaller</h4>
    <p>We have h1 through h6 available!</p>
```

---

## PART 3: YOU DO (Independent Practice) - 10 minutes

### Student Activity: Expand Your About Page

**Instructions:**
"You have 10 minutes to add more content to your about.html page. Complete these required tasks, then try the bonus challenges if you have time."

**Required Tasks:**
1. ✅ Add a new `<h2>` section called "My Goals"
2. ✅ Under it, add 2 paragraphs about your goals
3. ✅ Add a new `<h2>` section called "Fun Facts"  
4. ✅ Add at least 3 fun facts using separate `<p>` tags
5. ✅ Use `<strong>` at least twice to make important words bold
6. ✅ Use `<em>` at least once to emphasize something
7. ✅ Add a section with your schedule using `<br>` tags

**Bonus Challenges:**
- Use all six heading levels (h1 through h6) appropriately
- Create a "contact info" section with line breaks
- Add 10+ paragraphs total
- Experiment with nesting `<strong>` inside `<em>` for bold-italic text

### Complete Solution Example:
```html
<!DOCTYPE html>
<html>
<head>
    <title>About Me - Alex Chen</title>
</head>
<body>
    <h1>All About Alex Chen</h1>    <p>Hi! My name is Alex Chen and I'm a student at Lincoln High School.</p>
    <p>I am learning to build websites with HTML!</p>
    
    <h2>My Interests</h2>
    <p>I enjoy playing <strong>guitar</strong>, reading mystery novels, and coding.</p>
    <p>My <em>absolute favorite</em> hobby is building robots with Arduino!</p>
    
    <h2>My Goals</h2>
    <p>My <strong>short-term goal</strong> is to build a portfolio website by the end of this course.</p>
    <p>My long-term goal is to become a <em>web developer</em> or <em>software engineer</em> after college.</p>
    
    <h2>Fun Facts</h2>
    <p>I can solve a Rubik's cube in <strong>under 2 minutes</strong>!</p>
    <p>I speak three languages: English, Spanish, and Mandarin.</p>
    <p>I have a pet turtle named <strong>Leonardo</strong> (after the Ninja Turtle).</p>
    <p>I've been to <em>seven</em> different countries!</p>
    
    <h3>My Daily Schedule</h3>
    <p>Monday-Friday:<br>
    7:00 AM - Wake up<br>
    8:00 AM - School starts<br>
    3:00 PM - School ends<br>
    4:00 PM - Soccer practice<br>
    6:00 PM - Homework time<br>
    9:00 PM - Free time</p>
    
    <h3>Contact Information</h3>
    <p>Feel free to reach out!<br>
    School Email: achen@lincolnhs.edu<br>
    Class Period: 3rd Period<br>
    Room Number: Computer Lab 201</p>
    
    <h4>This Website</h4>
    <p>This is my <strong><em>very first</em></strong> HTML page created from scratch!</p>
</body>
</html>
```

---

## Uploading to Neocities (5 minutes)

### Step-by-Step Upload Process

**Teacher Demonstration:**
"Now let's make your page live on the internet! Follow along:"

1. **Go to Neocities Dashboard**
   - "Open neocities.org and log in"
   - "Click 'Edit Your Site' button"

2. **Upload Your File**
   - "Click the 'Upload' button or drag your about.html file into the browser"
   - "Make sure it says 'about.html' not 'about.html.txt'"

3. **Verify Upload**
   - "You should see about.html in your file list"
   - "Click on it to open in the editor and verify it looks right"

4. **View Your Live Page**
   - "Go to [yourusername].neocities.org/about.html"
   - "Congratulations! Your page is live on the internet!"

**Troubleshooting Common Upload Issues:**
- File not appearing: Refresh the page
- File shows as text: Check file extension is .html
- Changes not showing: Clear browser cache (Ctrl+F5)

---

## Assessment & Closing (5 minutes)

### Exit Ticket Questions
Students complete these before leaving:

1. **What's the difference between `<h1>` and `<h2>`?**
   - Answer: h1 is the largest heading (main title), h2 is the second-largest (section titles)

2. **Write the complete code for a paragraph that says "Hello World":**
   - Answer: `<p>Hello World</p>`
3. **What does the `<br>` tag do and why doesn't it need a closing tag?**
   - Answer: Creates a line break; it's self-closing because it doesn't contain content

4. **Fix this code: `<p>This is <strong>bold text</p></strong>`**
   - Answer: `<p>This is <strong>bold text</strong></p>` (tags must be properly nested)

### Success Criteria Checklist
Rate each student:
- [ ] Created valid HTML file from scratch (3 pts)
- [ ] Used proper HTML structure with all required tags (3 pts)
- [ ] Successfully added multiple heading levels (2 pts)
- [ ] Used strong and em tags correctly (2 pts)
- [ ] Included at least 5 paragraphs of content (3 pts)
- [ ] Successfully uploaded to Neocities (2 pts)
- [ ] Page displays correctly online (2 pts)
- [ ] Used proper indentation (1 pt)
- [ ] Added creative, personal content (2 pts)
**Total: ___/20 points**

### Homework Assignment

Create a new file called `favorites.html` that includes:

1. **Required Structure:**
   - Complete HTML document structure
   - Descriptive title in browser tab
   - At least 3 different heading levels

2. **Required Content:**
   - h1 with "My Favorite Things"
   - Section about favorite movie/TV show (3+ paragraphs)
   - Section about favorite food (2+ paragraphs)
   - Section about favorite website (2+ paragraphs)
   - Use strong tags for emphasis (3+ times)
   - Use em tags for emphasis (2+ times)
3. **Homework Solution Example:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>My Favorites - Student Name</title>
</head>
<body>
    <h1>My Favorite Things</h1>
    
    <h2>Favorite Movie: The Matrix</h2>
    <p>My <strong>all-time favorite</strong> movie is The Matrix from 1999.</p>
    <p>I love this movie because it combines <em>mind-bending philosophy</em> with incredible action scenes.</p>
    <p>The special effects were <strong>revolutionary</strong> for their time, especially the bullet-time sequences.</p>
    
    <h2>Favorite Food: Pizza</h2>
    <p>Nothing beats a <strong>hot, fresh pizza</strong> on a Friday night!</p>
    <p>My favorite toppings are <em>pepperoni, mushrooms, and extra cheese</em>.</p>
    
    <h2>Favorite Website: YouTube</h2>
    <p>I spend <strong>hours</strong> on YouTube watching educational videos.</p>
    <p>My favorite channels teach <em>programming, science, and history</em>.</p>
    
    <h3>Why These Are My Favorites</h3>
    <p>All of these things bring me <strong>joy</strong> and help me relax after school.</p>
</body>
</html>
```

---

## Teacher Notes & Tips

### Pacing Guide
- 0-5 min: Review & warm-up
- 5-15 min: I DO demonstration
- 15-35 min: WE DO guided practice
- 35-45 min: YOU DO independent work
- 45-50 min: Upload & assessment
### Common Student Errors to Watch For:
1. **Forgetting closing tags** - Have them count opening and closing tags
2. **Using backslash instead of forward slash** - Write `/` on the board
3. **Not saving before testing** - Remind constantly: "Save first!"
4. **Wrong file extension** - Check everyone has .html not .txt
5. **Broken nesting** - Draw boxes to show proper nesting
6. **Missing angle brackets** - Point them out in every example
7. **Case sensitivity** - HTML isn't case-sensitive but be consistent

### Differentiation Strategies:

**For Struggling Students:**
- Provide a printed template with blanks to fill in
- Pair with a stronger student for WE DO section
- Give them the first 5 lines of code to start with
- Use color-coding for different tag types
- Allow them to reference the solution file

**For Advanced Students:**
- Challenge to use all 6 heading levels appropriately
- Ask them to create a table of contents using headings
- Have them add HTML comments explaining their code
- Introduce additional tags: `<mark>`, `<small>`, `<del>`, `<ins>`
- Ask them to create multiple pages and plan how to link them

### Classroom Management Tips:
- Use "Stop and Show" - everyone stops typing and holds up their screen
- Have students trace tags with their finger while reading code
- Use partner checks: "Turn to your neighbor and compare line 5"
- Keep a "parking lot" for questions that will be answered later
- Celebrate first successful upload with applause

### Extension Activities:
1. Research and use 3 HTML tags not covered in class
2. Create a "recipe.html" page with ingredients and instructions
3. Make a "bucket-list.html" with 20 things you want to do
4. View page source of favorite website and identify familiar tags
### Required Preparations:
- Test Neocities upload process before class
- Have backup text editor on USB drive
- Create your own about.html as example
- Print HTML reference sheets
- Bookmark HTML validator website
- Prepare example files with common errors

### Assessment Rubric Details:

| Criterion | Excellent (3) | Good (2) | Needs Work (1) | Missing (0) |
|-----------|--------------|----------|----------------|-------------|
| HTML Structure | All tags present and correct | Minor errors | Major errors | Incomplete |
| Content Quality | Creative and detailed | Adequate content | Minimal content | Missing content |
| Tag Usage | Uses variety correctly | Uses basic tags | Errors in usage | Incorrect usage |
| Upload Success | Works perfectly online | Minor issues | Major issues | Failed upload |

### Quick Reference for Students (Write on Board):

```
HTML FORMULA:
<tagname>Content</tagname>

MUST HAVE STRUCTURE:
<!DOCTYPE html>
<html>
    <head>
        <title>Tab Title</title>
    </head>
    <body>
        <!-- All visible content here -->
    </body>
</html>

COMMON TAGS:
<h1> to <h6> = Headings
<p> = Paragraph
<strong> = Bold
<em> = Italic
<br> = Line break (no closing tag!)
```

### Links and Resources:
- W3Schools HTML Tutorial: https://www.w3schools.com/html/
- HTML Validator: https://validator.w3.org/
- HTML Reference Sheet: [Create handout with all tags covered]
- Neocities Help: https://neocities.org/help

**End of Lesson 2**