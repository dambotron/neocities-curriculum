# Lesson 4: Working with Text - All Text Elements Mastery
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Use all six heading levels appropriately
- Create ordered, unordered, and nested lists
- Apply text formatting tags (strong, em, mark, small, etc.)
- Understand the difference between semantic and presentational HTML
- Build a well-structured text-heavy webpage

### Materials Needed
- Text editor with HTML syntax highlighting
- Browser for testing
- Projector for demonstrations
- Printed text elements reference sheet
- Sample text content for exercises (provided)

### Key Vocabulary with Definitions
- **Heading Hierarchy**: The organized structure of headings from h1 (most important) to h6 (least important)
- **Semantic HTML**: HTML that describes meaning, not just appearance
- **List Item**: Individual entry in a list (`<li>`)
- **Ordered List**: Numbered list (`<ol>`)
- **Unordered List**: Bulleted list (`<ul>`)
- **Nested List**: A list inside another list
- **Text Formatting**: HTML elements that change text appearance or meaning
- **Block vs Inline**: Block elements start new lines, inline elements don't

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Heading Hierarchy Explained (5 minutes)

**Teacher Script:**
"Imagine you're writing a book. You wouldn't make every sentence the same size! HTML has SIX heading levels to organize content, just like a book has chapters, sections, and subsections."
**[CREATE new file: text-demo.html and TYPE with explanations]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Text Elements Demo</title>
</head>
<body>
    <h1>The Main Title - Only ONE per page!</h1>
    <p>Think of h1 as the book title. You only have one book title!</p>
    
    <h2>Chapter 1: Major Section</h2>
    <p>H2 is for major sections, like chapters in a book.</p>
    
    <h3>Section 1.1: Subsection</h3>
    <p>H3 breaks down chapters into smaller parts.</p>
    
    <h4>Topic A: Smaller Division</h4>
    <p>H4 is for specific topics within sections.</p>
    
    <h5>Subtopic: Getting Detailed</h5>
    <p>H5 is rarely used - only for very detailed organization.</p>
    
    <h6>Fine Print: Smallest Heading</h6>
    <p>H6 is the smallest - almost never needed!</p>
</body>
</html>
```

**"The Heading Rules:"**
1. "Only ONE h1 per page (it's the page title/topic)"
2. "Don't skip levels (no h1 then h3 - use h2 in between)"
3. "Headings create hierarchy - search engines use this!"
4. "Size doesn't matter - meaning does! (CSS changes size later)"

### Lists: The Three Types (5 minutes)

**[ADD to demo file]**
```html
<h2>Types of Lists</h2>

<h3>Unordered List (Bullets)</h3>
<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>

<h3>Ordered List (Numbers)</h3>
<ol>
    <li>Step one</li>
    <li>Step two</li>
    <li>Step three</li>
</ol>

<h3>Nested Lists (Lists Inside Lists)</h3>
<ul>
    <li>Fruits
        <ul>
            <li>Apples
                <ul>
                    <li>Red Delicious</li>
                    <li>Granny Smith</li>
                </ul>
            </li>
            <li>Bananas</li>
        </ul>
    </li>
    <li>Vegetables
        <ol>
            <li>Carrots</li>
            <li>Broccoli</li>
        </ol>
    </li>
</ul>

<h3>Definition List (Terms and Definitions)</h3>
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language - the structure of web pages</dd>
    
    <dt>CSS</dt>
    <dd>Cascading Style Sheets - the styling of web pages</dd>    
    <dt>JavaScript</dt>
    <dd>Programming language for web interactivity</dd>
</dl>
```

**Teacher Script:**
"Lists are everywhere on the web! 
- **Unordered (ul)**: Use when order doesn't matter (shopping list)
- **Ordered (ol)**: Use when sequence matters (recipe steps)
- **Definition (dl)**: Use for glossaries or term-definition pairs
- **Nesting**: Indent with TAB to show hierarchy - like an outline!"

### Text Formatting: Semantic vs Visual (5 minutes)

**[ADD to demo file]**

```html
<h2>Text Formatting Elements</h2>

<h3>Semantic Elements (Have Meaning)</h3>
<p>This text is <strong>very important</strong> (strong emphasis).</p>
<p>This text is <em>emphasized</em> (stress emphasis).</p>
<p>This text is <mark>highlighted</mark> like a highlighter pen.</p>
<p>This text is <small>small print</small> (fine print/disclaimers).</p>
<p>This text has <del>deleted content</del> (strikethrough).</p>
<p>This text has <ins>inserted content</ins> (underlined).</p>
<p>This is a <abbr title="World Wide Web">WWW</abbr> abbreviation.</p>
<p>This is <code>computer code</code> in a sentence.</p>
<p>Press <kbd>Ctrl</kbd> + <kbd>S</kbd> to save.</p>
<p>The computer says: <samp>File saved successfully</samp></p>

<h3>Quotations</h3>
<p>She said, <q>HTML is awesome!</q> (inline quote)</p>
<blockquote>
    This is a longer quotation that deserves its own block.
    It usually gets indented and stands out from regular text.
    - Someone Famous
</blockquote>
<h3>Special Text Elements</h3>
<pre>
    This preserves    spacing    and
    line breaks exactly as typed.
    Great for code or ASCII art!
</pre>

<p>Subscript: H<sub>2</sub>O (water)</p>
<p>Superscript: X<sup>2</sup> + Y<sup>2</sup> = Z<sup>2</sup></p>
<p>Line<br>Break<br>Example</p>
<hr>
<p>Horizontal rule above (thematic break)</p>
```

**Teacher Script:**
"Notice the difference:
- **<strong> vs <b>**: Strong has meaning (important!), b is just visual (bold)
- **<em> vs <i>**: Em has emphasis meaning, i is just visual (italic)
- **Semantic = meaning**: Screen readers understand these
- **Visual = appearance**: Just changes looks, no meaning
Always use semantic when possible!"

---

## PART 2: WE DO (Guided Practice) - 20 minutes

### Building a Recipe Page Together (12 minutes)

**Teacher Script:**
"Let's build a complete recipe page using ALL the text elements we learned. This shows real-world usage!"

**Step 1: Create the File**
"Everyone:
1. Create new file: `recipe.html`
2. Start with our template from Lesson 3
3. Update title to 'Chocolate Chip Cookies Recipe'
4. CHECKPOINT: Everyone ready?"

**Step 2: Build the Content Structure**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">    <title>Chocolate Chip Cookies Recipe | My Recipe Collection</title>
</head>
<body>
    <h1>The Ultimate Chocolate Chip Cookies</h1>
    <p>This recipe makes <strong>24 delicious cookies</strong> in just <em>30 minutes</em>!</p>
```
"Start with h1 for the recipe name. Add strong for important info and em for emphasis."

```html
    <h2>Quick Facts</h2>
    <ul>
        <li><strong>Prep Time:</strong> 15 minutes</li>
        <li><strong>Cook Time:</strong> 12 minutes</li>
        <li><strong>Total Time:</strong> 27 minutes</li>
        <li><strong>Servings:</strong> 24 cookies</li>
        <li><strong>Difficulty:</strong> <mark>Easy</mark></li>
    </ul>
```
"Use an unordered list for recipe facts - order doesn't matter here. Mark highlights the difficulty."

```html
    <h2>Ingredients</h2>
    <p>You'll need the following items:</p>
    <ul>
        <li>2¼ cups all-purpose flour</li>
        <li>1 <abbr title="teaspoon">tsp</abbr> baking soda</li>
        <li>1 <abbr title="teaspoon">tsp</abbr> salt</li>
        <li>1 cup butter <small>(2 sticks, softened)</small></li>
        <li>¾ cup granulated sugar</li>
        <li>¾ cup packed brown sugar</li>
        <li>2 large eggs</li>
        <li>2 <abbr title="teaspoons">tsp</abbr> vanilla extract</li>
        <li>2 cups chocolate chips <em>(semi-sweet recommended)</em></li>
    </ul>
```
"Ingredients use unordered list. Notice the abbreviations for measurements and small for clarifications."
```html
    <h2>Instructions</h2>
    <ol>
        <li>Preheat oven to <strong>375°F</strong> (190°C).</li>
        <li>In a small bowl, combine:
            <ul>
                <li>Flour</li>
                <li>Baking soda</li>
                <li>Salt</li>
            </ul>
        </li>
        <li>In a large bowl, beat butter and both sugars until <em>creamy</em>.</li>
        <li>Add eggs and vanilla, mix well.</li>
        <li>Gradually blend in flour mixture.</li>
        <li>Stir in chocolate chips.</li>
        <li>Drop rounded <abbr title="tablespoon">tbsp</abbr> onto ungreased cookie sheets.</li>
        <li>Bake for <mark>9 to 11 minutes</mark> or until golden brown.</li>
        <li>Cool on baking sheet for 2 minutes.</li>
        <li>Remove to wire rack to cool completely.</li>
    </ol>
```
"Instructions MUST be ordered list - sequence matters! Notice the nested list in step 2."

```html
    <h2>Chef's Tips</h2>
    <blockquote>
        "The secret to perfect cookies is to slightly underbake them. 
        They'll continue cooking on the hot pan after you remove them from the oven!"
        <br>
        - Grandma's wisdom
    </blockquote>
    
    <h3>Storage</h3>
    <p>Store in an airtight container for up to <strong>1 week</strong>.</p>
    <p><small>For longer storage, freeze for up to 3 months.</small></p>
    
    <hr>
    <footer>
        <p><small>&copy; 2024 My Recipe Collection. Feel free to share!</small></p>    </footer>
</body>
</html>
```

### Text Formatting Practice (8 minutes)

"Now let's practice using different text elements. Add this section to your recipe:"

```html
    <h2>Nutrition Information</h2>
    <p><strong>Per cookie:</strong></p>
    <dl>
        <dt>Calories</dt>
        <dd>Approximately 150 <abbr title="kilocalories">kcal</abbr></dd>
        
        <dt>Fat</dt>
        <dd>8g <small>(12% daily value)</small></dd>
        
        <dt>Carbohydrates</dt>
        <dd>20g <small>(7% daily value)</small></dd>
        
        <dt>Protein</dt>
        <dd>2g</dd>
    </dl>
    
    <h2>Variations</h2>
    <p>Try these delicious alternatives:</p>
    <ul>
        <li><strong>Double Chocolate:</strong> Replace ½ cup flour with cocoa powder</li>
        <li><strong>Nutty:</strong> Add 1 cup chopped <mark>walnuts</mark> or <mark>pecans</mark></li>
        <li><strong>Oatmeal:</strong> Replace 1 cup flour with <em>old-fashioned oats</em></li>
        <li><del>White chocolate chips</del> <ins>Dark chocolate chips</ins> for less sweetness</li>
    </ul>
```

---

## PART 3: YOU DO (Independent Practice) - 10 minutes

### Student Activity: Create a Study Guide Page

**Instructions:**
"Create a study guide for your favorite subject using ALL the text elements we learned. You have 10 minutes!"
**Required Tasks:**
1. ✅ Create `study-guide.html` with proper HTML5 structure
2. ✅ Use ALL 6 heading levels appropriately (h1-h6)
3. ✅ Include at least one of each list type (ul, ol, dl)
4. ✅ Create a nested list (list inside a list)
5. ✅ Use at least 5 different text formatting tags (strong, em, mark, etc.)
6. ✅ Add a blockquote with a famous quote about your subject
7. ✅ Include abbreviations with title attributes
8. ✅ Use pre tag for formatted text (like a formula or diagram)
9. ✅ Add subscript and superscript where appropriate
10. ✅ Include a horizontal rule to separate sections

**Bonus Challenges:**
- Create a table of contents using nested lists
- Add keyboard shortcuts using kbd tags
- Include code examples using code tags
- Make a glossary using definition lists

### Complete Solution Example:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biology Study Guide - Cell Structure | Student Resources</title>
</head>
<body>
    <h1>Biology Study Guide: Cell Structure</h1>
    <p>Master the fundamentals of <strong>cell biology</strong> with this comprehensive guide!</p>
    
    <h2>Table of Contents</h2>
    <ol>
        <li>Cell Theory
            <ul>
                <li>Historical Development</li>
                <li>Modern Understanding</li>
            </ul>        </li>
        <li>Cell Types
            <ul>
                <li>Prokaryotic</li>
                <li>Eukaryotic</li>
            </ul>
        </li>
        <li>Cell Organelles</li>
        <li>Cell Processes</li>
    </ol>
    
    <hr>
    
    <h2>1. Cell Theory</h2>
    <blockquote>
        "Every cell comes from another cell."
        <br>
        <small>- Rudolf Virchow, 1855</small>
    </blockquote>
    
    <h3>1.1 The Three Principles</h3>
    <ol>
        <li>All living things are made of <mark>one or more cells</mark></li>
        <li>The cell is the <strong>basic unit of life</strong></li>
        <li>All cells come from <em>pre-existing cells</em></li>
    </ol>
    
    <h4>Historical Timeline</h4>
    <ul>
        <li><strong>1665:</strong> Robert Hooke discovers cells</li>
        <li><strong>1674:</strong> Van Leeuwenhoek observes living cells</li>
        <li><strong>1838:</strong> Schleiden proposes plants are made of cells</li>
        <li><strong>1839:</strong> Schwann extends theory to animals</li>
    </ul>
    
    <h5>Key Scientists to Remember</h5>
    <p>Focus on these <mark>important figures</mark> for the exam:</p>
    
    <h6>For Extra Credit:</h6>
    <p><small>Research Lynn Margulis and endosymbiotic theory</small></p>    
    <hr>
    
    <h2>2. Cell Types</h2>
    
    <h3>Comparison Table</h3>
    <dl>
        <dt>Prokaryotic Cells</dt>
        <dd>No nucleus, no membrane-bound organelles, <abbr title="Deoxyribonucleic Acid">DNA</abbr> in nucleoid region</dd>
        <dd>Examples: Bacteria, Archaea</dd>
        <dd>Size: 1-5 <abbr title="micrometers">μm</abbr></dd>
        
        <dt>Eukaryotic Cells</dt>
        <dd>Has nucleus, membrane-bound organelles, DNA in chromosomes</dd>
        <dd>Examples: Animals, Plants, Fungi, Protists</dd>
        <dd>Size: 10-100 <abbr title="micrometers">μm</abbr></dd>
    </dl>
    
    <h2>3. Important Organelles</h2>
    <p>Remember these using the acronym <strong>MR. CHEN</strong>:</p>
    <ul>
        <li><strong>M</strong>itochondria - <em>powerhouse of the cell</em></li>
        <li><strong>R</strong>ibosomes - protein synthesis</li>
        <li><strong>C</strong>hloroplasts - photosynthesis <small>(plants only)</small></li>
        <li><strong>H</strong>istones - DNA packaging proteins</li>
        <li><strong>E</strong>ndoplasmic Reticulum - transport system</li>
        <li><strong>N</strong>ucleus - control center</li>
    </ul>
    
    <h2>4. Chemical Formulas</h2>
    <h3>Photosynthesis</h3>
    <p>6CO<sub>2</sub> + 6H<sub>2</sub>O + light energy → C<sub>6</sub>H<sub>12</sub>O<sub>6</sub> + 6O<sub>2</sub></p>
    
    <h3>Cellular Respiration</h3>
    <p>C<sub>6</sub>H<sub>12</sub>O<sub>6</sub> + 6O<sub>2</sub> → 6CO<sub>2</sub> + 6H<sub>2</sub>O + <abbr title="Adenosine Triphosphate">ATP</abbr></p>    
    <h2>5. Quick Review Diagram</h2>
    <pre>
    ANIMAL CELL STRUCTURE
    ┌─────────────────────────┐
    │  ┌──────┐              │
    │  │Nucleus│   [ER]       │
    │  └──────┘              │
    │      ○ Mitochondria    │
    │   ∙∙∙ Ribosomes       │
    │  ≈≈≈ Golgi Body       │
    └─────────────────────────┘
    Cell Membrane
    </pre>
    
    <h2>Study Tips</h2>
    <p>To memorize effectively:</p>
    <ol>
        <li>Review notes <mark>within 24 hours</mark> of class</li>
        <li>Use <strong>active recall</strong> instead of just re-reading</li>
        <li>Create <em>mnemonics</em> for difficult concepts</li>
        <li>Practice with <del>highlighting everything</del> <ins>selective marking</ins></li>
        <li>Test yourself using <kbd>Ctrl</kbd>+<kbd>F</kbd> to find key terms</li>
    </ol>
    
    <hr>
    
    <footer>
        <p><small>Last updated: January 2024 | Next test: Chapter 3-4</small></p>
        <p>Remember: <q>Cells are the basic units of life!</q></p>
    </footer>
</body>
</html>
```

---

## Assessment & Closing (5 minutes)

### Exit Ticket Questions
1. **What's the difference between `<ol>` and `<ul>`?**
   - Answer: `<ol>` creates ordered (numbered) lists when sequence matters, `<ul>` creates unordered (bulleted) lists when order doesn't matter.

2. **Write the HTML for a nested list with "Fruits" containing "Apples" and "Oranges":**
   - Answer: 
   ```html
   <ul>
       <li>Fruits
           <ul>
               <li>Apples</li>
               <li>Oranges</li>
           </ul>
       </li>
   </ul>
   ```

3. **What's the semantic difference between `<strong>` and `<b>`?**
   - Answer: `<strong>` indicates important content (has meaning), while `<b>` only makes text bold (visual only). Screen readers emphasize `<strong>` but not `<b>`.

4. **How do you write H₂O using HTML?**
   - Answer: `H<sub>2</sub>O`

5. **When should you use `<blockquote>` vs `<q>`?**
   - Answer: Use `<blockquote>` for long, standalone quotes (block-level), use `<q>` for short inline quotes within a sentence.

### Success Criteria Checklist
- [ ] Used all 6 heading levels appropriately (3 pts)
- [ ] Created all 3 list types correctly (3 pts)
- [ ] Successfully nested lists (2 pts)
- [ ] Used 5+ text formatting elements (3 pts)
- [ ] Included semantic HTML elements (2 pts)
- [ ] Added special elements (pre, sub, sup) (2 pts)
- [ ] Code validates without errors (2 pts)
- [ ] Content is well-organized (3 pts)
**Total: ___/20 points**
### Homework Assignment

**Create a "How-To" Tutorial Page (`tutorial.html`):**

Requirements:
1. Choose a topic you can teach (tying shoes, making a sandwich, solving a Rubik's cube, etc.)
2. Include:
   - Proper HTML5 structure from Lesson 3
   - At least 4 heading levels (h1-h4)
   - An ordered list for steps
   - An unordered list for materials/requirements
   - A definition list for terminology
   - At least one nested list
   - 8+ different text formatting elements
   - A blockquote with expert advice
   - Abbreviations with explanations
   - A pre-formatted section (diagram or code)
   - Proper use of semantic HTML

**Homework Solution Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>How to Solve a Rubik's Cube - Beginner Method</title>
</head>
<body>
    <h1>How to Solve a Rubik's Cube</h1>
    <p>Learn the <strong>beginner's method</strong> to solve any 3x3 Rubik's cube in <mark>under 5 minutes</mark>!</p>
    
    <h2>What You'll Need</h2>
    <ul>
        <li>A 3x3 Rubik's Cube</li>
        <li>Patience <em>(lots of it!)</em></li>
        <li>About <strong>2-3 hours</strong> to learn</li>
        <li>This guide</li>
    </ul>    
    <h2>Terminology</h2>
    <dl>
        <dt>Algorithm</dt>
        <dd>A sequence of moves to achieve a specific result</dd>
        
        <dt>Face</dt>
        <dd>One side of the cube (Front, Back, Up, Down, Left, Right)</dd>
        
        <dt>Layer</dt>
        <dd>A horizontal or vertical slice of the cube</dd>
    </dl>
    
    <h2>The Method: 7 Steps</h2>
    <ol>
        <li>Make a white cross
            <ul>
                <li>Match center colors</li>
                <li>Align edge pieces</li>
            </ul>
        </li>
        <li>Complete white face with corners</li>
        <li>Complete middle layer</li>
        <li>Make yellow cross</li>
        <li>Position yellow corners</li>
        <li>Orient yellow corners</li>
        <li>Position final edges</li>
    </ol>
    
    <h3>Notation Guide</h3>
    <h4>Basic Moves</h4>
    <pre>
    F = Front face clockwise
    F' = Front face counter-clockwise
    R = Right face clockwise
    U = Upper face clockwise
    </pre>
    
    <blockquote>
        "If you are not willing to learn, no one can help you. 
        If you are determined to learn, no one can stop you."
        <br>- <small>Erno Rubik, inventor of the Rubik's Cube</small>    </blockquote>
</body>
</html>
```

---

## Teacher Notes & Tips

### Common Student Errors:
1. **Forgetting to close list tags** - Each `<li>` needs `</li>`
2. **Incorrect nesting** - Lists inside lists must be INSIDE an `<li>`
3. **Using `<br>` instead of paragraphs** - Explain when each is appropriate
4. **Confusing `<b>` with `<strong>`** - Emphasize semantic importance
5. **Not indenting nested content** - Makes code hard to read
6. **Skipping heading levels** - Must go h1→h2→h3, not h1→h3

### Differentiation Strategies:

**For Struggling Students:**
- Provide a text elements cheat sheet
- Start with just headings and paragraphs
- Give them pre-written content to mark up
- Pair programming for nested lists

**For Advanced Students:**
- Challenge to create a complex nested outline
- Research additional text elements (cite, time, data)
- Create a text style guide document
- Build a FAQ page with all elements

### Time Management:
- 0-5 min: Review homework and warm-up
- 5-15 min: I DO demonstration of all elements
- 15-35 min: WE DO recipe page together
- 35-45 min: YOU DO study guide
- 45-50 min: Assessment and homework

### Key Teaching Points:
- **Semantic HTML matters** for accessibility
- **Lists can be nested** indefinitely (but keep it reasonable)
- **Headings create document outline** - important for SEO
- **Definition lists** are underused but perfect for glossaries
- **Special characters** need sub/sup tags, not regular text
### Demonstration Tips:
- Show real websites using View Source to find these elements
- Create errors on purpose and fix them together
- Use browser DevTools to show heading hierarchy
- Compare semantic vs non-semantic with screen reader demo (if available)

### Extension Activities:
1. Create a glossary page using only definition lists
2. Build a table of contents that links to sections (preview of Lesson 5)
3. Make an outline for a research paper using nested lists
4. Create ASCII art using the `<pre>` tag

### Assessment Rubric:

| Element | Excellent (3) | Good (2) | Needs Work (1) | Missing (0) |
|---------|--------------|----------|----------------|-------------|
| Heading Hierarchy | All 6 levels used correctly | 4-5 levels used correctly | 2-3 levels used | Less than 2 levels |
| Lists | All 3 types + nesting | 2-3 types used | 1 type used | No lists |
| Text Formatting | 8+ elements used | 5-7 elements | 3-4 elements | Less than 3 |
| Semantic HTML | Consistent semantic use | Mostly semantic | Some semantic | No semantic elements |

### Real-World Connections:
- Blog posts use these elements constantly
- Documentation sites rely on good heading structure
- Recipe sites use lists for ingredients/steps
- Wikipedia uses definition lists extensively
- Academic papers need sup/sub for citations

### Resources:
- MDN Text Elements: https://developer.mozilla.org/en-US/docs/Web/HTML/Element#text_content
- HTML Entity Reference: https://dev.w3.org/html5/html-author/charref
- Screen Reader Demo: https://webaim.org/articles/screenreader_testing/

### Quick Reference for Board:
```
TEXT ELEMENTS CHECKLIST:
Headings: h1, h2, h3, h4, h5, h6
Lists: ul, ol, dl (with li, dt, dd)
Format: strong, em, mark, small, del, ins
Special: abbr, code, kbd, samp, var
Quotes: q, blockquote, cite
Position: sub, sup
Other: pre, br, hr
```

**End of Lesson 4**