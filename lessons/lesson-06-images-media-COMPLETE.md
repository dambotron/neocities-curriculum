# Lesson 6: Adding Images and Media
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Add images to web pages with proper syntax
- Write effective alt text for accessibility
- Understand image formats (JPG, PNG, GIF, WebP)
- Upload and organize images in Neocities
- Use figure and figcaption for semantic image markup
- Resize images using HTML attributes
- Embed audio and video content
- Optimize images for web performance

### Materials Needed
- Text editor
- Sample images in different formats (provided)
- Web browser
- Neocities account
- Image files to upload (students should bring 3-5 images)
- Projector for demonstrations
- Printed image format comparison chart

### Key Vocabulary with Definitions
- **Alt Text**: Alternative text description for images (accessibility)
- **Image Format**: File type (JPG, PNG, GIF, etc.)
- **Pixel**: Smallest unit of a digital image
- **Resolution**: Number of pixels in an image
- **File Size**: How much storage space an image uses
- **Aspect Ratio**: Proportional relationship between width and height
- **Figure**: Semantic container for images with captions
- **Responsive**: Images that adapt to different screen sizes
- **Compression**: Reducing file size while maintaining quality

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding Web Images (5 minutes)

**Teacher Script:**
"Images make websites come alive! But adding images properly involves more than just making things pretty. We need to think about accessibility, performance, and user experience."
**[CREATE new file: images-demo.html]**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Images and Media Demo</title>
</head>
<body>
    <h1>Working with Images</h1>
```

**"The Image Tag Anatomy:"**
```html
    <img src="photo.jpg" alt="Description of the image">
```

"Let's break down the img tag:
- `<img>` = Image tag (self-closing, no </img>!)
- `src` = Source - WHERE the image file is
- `alt` = Alternative text - WHAT the image shows
- The img tag is EMPTY - it has no content between tags
- Think of it as a placeholder that pulls in an external file"

### Image Formats Explained (5 minutes)

**[ADD to demo file with examples]**

```html
    <h2>Image Format Comparison</h2>
    
    <!-- JPEG: Best for photographs -->
    <h3>JPEG (.jpg or .jpeg)</h3>
    <img src="sunset-photo.jpg" alt="Sunset over mountains">
    <p>JPEG: Best for photos with many colors. Smaller file size but loses quality when compressed.</p>
    
    <!-- PNG: Best for graphics with transparency -->
    <h3>PNG (.png)</h3>
    <img src="logo.png" alt="Company logo with transparent background">
    <p>PNG: Supports transparency. Best for logos, icons, screenshots. Larger file size.</p>    
    <!-- GIF: Best for simple animations -->
    <h3>GIF (.gif)</h3>
    <img src="loading-spinner.gif" alt="Animated loading spinner">
    <p>GIF: Supports animation. Limited to 256 colors. Good for simple animations.</p>
    
    <!-- WebP: Modern format -->
    <h3>WebP (.webp)</h3>
    <img src="modern-image.webp" alt="High quality compressed image">
    <p>WebP: Modern format. 25-35% smaller than JPEG/PNG. Not supported in older browsers.</p>
```

**Teacher Script:**
"Choose your format based on the image type:
- **Photos of people/nature**: Use JPEG
- **Logos/icons/text**: Use PNG
- **Simple animations**: Use GIF
- **Modern sites**: Consider WebP with fallbacks

File size matters! Large images = slow websites = unhappy users!"

### Complete Image Examples (5 minutes)

**[ADD comprehensive examples]**

```html
    <h2>Image Sizing and Attributes</h2>
    
    <!-- Specifying dimensions -->
    <h3>Fixed Size</h3>
    <img src="photo.jpg" alt="Beach sunset" width="300" height="200">
    <p>Setting width and height prevents layout shift while loading.</p>
    
    <!-- Using only width (maintains aspect ratio) -->
    <h3>Responsive Width</h3>
    <img src="photo.jpg" alt="Beach sunset" width="100%">
    <p>Percentage width makes images responsive.</p>
    
    <!-- Image as a link -->
    <h3>Clickable Image</h3>
    <a href="full-size.jpg">
        <img src="thumbnail.jpg" alt="Click for larger image" width="150">    </a>
    
    <!-- Figure with caption -->
    <h3>Figure with Caption</h3>
    <figure>
        <img src="chart.png" alt="Sales data for 2024 showing 50% growth">
        <figcaption>Figure 1: Our sales increased by 50% this year</figcaption>
    </figure>
    
    <!-- Multiple images in a figure -->
    <h3>Image Gallery Preview</h3>
    <figure>
        <img src="photo1.jpg" alt="Morning sunrise" width="200">
        <img src="photo2.jpg" alt="Afternoon clouds" width="200">
        <img src="photo3.jpg" alt="Evening sunset" width="200">
        <figcaption>A day in three photos</figcaption>
    </figure>
    
    <!-- Loading attribute for performance -->
    <h3>Lazy Loading (for performance)</h3>
    <img src="large-photo.jpg" alt="Large landscape photo" loading="lazy" width="600">
    <p>The loading="lazy" attribute delays loading until user scrolls near.</p>
```

**"Alt Text Best Practices:"**
```html
    <!-- GOOD alt text examples -->
    <img src="dog.jpg" alt="Golden retriever playing fetch in the park">
    <img src="logo.png" alt="Acme Company logo">
    <img src="graph.png" alt="Bar graph showing 30% increase in users from 2023 to 2024">
    
    <!-- BAD alt text examples -->
    <img src="dog.jpg" alt="image">  <!-- Too vague -->
    <img src="dog.jpg" alt="dog.jpg">  <!-- Never use filename -->
    <img src="dog.jpg" alt="">  <!-- Empty only for decorative images -->
```

"Alt text is CRUCIAL for:
- Screen readers (accessibility)
- When images fail to load
- Search engine optimization (SEO)
- Understanding content without seeing"
---

## PART 2: WE DO (Guided Practice) - 20 minutes

### Creating a Photo Gallery Together (10 minutes)

**Teacher Script:**
"Let's build a photo gallery page with properly optimized images. First, we need to organize our files!"

**Step 1: File Organization**
"CRITICAL: Create an images folder in Neocities!
1. Go to your Neocities dashboard
2. Click 'New Folder'
3. Name it 'images' (lowercase, no spaces!)
4. This keeps your site organized

Your structure should look like:
```
your-site/
├── index.html
├── about.html
├── gallery.html
└── images/
    ├── photo1.jpg
    ├── photo2.jpg
    └── logo.png
```
CHECKPOINT: Everyone create the images folder now!"

**Step 2: Upload Images to Neocities**

"Now let's upload images:
1. Click on your 'images' folder
2. Click 'Upload' or drag files in
3. Keep filenames simple: no spaces, lowercase
4. Good: sunset-beach.jpg
5. Bad: My Sunset @ The Beach!.JPG

IMPORTANT: Neocities has a 1GB storage limit. Optimize your images!"

**Step 3: Build the Gallery Page**

"Create gallery.html:"

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">    <title>Photo Gallery | My Portfolio</title>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <a href="index.html">Home</a> | 
        <a href="about.html">About</a> | 
        <a href="gallery.html">Gallery</a> | 
        <a href="contact.html">Contact</a>
    </nav>
    
    <h1>My Photo Gallery</h1>
    <p>A collection of my favorite images from this year.</p>
    
    <!-- Featured Image -->
    <section>
        <h2>Featured Photo</h2>
        <figure>
            <img src="images/sunset-beach.jpg" 
                 alt="Orange and pink sunset over ocean waves at Santa Monica beach"
                 width="600"
                 loading="eager">
            <figcaption>Sunset at Santa Monica Beach - My favorite capture of 2024</figcaption>
        </figure>
    </section>
```
"Notice the path: 'images/sunset-beach.jpg' - we include the folder name!"

```html
    <!-- Photo Grid -->
    <section>
        <h2>Recent Photos</h2>
        
        <!-- Each photo in a figure -->
        <figure>
            <a href="images/mountain-full.jpg" title="Click for full size">
                <img src="images/mountain-thumb.jpg" 
                     alt="Snow-capped mountain peak with pine trees in foreground"
                     width="300"
                     loading="lazy">
            </a>
            <figcaption>Rocky Mountains, Colorado</figcaption>
        </figure>        
        <figure>
            <img src="images/city-lights.jpg" 
                 alt="City skyline at night with illuminated buildings reflecting in water"
                 width="300"
                 loading="lazy">
            <figcaption>Downtown at Night</figcaption>
        </figure>
        
        <figure>
            <img src="images/flower-macro.jpg" 
                 alt="Close-up of purple iris flower showing detailed petals and yellow center"
                 width="300"
                 loading="lazy">
            <figcaption>Macro Photography Practice</figcaption>
        </figure>
    </section>
```

### Adding Audio and Video (10 minutes)

"Now let's add multimedia content:"

```html
    <!-- Audio Section -->
    <section>
        <h2>Audio Samples</h2>
        
        <!-- Basic audio player -->
        <h3>My Podcast Episode</h3>
        <audio controls>
            <source src="audio/podcast-ep1.mp3" type="audio/mpeg">
            <source src="audio/podcast-ep1.ogg" type="audio/ogg">
            Your browser does not support the audio element.
        </audio>
        
        <!-- Audio with attributes -->
        <h3>Background Music Sample</h3>
        <audio controls loop>
            <source src="audio/background-music.mp3" type="audio/mpeg">
            <p>Your browser doesn't support HTML5 audio. 
               <a href="audio/background-music.mp3">Download the file</a> instead.</p>
        </audio>
    </section>    
    <!-- Video Section -->
    <section>
        <h2>Video Content</h2>
        
        <!-- Basic video player -->
        <h3>My Introduction Video</h3>
        <video width="400" controls poster="images/video-thumbnail.jpg">
            <source src="videos/intro.mp4" type="video/mp4">
            <source src="videos/intro.webm" type="video/webm">
            Your browser does not support the video tag.
        </video>
        
        <!-- Video with multiple attributes -->
        <h3>Tutorial Video</h3>
        <video width="400" 
               controls 
               muted
               poster="images/tutorial-thumb.jpg"
               preload="metadata">
            <source src="videos/tutorial.mp4" type="video/mp4">
            <track src="captions.vtt" kind="captions" srclang="en" label="English">
            <p>Your browser doesn't support HTML5 video. 
               <a href="videos/tutorial.mp4">Download the video</a> instead.</p>
        </video>
    </section>
    
    <!-- Embedded Content -->
    <section>
        <h2>Embedded Content</h2>
        
        <!-- YouTube Video (using iframe - preview of next topic) -->
        <h3>YouTube Tutorial</h3>
        <iframe width="560" height="315" 
                src="https://www.youtube.com/embed/dQw4w9WgXcQ" 
                title="YouTube video player"
                allowfullscreen>
        </iframe>
    </section>
</body>
</html>
```
**Teacher Script:**
"Key points about media:
- **controls** attribute gives play/pause buttons
- **Multiple sources** for browser compatibility
- **Fallback content** for unsupported browsers
- **poster** attribute for video thumbnail
- **preload** controls loading behavior
- Keep media files small - users have limited bandwidth!"

---

## PART 3: YOU DO (Independent Practice) - 10 minutes

### Student Activity: Create a Media Portfolio Page

**Instructions:**
"Create a media-rich page showcasing images and optional audio/video. You have 10 minutes!"

**Required Tasks:**
1. ✅ Create `portfolio.html` with proper HTML5 structure
2. ✅ Create an 'images' folder in Neocities
3. ✅ Upload at least 3 images (optimized for web)
4. ✅ Display images with proper src paths (images/filename.ext)
5. ✅ Write descriptive alt text for EVERY image
6. ✅ Use at least one figure with figcaption
7. ✅ Set width attributes on all images
8. ✅ Make at least one image clickable (link to full size)
9. ✅ Use loading="lazy" on images below the fold
10. ✅ Include proper navigation to other pages

**Bonus Challenges:**
- Add an audio file with controls
- Embed a video with poster image
- Create an image gallery with thumbnail/full-size system
- Add an image map with clickable areas
- Include an SVG image or icon

### Complete Solution Example:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="My multimedia portfolio showcasing photography, design, and creative work">
    <title>Media Portfolio | Jane Smith</title>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <a href="index.html">Home</a> | 
        <a href="about.html">About</a> | 
        <a href="portfolio.html">Portfolio</a> | 
        <a href="contact.html">Contact</a>
    </nav>
    
    <header>
        <h1>My Creative Portfolio</h1>
        <p>Welcome to my collection of visual and audio work</p>
    </header>
    
    <main>
        <!-- Hero Image -->
        <section>
            <figure>
                <img src="images/hero-banner.jpg" 
                     alt="Panoramic view of mountain landscape at golden hour with dramatic clouds"
                     width="100%"
                     style="max-width: 1200px;">
                <figcaption>Featured Work: "Golden Hour in the Rockies" - Winner of School Photo Contest 2024</figcaption>
            </figure>
        </section>
        
        <!-- Photography Portfolio -->
        <section>
            <h2>Photography</h2>
            
            <figure>
                <a href="images/portrait-full.jpg" title="View full resolution">                    <img src="images/portrait-thumb.jpg" 
                         alt="Black and white portrait of elderly man with weathered face showing years of wisdom"
                         width="300"
                         loading="lazy">
                </a>
                <figcaption>Portrait Series: "Stories in Faces"</figcaption>
            </figure>
            
            <figure>
                <img src="images/macro-flower.jpg" 
                     alt="Extreme close-up of water droplets on red rose petals with soft bokeh background"
                     width="300"
                     loading="lazy">
                <figcaption>Macro Photography: "Morning Dew"</figcaption>
            </figure>
            
            <figure>
                <img src="images/street-photo.jpg" 
                     alt="Busy city intersection at night with streaking car lights creating red and white trails"
                     width="300"
                     loading="lazy">
                <figcaption>Urban Series: "City Never Sleeps"</figcaption>
            </figure>
        </section>
        
        <!-- Design Work -->
        <section>
            <h2>Graphic Design</h2>
            
            <figure>
                <img src="images/logo-design.png" 
                     alt="Minimalist logo design featuring stylized mountain peaks in gradient blue"
                     width="250">
                <figcaption>Logo Design for Mountain Sports Co.</figcaption>
            </figure>
            
            <figure>
                <img src="images/poster.png" 
                     alt="Concert poster with bold typography and vibrant geometric patterns in neon colors"                     width="250"
                     loading="lazy">
                <figcaption>Music Festival Poster Design</figcaption>
            </figure>
        </section>
        
        <!-- Audio Portfolio -->
        <section>
            <h2>Audio Production</h2>
            
            <h3>Podcast Sample</h3>
            <audio controls>
                <source src="audio/podcast-sample.mp3" type="audio/mpeg">
                <source src="audio/podcast-sample.ogg" type="audio/ogg">
                Your browser does not support audio. 
                <a href="audio/podcast-sample.mp3">Download the audio file</a>.
            </audio>
            
            <h3>Music Composition</h3>
            <audio controls>
                <source src="audio/original-music.mp3" type="audio/mpeg">
                <p>Listen to my original composition or 
                   <a href="audio/original-music.mp3">download it here</a>.</p>
            </audio>
        </section>
        
        <!-- Video Section (Optional) -->
        <section>
            <h2>Video Work</h2>
            <video width="400" 
                   controls 
                   poster="images/video-poster.jpg">
                <source src="videos/demo-reel.mp4" type="video/mp4">
                <source src="videos/demo-reel.webm" type="video/webm">
                Your browser doesn't support video. 
                <a href="videos/demo-reel.mp4">Download my demo reel</a>.
            </video>
        </section>
    </main>
    
    <footer>        <p>&copy; 2024 Jane Smith | 
           <a href="contact.html">Contact</a> | 
           <a href="#top">Back to top</a></p>
    </footer>
</body>
</html>
```

---

## Assessment & Closing (5 minutes)

### Exit Ticket Questions

1. **What's the difference between JPG and PNG formats?**
   - Answer: JPG is best for photographs with many colors but doesn't support transparency. PNG supports transparency and is best for graphics, logos, and images with text, but has larger file sizes.

2. **Write the HTML for an image with alt text:**
   - Answer: `<img src="photo.jpg" alt="Description of what the image shows">`

3. **Why is alt text important? Give 3 reasons:**
   - Answer: 
     1. Accessibility - screen readers read it to blind users
     2. SEO - search engines index alt text
     3. Fallback - displays when images fail to load

4. **How do you make an image clickable?**
   - Answer: Wrap it in an anchor tag: `<a href="link.html"><img src="image.jpg" alt="description"></a>`

5. **What does the loading="lazy" attribute do?**
   - Answer: It delays loading the image until the user scrolls near it, improving page load performance.

### Success Criteria Checklist
- [ ] Created organized folder structure (2 pts)
- [ ] Successfully uploaded images to Neocities (3 pts)
- [ ] Used correct image paths (2 pts)
- [ ] Wrote descriptive alt text for all images (3 pts)
- [ ] Used figure and figcaption correctly (2 pts)
- [ ] Set appropriate width attributes (2 pts)- [ ] Made at least one image clickable (2 pts)
- [ ] Optimized images for web (2 pts)
- [ ] Optional: Added audio/video correctly (2 bonus pts)
**Total: ___/20 points**

### Homework Assignment

**Create an "About Me" page with images (`aboutme-visual.html`):**

Requirements:
1. Include a profile photo with professional alt text
2. Create a "My Interests" section with 3+ images
3. Add a figure showing your favorite place with caption
4. Include an image gallery of hobbies (minimum 4 images)
5. All images must be in an organized folder structure
6. Use loading="lazy" for images below the fold
7. Make thumbnails clickable to full-size versions
8. Include one decorative image with empty alt text (alt="")
9. Total page size should be under 2MB

**Homework Solution Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Me - Visual Story | Alex Chen</title>
</head>
<body>
    <nav>
        <a href="index.html">Home</a> | 
        <a href="aboutme-visual.html">About</a> | 
        <a href="portfolio.html">Portfolio</a> | 
        <a href="contact.html">Contact</a>
    </nav>
    
    <h1>About Me - A Visual Introduction</h1>
    
    <!-- Profile Section -->
    <section>
        <h2>Hello, I'm Alex!</h2>        <img src="images/profile-photo.jpg" 
             alt="Alex Chen smiling, wearing a blue shirt, standing in front of a bookshelf"
             width="200"
             style="float: left; margin-right: 20px;">
        <p>I'm a high school student passionate about web development, photography, and music.</p>
        <p>I started learning HTML and CSS this year and I'm amazed by what I can create!</p>
        <div style="clear: both;"></div> <!-- Clear the float -->
    </section>
    
    <!-- Interests Section -->
    <section>
        <h2>My Interests</h2>
        
        <h3>Photography</h3>
        <img src="images/camera-gear.jpg" 
             alt="My Canon DSLR camera with three lenses arranged on wooden table"
             width="300"
             loading="lazy">
        
        <h3>Music</h3>
        <img src="images/guitar.jpg" 
             alt="Acoustic guitar leaning against amplifier in my practice room"
             width="300"
             loading="lazy">
        
        <h3>Coding</h3>
        <img src="images/desk-setup.jpg" 
             alt="My coding setup with dual monitors showing VS Code and a browser"
             width="300"
             loading="lazy">
    </section>
    
    <!-- Favorite Place -->
    <section>
        <h2>My Favorite Place</h2>
        <figure>
            <img src="images/library.jpg" 
                 alt="Interior of city library with towering bookshelves and natural light streaming through tall windows"                 width="500"
                 loading="lazy">
            <figcaption>The City Library - Where I spend hours reading and studying</figcaption>
        </figure>
    </section>
    
    <!-- Hobbies Gallery -->
    <section>
        <h2>My Hobbies Gallery</h2>
        <p>Click any image to see full size!</p>
        
        <a href="images/hiking-full.jpg">
            <img src="images/hiking-thumb.jpg" 
                 alt="View from mountain summit showing valley below"
                 width="200"
                 loading="lazy">
        </a>
        
        <a href="images/cooking-full.jpg">
            <img src="images/cooking-thumb.jpg" 
                 alt="Homemade pasta dish I prepared for family dinner"
                 width="200"
                 loading="lazy">
        </a>
        
        <a href="images/robotics-full.jpg">
            <img src="images/robotics-thumb.jpg" 
                 alt="Robot I built for the school robotics competition"
                 width="200"
                 loading="lazy">
        </a>
        
        <a href="images/art-full.jpg">
            <img src="images/art-thumb.jpg" 
                 alt="Watercolor painting of sunset over ocean"
                 width="200"
                 loading="lazy">
        </a>
        
        <!-- Decorative border image -->
        <img src="images/decorative-border.png" alt="" width="100%">
    </section>    
    <footer>
        <p>&copy; 2024 Alex Chen | Total images: 12 | Page size: 1.8MB</p>
    </footer>
</body>
</html>
```

---

## Teacher Notes & Tips

### Common Student Errors:
1. **Wrong file paths** - Forgetting 'images/' folder in src
2. **Missing alt text** - Every image needs alt (even if empty)
3. **Huge file sizes** - Not optimizing images before upload
4. **Spaces in filenames** - Causes broken images
5. **Wrong format choice** - Using PNG for photos (huge files)
6. **No width/height** - Causes layout shift while loading
7. **Copyright violations** - Using images without permission

### Image Optimization Tips:
- **Resize BEFORE uploading**: 1200px wide maximum for most uses
- **Compress images**: Use TinyPNG.com or similar
- **Choose right format**: JPG for photos, PNG for graphics
- **Aim for under 200KB** per image when possible
- **Use thumbnails**: Small version linking to full size

### Differentiation Strategies:

**For Struggling Students:**
- Provide pre-optimized images
- Start with just 2-3 images
- Give template with image tags to fill in
- Focus on alt text before other attributes

**For Advanced Students:**
- Create an image slider (preview of JavaScript)
- Use srcset for responsive images
- Add image filters with CSS (preview)
- Create an interactive image map
- Optimize for Core Web Vitals
### Time Management:
- 0-5 min: Review homework and warm-up
- 5-15 min: I DO image formats and examples
- 15-25 min: WE DO gallery creation
- 25-35 min: WE DO media elements
- 35-45 min: YOU DO portfolio page
- 45-50 min: Assessment and homework

### Accessibility Best Practices:
- **Alt text should be descriptive**, not just "image"
- **Decorative images** get empty alt text (alt="")
- **Complex images** may need longer descriptions
- **Videos need captions** for deaf users
- **Audio needs transcripts** for accessibility

### Copyright and Ethics:
- **Only use images you have rights to**:
  - Your own photos
  - Creative Commons with attribution
  - Royalty-free stock photos
  - Public domain images
- **Never hotlink** (use images from other servers)
- **Give credit** when required
- **Respect privacy** - get permission for photos of people

### Free Image Resources:
- Unsplash.com - High quality free photos
- Pexels.com - Free stock photos
- Pixabay.com - Free images and videos
- Commons.wikimedia.org - Wikipedia's media repository
- Placeholder.com - Temporary placeholder images

### Tools for Students:
- **Image editing**: GIMP (free), Canva (online)
- **Optimization**: TinyPNG.com, Squoosh.app
- **Format conversion**: CloudConvert.com
- **Screenshots**: Built-in OS tools
- **File size checker**: Browser developer tools
### Extension Activities:
1. Create a photo essay with captions telling a story
2. Build a before/after image comparison
3. Make an image gallery with CSS Grid (preview)
4. Add a favicon to your site
5. Create an infographic using HTML and images

### Real-World Applications:
- **E-commerce**: Product images with zoom
- **News sites**: Photo journalism with captions
- **Social media**: Image optimization for fast loading
- **Portfolios**: Showcasing visual work
- **Documentation**: Screenshots with annotations

### Performance Considerations:
- **Largest Contentful Paint (LCP)**: Hero images affect this
- **Cumulative Layout Shift (CLS)**: Always set dimensions
- **First Input Delay (FID)**: Large images can block interaction
- **Lazy loading**: Essential for image-heavy pages
- **WebP format**: 25-35% smaller but check browser support

### Quick Reference for Board:
```
IMAGE FORMULA:
<img src="path/image.jpg" alt="description">

IMAGE FORMATS:
JPG/JPEG - Photos, many colors
PNG - Graphics, transparency
GIF - Simple animations
WebP - Modern, smaller files
SVG - Vector graphics (logos)

MUST HAVE:
- src attribute (path to image)
- alt attribute (description)
- Organized folder structure

SHOULD HAVE:
- width and/or height
- loading="lazy" below fold
- Optimized file size
```

### Troubleshooting Guide:
- **Image not showing**: Check file path and spelling
- **Image too large**: Resize before uploading
- **Slow loading**: Optimize/compress images
- **Layout shifting**: Add width/height attributes
- **Broken on mobile**: Use responsive techniques

**End of Lesson 6**