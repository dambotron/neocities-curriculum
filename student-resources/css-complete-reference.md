# Complete CSS Properties Reference
## Essential CSS Properties for Web Development

### Table of Contents
1. [Text & Typography](#text--typography)
2. [Colors & Backgrounds](#colors--backgrounds)
3. [Box Model](#box-model)
4. [Display & Positioning](#display--positioning)
5. [Flexbox](#flexbox)
6. [CSS Grid](#css-grid)
7. [Transforms](#transforms)
8. [Transitions & Animations](#transitions--animations)
9. [Responsive Design](#responsive-design)
10. [Advanced Properties](#advanced-properties)

---

## Text & Typography

### Font Properties
```css
/* Font Family */
font-family: 'Helvetica', Arial, sans-serif;
font-family: 'Georgia', serif;
font-family: 'Courier New', monospace;
font-family: system-ui, -apple-system, sans-serif; /* System fonts */

/* Font Size */
font-size: 16px;              /* Pixels */
font-size: 1.5rem;            /* Relative to root */
font-size: 1.2em;             /* Relative to parent */
font-size: 120%;              /* Percentage */
font-size: clamp(1rem, 2vw, 1.5rem); /* Responsive */

/* Font Weight */
font-weight: normal;          /* 400 */
font-weight: bold;            /* 700 */
font-weight: 100;             /* Thin */
font-weight: 300;             /* Light */
font-weight: 500;             /* Medium */
font-weight: 900;             /* Black */

/* Font Style */
font-style: normal;
font-style: italic;
font-style: oblique;

/* Font Variant */
font-variant: small-caps;
font-variant: normal;

/* Line Height */
line-height: 1.5;             /* Multiplier */
line-height: 24px;            /* Fixed */
line-height: 150%;            /* Percentage */

/* Letter Spacing */
letter-spacing: 0.05em;
letter-spacing: 2px;
letter-spacing: -1px;

/* Word Spacing */
word-spacing: 0.25em;
word-spacing: 5px;

/* Text Transform */
text-transform: uppercase;
text-transform: lowercase;
text-transform: capitalize;
text-transform: none;

/* Text Decoration */
text-decoration: none;
text-decoration: underline;
text-decoration: overline;
text-decoration: line-through;
text-decoration: underline dotted red;

/* Text Align */
text-align: left;
text-align: right;
text-align: center;
text-align: justify;

/* Text Indent */
text-indent: 2em;
text-indent: 50px;
text-indent: -1em;            /* Hanging indent */

/* Text Shadow */
text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
text-shadow: 0 0 10px #ff0000;

/* Text Overflow */
text-overflow: ellipsis;
text-overflow: clip;

/* White Space */
white-space: normal;
white-space: nowrap;
white-space: pre;
white-space: pre-wrap;
white-space: pre-line;

/* Word Break */
word-break: normal;
word-break: break-all;
word-break: keep-all;
word-wrap: break-word;        /* Legacy */
overflow-wrap: break-word;    /* Modern */

/* Font Shorthand */
font: italic bold 16px/1.5 Arial, sans-serif;
/* style weight size/line-height family */
```

---

## Colors & Backgrounds

### Color Values
```css
/* Color Formats */
color: red;                   /* Named color */
color: #ff0000;              /* Hex */
color: #f00;                 /* Hex shorthand */
color: rgb(255, 0, 0);        /* RGB */
color: rgba(255, 0, 0, 0.5);  /* RGBA with alpha */
color: hsl(0, 100%, 50%);     /* HSL */
color: hsla(0, 100%, 50%, 0.5); /* HSLA */
color: transparent;           /* Transparent */
color: currentColor;          /* Inherit from color property */

/* Background Color */
background-color: #ffffff;
background-color: rgba(0, 0, 0, 0.8);
background-color: transparent;

/* Background Image */
background-image: url('image.jpg');
background-image: url('data:image/png;base64,...');
background-image: linear-gradient(to right, #ff0000, #00ff00);
background-image: radial-gradient(circle, #ff0000, #00ff00);
background-image: conic-gradient(from 45deg, #ff0000, #00ff00);

/* Background Position */
background-position: center;
background-position: top left;
background-position: 50% 50%;
background-position: 10px 20px;

/* Background Size */
background-size: cover;       /* Cover entire container */
background-size: contain;     /* Fit within container */
background-size: 100% 100%;   /* Stretch to fill */
background-size: 200px 100px; /* Specific size */
background-size: auto;        /* Original size */

/* Background Repeat */
background-repeat: repeat;    /* Default */
background-repeat: no-repeat;
background-repeat: repeat-x;
background-repeat: repeat-y;
background-repeat: space;
background-repeat: round;

/* Background Attachment */
background-attachment: scroll; /* Default */
background-attachment: fixed;  /* Parallax effect */
background-attachment: local;

/* Background Origin */
background-origin: padding-box; /* Default */
background-origin: border-box;
background-origin: content-box;

/* Background Clip */
background-clip: border-box;  /* Default */
background-clip: padding-box;
background-clip: content-box;
background-clip: text;        /* Webkit prefix needed */

/* Background Shorthand */
background: #fff url('bg.jpg') no-repeat center/cover fixed;
/* color image repeat position/size attachment */

/* Multiple Backgrounds */
background-image: url('top.png'), url('bottom.png');
background-position: top, bottom;
background-repeat: no-repeat, repeat;

/* Gradients */
background: linear-gradient(90deg, #ff0000 0%, #00ff00 100%);
background: linear-gradient(to bottom right, #ff0000, #00ff00);
background: radial-gradient(circle at center, #ff0000, #00ff00);
background: conic-gradient(from 0deg, #ff0000, #00ff00, #0000ff);
background: repeating-linear-gradient(45deg, #ff0000 0px, #00ff00 10px);
```

---

## Box Model

### Dimensions
```css
/* Width */
width: 300px;                /* Fixed */
width: 50%;                  /* Percentage */
width: 100vw;                /* Viewport width */
width: auto;                 /* Default */
width: fit-content;          /* Shrink to content */
width: max-content;          /* No wrapping */
width: min-content;          /* Minimum content */

/* Height */
height: 200px;
height: 100vh;               /* Viewport height */
height: auto;
height: 100%;

/* Min/Max Dimensions */
min-width: 200px;
max-width: 1200px;
min-height: 100px;
max-height: 500px;

/* Aspect Ratio */
aspect-ratio: 16 / 9;
aspect-ratio: 1;             /* Square */
```

### Margin
```css
/* Individual Sides */
margin-top: 20px;
margin-right: 10px;
margin-bottom: 20px;
margin-left: 10px;

/* Shorthand */
margin: 20px;                /* All sides */
margin: 20px 10px;           /* Vertical | Horizontal */
margin: 20px 10px 30px;      /* Top | Horizontal | Bottom */
margin: 10px 20px 30px 40px; /* Top | Right | Bottom | Left */

/* Special Values */
margin: auto;                /* Center horizontally */
margin: 0 auto;              /* Center block element */
margin: -10px;               /* Negative margin */
```

### Padding
```css
/* Individual Sides */
padding-top: 20px;
padding-right: 10px;
padding-bottom: 20px;
padding-left: 10px;

/* Shorthand */
padding: 20px;               /* All sides */
padding: 20px 10px;          /* Vertical | Horizontal */
padding: 20px 10px 30px;     /* Top | Horizontal | Bottom */
padding: 10px 20px 30px 40px; /* Top | Right | Bottom | Left */
```

### Border
```css
/* Border Width */
border-width: 1px;
border-width: thin medium thick;
border-top-width: 2px;

/* Border Style */
border-style: solid;
border-style: dashed;
border-style: dotted;
border-style: double;
border-style: groove;
border-style: ridge;
border-style: inset;
border-style: outset;
border-style: none;
border-style: hidden;

/* Border Color */
border-color: #000000;
border-color: red green blue yellow; /* TRBL */

/* Individual Borders */
border-top: 1px solid black;
border-right: 2px dashed red;
border-bottom: 3px dotted blue;
border-left: 4px double green;

/* Border Radius */
border-radius: 10px;         /* All corners */
border-radius: 10px 20px;    /* Top-left/bottom-right | Top-right/bottom-left */
border-radius: 10px 20px 30px 40px; /* TL | TR | BR | BL */
border-radius: 50%;          /* Circle */
border-top-left-radius: 10px;
border-top-right-radius: 20px;
border-bottom-right-radius: 30px;
border-bottom-left-radius: 40px;

/* Border Shorthand */
border: 1px solid black;
/* width style color */

/* Box Sizing */
box-sizing: content-box;     /* Default */
box-sizing: border-box;      /* Include padding/border in width */

/* Outline (doesn't affect layout) */
outline: 2px solid blue;
outline-offset: 5px;
outline: none;               /* Remove focus outline */
```

---

## Display & Positioning

### Display
```css
/* Display Values */
display: block;              /* Full width, new line */
display: inline;             /* Inline with text */
display: inline-block;       /* Inline but accepts dimensions */
display: none;               /* Remove from document */
display: flex;               /* Flexbox container */
display: inline-flex;        /* Inline flexbox */
display: grid;               /* Grid container */
display: inline-grid;        /* Inline grid */
display: table;              /* Table-like */
display: table-cell;
display: list-item;
display: contents;           /* Remove box, keep children */

/* Visibility */
visibility: visible;         /* Default */
visibility: hidden;          /* Hidden but takes space */
visibility: collapse;        /* For table elements */

/* Opacity */
opacity: 1;                  /* Fully visible */
opacity: 0.5;                /* Semi-transparent */
opacity: 0;                  /* Invisible but takes space */
```

### Position
```css
/* Position Values */
position: static;            /* Default */
position: relative;          /* Relative to normal position */
position: absolute;          /* Relative to positioned parent */
position: fixed;             /* Relative to viewport */
position: sticky;            /* Hybrid relative/fixed */

/* Position Properties */
top: 10px;
right: 20px;
bottom: 30px;
left: 40px;

/* Negative values */
top: -10px;
left: -20px;

/* Percentage */
top: 50%;
left: 50%;

/* Auto */
top: auto;
bottom: auto;

/* Z-index (stacking) */
z-index: 1;
z-index: 999;
z-index: -1;
z-index: auto;

/* Float (legacy) */
float: left;
float: right;
float: none;

/* Clear */
clear: left;
clear: right;
clear: both;
clear: none;

/* Overflow */
overflow: visible;           /* Default */
overflow: hidden;
overflow: scroll;
overflow: auto;

/* Individual axis */
overflow-x: hidden;
overflow-y: scroll;

/* Text overflow */
overflow: hidden;
text-overflow: ellipsis;
white-space: nowrap;
```

---

## Flexbox

### Container Properties
```css
/* Display */
display: flex;
display: inline-flex;

/* Direction */
flex-direction: row;         /* Default */
flex-direction: row-reverse;
flex-direction: column;
flex-direction: column-reverse;

/* Wrap */
flex-wrap: nowrap;          /* Default */
flex-wrap: wrap;
flex-wrap: wrap-reverse;

/* Flow Shorthand */
flex-flow: row wrap;
/* direction wrap */

/* Justify Content (main axis) */
justify-content: flex-start; /* Default */
justify-content: flex-end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;

/* Align Items (cross axis) */
align-items: stretch;        /* Default */
align-items: flex-start;
align-items: flex-end;
align-items: center;
align-items: baseline;

/* Align Content (multiple lines) */
align-content: stretch;      /* Default */
align-content: flex-start;
align-content: flex-end;
align-content: center;
align-content: space-between;
align-content: space-around;

/* Gap */
gap: 20px;                   /* All gaps */
gap: 10px 20px;             /* Row gap | Column gap */
row-gap: 10px;
column-gap: 20px;
```

### Item Properties
```css
/* Order */
order: 0;                    /* Default */
order: 1;
order: -1;

/* Flex Grow */
flex-grow: 0;                /* Default */
flex-grow: 1;
flex-grow: 2;

/* Flex Shrink */
flex-shrink: 1;              /* Default */
flex-shrink: 0;
flex-shrink: 2;

/* Flex Basis */
flex-basis: auto;            /* Default */
flex-basis: 200px;
flex-basis: 50%;
flex-basis: 0;

/* Flex Shorthand */
flex: 0 1 auto;              /* Default */
flex: 1;                     /* flex: 1 1 0 */
flex: 1 1 200px;            /* grow shrink basis */
flex: none;                  /* 0 0 auto */

/* Align Self */
align-self: auto;            /* Default */
align-self: flex-start;
align-self: flex-end;
align-self: center;
align-self: baseline;
align-self: stretch;
```

---

## CSS Grid

### Container Properties
```css
/* Display */
display: grid;
display: inline-grid;

/* Template Columns */
grid-template-columns: 200px 200px 200px;
grid-template-columns: 1fr 2fr 1fr;
grid-template-columns: repeat(3, 1fr);
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
grid-template-columns: [start] 1fr [middle] 2fr [end];

/* Template Rows */
grid-template-rows: 100px 200px;
grid-template-rows: repeat(3, 1fr);
grid-template-rows: minmax(100px, auto);

/* Template Areas */
grid-template-areas:
    "header header header"
    "sidebar main main"
    "footer footer footer";

/* Auto Rows/Columns */
grid-auto-rows: 100px;
grid-auto-rows: minmax(100px, auto);
grid-auto-columns: 1fr;

/* Auto Flow */
grid-auto-flow: row;         /* Default */
grid-auto-flow: column;
grid-auto-flow: row dense;
grid-auto-flow: column dense;

/* Gap */
gap: 20px;
gap: 10px 20px;
row-gap: 10px;
column-gap: 20px;

/* Justify Items */
justify-items: stretch;      /* Default */
justify-items: start;
justify-items: end;
justify-items: center;

/* Align Items */
align-items: stretch;        /* Default */
align-items: start;
align-items: end;
align-items: center;

/* Place Items Shorthand */
place-items: center center;

/* Justify Content */
justify-content: start;
justify-content: end;
justify-content: center;
justify-content: stretch;
justify-content: space-around;
justify-content: space-between;
justify-content: space-evenly;

/* Align Content */
align-content: start;
align-content: end;
align-content: center;
align-content: stretch;
align-content: space-around;
align-content: space-between;
align-content: space-evenly;

/* Place Content Shorthand */
place-content: center center;
```

### Item Properties
```css
/* Grid Column */
grid-column-start: 1;
grid-column-end: 3;
grid-column: 1 / 3;          /* start / end */
grid-column: span 2;
grid-column: 1 / -1;         /* Full width */

/* Grid Row */
grid-row-start: 1;
grid-row-end: 3;
grid-row: 1 / 3;
grid-row: span 2;

/* Grid Area */
grid-area: header;           /* Named area */
grid-area: 1 / 1 / 3 / 3;   /* row-start / col-start / row-end / col-end */

/* Justify Self */
justify-self: stretch;       /* Default */
justify-self: start;
justify-self: end;
justify-self: center;

/* Align Self */
align-self: stretch;         /* Default */
align-self: start;
align-self: end;
align-self: center;

/* Place Self Shorthand */
place-self: center center;
```

---

## Transforms

### 2D Transforms
```css
/* Translate (Move) */
transform: translateX(50px);
transform: translateY(-20px);
transform: translate(50px, -20px);
transform: translate(50%, -50%); /* Center element */

/* Scale (Size) */
transform: scale(1.5);       /* Uniform scale */
transform: scaleX(2);
transform: scaleY(0.5);
transform: scale(2, 0.5);

/* Rotate */
transform: rotate(45deg);
transform: rotate(-90deg);
transform: rotate(0.5turn);
transform: rotate(3.14rad);

/* Skew (Slant) */
transform: skewX(20deg);
transform: skewY(-10deg);
transform: skew(20deg, -10deg);

/* Multiple Transforms */
transform: translate(50px, 100px) rotate(45deg) scale(1.5);

/* Transform Origin */
transform-origin: center;    /* Default */
transform-origin: top left;
transform-origin: 50% 50%;
transform-origin: 10px 20px;
```

### 3D Transforms
```css
/* 3D Setup */
perspective: 1000px;         /* On parent */
transform-style: preserve-3d; /* Preserve 3D space */

/* 3D Translate */
transform: translateZ(100px);
transform: translate3d(50px, 100px, 200px);

/* 3D Rotate */
transform: rotateX(45deg);
transform: rotateY(45deg);
transform: rotateZ(45deg);
transform: rotate3d(1, 1, 1, 45deg);

/* 3D Scale */
transform: scaleZ(2);
transform: scale3d(1, 2, 3);

/* Backface Visibility */
backface-visibility: visible; /* Default */
backface-visibility: hidden;

/* Perspective Origin */
perspective-origin: 50% 50%; /* Default */
perspective-origin: top left;
```

---

## Transitions & Animations

### Transitions
```css
/* Transition Property */
transition-property: all;
transition-property: width;
transition-property: width, height, background-color;
transition-property: none;

/* Transition Duration */
transition-duration: 0.3s;
transition-duration: 300ms;
transition-duration: 0.3s, 0.5s;

/* Transition Timing Function */
transition-timing-function: ease;        /* Default */
transition-timing-function: linear;
transition-timing-function: ease-in;
transition-timing-function: ease-out;
transition-timing-function: ease-in-out;
transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
transition-timing-function: steps(4);

/* Transition Delay */
transition-delay: 0s;
transition-delay: 0.5s;
transition-delay: 1s, 2s;

/* Transition Shorthand */
transition: all 0.3s ease;
transition: width 0.3s ease-out 0.5s;
/* property duration timing-function delay */

/* Multiple Transitions */
transition: width 0.3s, height 0.5s, transform 0.3s;
```

### Animations
```css
/* Define Keyframes */
@keyframes slidein {
    from {
        transform: translateX(-100%);
    }
    to {
        transform: translateX(0);
    }
}

@keyframes bounce {
    0%, 100% {
        transform: translateY(0);
    }
    50% {
        transform: translateY(-30px);
    }
}

/* Animation Name */
animation-name: slidein;
animation-name: bounce, fade;

/* Animation Duration */
animation-duration: 2s;
animation-duration: 300ms;

/* Animation Timing Function */
animation-timing-function: ease;
animation-timing-function: linear;
animation-timing-function: cubic-bezier(0.4, 0, 0.2, 1);

/* Animation Delay */
animation-delay: 0s;
animation-delay: 1s;

/* Animation Iteration Count */
animation-iteration-count: 1;
animation-iteration-count: 3;
animation-iteration-count: infinite;

/* Animation Direction */
animation-direction: normal;  /* Default */
animation-direction: reverse;
animation-direction: alternate;
animation-direction: alternate-reverse;

/* Animation Fill Mode */
animation-fill-mode: none;    /* Default */
animation-fill-mode: forwards;
animation-fill-mode: backwards;
animation-fill-mode: both;

/* Animation Play State */
animation-play-state: running; /* Default */
animation-play-state: paused;

/* Animation Shorthand */
animation: slidein 2s ease-in-out 1s infinite alternate both;
/* name duration timing-function delay iteration-count direction fill-mode */

/* Multiple Animations */
animation: bounce 1s, fade 2s;
```

---

## Responsive Design

### Media Queries
```css
/* Basic Media Query */
@media screen and (min-width: 768px) {
    /* Styles for screens 768px and wider */
}

/* Max Width */
@media (max-width: 767px) {
    /* Mobile styles */
}

/* Range */
@media (min-width: 768px) and (max-width: 1024px) {
    /* Tablet styles */
}

/* Modern Range Syntax */
@media (width >= 768px) {
    /* 768px and up */
}

@media (768px <= width <= 1024px) {
    /* Between 768px and 1024px */
}

/* Orientation */
@media (orientation: portrait) {
    /* Portrait mode */
}

@media (orientation: landscape) {
    /* Landscape mode */
}

/* Resolution */
@media (min-resolution: 2dppx) {
    /* Retina displays */
}

/* Hover Capability */
@media (hover: hover) {
    /* Can hover (desktop) */
}

@media (hover: none) {
    /* Cannot hover (touch) */
}

/* Pointer */
@media (pointer: coarse) {
    /* Touch screen */
}

@media (pointer: fine) {
    /* Mouse/trackpad */
}

/* Prefers Reduced Motion */
@media (prefers-reduced-motion: reduce) {
    /* Reduce animations */
}

/* Prefers Color Scheme */
@media (prefers-color-scheme: dark) {
    /* Dark mode styles */
}

@media (prefers-color-scheme: light) {
    /* Light mode styles */
}

/* Print */
@media print {
    /* Print styles */
}

/* Combining Queries */
@media (min-width: 768px) and (orientation: landscape) {
    /* Tablet in landscape */
}
```

### Container Queries
```css
/* Define Container */
.container {
    container-type: inline-size;
    container-name: card;
}

/* Query Container */
@container card (min-width: 400px) {
    /* Styles when container is 400px+ */
}

@container (min-width: 300px) {
    /* Query nearest container */
}

/* Container Units */
.element {
    width: 50cqw;            /* Container query width */
    height: 100cqh;          /* Container query height */
    font-size: 5cqi;         /* Container query inline */
}
```

---

## Advanced Properties

### Custom Properties (CSS Variables)
```css
/* Define Variables */
:root {
    --primary-color: #007bff;
    --secondary-color: #6c757d;
    --spacing: 1rem;
    --border-radius: 4px;
}

/* Use Variables */
.element {
    color: var(--primary-color);
    padding: var(--spacing);
    margin: calc(var(--spacing) * 2);
    border-radius: var(--border-radius, 0); /* With fallback */
}

/* Scoped Variables */
.dark-theme {
    --primary-color: #ffffff;
    --bg-color: #000000;
}
```

### Filters
```css
/* Filter Effects */
filter: blur(5px);
filter: brightness(1.5);
filter: contrast(200%);
filter: grayscale(100%);
filter: hue-rotate(90deg);
filter: invert(100%);
filter: opacity(50%);
filter: saturate(200%);
filter: sepia(100%);
filter: drop-shadow(10px 10px 20px rgba(0,0,0,0.5));

/* Multiple Filters */
filter: blur(2px) brightness(1.2) contrast(1.5);

/* Backdrop Filter */
backdrop-filter: blur(10px);
backdrop-filter: brightness(0.8);
```

### Clip Path
```css
/* Basic Shapes */
clip-path: circle(50%);
clip-path: ellipse(50% 25%);
clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
clip-path: inset(10px 20px 30px 40px);

/* SVG Path */
clip-path: path('M10,10 L90,10 L90,90 L10,90 Z');

/* URL Reference */
clip-path: url(#myClip);
```

### Masks
```css
/* Mask Image */
mask-image: url('mask.png');
mask-image: linear-gradient(black, transparent);

/* Mask Properties */
mask-size: cover;
mask-position: center;
mask-repeat: no-repeat;

/* Webkit Prefix (often needed) */
-webkit-mask-image: url('mask.png');
```

### Scroll Behavior
```css
/* Smooth Scrolling */
html {
    scroll-behavior: smooth;
}

/* Scroll Snap */
.container {
    scroll-snap-type: x mandatory;
    scroll-snap-type: y proximity;
    overflow-x: auto;
}

.item {
    scroll-snap-align: start;
    scroll-snap-align: center;
    scroll-snap-align: end;
}

/* Scroll Padding */
.container {
    scroll-padding: 20px;
    scroll-padding-top: 100px;
}

/* Overscroll Behavior */
overscroll-behavior: auto;   /* Default */
overscroll-behavior: contain;
overscroll-behavior: none;
```

### Miscellaneous
```css
/* Cursor */
cursor: pointer;
cursor: move;
cursor: text;
cursor: wait;
cursor: help;
cursor: not-allowed;
cursor: crosshair;
cursor: url('cursor.png'), auto;

/* User Select */
user-select: none;
user-select: all;
user-select: text;
user-select: auto;

/* Pointer Events */
pointer-events: none;
pointer-events: auto;

/* Resize */
resize: none;
resize: both;
resize: horizontal;
resize: vertical;

/* Will Change (Performance) */
will-change: transform;
will-change: opacity;
will-change: scroll-position;
will-change: contents;
will-change: auto;

/* Appearance */
appearance: none;            /* Remove default styling */
-webkit-appearance: none;

/* Touch Action */
touch-action: auto;
touch-action: none;
touch-action: pan-x;
touch-action: pan-y;
touch-action: manipulation;

/* Object Fit (for img/video) */
object-fit: fill;            /* Default */
object-fit: contain;
object-fit: cover;
object-fit: none;
object-fit: scale-down;

/* Object Position */
object-position: center;
object-position: top left;
object-position: 50% 50%;

/* Mix Blend Mode */
mix-blend-mode: normal;
mix-blend-mode: multiply;
mix-blend-mode: screen;
mix-blend-mode: overlay;
mix-blend-mode: darken;
mix-blend-mode: lighten;
mix-blend-mode: color-dodge;
mix-blend-mode: color-burn;
mix-blend-mode: difference;
mix-blend-mode: exclusion;

/* Isolation */
isolation: auto;
isolation: isolate;
```

---

## Quick Reference Tips

### Performance Tips
- Use `transform` and `opacity` for animations (GPU accelerated)
- Avoid animating `width`, `height`, `top`, `left` (causes reflow)
- Use `will-change` sparingly and remove after animation
- Prefer `transform: translateX()` over `left` for movement

### Accessibility Tips
- Always include `:focus` styles
- Ensure color contrast ratio of at least 4.5:1
- Use `rem` for font sizes (respects user preferences)
- Include `prefers-reduced-motion` media query
- Make touch targets at least 44x44px

### Browser Compatibility
- Check [caniuse.com](https://caniuse.com) for support
- Use vendor prefixes when needed (-webkit-, -moz-, -ms-)
- Provide fallbacks for new features
- Test in multiple browsers

### Best Practices
- Use semantic class names
- Organize CSS logically
- Comment your code
- Use CSS variables for consistency
- Mobile-first approach
- Minimize specificity
- Avoid !important when possible

---

## Common Patterns

### Centering
```css
/* Flexbox Center */
.flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
}

/* Grid Center */
.grid-center {
    display: grid;
    place-items: center;
}

/* Absolute Center */
.absolute-center {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

/* Margin Auto */
.margin-center {
    margin: 0 auto;
}
```

### Responsive Images
```css
img {
    max-width: 100%;
    height: auto;
    display: block;
}
```

### Text Truncation
```css
.truncate {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

.line-clamp {
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
}
```

### Aspect Ratio Box
```css
.aspect-ratio {
    aspect-ratio: 16 / 9;
}

/* Legacy method */
.aspect-ratio-legacy {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 */
}

.aspect-ratio-legacy > * {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
```

---

Keep this reference handy as you build your websites. Remember that not all properties work in all situations, and always test your CSS across different browsers and devices!
