# CSS Quick Reference Sheet

## Adding CSS to HTML

### 1. Inline CSS (in HTML tag)
```html
<p style="color: blue; font-size: 16px;">Blue text</p>
```

### 2. Internal CSS (in head section)
```html
<head>
    <style>
        p { color: blue; }
        h1 { font-size: 32px; }
    </style>
</head>
```

### 3. External CSS (separate file)
```html
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```

## CSS Syntax
```css
selector {
    property: value;
    property: value;
}
```

## Common Selectors
```css
/* Element selector */
p { }

/* Class selector */
.classname { }

/* ID selector */
#idname { }

/* Multiple selectors */
h1, h2, h3 { }
```
## Text Properties
```css
color: red;                    /* Text color */
font-family: Arial, sans-serif;/* Font */
font-size: 16px;              /* Size */
font-weight: bold;            /* Bold */
font-style: italic;           /* Italic */
text-align: center;           /* Alignment */
text-decoration: underline;   /* Underline */
line-height: 1.5;            /* Line spacing */
```

## Colors
```css
/* Named colors */
color: red;
background-color: lightblue;

/* Hex colors */
color: #FF0000;
background-color: #F0F0F0;

/* RGB colors */
color: rgb(255, 0, 0);
background-color: rgba(0, 0, 0, 0.5);
```

## Box Model Properties
```css
/* Margin (outside space) */
margin: 10px;                 /* All sides */
margin-top: 10px;
margin-right: 20px;
margin-bottom: 10px;
margin-left: 20px;

/* Padding (inside space) */
padding: 10px;                /* All sides */
padding: 10px 20px;          /* Top/bottom, left/right */

/* Border */
border: 1px solid black;
border-radius: 5px;          /* Rounded corners */
```
## Size Properties
```css
width: 300px;                /* Fixed width */
width: 50%;                  /* Percentage width */
max-width: 800px;           /* Maximum width */
min-width: 200px;           /* Minimum width */
height: 200px;              /* Fixed height */
```

## Display & Layout
```css
display: block;              /* Block element */
display: inline;             /* Inline element */
display: inline-block;       /* Inline-block */
display: none;              /* Hidden */
display: flex;              /* Flexbox container */
```

## Flexbox Properties
```css
/* Container */
display: flex;
flex-direction: row;         /* or column */
justify-content: center;     /* Horizontal alignment */
align-items: center;        /* Vertical alignment */
gap: 10px;                  /* Space between items */

/* Items */
flex: 1;                    /* Grow to fill space */
```

## Background Properties
```css
background-color: #f0f0f0;
background-image: url('image.jpg');
background-size: cover;
background-position: center;
background-repeat: no-repeat;
```

## Common Combinations
```css
/* Centered content box */
.box {
    width: 80%;
    margin: 0 auto;
    padding: 20px;
    background-color: white;
    border: 1px solid #ccc;
}

/* Button style */
.button {
    display: inline-block;
    padding: 10px 20px;
    background-color: blue;
    color: white;
    text-decoration: none;
    border-radius: 5px;
}
```