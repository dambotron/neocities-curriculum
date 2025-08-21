# Lesson 3: HTML Document Structure

## Duration: 45-50 minutes

### Learning Objectives
- Understand the complete HTML document structure
- Learn about metadata and the head section
- Practice creating well-structured HTML documents
- Understand HTML comments

### Materials Needed
- Text editor
- Web browser with developer tools
- Lesson 3 worksheet

### Lesson Outline

#### Review (5 minutes)
- Quick quiz: What does HTML stand for?
- Review the basic tags learned in Lesson 2
- Check homework (favorites.html)

#### The Complete HTML Structure (15 minutes)

1. **DOCTYPE Declaration**
   ```html
   <!DOCTYPE html>
   ```
   - Always the first line
   - Tells browser to use HTML5
   - Not technically an HTML tag

2. **The HTML Element**
   ```html
   <html lang="en">
   ```
   - Root element of the page
   - `lang` attribute for language
   - Everything else goes inside
3. **The Head Section**
   ```html
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <meta name="description" content="A description of your page">
       <title>Page Title</title>
   </head>
   ```
   - Contains metadata (data about data)
   - Not visible on the page
   - Important for browsers and search engines

4. **The Body Section**
   ```html
   <body>
       <!-- All visible content goes here -->
   </body>
   ```

#### HTML Comments (10 minutes)

1. **Comment Syntax**
   ```html
   <!-- This is a comment -->
   ```
   - Not visible on the webpage
   - Helpful for notes and organization
   - Can span multiple lines

2. **When to Use Comments**
   - Explain complex code
   - Temporarily disable code
   - Leave notes for yourself or others
   - Mark sections of your page
#### Hands-On Activity: Creating a Template (15 minutes)

Students create `template.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Metadata Section -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="My personal website">
    <meta name="author" content="Your Name">
    <title>My Website - Page Title</title>
</head>
<body>
    <!-- Header Section -->
    <h1>Welcome to My Website</h1>
    
    <!-- Main Content -->
    <p>This is my template page.</p>
    
    <!-- Footer Section -->
    <p>Created by [Your Name] - 2024</p>
</body>
</html>
```

#### Browser Developer Tools Demo (5 minutes)

1. Open the page in browser
2. Right-click → Inspect
3. Show the HTML structure in DevTools
4. Demonstrate how comments don't appear
5. Show the head section in DevTools
### Practice Exercise (5 minutes)

1. Create a new file called `contact.html`
2. Use the complete HTML structure
3. Include all meta tags discussed
4. Add comments to organize sections
5. Add at least 3 different elements in the body

### Common Issues to Address
- Missing DOCTYPE
- Incorrect meta tag syntax
- Comments inside comments
- Missing lang attribute
- Unclosed tags

### Homework Assignment

Create `index.html` (replacing the default Neocities page):
1. Use complete HTML5 structure
2. Include all meta tags learned
3. Add comments for each major section
4. Content requirements:
   - A welcome message
   - Brief introduction about yourself
   - What you hope to learn
   - Links to your other pages (we'll make these work in Lesson 5)

### Assessment Rubric
- Correct DOCTYPE: 2 points
- Complete head section: 3 points
- Proper use of comments: 2 points
- Valid HTML structure: 3 points
- Total: 10 points

### Teacher Notes
- Emphasize the importance of proper structure
- Show how DevTools can help debug
- Encourage students to save their template for future use
- Check that students understand comments aren't visible