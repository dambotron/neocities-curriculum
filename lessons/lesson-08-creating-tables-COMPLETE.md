# Lesson 8: Creating Tables - Organizing Data Effectively
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Create properly structured HTML tables
- Use table headers for accessibility
- Implement thead, tbody, and tfoot sections
- Span cells across columns and rows
- Add captions to tables
- Understand when to use tables (data) vs when not to (layout)
- Build responsive-friendly tables
- Create complex data tables with proper semantics

### Materials Needed
- Text editor
- Web browser with developer tools
- Sample data sets (provided)
- Projector for demonstrations
- Printed table structure diagram
- Calculator or spreadsheet with data to convert

### Key Vocabulary with Definitions
- **Table**: HTML element for displaying tabular data
- **Table Row (tr)**: Horizontal row of cells
- **Table Data (td)**: Standard cell containing data
- **Table Header (th)**: Header cell with special meaning
- **Caption**: Title/description of table
- **Thead**: Table header section
- **Tbody**: Table body section
- **Tfoot**: Table footer section
- **Colspan**: Span cell across multiple columns
- **Rowspan**: Span cell across multiple rows
- **Scope**: Defines what a header cell relates to

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding Table Structure (5 minutes)

**Teacher Script:**
"Tables are for DATA, not layout! Think of them like spreadsheets - rows and columns of related information. Let me show you how HTML tables mirror real-world data tables."
**[CREATE new file: tables-demo.html]**

**Basic Table Structure:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>HTML Tables Demo</title>
</head>
<body>
    <h1>Understanding HTML Tables</h1>
    
    <!-- SIMPLEST TABLE -->
    <h2>1. Basic Table Structure</h2>
    <table>
        <tr>
            <td>Row 1, Cell 1</td>
            <td>Row 1, Cell 2</td>
        </tr>
        <tr>
            <td>Row 2, Cell 1</td>
            <td>Row 2, Cell 2</td>
        </tr>
    </table>
```

"Let's decode this:
- `<table>` = Container for the entire table
- `<tr>` = Table Row (horizontal line of cells)
- `<td>` = Table Data (individual cell)
- Tables are built row by row, left to right
- Think of it like a grid - rows and columns!"

**Adding Headers and Meaning:**
```html
    <!-- TABLE WITH HEADERS -->
    <h2>2. Table with Headers</h2>
    <table>
        <tr>
            <th>Name</th>
            <th>Age</th>
            <th>City</th>
        </tr>
        <tr>
            <td>Alice Johnson</td>
            <td>16</td>            <td>New York</td>
        </tr>
        <tr>
            <td>Bob Smith</td>
            <td>17</td>
            <td>Los Angeles</td>
        </tr>
    </table>
```

"Key points about headers:
- `<th>` = Table Header (bold and centered by default)
- Headers help screen readers understand data
- Can be in rows OR columns
- Always use th for headers, not just bold text!"

### Complete Table Structure (10 minutes)

**[ADD comprehensive table example]**

```html
    <!-- COMPLETE TABLE STRUCTURE -->
    <h2>3. Professional Table with All Sections</h2>
    <table>
        <caption>Student Grade Report - Fall 2024</caption>
        
        <thead>
            <tr>
                <th scope="col">Student</th>
                <th scope="col">Math</th>
                <th scope="col">Science</th>
                <th scope="col">English</th>
                <th scope="col">Average</th>
            </tr>
        </thead>
        
        <tbody>
            <tr>
                <th scope="row">Sarah Chen</th>
                <td>95</td>
                <td>88</td>
                <td>92</td>
                <td>91.7</td>
            </tr>
            <tr>                <th scope="row">Mike Johnson</th>
                <td>87</td>
                <td>91</td>
                <td>85</td>
                <td>87.7</td>
            </tr>
            <tr>
                <th scope="row">Emma Davis</th>
                <td>92</td>
                <td>96</td>
                <td>89</td>
                <td>92.3</td>
            </tr>
        </tbody>
        
        <tfoot>
            <tr>
                <th scope="row">Class Average</th>
                <td>91.3</td>
                <td>91.7</td>
                <td>88.7</td>
                <td>90.6</td>
            </tr>
        </tfoot>
    </table>
```

"Professional table structure:
- `<caption>` = Table title (always first inside table)
- `<thead>` = Header section (column labels)
- `<tbody>` = Main data section
- `<tfoot>` = Footer section (summaries/totals)
- `scope` attribute = Tells screen readers what headers apply to"

**Advanced Features - Spanning Cells:**
```html
    <!-- COLSPAN AND ROWSPAN -->
    <h2>4. Spanning Cells</h2>
    <table>
        <caption>Class Schedule</caption>
        <thead>
            <tr>
                <th>Time</th>                <th>Monday</th>
                <th>Tuesday</th>
                <th>Wednesday</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th>9:00 AM</th>
                <td>Math</td>
                <td colspan="2">Double Period: Science Lab</td>
            </tr>
            <tr>
                <th>10:00 AM</th>
                <td>English</td>
                <td rowspan="2">PE<br>(2 hours)</td>
                <td>History</td>
            </tr>
            <tr>
                <th>11:00 AM</th>
                <td>Art</td>
                <td>Music</td>
            </tr>
            <tr>
                <th>12:00 PM</th>
                <td colspan="3">Lunch Break</td>
            </tr>
        </tbody>
    </table>
```

"Spanning cells:
- `colspan='2'` = Cell spans 2 columns horizontally
- `rowspan='2'` = Cell spans 2 rows vertically
- Count carefully! Spanned cells affect other rows
- Use for merged cells like 'Lunch Break' across all periods"

**When NOT to Use Tables:**
```html
    <!-- BAD: Layout table (DON'T DO THIS!) -->
    <h2>5. DON'T Use Tables for Layout!</h2>
    <!-- This is WRONG -->
    <!--
    <table>
        <tr>            <td>Navigation</td>
            <td>Main Content</td>
            <td>Sidebar</td>
        </tr>
    </table>
    -->
    <p>Tables are for DATA, not page layout! Use CSS for layout instead.</p>
</body>
</html>
```

---

## PART 2: WE DO (Guided Practice) - 20 minutes

### Building a Grade Book Table Together (10 minutes)

**Teacher Script:**
"Let's build a real grade book table that a teacher might use. This will include all the features we learned!"

**Step 1: Plan the Table Structure**
"First, let's plan what we need:
- Student names (row headers)
- Assignment names (column headers)  
- Grades (data cells)
- Averages (footer)
- A title (caption)

CHECKPOINT: Everyone sketch this table on paper first!"

**Step 2: Build the Complete Table**

"Create `gradebook.html` and follow along:"

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Class Gradebook | Web Development</title>
    <style>
        /* We'll add CSS next week - this just makes it easier to see */
        table { border-collapse: collapse; width: 100%; }
        th, td { border: 1px solid #ddd; padding: 8px; text-align: left; }
        th { background-color: #f2f2f2; }
        caption { font-weight: bold; margin-bottom: 10px; }    </style>
</head>
<body>
    <h1>Web Development Class - Grade Tracker</h1>
    
    <table>
        <caption>
            Grade Report - First Quarter 2024
            <br>
            <small>All grades out of 100 points</small>
        </caption>
        
        <thead>
            <tr>
                <th scope="col">Student Name</th>
                <th scope="col">HTML Project</th>
                <th scope="col">CSS Project</th>
                <th scope="col">Midterm Exam</th>
                <th scope="col">Participation</th>
                <th scope="col">Average</th>
                <th scope="col">Letter Grade</th>
            </tr>
        </thead>
        
        <tbody>
            <tr>
                <th scope="row">Anderson, Amy</th>
                <td>95</td>
                <td>88</td>
                <td>92</td>
                <td>100</td>
                <td>93.75</td>
                <td>A</td>
            </tr>
            <tr>
                <th scope="row">Brown, Brian</th>
                <td>82</td>
                <td>79</td>
                <td>85</td>
                <td>90</td>
                <td>84.00</td>
                <td>B</td>
            </tr>            <tr>
                <th scope="row">Chen, Charlie</th>
                <td>91</td>
                <td>94</td>
                <td>88</td>
                <td>95</td>
                <td>92.00</td>
                <td>A</td>
            </tr>
            <tr>
                <th scope="row">Davis, Diana</th>
                <td>78</td>
                <td>85</td>
                <td>81</td>
                <td>85</td>
                <td>82.25</td>
                <td>B</td>
            </tr>
            <tr>
                <th scope="row">Evans, Eric</th>
                <td>88</td>
                <td>91</td>
                <td>79</td>
                <td>100</td>
                <td>89.50</td>
                <td>B+</td>
            </tr>
        </tbody>
        
        <tfoot>
            <tr>
                <th scope="row">Class Average</th>
                <td>86.8</td>
                <td>87.4</td>
                <td>85.0</td>
                <td>94.0</td>
                <td><strong>88.3</strong></td>
                <td><strong>B+</strong></td>
            </tr>
        </tfoot>
    </table>```

"Key teaching points:
- Headers in BOTH first column AND first row
- Use scope='col' for column headers
- Use scope='row' for row headers
- Footer shows summary data
- Caption describes the table"

### Creating a Complex Schedule Table (10 minutes)

"Now let's create a more complex table with merged cells for a weekly schedule:"

```html
    <h2>Weekly Course Schedule</h2>
    
    <table>
        <caption>
            Spring 2024 Class Schedule
            <br>
            <small>Room numbers in parentheses</small>
        </caption>
        
        <thead>
            <tr>
                <th scope="col">Time</th>
                <th scope="col">Monday</th>
                <th scope="col">Tuesday</th>
                <th scope="col">Wednesday</th>
                <th scope="col">Thursday</th>
                <th scope="col">Friday</th>
            </tr>
        </thead>
        
        <tbody>
            <!-- 8:00 AM -->
            <tr>
                <th scope="row">8:00 - 9:00</th>
                <td>Math (201)</td>
                <td>Math (201)</td>
                <td>Math (201)</td>
                <td>Math (201)</td>
                <td>Math (201)</td>
            </tr>            
            <!-- 9:00 AM -->
            <tr>
                <th scope="row">9:00 - 10:00</th>
                <td>English (105)</td>
                <td colspan="2">Double Period: Science Lab (Lab 3)</td>
                <td>English (105)</td>
                <td>English (105)</td>
            </tr>
            
            <!-- 10:00 AM -->
            <tr>
                <th scope="row">10:00 - 11:00</th>
                <td>History (302)</td>
                <!-- Tuesday cell is merged from above -->
                <td>History (302)</td>
                <td>History (302)</td>
                <td rowspan="2">PE<br>(Gym)</td>
            </tr>
            
            <!-- 11:00 AM -->
            <tr>
                <th scope="row">11:00 - 12:00</th>
                <td>Web Dev (Lab 1)</td>
                <td>Art (Studio)</td>
                <td>Web Dev (Lab 1)</td>
                <td>Music (Aud)</td>
                <!-- Friday cell is merged from above -->
            </tr>
            
            <!-- Lunch -->
            <tr>
                <th scope="row">12:00 - 1:00</th>
                <td colspan="5" style="text-align: center;">
                    Lunch Break (Cafeteria)
                </td>
            </tr>
            
            <!-- Afternoon -->
            <tr>
                <th scope="row">1:00 - 2:00</th>
                <td>Spanish (204)</td>                <td>Library Study</td>
                <td>Spanish (204)</td>
                <td>Spanish (204)</td>
                <td>Free Period</td>
            </tr>
            
            <!-- 2:00 PM -->
            <tr>
                <th scope="row">2:00 - 3:00</th>
                <td colspan="2">Club Meeting (Various)</td>
                <td>Study Hall (Library)</td>
                <td colspan="2">Early Release</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

**Teacher Script:**
"Notice the complexity:
- Colspan for double periods and lunch
- Rowspan for 2-hour PE class
- Empty cells where spans continue
- Careful counting of cells per row
- Every row still has same total columns!"

---

## PART 3: YOU DO (Independent Practice) - 10 minutes

### Student Activity: Create a Sports Statistics Table

**Instructions:**
"Create a comprehensive sports statistics table for your favorite sport or activity. Use ALL the table features we learned!"

**Required Tasks:**
1. ✅ Create `sports-stats.html` with proper HTML5 structure
2. ✅ Include a descriptive `<caption>` for the table
3. ✅ Use `<thead>`, `<tbody>`, and `<tfoot>` sections
4. ✅ Include both row and column headers with scope attributes
5. ✅ Use at least one `colspan` for merged cells
6. ✅ Use at least one `rowspan` for merged cells
7. ✅ Include summary data in the footer
8. ✅ Have at least 5 data rows and 5 columns
9. ✅ Make headers meaningful and descriptive
10. ✅ Include proper semantic HTML structure around the table
**Bonus Challenges:**
- Add multiple tables for different statistics
- Create a tournament bracket using tables
- Include abbreviations with `<abbr>` tags in headers
- Add a legend explaining abbreviations
- Style alternating rows (preview of CSS)

### Complete Solution Example:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Basketball team statistics for Lincoln High School">
    <title>Basketball Team Stats | Lincoln High Eagles</title>
    <style>
        table { border-collapse: collapse; width: 100%; margin: 20px 0; }
        th, td { border: 1px solid #333; padding: 10px; text-align: center; }
        th { background-color: #4CAF50; color: white; }
        tbody tr:nth-child(even) { background-color: #f2f2f2; }
        caption { font-size: 1.2em; margin-bottom: 10px; font-weight: bold; }
        .text-left { text-align: left; }
    </style>
</head>
<body>
    <header>
        <h1>Lincoln High Eagles - Basketball Statistics</h1>
        <p>2023-2024 Season Performance</p>
    </header>
    
    <main>
        <section>
            <h2>Player Statistics</h2>
            
            <table>
                <caption>
                    Season Statistics - Varsity Team
                    <br>
                    <small>Through 20 games (15-5 record)</small>                </caption>
                
                <thead>
                    <tr>
                        <th rowspan="2" scope="col">Player</th>
                        <th rowspan="2" scope="col">Position</th>
                        <th rowspan="2" scope="col">Games<br>Played</th>
                        <th colspan="3" scope="colgroup">Scoring</th>
                        <th colspan="3" scope="colgroup">Other Stats</th>
                    </tr>
                    <tr>
                        <th scope="col"><abbr title="Points Per Game">PPG</abbr></th>
                        <th scope="col"><abbr title="Field Goal Percentage">FG%</abbr></th>
                        <th scope="col"><abbr title="Free Throw Percentage">FT%</abbr></th>
                        <th scope="col"><abbr title="Rebounds Per Game">RPG</abbr></th>
                        <th scope="col"><abbr title="Assists Per Game">APG</abbr></th>
                        <th scope="col"><abbr title="Steals Per Game">SPG</abbr></th>
                    </tr>
                </thead>
                
                <tbody>
                    <tr>
                        <th scope="row" class="text-left">#23 Johnson, Mike</th>
                        <td>Guard</td>
                        <td>20</td>
                        <td>18.5</td>
                        <td>45.2%</td>
                        <td>82.0%</td>
                        <td>4.2</td>
                        <td>6.8</td>
                        <td>2.1</td>
                    </tr>
                    <tr>
                        <th scope="row" class="text-left">#15 Williams, David</th>
                        <td>Forward</td>
                        <td>19</td>                        <td>15.3</td>
                        <td>52.1%</td>
                        <td>75.5%</td>
                        <td>8.5</td>
                        <td>3.2</td>
                        <td>1.5</td>
                    </tr>
                    <tr>
                        <th scope="row" class="text-left">#32 Thompson, James</th>
                        <td>Center</td>
                        <td>20</td>
                        <td>12.8</td>
                        <td>58.3%</td>
                        <td>68.0%</td>
                        <td>10.2</td>
                        <td>2.1</td>
                        <td>0.8</td>
                    </tr>
                    <tr>
                        <th scope="row" class="text-left">#11 Garcia, Carlos</th>
                        <td>Guard</td>
                        <td>18</td>
                        <td>10.5</td>
                        <td>41.0%</td>
                        <td>78.2%</td>
                        <td>3.5</td>
                        <td>5.2</td>
                        <td>1.9</td>
                    </tr>
                    <tr>
                        <th scope="row" class="text-left">#24 Lee, Kevin</th>
                        <td>Forward</td>
                        <td>20</td>
                        <td>8.2</td>
                        <td>48.5%</td>
                        <td>70.0%</td>
                        <td>6.8</td>                        <td>2.5</td>
                        <td>1.2</td>
                    </tr>
                </tbody>
                
                <tfoot>
                    <tr>
                        <th scope="row" colspan="2">Team Averages</th>
                        <td>—</td>
                        <td><strong>65.3</strong></td>
                        <td><strong>48.8%</strong></td>
                        <td><strong>74.7%</strong></td>
                        <td><strong>33.2</strong></td>
                        <td><strong>19.8</strong></td>
                        <td><strong>7.5</strong></td>
                    </tr>
                    <tr>
                        <th scope="row" colspan="2">Opponent Averages</th>
                        <td>—</td>
                        <td>58.1</td>
                        <td>42.3%</td>
                        <td>69.2%</td>
                        <td>30.5</td>
                        <td>15.2</td>
                        <td>5.8</td>
                    </tr>
                </tfoot>
            </table>
        </section>
        
        <section>
            <h2>Game Schedule</h2>
            
            <table>
                <caption>Upcoming Games - February 2024</caption>
                
                <thead>
                    <tr>
                        <th scope="col">Date</th>
                        <th scope="col">Opponent</th>                        <th scope="col">Location</th>
                        <th scope="col">Time</th>
                    </tr>
                </thead>
                
                <tbody>
                    <tr>
                        <th scope="row">Feb 2</th>
                        <td>Washington High</td>
                        <td>Home</td>
                        <td>7:00 PM</td>
                    </tr>
                    <tr>
                        <th scope="row">Feb 5</th>
                        <td>Jefferson Academy</td>
                        <td>Away</td>
                        <td>6:30 PM</td>
                    </tr>
                    <tr>
                        <th scope="row">Feb 9-10</th>
                        <td colspan="2">Regional Tournament</td>
                        <td>TBA</td>
                    </tr>
                </tbody>
            </table>
        </section>
        
        <aside>
            <h3>Legend</h3>
            <dl>
                <dt>PPG</dt><dd>Points Per Game</dd>
                <dt>FG%</dt><dd>Field Goal Percentage</dd>
                <dt>FT%</dt><dd>Free Throw Percentage</dd>
                <dt>RPG</dt><dd>Rebounds Per Game</dd>
                <dt>APG</dt><dd>Assists Per Game</dd>
                <dt>SPG</dt><dd>Steals Per Game</dd>
            </dl>
        </aside>
    </main>
    
    <footer>        <p><small>Statistics updated after each game. Last update: January 25, 2024</small></p>
    </footer>
</body>
</html>
```

---

## Assessment & Closing (5 minutes)

### Exit Ticket Questions

1. **What HTML element creates a table row?**
   - Answer: `<tr>` (table row)

2. **What's the difference between `<th>` and `<td>`?**
   - Answer: `<th>` is for header cells (bold, centered by default), `<td>` is for regular data cells.

3. **Write the HTML to make a cell span 3 columns:**
   - Answer: `<td colspan="3">Content</td>`

4. **Which section contains summary data like totals or averages?**
   - Answer: `<tfoot>` (table footer)

5. **Why should you use scope attributes on header cells?**
   - Answer: They help screen readers understand which data cells each header describes, improving accessibility.

### Success Criteria Checklist
- [ ] Created valid table structure (2 pts)
- [ ] Used caption for table description (2 pts)
- [ ] Included thead, tbody, tfoot sections (3 pts)
- [ ] Used th for all headers with scope (3 pts)
- [ ] Successfully used colspan (2 pts)
- [ ] Successfully used rowspan (2 pts)
- [ ] Table displays data logically (3 pts)
- [ ] Included footer with summary data (3 pts)
**Total: ___/20 points**

### Homework Assignment

**Create a "Comparison Table" (`comparison-table.html`):**

Requirements:
1. Compare at least 5 items (products, schools, movies, games, etc.)
2. Include at least 6 comparison criteria
3. Use a descriptive caption with subtitle4. Use thead with column headers and scope attributes
5. Use tbody for data rows
6. Include a "Winner" or "Best Choice" row in tfoot
7. Use at least one colspan for grouped headers
8. Use at least one rowspan for categories
9. Include both text and numeric data
10. Add a legend or notes section explaining criteria

**Homework Solution Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smartphone Comparison Table</title>
    <style>
        table { border-collapse: collapse; width: 100%; }
        th, td { border: 1px solid #ccc; padding: 10px; }
        th { background-color: #333; color: white; }
        .category { background-color: #f0f0f0; font-weight: bold; }
        .winner { background-color: #90EE90; }
    </style>
</head>
<body>
    <h1>Smartphone Comparison Guide</h1>
    
    <table>
        <caption>
            2024 Flagship Smartphone Comparison
            <br>
            <small>Prices as of January 2024</small>
        </caption>
        
        <thead>
            <tr>
                <th rowspan="2" scope="col">Feature</th>
                <th colspan="5" scope="colgroup">Smartphone Models</th>
            </tr>
            <tr>
                <th scope="col">iPhone 15 Pro</th>
                <th scope="col">Samsung S24 Ultra</th>                <th scope="col">Google Pixel 8 Pro</th>
                <th scope="col">OnePlus 12</th>
                <th scope="col">Xiaomi 14 Pro</th>
            </tr>
        </thead>
        
        <tbody>
            <!-- Specs Category -->
            <tr>
                <th scope="row" class="category" rowspan="3">Display</th>
                <td>6.1" OLED</td>
                <td>6.8" AMOLED</td>
                <td>6.7" OLED</td>
                <td>6.7" AMOLED</td>
                <td>6.73" AMOLED</td>
            </tr>
            <tr>
                <td>120Hz ProMotion</td>
                <td>120Hz Adaptive</td>
                <td>120Hz LTPO</td>
                <td>120Hz LTPO</td>
                <td>120Hz LTPO</td>
            </tr>
            <tr>
                <td>2532 x 1170</td>
                <td>3088 x 1440</td>
                <td>2992 x 1344</td>
                <td>3168 x 1440</td>
                <td>3200 x 1440</td>
            </tr>
            
            <!-- Performance -->
            <tr>
                <th scope="row" class="category" rowspan="2">Performance</th>
                <td>A17 Pro</td>
                <td>Snapdragon 8 Gen 3</td>
                <td>Tensor G3</td>
                <td>Snapdragon 8 Gen 3</td>
                <td>Snapdragon 8 Gen 3</td>
            </tr>
            <tr>                <td>8GB RAM</td>
                <td>12GB RAM</td>
                <td>12GB RAM</td>
                <td>16GB RAM</td>
                <td>12GB RAM</td>
            </tr>
            
            <!-- Price -->
            <tr>
                <th scope="row">Starting Price</th>
                <td>$999</td>
                <td>$1,299</td>
                <td>$999</td>
                <td>$799</td>
                <td>$899</td>
            </tr>
            
            <!-- Battery -->
            <tr>
                <th scope="row">Battery</th>
                <td>3,274 mAh</td>
                <td>5,000 mAh</td>
                <td>5,050 mAh</td>
                <td>5,400 mAh</td>
                <td>4,880 mAh</td>
            </tr>
            
            <!-- Camera -->
            <tr>
                <th scope="row">Main Camera</th>
                <td>48MP</td>
                <td>200MP</td>
                <td>50MP</td>
                <td>50MP</td>
                <td>50MP</td>
            </tr>
        </tbody>
        
        <tfoot>
            <tr class="winner">
                <th scope="row">Best Overall</th>
                <td colspan="5" style="text-align: center;">                    <strong>Samsung S24 Ultra</strong> - Best display and camera system
                </td>
            </tr>
            <tr class="winner">
                <th scope="row">Best Value</th>
                <td colspan="5" style="text-align: center;">
                    <strong>OnePlus 12</strong> - Great specs at lower price
                </td>
            </tr>
        </tfoot>
    </table>
    
    <section>
        <h2>Notes</h2>
        <ul>
            <li>Prices shown are for base storage models</li>
            <li>All phones support 5G connectivity</li>
            <li>Battery life varies based on usage</li>
            <li>Camera quality is subjective - megapixels aren't everything</li>
        </ul>
    </section>
</body>
</html>
```

---

## Teacher Notes & Tips

### Common Student Errors:
1. **Forgetting to close table tags** - Missing `</table>` breaks page layout
2. **Incorrect cell counting** - Colspan/rowspan throws off row alignment
3. **Using tables for layout** - Emphasize tables are ONLY for data
4. **Missing scope attributes** - Important for accessibility
5. **Wrong section order** - thead, tbody, tfoot must be in that order
6. **Forgetting caption goes first** - Must be first child of table
7. **Mixing th and td incorrectly** - Headers need th tags
8. **Not accounting for merged cells** - Each row needs same column count

### Differentiation Strategies:

**For Struggling Students:**
- Start with simple 3x3 tables
- Provide grid paper to plan tables first
- Give pre-made table structure to fill in- Color-code headers vs data cells
- Focus on structure before complex features

**For Advanced Students:**
- Create nested tables (table within a cell)
- Build a calendar using tables
- Add sorting indicators to headers
- Create a responsive table design
- Research data-* attributes for sorting

### Time Management:
- 0-5 min: Review homework and warm-up
- 5-15 min: I DO basic and complex table demos
- 15-25 min: WE DO gradebook table
- 25-35 min: WE DO schedule with spans
- 35-45 min: YOU DO sports statistics
- 45-50 min: Assessment and homework

### Key Teaching Points:
- **Tables = Tabular Data** (not layout!)
- **Accessibility matters** - Use th, scope, caption
- **Structure before style** - Get HTML right first
- **Plan before coding** - Sketch table on paper
- **Count cells carefully** - Spans affect totals
- **Semantic HTML** - Use proper sections

### Real-World Applications:
- **Spreadsheet exports** - Excel to HTML
- **Financial reports** - Stock tables, budgets
- **Sports statistics** - League standings
- **Product comparisons** - E-commerce sites
- **Scientific data** - Research findings
- **Schedules** - Class timetables, TV guides

### Accessibility Best Practices:
1. **Always use `<th>` for headers** - Never just bold `<td>`
2. **Include scope attributes** - Help screen readers
3. **Add captions** - Describe table purpose
4. **Keep tables simple** - Avoid excessive nesting
5. **Consider mobile users** - Tables are hard on small screens
6. **Use abbr for abbreviations** - Explain shortened terms
### Extension Activities:
1. Create a multiplication table (1-12)
2. Build a periodic table section
3. Design a tournament bracket
4. Make a bus/train schedule
5. Create a menu with prices
6. Build a grade calculator table

### CSS Preview (Next Week):
```css
/* Basic table styling preview */
table {
    border-collapse: collapse;
    width: 100%;
}
th, td {
    border: 1px solid #ddd;
    padding: 8px;
}
th {
    background-color: #4CAF50;
    color: white;
}
tr:nth-child(even) {
    background-color: #f2f2f2;
}
```

### Assessment Rubric:

| Criteria | Excellent (3) | Good (2) | Needs Work (1) | Missing (0) |
|----------|--------------|-----------|----------------|-------------|
| Structure | All sections present | Most sections | Basic table only | Invalid structure |
| Headers | th with scope | th tags used | Some headers | No headers |
| Spanning | Multiple spans correct | One span works | Attempted | None |
| Accessibility | Caption, scope, structure | Some features | Minimal | None |

### Resources:
- MDN Tables Guide: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table
- WebAIM Tables: https://webaim.org/articles/creating/tables
- Table Generator: https://www.tablesgenerator.com/html_tables
- Responsive Tables: https://css-tricks.com/responsive-data-tables/
### Quick Reference for Board:
```
TABLE STRUCTURE:
<table>
    <caption>Title</caption>
    <thead>
        <tr>
            <th>Header</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Data</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>Footer</td>
        </tr>
    </tfoot>
</table>

SPANNING:
colspan="2" - Span 2 columns
rowspan="3" - Span 3 rows

ACCESSIBILITY:
scope="col" - Column header
scope="row" - Row header
scope="colgroup" - Group header
```

### Troubleshooting Guide:
- **Table looks broken**: Check all tags are closed
- **Cells misaligned**: Count cells including spans
- **Headers not bold**: Use `<th>` not `<td>`
- **Caption in wrong place**: Must be first inside table
- **Rowspan not working**: Check cell placement in next rows
- **Table too wide**: Will need CSS to control (next week)
- **Not accessible**: Add scope attributes to headers

### When to Use Tables:
✅ **DO use tables for:**
- Numerical data
- Comparisons
- Schedules
- Statistics
- Prices/menus
- Scientific data

❌ **DON'T use tables for:**
- Page layout
- Navigation menus
- Image galleries
- Forms
- General content arrangement

### Sample Data Sets for Practice:
1. Class grades/scores
2. Sports team statistics
3. Weather data for a week
4. Product price comparisons
5. TV/movie schedules
6. Nutrition information
7. Budget/expense tracking
8. Video game high scores

**End of Lesson 8**