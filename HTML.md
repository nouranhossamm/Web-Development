# Introduction to HTML ###

### Hypertext Markup Language

**By: Nouran Hosam**

## What HTML consists of

HTML consists of elements that work together to create a web page.

### HTML Elements

There are two types of HTML elements:

1. **Pair Element:** `<tagname> content </tagname>`
2. **Empty Element:** `<tagname />` or `<tagname>`

### Main Elements

Elements that must be added in any HTML file:

1. `<html></html>`: Holds all HTML page elements.
2. `<head></head>`: Contains the page title and metadata.
3. `<body></body>`: Contains all HTML elements that describe the content.

### Nesting in HTML

Nesting means putting an element inside another element. The main elements are nested like this:

```html
<html lang="en">
  <head></head>
  <body></body>
</html>
```

### DOCTYPE Declaration

Use `<!DOCTYPE html>` at the first line to let the browser know the HTML version is 5.

Example:

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body></body>
</html>
```

### Title Element

`<title>title here</title>` defines a title in the browser tab, provides a title for the page when it is added to favorites, and displays a title for the page in search engine results.

Example:

```html
<head>
  <title>My Project</title>
</head>
```

### Heading Elements

Use `<h1>` to `<h6>` for headings, with `<h1>` being the most important.

Example:

```html
<body>
  <h1>heading1</h1>
  <h2>heading2</h2>
  <h3>heading3</h3>
  <h4>heading4</h4>
  <h5>heading5</h5>
  <h6>heading6</h6>
</body>
```

### Paragraph Element

`<p>paragraph here</p>` is used to add a paragraph.

Example:

```html
<p>
  Web design is the process of creating visually appealing and functional websites.
  It involves layout, color scheme, graphics, fonts, and content.
  Effective web design ensures a user-friendly experience,
  enhances brand recognition, and boosts engagement.
  It combines aesthetics with usability to create an impactful online presence.
</p>
```

### Break Line Element

`<br>` is used to add a break line anywhere in the document.

Example:

```html
<p>this is paragraph, <br> this is paragraph</p>
```

### Horizontal Rule Element

`<hr>` is used to add a horizontal rule between elements.

Example:

```html
<p>This is a paragraph, this is paragraph</p>
<hr>
<p>This is a paragraph, this is paragraph</p>
```

### Preformatted Text Element

`<pre>` is used to add text without removing white spaces.

Example:

```html
<p>This is a paragraph, this is a paragraph</p>
<pre>This is a paragraph, this is a paragraph</pre>
```

### **HTML `<code>` Tag**

- **Definition:** The `<code>` tag is used to display a fragment of computer code in a web page.
- **Appearance:** By default, text inside `<code>` is shown in a **monospace font**.
- **Best Practice:** Often wrapped inside `<pre>` to preserve formatting like spaces and line breaks.

---

### **Examples**

1. **Inline Code Example**

```html
<p>To print in Java use: <code>System.out.println("Hello World");</code></p>
```

**Result:**

To print in Java use: `System.out.println("Hello World");`

---

1. **Block Code Example with `<pre>`**

```html
<pre>
<code>
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
</code>
</pre>
```

**Result:**

```
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

### **Quotations & Citations Tags**

- `<q>` → short inline quotation (adds quotation marks automatically)
- `<blockquote>` → long quotation (usually indented)

**Example:**

```html
<p>Einstein once said: <q>Imagination is more important than knowledge.</q></p>

<blockquote>
  "The greatest glory in living lies not in never falling, but in rising every time we fall."
  – Nelson Mandela
</blockquote>
```

### **Word Breaks**

- `<wbr>` → word break opportunity (used in long words/links to allow line breaks without inserting visible characters)

**Example:**

```html
<p>
  Visit our website at:
  www.verylongdomainname<wbr>.com/withaverylongpath<wbr>/andaverylongfile.html
</p>
```

### **Bi-Directional Text**

- `<bdi>` → *Bi-Directional Isolation* → isolates a span of text that might have a different text direction from the surrounding text

**Example:**

```html
<ul>
  <li>User: <bdi>إيمان</bdi> – Score: 90</li>
  <li>User: <bdi>John</bdi> – Score: 85</li>
</ul>
```

## HTML Styling Tags

1. `<b>`, `<strong>`: **Bold text**
2. `<i>`, `<em>`: *Italic text*
3. `<small>`: Smaller font size
4. `<del>`: ~~Line-through text~~
5. `<ins>`: <ins>Underlined text</ins>
6. `<sub>`: Subscript text
7. `<sup>`: Superscript text
8. `<mark>`: <mark>Highlighted text</mark>
9. `<u>`: <u>Underlined text</u>

## Links

```html
<a> is used to add a link to a page.
Use the `href` attribute to specify the URL and the `target` attribute to open the link in a new tab.
```

Example:

```html
<a href="https://www.google.com" title="Go to Google">click here</a>
<a href="https://www.google.com" target="_blank">click here</a>
<a href="mailto:info@example.com" title="Send Email">Email Us</a>
<a href="#contact">Go to Contact Section</a>
```

Example section with id:

```html
<section id="contact">
  <h2>Contact Section</h2>
  <p>Here is the contact section.</p>
</section>
```

## Images

`<img src="" alt="" />` is used to insert an image.

Example:

```html
<img src="1.jpg" alt="this image about tourism">
```

Specify the correct path if the image is not next to the HTML file.

Example:

```html
<img src="images/1.jpg" alt="this image about tourism">
```

## Buttons

`<button>` is used to add a button.

Example:

```html
<button>click here</button>
```

## HTML Comments

HTML comments are not displayed in the browser, so if you type code inside it, it will not be displayed.

Example:

```html
<!-- <h1>Welcome</h1> -->
```

Comments can be used as reminders in your HTML code.

Example:

```html
<p>Welcome</p>
<!-- Remember to do something -->
```

## Importance of Comments

Comments are very important for understanding and maintaining the code.

## HTML Lists

There are three types of lists in HTML:

1. Unordered list (with bullets)
2. Ordered list
3. Description list

### Unordered Lists

- Use `<ul></ul>` to start a new unordered list.
- Use `<li></li>` inside `<ul>` for each list item.
Example:

```html
<ul>
  <li>text1</li>
  <li>text2</li>
  <li>text3</li>
</ul>
```

- Use the `type` attribute to change the type of bullets.
Example:

```html
<ul type="square">
  <li>text1</li>
  <li>text2</li>
  <li>text3</li>
</ul>
```

### Ordered Lists

- Use `<ol></ol>` to start a new ordered list.
- Use `<li></li>` inside `<ol>` for each list item.
Example:

```html
<ol>
  <li>one</li>
  <li>two</li>
  <li>three</li>
</ol>
```

- Use the `type` attribute to change the type of numbers.
Example:

```html
<ol type="a">
  <li>one</li>
  <li>two</li>
  <li>three</li>
</ol>
```

### Ordered Lists with `start` and `reversed`

```html
<ol start="5">
  <li>Item A</li>
  <li>Item B</li>
</ol>

<ol reversed>
  <li>Step 3</li>
  <li>Step 2</li>
  <li>Step 1</li>
</ol>
```

### Description Lists

- Use `<dl></dl>` to start a new description list.
- Use `<dt></dt>` for terms and `<dd></dd>` for descriptions.
Example:

```html
<dl>
  <dt>term1</dt>
  <dd>- description 1</dd>
  <dt>term2</dt>
  <dd>- description 2</dd>
</dl>
```

### Nested Lists

- Lists can be nested within each other.
Example:

```html
<ol type="a">
  <li>one
    <ul>
      <li>1</li>
      <li>2</li>
      <li>3</li>
    </ul>
  </li>
  <li>two</li>
  <li>three</li>
</ol>
```

## HTML Tables

- Use `<table></table>` to start a new table.
- Use `<tr></tr>` to create a new row.
- Use `<td></td>` for table data and `<th></th>` for table headings.
Example:

```html
<table border="1">
  <tr>
    <th>name</th>
    <th>email</th>
  </tr>
  <tr>
    <td>ahmed</td>
    <td>ahmed@gmail.com</td>
  </tr>
</table>
```

Example with `<caption>` and `<tfoot>`:

```html
<table border="1">
  <caption>Student Grades</caption>
  <thead>
    <tr>
      <th>Name</th>
      <th>Math</th>
      <th>Science</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ali</td>
      <td>90</td>
      <td>85</td>
    </tr>
    <tr>
      <td>Nour</td>
      <td>95</td>
      <td>88</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total Students</td>
      <td colspan="2">2</td>
    </tr>
  </tfoot>
</table>

```

### Advanced Table Features

- Use `<thead>` and `<tbody>` to structure the table.
- Use `colspan` and `rowspan` attributes to merge cells.
Example:

```html
<table border="1">
  <thead>
    <tr>
      <th>name</th>
      <th colspan="2">number</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ali</td>
      <td>011111111111</td>
      <td>011111111122</td>
    </tr>
  </tbody>
</table>
```

## HTML Iframes

- Use `<iframe>` to embed another document within the current HTML document.
Example:

```html
<iframe src="index2.html"></iframe>
```

## The Head Section

The head includes:

1. `<title>`
2. Metadata (`<meta>`)
3. `<style>` element for CSS
4. `<script>` element for JavaScript
5. `<link>` tag for external resources
Example:

```html
<head>
  <meta charset="UTF-8">
  <meta name="keywords" content="HTML, CSS, XML, JavaScript">
  <meta name="author" content="John Doe">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
```

## HTML Container Elements

Common container elements:

1. `<section>` – Defines a thematic grouping of content.
2. `<div>` – Block-level container for grouping elements.
3. `<article>` – Represents self-contained content (e.g., blog post, news).
4. `<span>` – Inline container for styling parts of text or elements.
- Example:

```html
<div>
  <h2>This is a div container</h2>
  <p>Used for grouping elements.</p>
</div>

<span>This is an inline container.</span>
```

- **Semantic Containers**
1. `<header>` – Represents the header of a page or section.
2. `<nav>` – Contains navigation links.
3. `<aside>` – Sidebar for related info, ads, or secondary content.
4. `<footer>` – Footer of a page or section.
5. `<figure>` – Used to group media content (images, diagrams, code snippets, etc.).
6. `<figcaption>` – Provides a caption or description for a `<figure>`.

```html
<header>
  <h1>Website Title</h1>
  <p>Tagline or description</p>
</header>

<nav>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<aside>
  <h2>Sidebar</h2>
  <p>Additional info, ads, or related links.</p>
</aside>

<footer>
  <p>&copy; 2025 My Website. All rights reserved.</p>
</footer>
```

These semantic containers describe the **purpose** of the content instead of just being a generic `div`.

## **HTML Forms**

- **Purpose**: HTML forms are used to collect user input and send it to a server for processing.
- **Structure**: Forms start with the `<form>` tag and are closed with the `</form>` tag.
- **Attributes**: Important attributes include `action` (where to send data) and `method` (how to send data, e.g., GET or POST).

### **Form Elements and Attributes**

1. **Input Elements (`<input>`)**
    - Various types of inputs are available, each serving a different purpose:
        - `type="text"`: Single-line text input.
        - `type="password"`: Masks user input for sensitive data.
        - `type="email"`: Validates an email address.
        - `type="url"`: Validates a URL format
        - `type="search"`: Used for search fields.
        - `type="submit"`: Submits the form.
        - `type="reset"`: Resets form fields.
        - `type="radio"`: Allows the user to select one option from a group.
        - `type="checkbox"`: Allows the user to select multiple options.
        - `type="color"`, `type="date"`, `type="file"`, etc., provide specialized input fields.
    - Attributes like `name`, `id`, `value`, `placeholder`, and more define the input fields' properties.
    - `autofocus` automatically sets focus to the specified input field when the page loads.
2. **Labels (`<label>`)**
    - `for` attribute connects the label to an input by matching the `id` of the input.
    - Example: `<label for="user">Username:</label>`
3. **Select, Option, and Optgroup (`<select>`, `<option>`, `<optgroup>`)**
    - Used to create dropdown menus.
    - `<option>` defines an item inside the list.
    - `<optgroup>` groups related options together for better readability.
    - Attributes like `multiple` and `size` enhance functionality.
    - The `selected` attribute pre-selects an option by default.
    
    **Example:**
    
    ```html
    <label for="cars">Choose a car:</label>
    <select id="cars" name="cars" autofocus>
      <optgroup label="German Cars">
        <option value="audi">Audi</option>
        <option value="bmw">BMW</option>
      </optgroup>
      <optgroup label="Japanese Cars">
        <option value="toyota">Toyota</option>
        <option value="honda">Honda</option>
      </optgroup>
    </select>
    
    ```
    
4. **Textarea (`<textarea>`)**
    - For multi-line text input.
    - Attributes `rows` and `cols` define the visible area size.
    - Example:
    
    ```html
    <textarea name="message" rows="5" cols="30"></textarea>
    ```
    
5. **Datalist (`<datalist>`)**
    - Provides a list of predefined options for an `<input>` element.
    - Works together with the `list` attribute in the `<input>` tag.
    - Unlike `<select>`, it allows both typing freely and choosing from suggestions.
    
    **Example:**
    
    ```html
    <label for="browser">Choose a browser:</label>
    <input list="browsers" id="browser" name="browser">
    
    <datalist id="browsers">
      <option value="Chrome">
      <option value="Firefox">
      <option value="Safari">
      <option value="Edge">
      <option value="Opera">
    </datalist>
    ```
    
    ### **Input Restrictions and Validation**
    
    - **`required`**: Ensures the field is filled before form submission.
    - **`disabled`** and **`readonly`**: Control user interaction with fields.
    - **`min`, `max`, `maxlength`**: Set limits on user input.
    - **`checked`**: Sets the default state of checkboxes and radio buttons.
    
    ### **Styling Forms with CSS**
    
    - **Selectors**: Use attribute selectors to target specific input types.
        
        ```css
        input[type="text"] {
          width: 80%;
          padding: 12px;
        }
        ```
        
    - **Pseudo-classes**: Style elements based on their state.
        - `:focus`: Applies style when an element is focused.
        - `:checked`: Styles checkboxes and radio buttons when selected.
    - **Form Layout**: Use CSS properties like `width`, `height`, `padding`, and `border` to style form elements and layout.
    
    ### **Complete Form Example**
    
    **HTML:**
    
    ```html
    <section class="register">
      <h2>Please fill this form</h2>
      <form action="#" method="post">
        <label for="first">First Name:</label>
        <input type="text" id="first" name="first" placeholder="Enter first name" required>
    
        <label for="last">Last Name:</label>
        <input type="text" id="last" name="last" placeholder="Enter last name" required>
    
        <label for="pass">Password:</label>
        <input type="password" id="pass" name="pass" placeholder="Enter your password" required>
    
        <label for="email">Email:</label>
        <input type="email" name="email" id="email" placeholder="Enter your email" required>
    
        <label for="date">Birth Date:</label>
        <input type="date" name="date" id="date">
    
        <label for="country">Country:</label>
        <select name="country" id="country">
          <option value="egypt">Egypt</option>
          <option value="italy">Italy</option>
          <option value="england">England</option>
        </select>
    
        <label>Gender:</label>
        <label for="male">Male</label>
        <input type="radio" name="gender" id="male" value="male">
        <label for="female">Female</label>
        <input type="radio" name="gender" id="female" value="female">
    
        <label>Hobbies:</label>
        <label for="swimming">Swimming</label>
        <input type="checkbox" id="swimming" name="hobby" value="swimming">
        <label for="football">Football</label>
        <input type="checkbox" id="football" name="hobby" value="football">
    
        <textarea name="comment" id="comment" placeholder="Please leave your comment"></textarea>
    
        <input type="submit" name="register" value="Register">
      </form>
    </section>
    ```
    

## HTML Video

**Attributes:**

1. `src` → video file URL
2. `controls` → shows controls
3. `poster` → placeholder image before playing
4. `loop` → repeat video
5. `muted` → no sound by default
6. `autoplay` → automatically plays the video when the page loads

**Example:**

```html
<video src="vid.mp4" poster="img.png" muted controls loop width="600px" height="500px"></video>
```

## **HTML Audio**

**Attributes:**

1. `src` → audio file URL
2. `controls` → shows controls
3. `loop` → repeat audio
4. `muted` → mute sound
5. `hidden` → hides the audio player from the page
6. `autoplay` → automatically plays the audio when the page loads

**Example:**

```html
<audio src="mixkit-fast-rocket-whoosh-1714.wav" controls loop></audio>
```

## **Embedding Google Maps**

1. Go to **Google Maps**
2. Click **settings**
3. Choose **Share and embed map**
4. Copy **Embed HTML**
5. Paste into your HTML file

## HTML Entities

- **Definition:** HTML entities are used to display reserved characters or symbols that otherwise would be interpreted as code in HTML.
- **Syntax:** `&entity_name;` or `&#entity_number;`
    
    ### Common Entities
    
    1. **Reserved Characters**
        
        ```html
        &lt;   → <
        &gt;   → >
        &amp;  → &
        &quot; → "
        &apos; → '
        ```
        
        Example:
        
        ```html
        <p>2 &lt; 5 and 5 &gt; 2</p>
        <p>Use &amp; to represent an ampersand</p>
        ```
        
    2. **Non-Breaking Space**
        - Use `&nbsp;` for spaces that should not break into a new line.
        
        Example:
        
        ```html
        <p>Hello&nbsp;World</p>
        ```
        
    3. **Currency Symbols**
        
        ```html
        &dollar; → $
        &euro;   → €
        &pound;  → £
        &yen;    → ¥
        ```
        
        Example:
        
        ```html
        <p>Price: 100 &dollar;</p>
        ```
        
    4. **Mathematical Symbols**
        
        ```html
        &plus;   → +
        &minus;  → −
        &times;  → ×
        &divide; → ÷
        ```
        
        Example:
        
        ```html
        <p>10 &times; 5 = 50</p>
        ```
        
    5. **Arrows**
        
        ```html
        &larr; → ←
        &uarr; → ↑
        &rarr; → →
        &darr; → ↓
        ```
        
        Example:
        
        ```html
        <p>Click &rarr; Next</p>
        ```
        
        ### Full Reference for HTML Entities
        
        For a **complete list** of HTML entities—including ASCII characters, ISO-8859-1 symbols, math symbols, Greek letters, and more—you can consult this helpful resource:
        
        - *Complete list of HTML entities with their names and codes: the FreeFormatter HTML Entities page* [freeformatter.com](https://www.freeformatter.com/html-entities.html?utm_source=chatgpt.com)
