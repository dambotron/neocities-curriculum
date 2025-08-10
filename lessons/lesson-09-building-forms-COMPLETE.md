# Lesson 9: Building Forms - Creating Interactive Web Pages
## Duration: 45-50 minutes

### Learning Objectives
By the end of this lesson, students will be able to:
- Create accessible HTML forms with proper structure
- Use all major input types (text, email, password, number, date, etc.)
- Implement labels correctly for accessibility
- Create select dropdowns and textareas
- Use radio buttons and checkboxes appropriately
- Add HTML5 validation attributes
- Group form elements with fieldsets
- Understand form submission (without backend)
- Build professional contact and registration forms

### Materials Needed
- Text editor
- Web browser with developer tools
- Projector for demonstrations
- Printed form elements reference sheet
- Sample forms from popular websites
- Paper for sketching form layouts

### Key Vocabulary with Definitions
- **Form**: Container for user input elements
- **Input**: Field where users enter data
- **Label**: Text description for form controls
- **Placeholder**: Hint text inside input fields
- **Required**: Mandatory field that must be filled
- **Validation**: Checking if input meets requirements
- **Fieldset**: Groups related form elements
- **Legend**: Title for a fieldset
- **Submit**: Button to send form data
- **Method**: How form data is sent (GET/POST)
- **Action**: Where form data is sent

---

## PART 1: I DO (Teacher Demonstration) - 15 minutes

### Understanding Form Basics (5 minutes)

**Teacher Script:**
"Forms are how users communicate with websites! Every time you log in, sign up, or send a message online, you're using a form. Today, you'll learn to build forms that are both functional AND accessible!"
**[CREATE new file: forms-demo.html]**

**Basic Form Structure:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>HTML Forms Demo</title>
</head>
<body>
    <h1>Understanding HTML Forms</h1>
    
    <!-- SIMPLEST FORM -->
    <h2>1. Basic Form Structure</h2>
    <form>
        <label for="username">Username:</label>
        <input type="text" id="username" name="username">
        
        <button type="submit">Submit</button>
    </form>
```

"Let's decode this:
- `<form>` = Container for all form elements
- `<label>` = Describes the input (CRUCIAL for accessibility!)
- `for="username"` = Connects label to input with id="username"
- `<input>` = Where users type
- `type="text"` = Defines what kind of input
- `name="username"` = Identifies data when submitted
- `id="username"` = Connects to label
- Labels and inputs are PARTNERS - always connect them!"

### All Input Types Explained (10 minutes)

**[ADD comprehensive input examples]**

```html
    <!-- TEXT INPUTS -->
    <h2>2. Text Input Types</h2>
    <form>
        <!-- Basic Text -->
        <label for="fullname">Full Name:</label>
        <input type="text" id="fullname" name="fullname" 
               placeholder="John Smith" required>
        <br><br>        
        <!-- Email (with validation) -->
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" 
               placeholder="name@example.com" required>
        <br><br>
        
        <!-- Password (hidden text) -->
        <label for="password">Password:</label>
        <input type="password" id="password" name="password" 
               minlength="8" required>
        <br><br>
        
        <!-- Search -->
        <label for="search">Search:</label>
        <input type="search" id="search" name="search" 
               placeholder="Search...">
        <br><br>
        
        <!-- URL -->
        <label for="website">Website:</label>
        <input type="url" id="website" name="website" 
               placeholder="https://example.com">
        <br><br>
        
        <!-- Telephone -->
        <label for="phone">Phone:</label>
        <input type="tel" id="phone" name="phone" 
               placeholder="555-123-4567" 
               pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}">
    </form>
```

"Each input type has special features:
- `email` = Validates email format automatically
- `password` = Hides characters for security
- `search` = May show search icon on mobile
- `url` = Validates web addresses
- `tel` = Shows number pad on mobile
- `placeholder` = Gray hint text (NOT a label substitute!)
- `required` = Must be filled before submitting
- `minlength/maxlength` = Character limits
- `pattern` = Custom validation with regex"
```html
    <!-- NUMBER AND RANGE INPUTS -->
    <h2>3. Number and Range Inputs</h2>
    <form>
        <!-- Number -->
        <label for="age">Age:</label>
        <input type="number" id="age" name="age" 
               min="13" max="120" step="1" required>
        <br><br>
        
        <!-- Range (slider) -->
        <label for="volume">Volume:</label>
        <input type="range" id="volume" name="volume" 
               min="0" max="100" value="50">
        <output for="volume">50</output>
        <br><br>
    </form>
    
    <!-- DATE AND TIME INPUTS -->
    <h2>4. Date and Time Inputs</h2>
    <form>
        <!-- Date -->
        <label for="birthday">Birthday:</label>
        <input type="date" id="birthday" name="birthday" 
               min="1900-01-01" max="2024-12-31">
        <br><br>
        
        <!-- Time -->
        <label for="appointment">Appointment Time:</label>
        <input type="time" id="appointment" name="appointment">
        <br><br>
        
        <!-- DateTime-Local -->
        <label for="meeting">Meeting:</label>
        <input type="datetime-local" id="meeting" name="meeting">
        <br><br>
        
        <!-- Month -->
        <label for="gradmonth">Graduation Month:</label>
        <input type="month" id="gradmonth" name="gradmonth">
        <br><br>
        
        <!-- Week -->        <label for="week">Week:</label>
        <input type="week" id="week" name="week">
    </form>
    
    <!-- CHOICE INPUTS -->
    <h2>5. Checkboxes and Radio Buttons</h2>
    <form>
        <!-- Checkboxes (multiple selections) -->
        <fieldset>
            <legend>Select Your Interests (check all that apply):</legend>
            
            <input type="checkbox" id="sports" name="interests" value="sports">
            <label for="sports">Sports</label><br>
            
            <input type="checkbox" id="music" name="interests" value="music" checked>
            <label for="music">Music</label><br>
            
            <input type="checkbox" id="art" name="interests" value="art">
            <label for="art">Art</label><br>
            
            <input type="checkbox" id="tech" name="interests" value="tech">
            <label for="tech">Technology</label>
        </fieldset>
        
        <!-- Radio Buttons (single selection) -->
        <fieldset>
            <legend>Select Your Grade Level:</legend>
            
            <input type="radio" id="freshman" name="grade" value="9" required>
            <label for="freshman">Freshman</label><br>
            
            <input type="radio" id="sophomore" name="grade" value="10">
            <label for="sophomore">Sophomore</label><br>
            
            <input type="radio" id="junior" name="grade" value="11">
            <label for="junior">Junior</label><br>
            
            <input type="radio" id="senior" name="grade" value="12">
            <label for="senior">Senior</label>
        </fieldset>
    </form>
```
"Key differences:
- **Checkboxes** = Multiple selections allowed
- **Radio buttons** = Only ONE selection
- **Same name** = Groups radio buttons together
- **Fieldset** = Visual grouping with border
- **Legend** = Title for the group
- **checked** = Pre-selected option"

```html
    <!-- DROPDOWN AND TEXTAREA -->
    <h2>6. Dropdown Menus and Text Areas</h2>
    <form>
        <!-- Select Dropdown -->
        <label for="country">Country:</label>
        <select id="country" name="country" required>
            <option value="">--Please choose--</option>
            <option value="usa">United States</option>
            <option value="canada">Canada</option>
            <option value="mexico">Mexico</option>
            <option value="uk">United Kingdom</option>
            <option value="other">Other</option>
        </select>
        <br><br>
        
        <!-- Multiple Selection -->
        <label for="languages">Languages (hold Ctrl/Cmd to select multiple):</label>
        <select id="languages" name="languages" multiple size="5">
            <option value="english">English</option>
            <option value="spanish">Spanish</option>
            <option value="french">French</option>
            <option value="chinese">Chinese</option>
            <option value="arabic">Arabic</option>
        </select>
        <br><br>
        
        <!-- Textarea -->
        <label for="message">Your Message:</label><br>
        <textarea id="message" name="message" 
                  rows="5" cols="50" 
                  placeholder="Type your message here..."
                  maxlength="500" required></textarea>    </form>
    
    <!-- OTHER INPUTS -->
    <h2>7. Special Input Types</h2>
    <form>
        <!-- Color Picker -->
        <label for="favcolor">Favorite Color:</label>
        <input type="color" id="favcolor" name="favcolor" value="#ff0000">
        <br><br>
        
        <!-- File Upload -->
        <label for="avatar">Upload Profile Picture:</label>
        <input type="file" id="avatar" name="avatar" 
               accept="image/png, image/jpeg">
        <br><br>
        
        <!-- Hidden Field (not visible to users) -->
        <input type="hidden" name="form_id" value="contact_form_v1">
    </form>
    
    <!-- BUTTONS -->
    <h2>8. Form Buttons</h2>
    <form>
        <!-- Submit Button (sends form) -->
        <button type="submit">Submit Form</button>
        
        <!-- Reset Button (clears form) -->
        <button type="reset">Clear Form</button>
        
        <!-- Regular Button (needs JavaScript) -->
        <button type="button">Click Me</button>
        
        <!-- Input Submit (older style) -->
        <input type="submit" value="Send">
        
        <!-- Input Reset -->
        <input type="reset" value="Reset">
    </form>
</body>
</html>
```

---
## PART 2: WE DO (Guided Practice) - 20 minutes

### Building a Contact Form Together (10 minutes)

**Teacher Script:**
"Let's build a professional contact form that you might see on any business website. We'll use proper accessibility and validation!"

**Step 1: Plan the Form**
"First, let's plan what we need:
- Name field (required)
- Email field (required, validated)
- Phone field (optional)
- Subject dropdown
- Message textarea (required)
- Submit button

CHECKPOINT: Everyone sketch this form on paper!"

**Step 2: Build the Complete Form**

"Create `contact-form.html` and follow along:"

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contact Us | Your Business Name</title>
    <style>
        /* Basic styling to make form readable */
        body { font-family: Arial, sans-serif; max-width: 600px; margin: 40px auto; padding: 20px; }
        form { background: #f4f4f4; padding: 20px; border-radius: 8px; }
        label { display: block; margin-top: 10px; font-weight: bold; }
        input, select, textarea { width: 100%; padding: 8px; margin-top: 5px; border: 1px solid #ddd; border-radius: 4px; box-sizing: border-box; }
        button { background: #333; color: white; padding: 10px 20px; border: none; border-radius: 4px; cursor: pointer; margin-top: 10px; }
        button:hover { background: #555; }
        .required { color: red; }
        fieldset { margin: 20px 0; border: 1px solid #ddd; border-radius: 4px; }
        legend { font-weight: bold; padding: 0 10px; }    </style>
</head>
<body>
    <h1>Contact Us</h1>
    <p>We'd love to hear from you! Fill out the form below and we'll get back to you within 24 hours.</p>
    
    <form action="#" method="POST">
        <!-- Personal Information -->
        <fieldset>
            <legend>Your Information</legend>
            
            <label for="name">
                Full Name <span class="required">*</span>
            </label>
            <input type="text" 
                   id="name" 
                   name="name" 
                   placeholder="John Smith"
                   required
                   autofocus>
            
            <label for="email">
                Email Address <span class="required">*</span>
            </label>
            <input type="email" 
                   id="email" 
                   name="email" 
                   placeholder="name@example.com"
                   required>
            
            <label for="phone">
                Phone Number (optional)
            </label>
            <input type="tel" 
                   id="phone" 
                   name="phone" 
                   placeholder="(555) 123-4567"
                   pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}">
        </fieldset>
```

"Key points so far:
- Fieldset groups related inputs
- Red asterisk shows required fields visually
- 'required' attribute enforces it
- 'autofocus' puts cursor in first field
- Pattern validates phone format"
```html
        <!-- Message Details -->
        <fieldset>
            <legend>Your Message</legend>
            
            <label for="subject">
                Subject <span class="required">*</span>
            </label>
            <select id="subject" name="subject" required>
                <option value="">-- Please select --</option>
                <option value="general">General Inquiry</option>
                <option value="support">Technical Support</option>
                <option value="billing">Billing Question</option>
                <option value="feedback">Feedback</option>
                <option value="other">Other</option>
            </select>
            
            <label for="priority">
                Priority Level
            </label>
            <select id="priority" name="priority">
                <option value="low">Low</option>
                <option value="normal" selected>Normal</option>
                <option value="high">High</option>
                <option value="urgent">Urgent</option>
            </select>
            
            <label for="message">
                Your Message <span class="required">*</span>
            </label>
            <textarea id="message" 
                      name="message" 
                      rows="6" 
                      placeholder="Please provide details about your inquiry..."
                      minlength="10"
                      maxlength="1000"
                      required></textarea>
            <small>10-1000 characters</small>
        </fieldset>
        
        <!-- Additional Options -->
        <fieldset>
            <legend>Additional Options</legend>            
            <input type="checkbox" 
                   id="newsletter" 
                   name="newsletter" 
                   value="yes">
            <label for="newsletter" style="display: inline; font-weight: normal;">
                Subscribe to our newsletter
            </label>
            <br><br>
            
            <input type="checkbox" 
                   id="copy" 
                   name="copy" 
                   value="yes">
            <label for="copy" style="display: inline; font-weight: normal;">
                Send me a copy of this message
            </label>
        </fieldset>
        
        <!-- Form Actions -->
        <button type="submit">Send Message</button>
        <button type="reset">Clear Form</button>
        
        <p><small>Fields marked with <span class="required">*</span> are required.</small></p>
    </form>
</body>
</html>
```

### Building a Registration Form (10 minutes)

"Now let's create a more complex registration form with validation:"

```html
    <h1>Student Registration Form</h1>
    
    <form action="#" method="POST">
        <!-- Account Information -->
        <fieldset>
            <legend>Account Setup</legend>
            
            <label for="username">
                Choose Username <span class="required">*</span>
            </label>
            <input type="text"                   id="username"
                   name="username"
                   pattern="[a-z0-9]{4,16}"
                   title="4-16 lowercase letters and numbers only"
                   placeholder="johndoe123"
                   required>
            <small>4-16 characters, lowercase letters and numbers only</small>
            
            <label for="reg-email">
                Email Address <span class="required">*</span>
            </label>
            <input type="email"
                   id="reg-email"
                   name="email"
                   placeholder="student@school.edu"
                   required>
            
            <label for="reg-password">
                Password <span class="required">*</span>
            </label>
            <input type="password"
                   id="reg-password"
                   name="password"
                   minlength="8"
                   maxlength="20"
                   pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
                   title="Must contain at least one number, one uppercase and lowercase letter, and at least 8 characters"
                   required>
            <small>8-20 characters, must include uppercase, lowercase, and number</small>
            
            <label for="confirm-password">
                Confirm Password <span class="required">*</span>
            </label>
            <input type="password"
                   id="confirm-password"
                   name="confirm_password"
                   required>
        </fieldset>
        
        <!-- Personal Information -->
        <fieldset>
            <legend>Personal Details</legend>            
            <label for="firstname">
                First Name <span class="required">*</span>
            </label>
            <input type="text"
                   id="firstname"
                   name="firstname"
                   required>
            
            <label for="lastname">
                Last Name <span class="required">*</span>
            </label>
            <input type="text"
                   id="lastname"
                   name="lastname"
                   required>
            
            <label for="birthdate">
                Date of Birth <span class="required">*</span>
            </label>
            <input type="date"
                   id="birthdate"
                   name="birthdate"
                   min="1950-01-01"
                   max="2011-12-31"
                   required>
            
            <fieldset>
                <legend>Gender</legend>
                <input type="radio" id="male" name="gender" value="male">
                <label for="male" style="display: inline; font-weight: normal;">Male</label><br>
                
                <input type="radio" id="female" name="gender" value="female">
                <label for="female" style="display: inline; font-weight: normal;">Female</label><br>
                
                <input type="radio" id="other-gender" name="gender" value="other">
                <label for="other-gender" style="display: inline; font-weight: normal;">Other</label><br>
                
                <input type="radio" id="prefer-not" name="gender" value="prefer-not" checked>
                <label for="prefer-not" style="display: inline; font-weight: normal;">Prefer not to say</label>
            </fieldset>
        </fieldset>        
        <!-- Preferences -->
        <fieldset>
            <legend>Preferences</legend>
            
            <label for="course">
                Select Course <span class="required">*</span>
            </label>
            <select id="course" name="course" required>
                <option value="">-- Select Course --</option>
                <optgroup label="Web Development">
                    <option value="html">HTML Fundamentals</option>
                    <option value="css">CSS Styling</option>
                    <option value="js">JavaScript Basics</option>
                </optgroup>
                <optgroup label="Programming">
                    <option value="python">Python Programming</option>
                    <option value="java">Java Development</option>
                    <option value="cpp">C++ Programming</option>
                </optgroup>
            </select>
            
            <label>Interests (check all that apply):</label>
            <input type="checkbox" id="web" name="interests[]" value="web">
            <label for="web" style="display: inline; font-weight: normal;">Web Design</label><br>
            
            <input type="checkbox" id="mobile" name="interests[]" value="mobile">
            <label for="mobile" style="display: inline; font-weight: normal;">Mobile Apps</label><br>
            
            <input type="checkbox" id="games" name="interests[]" value="games">
            <label for="games" style="display: inline; font-weight: normal;">Game Development</label><br>
            
            <input type="checkbox" id="ai" name="interests[]" value="ai">
            <label for="ai" style="display: inline; font-weight: normal;">Artificial Intelligence</label>
        </fieldset>
        
        <!-- Terms and Submit -->
        <fieldset>
            <legend>Terms and Conditions</legend>
            
            <input type="checkbox" id="terms" name="terms" required>            <label for="terms" style="display: inline; font-weight: normal;">
                I agree to the <a href="#">terms and conditions</a> <span class="required">*</span>
            </label>
        </fieldset>
        
        <button type="submit">Register</button>
        <button type="reset">Clear Form</button>
    </form>
```

**Teacher Script:**
"Notice the advanced features:
- Pattern attribute for custom validation
- Title attribute explains requirements
- Optgroup in select for grouping
- Nested fieldsets for sub-sections
- Array notation [] for multiple values
- Links within labels for terms"

---

## PART 3: YOU DO (Independent Practice) - 10 minutes

### Student Activity: Create a Survey Form

**Instructions:**
"Create a comprehensive survey form about student life. Use various input types and proper accessibility!"

**Required Tasks:**
1. ✅ Create `survey-form.html` with proper HTML5 structure
2. ✅ Include at least 5 different input types
3. ✅ Use fieldsets to group related questions
4. ✅ Add proper labels for ALL inputs (connected with for/id)
5. ✅ Include required fields with validation
6. ✅ Add at least one set of radio buttons
7. ✅ Add at least one set of checkboxes
8. ✅ Include a select dropdown with options
9. ✅ Add a textarea for comments
10. ✅ Include placeholder text and helpful hints
11. ✅ Add submit and reset buttons
12. ✅ Use HTML5 validation attributes (required, min, max, pattern)

**Bonus Challenges:**
- Add a file upload for submitting documents
- Create a multi-step form appearance with fieldsets
- Include a progress meter showing form completion
- Add autocomplete attributes for common fields
- Style the form with CSS (preview of next unit)
### Complete Solution Example:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Student life survey to improve campus experience">
    <title>Student Life Survey | Lincoln High School</title>
    <style>
        * { box-sizing: border-box; }
        body { 
            font-family: 'Segoe UI', Arial, sans-serif; 
            max-width: 700px; 
            margin: 0 auto; 
            padding: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }
        .form-container {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
        }
        h1 { color: #333; margin-bottom: 10px; }
        p { color: #666; margin-bottom: 30px; }
        fieldset { 
            margin: 25px 0; 
            padding: 20px;
            border: 2px solid #e0e0e0; 
            border-radius: 8px; 
        }
        legend { 
            font-weight: bold; 
            color: #5a67d8;
            padding: 0 10px; 
        }
        label { 
            display: block; 
            margin-top: 15px; 
            color: #333;
            font-weight: 500;
        }        input[type="text"],
        input[type="email"],
        input[type="tel"],
        input[type="number"],
        input[type="date"],
        input[type="time"],
        select,
        textarea {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border: 2px solid #e0e0e0;
            border-radius: 5px;
            font-size: 16px;
            transition: border-color 0.3s;
        }
        input:focus,
        select:focus,
        textarea:focus {
            outline: none;
            border-color: #5a67d8;
        }
        .radio-group,
        .checkbox-group {
            margin: 10px 0;
        }
        input[type="radio"],
        input[type="checkbox"] {
            margin-right: 8px;
        }
        .inline-label {
            display: inline;
            font-weight: normal;
            margin-left: 5px;
        }
        button {
            padding: 12px 30px;
            margin: 10px 10px 10px 0;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            transition: transform 0.2s;
        }
        button[type="submit"] {
            background: #5a67d8;
            color: white;
        }        button[type="reset"] {
            background: #e0e0e0;
            color: #333;
        }
        button:hover {
            transform: translateY(-2px);
        }
        .required { color: #e53e3e; }
        small { color: #718096; display: block; margin-top: 5px; }
        .progress-bar {
            height: 20px;
            background: #e0e0e0;
            border-radius: 10px;
            margin-bottom: 20px;
        }
        .progress-fill {
            height: 100%;
            background: #5a67d8;
            border-radius: 10px;
            width: 0%;
            transition: width 0.3s;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h1>📚 Student Life Survey</h1>
        <p>Help us improve your school experience! This survey takes about 5 minutes.</p>
        
        <!-- Progress indicator -->
        <div class="progress-bar">
            <div class="progress-fill" style="width: 25%;"></div>
        </div>
        
        <form action="#" method="POST" enctype="multipart/form-data">
            <!-- Section 1: Basic Information -->
            <fieldset>
                <legend>1. Basic Information</legend>
                
                <label for="student-name">
                    Full Name <span class="required">*</span>
                </label>
                <input type="text" 
                       id="student-name" 
                       name="student_name"                       placeholder="Jane Doe"
                       autocomplete="name"
                       required>
                
                <label for="student-id">
                    Student ID <span class="required">*</span>
                </label>
                <input type="text" 
                       id="student-id" 
                       name="student_id"
                       pattern="[0-9]{6}"
                       placeholder="123456"
                       title="6-digit student ID"
                       required>
                <small>Enter your 6-digit student ID number</small>
                
                <label for="student-email">
                    School Email <span class="required">*</span>
                </label>
                <input type="email" 
                       id="student-email" 
                       name="email"
                       placeholder="student@lincolnhs.edu"
                       autocomplete="email"
                       required>
                
                <label for="grade-level">
                    Current Grade Level <span class="required">*</span>
                </label>
                <select id="grade-level" name="grade_level" required>
                    <option value="">-- Select Grade --</option>
                    <option value="9">9th Grade (Freshman)</option>
                    <option value="10">10th Grade (Sophomore)</option>
                    <option value="11">11th Grade (Junior)</option>
                    <option value="12">12th Grade (Senior)</option>
                </select>
            </fieldset>
            
            <!-- Section 2: Academic Experience -->
            <fieldset>
                <legend>2. Academic Experience</legend>                
                <label for="gpa">
                    Current GPA (optional)
                </label>
                <input type="number" 
                       id="gpa" 
                       name="gpa"
                       min="0.0"
                       max="4.0"
                       step="0.1"
                       placeholder="3.5">
                
                <label for="study-hours">
                    Hours spent studying per week <span class="required">*</span>
                </label>
                <input type="range" 
                       id="study-hours" 
                       name="study_hours"
                       min="0"
                       max="40"
                       value="10"
                       oninput="this.nextElementSibling.value = this.value"
                       required>
                <output>10</output> hours
                
                <label>Favorite subjects (check all that apply):</label>
                <div class="checkbox-group">
                    <input type="checkbox" id="math" name="subjects[]" value="math">
                    <label for="math" class="inline-label">Mathematics</label><br>
                    
                    <input type="checkbox" id="science" name="subjects[]" value="science">
                    <label for="science" class="inline-label">Science</label><br>
                    
                    <input type="checkbox" id="english" name="subjects[]" value="english">
                    <label for="english" class="inline-label">English</label><br>
                    
                    <input type="checkbox" id="history" name="subjects[]" value="history">
                    <label for="history" class="inline-label">History</label><br>
                    
                    <input type="checkbox" id="arts" name="subjects[]" value="arts">
                    <label for="arts" class="inline-label">Arts</label><br>                    
                    <input type="checkbox" id="pe" name="subjects[]" value="pe">
                    <label for="pe" class="inline-label">Physical Education</label><br>
                    
                    <input type="checkbox" id="tech" name="subjects[]" value="tech">
                    <label for="tech" class="inline-label">Technology/Computer Science</label>
                </div>
                
                <label>How satisfied are you with your classes?</label>
                <div class="radio-group">
                    <input type="radio" id="very-satisfied" name="satisfaction" value="5" required>
                    <label for="very-satisfied" class="inline-label">Very Satisfied</label><br>
                    
                    <input type="radio" id="satisfied" name="satisfaction" value="4">
                    <label for="satisfied" class="inline-label">Satisfied</label><br>
                    
                    <input type="radio" id="neutral" name="satisfaction" value="3">
                    <label for="neutral" class="inline-label">Neutral</label><br>
                    
                    <input type="radio" id="dissatisfied" name="satisfaction" value="2">
                    <label for="dissatisfied" class="inline-label">Dissatisfied</label><br>
                    
                    <input type="radio" id="very-dissatisfied" name="satisfaction" value="1">
                    <label for="very-dissatisfied" class="inline-label">Very Dissatisfied</label>
                </div>
            </fieldset>
            
            <!-- Section 3: Campus Life -->
            <fieldset>
                <legend>3. Campus Life</legend>
                
                <label for="lunch-time">
                    Preferred lunch time
                </label>
                <input type="time" 
                       id="lunch-time" 
                       name="lunch_time"
                       min="11:00"
                       max="13:30">
                                <label for="activities">
                    Extracurricular Activities
                </label>
                <select id="activities" name="activities[]" multiple size="5">
                    <option value="sports">Sports Teams</option>
                    <option value="music">Music/Band</option>
                    <option value="drama">Drama/Theater</option>
                    <option value="debate">Debate Club</option>
                    <option value="stem">STEM Club</option>
                    <option value="volunteer">Volunteer Work</option>
                    <option value="student-gov">Student Government</option>
                    <option value="yearbook">Yearbook</option>
                </select>
                <small>Hold Ctrl/Cmd to select multiple activities</small>
                
                <label for="transport">
                    How do you get to school? <span class="required">*</span>
                </label>
                <select id="transport" name="transport" required>
                    <option value="">-- Select Transportation --</option>
                    <option value="walk">Walk</option>
                    <option value="bike">Bicycle</option>
                    <option value="bus">School Bus</option>
                    <option value="car">Car (self/parent)</option>
                    <option value="public">Public Transit</option>
                    <option value="other">Other</option>
                </select>
            </fieldset>
            
            <!-- Section 4: Feedback -->
            <fieldset>
                <legend>4. Feedback & Suggestions</legend>
                
                <label for="improvements">
                    What would you like to see improved? <span class="required">*</span>
                </label>
                <textarea id="improvements" 
                          name="improvements"
                          rows="5"                          placeholder="Share your ideas for improving student life..."
                          minlength="20"
                          maxlength="500"
                          required></textarea>
                <small>20-500 characters</small>
                
                <label for="recommend">
                    Would you recommend our school to others?
                </label>
                <select id="recommend" name="recommend">
                    <option value="definitely">Definitely Yes</option>
                    <option value="probably">Probably Yes</option>
                    <option value="unsure" selected>Not Sure</option>
                    <option value="probably-not">Probably Not</option>
                    <option value="definitely-not">Definitely Not</option>
                </select>
                
                <label for="school-color">
                    What should be our new school color?
                </label>
                <input type="color" 
                       id="school-color" 
                       name="school_color"
                       value="#5a67d8">
                
                <label for="photo-upload">
                    Upload a photo for the yearbook (optional)
                </label>
                <input type="file" 
                       id="photo-upload" 
                       name="yearbook_photo"
                       accept="image/png, image/jpeg, image/jpg">
                <small>Accepted formats: JPG, PNG (max 5MB)</small>
            </fieldset>
            
            <!-- Section 5: Contact Preferences -->
            <fieldset>
                <legend>5. Follow-up</legend>
                
                <input type="checkbox" id="contact-me" name="contact_me" value="yes">
                <label for="contact-me" class="inline-label">                    I'd like to be contacted about survey results
                </label><br><br>
                
                <input type="checkbox" id="anonymous" name="anonymous" value="yes">
                <label for="anonymous" class="inline-label">
                    Submit my responses anonymously
                </label>
            </fieldset>
            
            <!-- Hidden field for tracking -->
            <input type="hidden" name="survey_version" value="2024.1">
            <input type="hidden" name="submission_date" value="2024-01-25">
            
            <!-- Submit buttons -->
            <button type="submit">📤 Submit Survey</button>
            <button type="reset">🔄 Clear All</button>
            
            <p><small>Your responses help us improve the school experience for all students. 
                      Data is kept confidential and used only for statistical purposes.</small></p>
        </form>
    </div>
</body>
</html>
```

---

## Assessment & Closing (5 minutes)

### Exit Ticket Questions

1. **What's the difference between the `id` and `name` attributes on form inputs?**
   - Answer: `id` connects the input to its label (for accessibility), `name` identifies the data when the form is submitted to a server.

2. **When should you use radio buttons vs checkboxes?**
   - Answer: Radio buttons when only ONE option can be selected (like choosing a grade level), checkboxes when MULTIPLE options can be selected (like choosing interests).

3. **Write the HTML for a required email input with a label:**
   - Answer: 
   ```html
   <label for="email">Email:</label>
   <input type="email" id="email" name="email" required>
   ```
4. **What does the `required` attribute do?**
   - Answer: It prevents the form from being submitted unless that field is filled out, providing basic client-side validation.

5. **Why is connecting labels to inputs important?**
   - Answer: It improves accessibility (screen readers can identify fields), and allows users to click the label to focus/select the input.

### Success Criteria Checklist
- [ ] Created valid form structure (2 pts)
- [ ] Used proper labels connected with for/id (3 pts)
- [ ] Included multiple input types (3 pts)
- [ ] Used fieldsets to group elements (2 pts)
- [ ] Added validation attributes (2 pts)
- [ ] Implemented radio buttons correctly (2 pts)
- [ ] Implemented checkboxes correctly (2 pts)
- [ ] Included select dropdown (2 pts)
- [ ] Added textarea with attributes (2 pts)
**Total: ___/20 points**

### Homework Assignment

**Create a "Job Application Form" (`job-application.html`):**

Requirements:
1. Create sections using fieldsets for:
   - Personal Information
   - Education
   - Work Experience
   - Skills
   - References
   - Additional Information
2. Include these input types:
   - Text, email, tel, date, number
   - Radio buttons for full-time/part-time preference
   - Checkboxes for available days
   - Select dropdown for position applying for
   - File upload for resume
   - Textarea for cover letter
3. Add proper validation:
   - Required fields marked and enforced
   - Pattern validation for phone numbers
   - Min/max for dates and numbers
4. Include helpful placeholder text
5. Add autocomplete attributes where appropriate
**Homework Solution Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Job Application Form | Tech Company</title>
    <style>
        body { font-family: Arial, sans-serif; max-width: 800px; margin: 0 auto; padding: 20px; }
        fieldset { margin: 20px 0; padding: 15px; border: 2px solid #ddd; border-radius: 5px; }
        legend { font-weight: bold; color: #333; }
        label { display: block; margin-top: 10px; }
        input, select, textarea { width: 100%; padding: 8px; margin-top: 5px; border: 1px solid #ddd; border-radius: 3px; box-sizing: border-box; }
        .required { color: red; }
        button { padding: 10px 20px; margin: 10px 5px; cursor: pointer; }
    </style>
</head>
<body>
    <h1>Job Application</h1>
    <p>Please complete all required fields marked with <span class="required">*</span></p>
    
    <form action="#" method="POST" enctype="multipart/form-data">
        <!-- Personal Information -->
        <fieldset>
            <legend>Personal Information</legend>
            
            <label for="full-name">Full Name <span class="required">*</span></label>
            <input type="text" id="full-name" name="full_name" required autocomplete="name">
            
            <label for="app-email">Email <span class="required">*</span></label>
            <input type="email" id="app-email" name="email" required autocomplete="email">
            
            <label for="app-phone">Phone <span class="required">*</span></label>
            <input type="tel" id="app-phone" name="phone" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" 
                   placeholder="555-123-4567" required autocomplete="tel">            
            <label for="dob">Date of Birth <span class="required">*</span></label>
            <input type="date" id="dob" name="date_of_birth" max="2006-12-31" required>
        </fieldset>
        
        <!-- Position & Availability -->
        <fieldset>
            <legend>Position & Availability</legend>
            
            <label for="position">Position Applying For <span class="required">*</span></label>
            <select id="position" name="position" required>
                <option value="">-- Select Position --</option>
                <optgroup label="Development">
                    <option value="frontend">Frontend Developer</option>
                    <option value="backend">Backend Developer</option>
                    <option value="fullstack">Full Stack Developer</option>
                </optgroup>
                <optgroup label="Design">
                    <option value="ui">UI Designer</option>
                    <option value="ux">UX Designer</option>
                </optgroup>
            </select>
            
            <fieldset>
                <legend>Employment Type Preference</legend>
                <input type="radio" id="fulltime" name="employment_type" value="fulltime" required>
                <label for="fulltime" style="display:inline">Full-time</label><br>
                <input type="radio" id="parttime" name="employment_type" value="parttime">
                <label for="parttime" style="display:inline">Part-time</label><br>
                <input type="radio" id="contract" name="employment_type" value="contract">
                <label for="contract" style="display:inline">Contract</label>
            </fieldset>
            
            <label>Available Days (check all):</label>
            <input type="checkbox" id="mon" name="days[]" value="monday">
            <label for="mon" style="display:inline">Monday</label><br>
            <input type="checkbox" id="tue" name="days[]" value="tuesday">
            <label for="tue" style="display:inline">Tuesday</label><br>            <input type="checkbox" id="wed" name="days[]" value="wednesday">
            <label for="wed" style="display:inline">Wednesday</label><br>
            <input type="checkbox" id="thu" name="days[]" value="thursday">
            <label for="thu" style="display:inline">Thursday</label><br>
            <input type="checkbox" id="fri" name="days[]" value="friday">
            <label for="fri" style="display:inline">Friday</label>
            
            <label for="start-date">Available Start Date <span class="required">*</span></label>
            <input type="date" id="start-date" name="start_date" min="2024-02-01" required>
        </fieldset>
        
        <!-- Education & Experience -->
        <fieldset>
            <legend>Education & Experience</legend>
            
            <label for="education">Highest Education <span class="required">*</span></label>
            <select id="education" name="education" required>
                <option value="">-- Select --</option>
                <option value="highschool">High School</option>
                <option value="associate">Associate Degree</option>
                <option value="bachelor">Bachelor's Degree</option>
                <option value="master">Master's Degree</option>
                <option value="phd">PhD</option>
            </select>
            
            <label for="experience">Years of Experience <span class="required">*</span></label>
            <input type="number" id="experience" name="experience" min="0" max="50" required>
            
            <label for="salary">Expected Salary (USD)</label>
            <input type="number" id="salary" name="salary" min="30000" max="200000" step="5000" placeholder="50000">
        </fieldset>
        
        <!-- Documents -->
        <fieldset>
            <legend>Documents</legend>
            
            <label for="resume">Upload Resume <span class="required">*</span></label>            <input type="file" id="resume" name="resume" accept=".pdf,.doc,.docx" required>
            
            <label for="cover-letter">Cover Letter <span class="required">*</span></label>
            <textarea id="cover-letter" name="cover_letter" rows="8" 
                      placeholder="Tell us why you're interested in this position..." 
                      minlength="100" maxlength="1000" required></textarea>
        </fieldset>
        
        <button type="submit">Submit Application</button>
        <button type="reset">Clear Form</button>
    </form>
</body>
</html>
```

---

## Teacher Notes & Tips

### Common Student Errors:
1. **Not connecting labels to inputs** - Missing for/id relationship
2. **Using same name for checkboxes** - Each needs unique name or array notation
3. **Using same name for unrelated radio buttons** - Only related options share names
4. **Forgetting closing tags** - Form and fieldset tags often left open
5. **Wrong input types** - Using text when email/tel/url would be better
6. **Missing required attribute** - Validation doesn't work without it
7. **Placeholder as label substitute** - Labels are required for accessibility
8. **Not testing form submission** - Check that data would be sent correctly

### Differentiation Strategies:

**For Struggling Students:**
- Start with a simple 3-field form
- Provide form template with structure
- Focus on text inputs before complex types
- Use visual diagrams of label-input connection
- Pair with stronger students

**For Advanced Students:**
- Add custom validation with pattern attribute
- Create multi-step form appearance
- Research autocomplete attribute values
- Add ARIA labels for better accessibility
- Style forms with advanced CSS
### Time Management:
- 0-5 min: Review homework and warm-up
- 5-15 min: I DO demonstrate all input types
- 15-25 min: WE DO contact form
- 25-35 min: WE DO registration form
- 35-45 min: YOU DO survey form
- 45-50 min: Assessment and homework

### Key Teaching Points:
- **Labels are CRUCIAL** - Never skip them
- **Accessibility first** - Forms must work for everyone
- **Validation helps users** - Prevent errors before submission
- **Fieldsets organize** - Group related inputs
- **Test on mobile** - Different keyboards for different types
- **Forms don't work alone** - Need server-side processing (explain concept)

### Real-World Applications:
- **Every website uses forms** - Login, signup, contact, checkout
- **Data collection** - Surveys, feedback, applications
- **User interaction** - Comments, reviews, messages
- **E-commerce** - Shopping carts, payment forms
- **Social media** - Posts, profiles, settings

### Accessibility Best Practices:
1. **Always use labels** - Never rely on placeholder alone
2. **Connect with for/id** - Explicit association
3. **Group with fieldsets** - Logical sections
4. **Mark required fields** - Both visually and with attribute
5. **Provide error messages** - Clear feedback
6. **Keyboard navigation** - Test without mouse
7. **Screen reader testing** - If possible, demonstrate

### Extension Activities:
1. Create a quiz form with scoring
2. Build a pizza order form with calculations
3. Design a event registration with date validation
4. Make a feedback form with star ratings
5. Create a search form with filters
6. Build a login/signup toggle form
### Form Security Note:
Explain to students that:
- Forms need server-side processing to actually work
- Never put sensitive data in hidden fields
- Validation in HTML can be bypassed - servers must validate too
- GET vs POST methods (conceptual understanding)
- Forms on Neocities won't actually submit anywhere (static hosting)

### Assessment Rubric:

| Criteria | Excellent (3) | Good (2) | Needs Work (1) | Missing (0) |
|----------|--------------|-----------|----------------|-------------|
| Form Structure | Complete with fieldsets | Basic structure | Some organization | Poor structure |
| Input Types | 8+ different types | 5-7 types | 3-4 types | Less than 3 |
| Labels | All inputs labeled correctly | Most labeled | Some labeled | Few/no labels |
| Validation | Multiple validation types | Basic validation | Minimal | None |
| Accessibility | Excellent | Good | Fair | Poor |

### Resources:
- MDN Forms Guide: https://developer.mozilla.org/en-US/docs/Learn/Forms
- HTML5 Input Types: https://www.w3schools.com/html/html_form_input_types.asp
- Form Validation: https://www.w3schools.com/js/js_validation.asp
- WebAIM Forms: https://webaim.org/techniques/forms/

### Quick Reference for Board:
```
FORM STRUCTURE:
<form action="url" method="POST">
    <label for="id">Text:</label>
    <input type="text" id="id" name="name">
    <button type="submit">Submit</button>
</form>

INPUT TYPES:
Text: text, email, password, search, url, tel
Numbers: number, range
Dates: date, time, datetime-local, month, week
Choices: radio, checkbox
Other: color, file, hidden

ATTRIBUTES:
required - must fill
placeholder - hint text
min/max - limits
pattern - regex validation
autocomplete - browser hints
```

### Troubleshooting Guide:
- **Form not submitting**: Check for required fields
- **Radio buttons all selected**: Ensure same name attribute
- **Checkboxes not working**: Each needs unique id
- **Labels not clicking**: Check for/id match
- **Validation not working**: Check input type and attributes
- **Dropdown not showing**: Check option tags are closed

**End of Lesson 9**