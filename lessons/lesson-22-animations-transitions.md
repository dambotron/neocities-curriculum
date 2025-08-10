# Lesson 22: CSS Animations and Transitions

## Duration: 45-50 minutes

### Learning Objectives
- Create smooth transitions between states
- Build keyframe animations
- Understand animation properties
- Apply animations effectively

### Materials Needed
- Animation examples
- Performance tips sheet
- Creative inspiration gallery

### Lesson Outline

#### CSS Transitions (15 minutes)

1. **What are Transitions?**
   - Smooth change between two states
   - Triggered by hover, focus, etc.
   - Simple and performant

2. **Transition Syntax**
   ```css
   /* Transition single property */
   .button {
       background-color: blue;
       transition: background-color 0.3s;
   }
   
   .button:hover {
       background-color: darkblue;
   }
   
   /* Transition all properties */
   .box {
       transition: all 0.3s ease;
   }
   
   /* Multiple properties */
   .card {
       transition: transform 0.3s, box-shadow 0.3s;
   }
   ```
3. **Transition Properties**
   ```css
   .element {
       /* Property | Duration | Timing | Delay */
       transition: transform 0.3s ease-in-out 0.1s;
       
       /* Or separately */
       transition-property: transform;
       transition-duration: 0.3s;
       transition-timing-function: ease-in-out;
       transition-delay: 0.1s;
   }
   ```

4. **Timing Functions**
   - `ease` - Default, slow start/end
   - `linear` - Constant speed
   - `ease-in` - Slow start
   - `ease-out` - Slow end
   - `ease-in-out` - Slow start and end
   - `cubic-bezier()` - Custom curve

#### Practical Transitions (8 minutes)

```css
/* Hover Effects */
.link {
    color: blue;
    text-decoration: none;
    transition: color 0.2s;
}

.link:hover {
    color: darkblue;
}

/* Transform Examples */
.scale-box {
    transition: transform 0.3s;
}

.scale-box:hover {
    transform: scale(1.1);
}

/* Multiple Properties */
.card {
    transition: transform 0.3s, box-shadow 0.3s;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 5px 15px rgba(0,0,0,0.3);
}
```
#### CSS Animations (15 minutes)

1. **Keyframe Syntax**
   ```css
   /* Define animation */
   @keyframes slideIn {
       from {
           transform: translateX(-100%);
           opacity: 0;
       }
       to {
           transform: translateX(0);
           opacity: 1;
       }
   }
   
   /* Apply animation */
   .element {
       animation: slideIn 1s ease-out;
   }
   ```

2. **Multiple Keyframes**
   ```css
   @keyframes bounce {
       0% {
           transform: translateY(0);
       }
       50% {
           transform: translateY(-30px);
       }
       100% {
           transform: translateY(0);
       }
   }
   ```

3. **Animation Properties**
   ```css
   .animated {
       animation-name: bounce;
       animation-duration: 1s;
       animation-timing-function: ease;
       animation-delay: 0.5s;
       animation-iteration-count: infinite;
       animation-direction: alternate;
       animation-fill-mode: forwards;
       
       /* Shorthand */
       animation: bounce 1s ease 0.5s infinite alternate;
   }
   ```
#### Hands-On: Loading Animation (10 minutes)

Create a loading spinner:

```html
<div class="loader">
    <div class="spinner"></div>
</div>
```

```css
.loader {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.spinner {
    width: 50px;
    height: 50px;
    border: 5px solid #f3f3f3;
    border-top: 5px solid #3498db;
    border-radius: 50%;
    animation: spin 1s linear infinite;
}

@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}
```

#### Creative Examples (5 minutes)

```css
/* Pulse Effect */
@keyframes pulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.05); }
    100% { transform: scale(1); }
}

.pulse {
    animation: pulse 2s ease-in-out infinite;
}

/* Fade In on Scroll */
.fade-in {
    opacity: 0;
    transform: translateY(20px);
    animation: fadeIn 1s forwards;
}

@keyframes fadeIn {
    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```
### Performance Tips (2 minutes)

1. **Animate Efficiently**
   - Use `transform` and `opacity`
   - Avoid animating `width`, `height`, `top`, `left`
   - Use `will-change` sparingly
   - Keep animations under 60fps

2. **Accessibility**
   ```css
   /* Respect user preferences */
   @media (prefers-reduced-motion: reduce) {
       * {
           animation: none !important;
           transition: none !important;
       }
   }
   ```

### Practice Exercise

Create an animated button with:
1. Color transition on hover
2. Scale transform on click
3. Shadow animation
4. Smooth all transitions

### Homework Assignment

1. **Animation Gallery**
   - Create 5 different animations
   - Include transitions and keyframes
   - Make a "showcase" page
   - Document what each does

2. **Enhance Your Site**
   - Add hover transitions to all links
   - Animate your navigation
   - Create a loading animation
   - Add entrance animations to content

3. **Creative Challenge**
   - Design an animated logo
   - Create a CSS-only hamburger menu animation
   - Build an animated progress bar
### Common Animation Patterns

```css
/* Button Press Effect */
.button:active {
    transform: scale(0.95);
}

/* Card Lift */
.card {
    transition: all 0.3s;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.2);
}

/* Slide In Menu */
.menu {
    transform: translateX(-100%);
    transition: transform 0.3s;
}

.menu.open {
    transform: translateX(0);
}
```

### Assessment Criteria
- Implements transitions correctly: 3 points
- Creates keyframe animations: 3 points
- Uses appropriate timing: 2 points
- Considers performance: 1 point
- Shows creativity: 1 point
- Total: 10 points

### Common Mistakes
- Overusing animations
- Poor performance choices
- Ignoring accessibility
- Animations too fast/slow
- Not testing on devices

### Teacher Notes
- Show subtle vs dramatic animations
- Discuss when to use animations
- Emphasize performance
- Let students share creations
- Demo browser DevTools animations panel

### Resources
- Animate.css library
- Cubic-bezier.com
- CSS Animation examples on CodePen
- Web Animations API (advanced)