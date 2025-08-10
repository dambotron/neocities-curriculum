# Lesson 4: Working with Text (Headings, Paragraphs, Lists)

## Duration: 45-50 minutes

### Learning Objectives
- Master text-based HTML elements
- Create properly structured content
- Understand semantic importance of headings
- Build organized lists

### Materials Needed
- Text editor
- HTML cheat sheet
- Example content document

### Lesson Outline

#### Warm-up Review (5 minutes)
- Quick review of HTML structure
- Check homework (new index.html)
- Preview today's elements

#### Headings Deep Dive (10 minutes)

1. **The Six Heading Levels**
   ```html
   <h1>Main Page Title</h1>
   <h2>Section Title</h2>
   <h3>Subsection Title</h3>
   <h4>Sub-subsection Title</h4>
   <h5>Minor Heading</h5>
   <h6>Smallest Heading</h6>
   ```

2. **Heading Best Practices**
   - Only one `<h1>` per page
   - Don't skip levels (h1 → h3)
   - Use headings for structure, not size
   - Think of headings like an outline
#### Text Formatting Elements (10 minutes)

1. **Paragraph and Line Breaks**
   ```html
   <p>This is a paragraph.</p>
   <p>This is another paragraph.<br>
   With a line break in it.</p>
   ```

2. **Text Emphasis**
   ```html
   <strong>This text is important (bold)</strong>
   <em>This text has emphasis (italic)</em>
   <mark>This text is highlighted</mark>
   <small>This text is smaller</small>
   ```

3. **Other Text Elements**
   ```html
   <blockquote>
       "This is a quotation from someone important."
   </blockquote>
   <pre>This text preserves    spacing
   and line breaks</pre>
   <code>console.log("This is code");</code>
   ```

#### Lists (10 minutes)

1. **Unordered Lists (Bullets)**
   ```html
   <ul>
       <li>First item</li>
       <li>Second item</li>
       <li>Third item</li>
   </ul>
   ```
2. **Ordered Lists (Numbers)**
   ```html
   <ol>
       <li>First step</li>
       <li>Second step</li>
       <li>Third step</li>
   </ol>
   ```

3. **Nested Lists**
   ```html
   <ul>
       <li>Fruits
           <ul>
               <li>Apples</li>
               <li>Oranges</li>
           </ul>
       </li>
       <li>Vegetables
           <ul>
               <li>Carrots</li>
               <li>Broccoli</li>
           </ul>
       </li>
   </ul>
   ```

#### Hands-On Project: Recipe Page (12 minutes)

Students create `recipe.html`:
1. Use h1 for recipe name
2. Use h2 for "Ingredients" and "Instructions"
3. Use unordered list for ingredients
4. Use ordered list for instructions
5. Use paragraphs for description
6. Include emphasized text for important notes
#### Sample Recipe Page Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Favorite Recipe</title>
</head>
<body>
    <h1>Chocolate Chip Cookies</h1>
    
    <p>These <em>delicious</em> cookies are <strong>perfect</strong> for any occasion!</p>
    
    <h2>Ingredients</h2>
    <ul>
        <li>2 cups flour</li>
        <li>1 cup butter</li>
        <li>1 cup chocolate chips</li>
    </ul>
    
    <h2>Instructions</h2>
    <ol>
        <li>Preheat oven to 350°F</li>
        <li>Mix ingredients</li>
        <li>Bake for 12 minutes</li>
    </ol>
    
    <p><small>Recipe serves 24 cookies</small></p>
</body>
</html>
```

### Practice Extension (3 minutes)
Add to recipe page:
- Nested list for ingredient categories
- Blockquote with a review
- Mark important warnings
### Homework Assignment

Create a `study-guide.html` page that includes:
1. A main title (h1) for your favorite school subject
2. At least 3 section headings (h2)
3. Subsection headings (h3) under each section
4. Multiple paragraphs explaining concepts
5. An unordered list of key terms
6. An ordered list of steps for solving a problem
7. Use of `<strong>`, `<em>`, and `<mark>` appropriately
8. At least one blockquote from a textbook or teacher

### Assessment Criteria
- Proper heading hierarchy: 3 points
- Correct list usage: 3 points
- Text formatting elements: 2 points
- Overall structure and content: 2 points
- Total: 10 points

### Common Mistakes to Watch For
- Using `<b>` instead of `<strong>`
- Using `<i>` instead of `<em>`
- Forgetting to close list tags
- Incorrect nesting of lists
- Using headings for styling instead of structure

### Teacher Notes
- Show examples of good heading hierarchy
- Demonstrate the visual difference between elements
- Explain semantic HTML (meaning vs. appearance)
- Let students choose their own recipe or topic
- Encourage creativity while maintaining structure