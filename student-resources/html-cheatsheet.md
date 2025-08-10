# HTML Quick Reference Sheet

## Basic HTML Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
</head>
<body>
    <!-- Content goes here -->
</body>
</html>
```

## Common HTML Tags

### Text Elements
- `<h1>` to `<h6>` - Headings (h1 is largest)
- `<p>` - Paragraph
- `<strong>` - Bold text (important)
- `<em>` - Italic text (emphasis)
- `<br>` - Line break
- `<hr>` - Horizontal rule (line)

### Lists
```html
<!-- Unordered List -->
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
</ul>

<!-- Ordered List -->
<ol>
    <li>First item</li>
    <li>Second item</li>
</ol>
```
### Links
```html
<!-- Link to another page -->
<a href="about.html">About Me</a>

<!-- Link to external website -->
<a href="https://www.example.com">Visit Example</a>

<!-- Link to email -->
<a href="mailto:someone@example.com">Email Me</a>
```

### Images
```html
<!-- Basic image -->
<img src="picture.jpg" alt="Description of image">

<!-- Image with size -->
<img src="photo.png" alt="My photo" width="300" height="200">
```

### Tables
```html
<table>
    <tr>
        <th>Header 1</th>
        <th>Header 2</th>
    </tr>
    <tr>
        <td>Data 1</td>
        <td>Data 2</td>
    </tr>
</table>
```

### Forms
```html
<form>
    <label for="name">Name:</label>
    <input type="text" id="name" name="name">
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email">
    
    <input type="submit" value="Submit">
</form>
```