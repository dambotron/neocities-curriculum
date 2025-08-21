# Lesson 6: Adding Images and Media

## Duration: 45-50 minutes

### Learning Objectives
- Add images to web pages
- Understand image formats and optimization
- Use proper alt text for accessibility
- Embed other media types

### Materials Needed
- Sample images (school appropriate)
- Image editing software (optional)
- File size comparison chart

### Lesson Outline

#### Introduction to Images (10 minutes)

1. **The Image Tag**
   ```html
   <img src="image.jpg" alt="Description">
   ```
   - Self-closing tag
   - Two required attributes

2. **Image Formats**
   - **JPEG/JPG**: Photos, many colors
   - **PNG**: Graphics, transparency
   - **GIF**: Simple animations
   - **WebP**: Modern format, smaller files

3. **The Importance of Alt Text**
   - Accessibility for screen readers
   - Shows if image fails to load
   - Helps with SEO
   - Should describe image content
#### Image Attributes (10 minutes)

1. **Size Control**
   ```html
   <!-- Specify width only (height auto-adjusts) -->
   <img src="photo.jpg" alt="My photo" width="300">
   
   <!-- Specify both dimensions -->
   <img src="logo.png" alt="Logo" width="200" height="100">
   
   <!-- Responsive sizing (we'll learn more with CSS) -->
   <img src="banner.jpg" alt="Banner" style="width: 100%;">
   ```

2. **Image Sources**
   ```html
   <!-- Local image in same folder -->
   <img src="picture.jpg" alt="Picture">
   
   <!-- Image in subfolder -->
   <img src="images/photo.jpg" alt="Photo">
   
   <!-- External image (use sparingly) -->
   <img src="https://example.com/image.jpg" alt="External image">
   ```

#### Best Practices (8 minutes)

1. **File Organization**
   - Create an "images" folder
   - Use descriptive filenames
   - No spaces in filenames (use-dashes)

2. **Image Optimization**
   - Keep file sizes small (under 500KB ideal)
   - Use appropriate dimensions
   - Choose right format for content
#### Hands-On: Creating a Gallery Page (15 minutes)

Students create `gallery.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Gallery</title>
</head>
<body>
    <h1>My Photo Gallery</h1>
    
    <h2>My Hobbies</h2>
    <img src="images/hobby1.jpg" alt="Playing guitar" width="400">
    <p>I love playing guitar in my free time.</p>
    
    <h2>School Events</h2>
    <img src="images/event1.jpg" alt="Science fair project" width="400">
    <p>My volcano project at the science fair.</p>
    
    <h2>Nature Photos</h2>
    <img src="images/nature1.jpg" alt="Sunset at the beach" width="400">
    <img src="images/nature2.jpg" alt="Mountain landscape" width="400">
</body>
</html>
```

**Activity Steps:**
1. Create images folder in Neocities
2. Upload 3-5 appropriate images
3. Create gallery.html
4. Add images with proper alt text
5. Include captions using paragraphs
#### Other Media Types (5 minutes)

1. **Audio**
   ```html
   <audio controls>
       <source src="music.mp3" type="audio/mpeg">
       Your browser doesn't support audio.
   </audio>
   ```

2. **Video**
   ```html
   <video width="320" height="240" controls>
       <source src="movie.mp4" type="video/mp4">
       Your browser doesn't support video.
   </video>
   ```

3. **Embedding YouTube**
   ```html
   <iframe width="560" height="315" 
           src="https://www.youtube.com/embed/VIDEO_ID" 
           allowfullscreen></iframe>
   ```

### Practice Extension (2 minutes)
- Add image links (images that are clickable)
- Create a figure with caption
- Try different image sizes

### Homework Assignment

Update your website with images:
1. Add at least one image to your homepage
2. Create a dedicated gallery or portfolio page
3. Ensure all images have descriptive alt text
4. Organize images in an "images" folder
5. Keep total page size under 5MB
6. Add your gallery to the navigation menu
### Image Guidelines for Students
- Only use images you have permission to use
- School-appropriate content only
- Consider Creative Commons images
- Always give credit when required
- Avoid copyright violations

### Assessment Rubric
- Proper img tag syntax: 2 points
- Meaningful alt text: 3 points
- Organized file structure: 2 points
- Appropriate image sizes: 2 points
- Gallery page creation: 1 point
- Total: 10 points

### Common Mistakes
- Missing alt attributes
- Images too large (slow loading)
- Broken image links
- Spaces in filenames
- Using images without permission
- Not organizing in folders

### Teacher Notes
- Prepare a folder of sample images students can use
- Demonstrate image compression tools
- Show how to check image file sizes
- Discuss copyright and fair use
- Review school policies on image use
- Consider having students take their own photos
- Show accessibility tools to demonstrate alt text importance

### Resources
- Unsplash.com (free stock photos)
- Pixabay.com (free images)
- TinyPNG.com (image compression)
- School media library