# Introduction to HTML
### Hypertext Markup Language

**By: Nouran Hosam**

---

## Table of Contents

1. [What HTML Is](#1-what-html-is)
2. [HTML Elements](#2-html-elements)
3. [Document Structure](#3-document-structure)
4. [Text-Level Elements](#4-text-level-elements)
5. [Text Styling Tags](#5-text-styling-tags)
6. [Links](#6-links)
7. [Images](#7-images)
8. [Buttons](#8-buttons)
9. [Comments](#9-comments)
10. [Lists](#10-lists)
11. [Tables](#11-tables)
12. [Iframes](#12-iframes)
13. [The Head Section](#13-the-head-section)
14. [Container Elements](#14-container-elements)
15. [Forms](#15-forms)
16. [Video](#16-video)
17. [Audio](#17-audio)
18. [Embedding Google Maps](#18-embedding-google-maps)
19. [HTML Entities](#19-html-entities)
20. [Accessibility Basics](#20-accessibility-basics)
21. [Quick Reference Cheat Sheet](#21-quick-reference-cheat-sheet)

---

## 1. What HTML Is

**HTML (HyperText Markup Language)** is the standard markup language used to structure content on the web. It doesn't describe how a page *looks* (that's CSS's job) or how it *behaves* (that's JavaScript's job) — it describes what content *is*: a heading, a paragraph, a list, an image, a form, and so on.

A web page is built from HTML **elements** that nest inside one another to form a tree-like structure, often called the **DOM (Document Object Model)** once the browser parses it.

---

## 2. HTML Elements

There are two types of HTML elements:

| Type | Syntax | Notes |
|---|---|---|
| **Pair (container) element** | `<tagname>content</tagname>` | Has an opening and closing tag; wraps content |
| **Empty (void) element** | `<tagname>` or `<tagname />` | Self-closing; has no content or closing tag (e.g. `<br>`, `<img>`, `<hr>`, `<input>`) |

Elements can also have **attributes**, which provide additional information and always live in the opening tag:

```html
<a href="https://example.com" target="_blank">Visit site</a>
```

Here, `href` and `target` are attributes of the `<a>` element.

---

## 3. Document Structure

### 3.1 Main Elements

Every HTML document needs three core elements:

1. **`<html></html>`** — The root element; holds all other HTML content.
2. **`<head></head>`** — Contains metadata: title, character set, linked stylesheets/scripts, SEO tags. Nothing inside `<head>` is displayed directly on the page.
3. **`<body></body>`** — Contains all visible content: text, images, links, forms, etc.

### 3.2 Nesting

Nesting means placing one element inside another. This is how the main skeleton looks:

```html
<html lang="en">
  <head></head>
  <body></body>
</html>
```

The `lang` attribute tells browsers and screen readers what language the page is written in, which helps with accessibility, translation tools, and search engines.

### 3.3 DOCTYPE Declaration

`<!DOCTYPE html>` must be the very first line of an HTML file. It tells the browser to render the page using the modern HTML5 standard rather than an older or "quirks" mode.

```html
<!DOCTYPE html>
<html lang="en">
  <head></head>
  <body></body>
</html>
```

### 3.4 The Title Element

`<title>` sets the text that appears:
- In the **browser tab**
- As the default name when a page is **bookmarked**
- As the **clickable headline** in search engine results

```html
<head>
  <title>My Project</title>
</head>
```

> **Tip:** Keep titles under ~60 characters so they don't get cut off in search results.

### 3.5 Heading Elements

`<h1>` through `<h6>` define headings, with `<h1>` being the highest level of importance and `<h6>` the lowest.

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

> **Best practice:** Use only **one `<h1>` per page** and keep headings in logical order (don't skip from `<h1>` to `<h4>`) — this matters both for SEO and for screen-reader navigation.

---

## 4. Text-Level Elements

### 4.1 Paragraph

`<p>` defines a block of text as a paragraph.

```html
<p>
  Web design is the process of creating visually appealing and functional websites.
  It involves layout, color scheme, graphics, fonts, and content.
</p>
```

### 4.2 Line Break

`<br>` forces a line break within text, without starting a new paragraph.

```html
<p>This is a line, <br> and this continues on a new line.</p>
```

### 4.3 Horizontal Rule

`<hr>` draws a horizontal divider line, typically used to separate sections of content.

```html
<p>First section text.</p>
<hr>
<p>Second section text.</p>
```

### 4.4 Preformatted Text

`<pre>` preserves whitespace and line breaks exactly as written in the source code — useful for displaying code, ASCII art, or anything where spacing matters.

```html
<pre>
This    text
    keeps its   spacing.
</pre>
```

### 4.5 The `<code>` Element

- Displays a fragment of computer code, typically rendered in a **monospace font**.
- Often nested inside `<pre>` to preserve indentation and line breaks for multi-line snippets.

**Inline example:**

```html
<p>To print in Java use: <code>System.out.println("Hello World");</code></p>
```

**Block example (with `<pre>`):**

```html
<pre><code>for (int i = 0; i < 5; i++) {
    System.out.println(i);
}</code></pre>
```

### 4.6 Quotations and Citations

| Tag | Purpose |
|---|---|
| `<q>` | Short **inline** quotation (browsers add quotation marks automatically) |
| `<blockquote>` | Long, **block-level** quotation (usually indented) |
| `<cite>` | References the *title* of a creative work (a book, article, etc.) |

```html
<p>Einstein once said: <q>Imagination is more important than knowledge.</q></p>

<blockquote cite="https://example.com/source">
  The greatest glory in living lies not in never falling, but in rising every time we fall.
  <footer>— <cite>Nelson Mandela</cite></footer>
</blockquote>
```

### 4.7 Word Breaks

`<wbr>` marks a point where the browser *may* break a long word or URL onto a new line if needed — without inserting a visible hyphen or character.

```html
<p>
  Visit: www.verylongdomainname<wbr>.com/withaverylongpath<wbr>/andaverylongfile.html
</p>
```

### 4.8 Bi-Directional Text

`<bdi>` (**Bi-Directional Isolation**) isolates a span of text so its directionality (e.g. right-to-left languages like Arabic) doesn't affect the layout of surrounding text.

```html
<ul>
  <li>User: <bdi>إيمان</bdi> — Score: 90</li>
  <li>User: <bdi>John</bdi> — Score: 85</li>
</ul>
```

A related attribute, `dir="rtl"` or `dir="ltr"`, can also be set directly on any element to control text direction explicitly.

### 4.9 Abbreviations and Definitions

Two useful semantic tags that are often overlooked:

- `<abbr title="full text">ABC</abbr>` — marks an abbreviation/acronym; the `title` shows a tooltip with the full meaning on hover.
- `<dfn>term</dfn>` — marks the defining instance of a term.

```html
<p><abbr title="Hypertext Markup Language">HTML</abbr> is the standard markup language for web pages.</p>
```

---

## 5. Text Styling Tags

| Tag | Effect | Example |
|---|---|---|
| `<b>` | Bold (no extra semantic meaning) | **Bold text** |
| `<strong>` | Bold **and** indicates strong importance | **Important text** |
| `<i>` | Italic (no extra semantic meaning) | *Italic text* |
| `<em>` | Italic **and** indicates emphasis | *Emphasized text* |
| `<small>` | Renders text in a smaller font | Fine print |
| `<del>` | Strikethrough — marks deleted text | ~~removed text~~ |
| `<ins>` | Underline — marks inserted text | inserted text |
| `<sub>` | Subscript | H₂O |
| `<sup>` | Superscript | x² |
| `<mark>` | Highlighted background | highlighted text |
| `<u>` | Underlined text (use sparingly — can be mistaken for a link) | underlined text |

> **Semantic tip:** Prefer `<strong>`/`<em>` over `<b>`/`<i>` when the emphasis is meaningful, not just visual — screen readers announce them differently.

---

## 6. Links

The `<a>` (anchor) element creates a hyperlink.

**Key attributes:**
- `href` — the destination URL
- `target="_blank"` — opens the link in a new tab
- `title` — tooltip text shown on hover
- `rel="noopener noreferrer"` — recommended security practice when using `target="_blank"`, to prevent the new page from accessing the original page via `window.opener`

```html
<a href="https://www.google.com" title="Go to Google">Click here</a>
<a href="https://www.google.com" target="_blank" rel="noopener noreferrer">Open in new tab</a>
<a href="mailto:info@example.com" title="Send Email">Email Us</a>
<a href="tel:+201234567890">Call Us</a>
<a href="#contact">Go to Contact Section</a>
```

**Linking to a section on the same page** requires a matching `id`:

```html
<section id="contact">
  <h2>Contact Section</h2>
  <p>Here is the contact section.</p>
</section>
```

---

## 7. Images

`<img>` is a void (self-closing) element used to insert an image.

```html
<img src="1.jpg" alt="A photo of a tourist landmark" width="600" height="400">
```

**Key attributes:**
- `src` — path or URL to the image file
- `alt` — **required for accessibility**: describes the image for screen readers and displays if the image fails to load
- `width` / `height` — reserve space for the image before it loads, preventing layout shift
- `loading="lazy"` — defers loading off-screen images until the user scrolls near them, improving page performance

```html
<img src="images/1.jpg" alt="Aerial view of the tourist site" loading="lazy">
```

For responsive images that adapt to screen size, `<picture>` and the `srcset` attribute can serve different image files depending on device width — useful for performance on mobile devices.

---

## 8. Buttons

`<button>` creates a clickable button. It supports a `type` attribute:

```html
<button type="button">Click here</button>
<button type="submit">Submit Form</button>
<button type="reset">Reset Form</button>
```

If no `type` is specified inside a `<form>`, it defaults to `"submit"` — a common source of bugs when a button is meant only to trigger JavaScript.

---

## 9. Comments

HTML comments are not rendered in the browser and are useful for leaving notes or temporarily disabling code.

```html
<!-- <h1>Welcome</h1> -->
<p>Welcome</p>
<!-- Remember to update this section later -->
```

Comments improve code readability and make collaboration and maintenance easier, especially in larger projects.

---

## 10. Lists

HTML supports three list types:

### 10.1 Unordered Lists

Bulleted lists using `<ul>` and `<li>`:

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

The `type` attribute (legacy — prefer the CSS `list-style-type` property) changes the bullet style:

```html
<ul type="square">
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

### 10.2 Ordered Lists

Numbered lists using `<ol>` and `<li>`:

```html
<ol>
  <li>Step one</li>
  <li>Step two</li>
  <li>Step three</li>
</ol>
```

The `type` attribute changes the numbering style (`1`, `a`, `A`, `i`, `I`):

```html
<ol type="a">
  <li>Item one</li>
  <li>Item two</li>
</ol>
```

The `start` and `reversed` attributes control the starting number and count direction:

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

### 10.3 Description Lists

Used for term/definition pairs (glossaries, metadata, FAQs):

```html
<dl>
  <dt>HTML</dt>
  <dd>Markup language for structuring web content.</dd>
  <dt>CSS</dt>
  <dd>Stylesheet language used to style HTML content.</dd>
</dl>
```

### 10.4 Nested Lists

Lists can be nested inside one another:

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

---

## 11. Tables

Tables display tabular (row/column) data.

**Core elements:**
- `<table>` — starts the table
- `<tr>` — table row
- `<th>` — header cell (bold, centered by default)
- `<td>` — standard data cell

```html
<table border="1">
  <tr>
    <th>Name</th>
    <th>Email</th>
  </tr>
  <tr>
    <td>Ahmed</td>
    <td>ahmed@gmail.com</td>
  </tr>
</table>
```

### 11.1 Structured Tables

`<thead>`, `<tbody>`, and `<tfoot>` group rows semantically, and `<caption>` provides an accessible table title:

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

### 11.2 Merging Cells

`colspan` merges cells horizontally; `rowspan` merges cells vertically.

```html
<table border="1">
  <thead>
    <tr>
      <th>Name</th>
      <th colspan="2">Phone Numbers</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ali</td>
      <td>011-1111-1111</td>
      <td>011-1111-2222</td>
    </tr>
  </tbody>
</table>
```

> **Accessibility note:** Add `scope="col"` or `scope="row"` to `<th>` elements in complex tables so screen readers can correctly associate headers with data cells.

---

## 12. Iframes

`<iframe>` embeds another HTML document within the current page (commonly used for maps, videos, or third-party widgets).

```html
<iframe src="index2.html" width="600" height="400" title="Embedded page"></iframe>
```

> **Security tip:** Only embed trusted sources — iframes can be used maliciously. Consider the `sandbox` attribute to restrict what an embedded page can do.

---

## 13. The Head Section

The `<head>` can include:

1. `<title>` — page/browser tab title
2. `<meta>` — metadata: character encoding, description, keywords, viewport settings
3. `<style>` — internal CSS
4. `<script>` — internal or external JavaScript
5. `<link>` — external resources such as stylesheets or favicons

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="A short summary of the page for search engines.">
  <meta name="keywords" content="HTML, CSS, XML, JavaScript">
  <meta name="author" content="John Doe">
  <link rel="stylesheet" href="styles.css">
  <link rel="icon" href="favicon.ico" type="image/x-icon">
  <title>Document</title>
</head>
```

**Notable additions:**
- `charset="UTF-8"` — ensures special characters (accents, non-Latin scripts, emoji) render correctly.
- `viewport` meta tag — essential for responsive design; without it, mobile browsers render the page at desktop width and zoom out.
- `meta name="description"` — the snippet often shown under a page's title in search results.

---

## 14. Container Elements

### 14.1 Generic Containers

| Tag | Purpose |
|---|---|
| `<div>` | Block-level generic container, used for grouping and styling |
| `<span>` | Inline generic container, used for styling parts of text |
| `<section>` | Groups content thematically (usually with its own heading) |
| `<article>` | Self-contained, independently distributable content (blog post, news story, forum post) |

```html
<div>
  <h2>Grouped Content</h2>
  <p>Used for grouping elements together.</p>
</div>

<span>This is an inline container.</span>
```

### 14.2 Semantic Layout Containers

These describe the **purpose** of a section rather than being a generic `<div>`, which improves both accessibility and code readability:

| Tag | Purpose |
|---|---|
| `<header>` | Introductory content for a page or section (logo, title, nav) |
| `<nav>` | Navigation links |
| `<aside>` | Sidebar content — related info, ads, secondary content |
| `<footer>` | Footer of a page or section (copyright, contact links) |
| `<main>` | The dominant, unique content of the page (only one per page) |
| `<figure>` | Groups media (image, diagram, code snippet) with its caption |
| `<figcaption>` | Caption/description for a `<figure>` |

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

<main>
  <article>
    <h2>Article Title</h2>
    <p>Article content goes here.</p>
  </article>

  <aside>
    <h2>Related Links</h2>
    <p>Additional info, ads, or related content.</p>
  </aside>
</main>

<footer>
  <p>&copy; 2025 My Website. All rights reserved.</p>
</footer>
```

```html
<figure>
  <img src="chart.png" alt="Bar chart of quarterly sales">
  <figcaption>Fig. 1 — Quarterly sales performance</figcaption>
</figure>
```

---

## 15. HTML Forms

### 15.1 Purpose and Structure

Forms collect user input and send it to a server for processing. A form starts with `<form>` and ends with `</form>`.

**Key attributes:**
- `action` — the URL the form data is sent to
- `method` — how the data is sent: `GET` (visible in the URL, for non-sensitive data) or `POST` (sent in the request body, for sensitive/large data)

### 15.2 Input Elements

`<input>` is the most versatile form element; its behavior changes entirely based on the `type` attribute:

| Type | Purpose |
|---|---|
| `text` | Single-line text |
| `password` | Masks input for sensitive data |
| `email` | Validates email format |
| `url` | Validates URL format |
| `search` | Styled/optimized for search fields |
| `number` | Numeric input, often with spinner controls |
| `tel` | Telephone number (no automatic validation, but triggers numeric keypad on mobile) |
| `date`, `time`, `datetime-local` | Date/time pickers |
| `color` | Color picker |
| `file` | File upload |
| `range` | Slider control |
| `radio` | Single choice from a group |
| `checkbox` | Multiple choice selections |
| `hidden` | Data submitted but not visible to the user |
| `submit` | Submits the form |
| `reset` | Clears form fields |

Common attributes: `name`, `id`, `value`, `placeholder`, `autofocus` (focuses the field on page load).

### 15.3 Labels

`<label>` improves accessibility and usability by linking descriptive text to an input — clicking the label focuses/activates the input.

```html
<label for="user">Username:</label>
<input type="text" id="user" name="user">
```

### 15.4 Select, Option, and Optgroup

Used to build dropdown menus:

```html
<label for="cars">Choose a car:</label>
<select id="cars" name="cars" autofocus>
  <optgroup label="German Cars">
    <option value="audi">Audi</option>
    <option value="bmw">BMW</option>
  </optgroup>
  <optgroup label="Japanese Cars">
    <option value="toyota">Toyota</option>
    <option value="honda" selected>Honda</option>
  </optgroup>
</select>
```

- `multiple` — allows selecting more than one option
- `size` — number of visible options without scrolling
- `selected` — pre-selects an option by default

### 15.5 Textarea

Used for multi-line text input:

```html
<textarea name="message" rows="5" cols="30" placeholder="Type your message..."></textarea>
```

### 15.6 Datalist

Provides suggestions for an `<input>` while still allowing free typing — unlike `<select>`, which restricts input to the listed options:

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

### 15.7 Input Restrictions and Validation

| Attribute | Effect |
|---|---|
| `required` | Field must be filled before submission |
| `disabled` | Field is uneditable and not submitted with the form |
| `readonly` | Field is uneditable but still submitted with the form |
| `min`, `max` | Numeric/date range limits |
| `maxlength`, `minlength` | Character length limits |
| `pattern` | Regex pattern the value must match |
| `checked` | Default state for checkboxes/radio buttons |

### 15.8 Styling Forms with CSS

**Attribute selectors** target specific input types:

```css
input[type="text"] {
  width: 80%;
  padding: 12px;
}
```

**Pseudo-classes** style elements based on state:

- `:focus` — while the element has focus
- `:checked` — for selected checkboxes/radio buttons
- `:invalid` / `:valid` — based on validation state
- `:disabled` — for disabled fields

### 15.9 Complete Form Example

```html
<section class="register">
  <h2>Please fill this form</h2>
  <form action="#" method="post">
    <label for="first">First Name:</label>
    <input type="text" id="first" name="first" placeholder="Enter first name" required>

    <label for="last">Last Name:</label>
    <input type="text" id="last" name="last" placeholder="Enter last name" required>

    <label for="pass">Password:</label>
    <input type="password" id="pass" name="pass" placeholder="Enter your password" required minlength="8">

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

    <fieldset>
      <legend>Gender:</legend>
      <label for="male">Male</label>
      <input type="radio" name="gender" id="male" value="male">
      <label for="female">Female</label>
      <input type="radio" name="gender" id="female" value="female">
    </fieldset>

    <fieldset>
      <legend>Hobbies:</legend>
      <label for="swimming">Swimming</label>
      <input type="checkbox" id="swimming" name="hobby" value="swimming">
      <label for="football">Football</label>
      <input type="checkbox" id="football" name="hobby" value="football">
    </fieldset>

    <label for="comment">Comment:</label>
    <textarea name="comment" id="comment" placeholder="Please leave your comment"></textarea>

    <input type="submit" name="register" value="Register">
  </form>
</section>
```

> **Added tip:** `<fieldset>` and `<legend>` group related form controls (like a radio button group) and give them an accessible collective label — a small addition that meaningfully improves screen-reader usability.

---

## 16. HTML Video

**Attributes:**

| Attribute | Effect |
|---|---|
| `src` | Video file URL |
| `controls` | Displays play/pause/volume controls |
| `poster` | Placeholder image shown before playback starts |
| `loop` | Repeats the video automatically |
| `muted` | Video plays without sound by default |
| `autoplay` | Plays automatically on page load (most browsers require `muted` for autoplay to work) |
| `preload` | Hints how much to load in advance: `none`, `metadata`, or `auto` |

```html
<video src="vid.mp4" poster="img.png" muted controls loop width="600" height="500">
  Your browser does not support the video tag.
</video>
```

Multiple formats can be provided for broader compatibility using `<source>`:

```html
<video controls width="600">
  <source src="vid.mp4" type="video/mp4">
  <source src="vid.webm" type="video/webm">
  Your browser does not support the video tag.
</video>
```

---

## 17. HTML Audio

**Attributes:**

| Attribute | Effect |
|---|---|
| `src` | Audio file URL |
| `controls` | Displays play/pause/volume controls |
| `loop` | Repeats the audio automatically |
| `muted` | Mutes the sound by default |
| `hidden` | Hides the audio player UI from the page |
| `autoplay` | Plays automatically on page load |

```html
<audio src="notification-sound.wav" controls loop></audio>
```

---

## 18. Embedding Google Maps

1. Go to **Google Maps** and find the location you want to embed.
2. Click the **Menu (☰)** or **Share** option.
3. Choose **"Embed a map"**.
4. Copy the provided **`<iframe>` HTML code**.
5. Paste it directly into your HTML file.

```html
<iframe
  src="https://www.google.com/maps/embed?..."
  width="600"
  height="450"
  style="border:0;"
  allowfullscreen=""
  loading="lazy"
  title="Google Map location">
</iframe>
```

---

## 19. HTML Entities

**Definition:** HTML entities display reserved characters or symbols that would otherwise be interpreted as HTML code (like `<` and `>`), or characters that are hard to type directly.

**Syntax:** `&entity_name;` or `&#entity_number;`

### 19.1 Reserved Characters

| Entity | Renders as |
|---|---|
| `&lt;` | < |
| `&gt;` | > |
| `&amp;` | & |
| `&quot;` | " |
| `&apos;` | ' |

```html
<p>2 &lt; 5 and 5 &gt; 2</p>
<p>Use &amp; to represent an ampersand</p>
```

### 19.2 Non-Breaking Space

`&nbsp;` prevents a line break from occurring at that space:

```html
<p>Hello&nbsp;World</p>
```

### 19.3 Currency Symbols

| Entity | Renders as |
|---|---|
| `&dollar;` | $ |
| `&euro;` | € |
| `&pound;` | £ |
| `&yen;` | ¥ |
| `&cent;` | ¢ |

```html
<p>Price: 100 &dollar;</p>
```

### 19.4 Mathematical Symbols

| Entity | Renders as |
|---|---|
| `&plus;` | + |
| `&minus;` | − |
| `&times;` | × |
| `&divide;` | ÷ |
| `&ne;` | ≠ |
| `&le;` | ≤ |
| `&ge;` | ≥ |
| `&infin;` | ∞ |

```html
<p>10 &times; 5 = 50</p>
```

### 19.5 Arrows

| Entity | Renders as |
|---|---|
| `&larr;` | ← |
| `&uarr;` | ↑ |
| `&rarr;` | → |
| `&darr;` | ↓ |

```html
<p>Click &rarr; Next</p>
```

### 19.6 Copyright, Trademark, and Miscellaneous

| Entity | Renders as |
|---|---|
| `&copy;` | © |
| `&reg;` | ® |
| `&trade;` | ™ |
| `&hellip;` | … |
| `&mdash;` | — |
| `&ndash;` | – |

```html
<p>&copy; 2026 My Company. All rights reserved.</p>
```

For a complete list of HTML entities — including ASCII, ISO-8859-1, math symbols, and Greek letters — see the [FreeFormatter HTML Entities reference](https://www.freeformatter.com/html-entities.html).

---

## 20. Accessibility Basics

A short addition worth including in any HTML introduction, since accessibility is a core part of writing good markup:

- Always include meaningful `alt` text on images.
- Use semantic elements (`<nav>`, `<header>`, `<main>`, `<footer>`) instead of generic `<div>`s wherever the meaning fits.
- Associate every `<input>` with a `<label>`.
- Maintain a logical heading order (`<h1>` → `<h2>` → `<h3>`, without skipping levels).
- Add `lang` to the `<html>` tag.
- Use ARIA attributes (`aria-label`, `aria-hidden`, `role`) only when semantic HTML alone can't express something.
- Ensure sufficient color contrast (this is technically CSS, but it starts with correct HTML structure).

---

## 21. Quick Reference Cheat Sheet

| Category | Tags |
|---|---|
| Structure | `<html>`, `<head>`, `<body>`, `<title>`, `<meta>` |
| Text | `<h1>`–`<h6>`, `<p>`, `<br>`, `<hr>`, `<pre>`, `<code>`, `<q>`, `<blockquote>` |
| Styling | `<b>`, `<strong>`, `<i>`, `<em>`, `<mark>`, `<small>`, `<sub>`, `<sup>`, `<del>`, `<ins>`, `<u>` |
| Links & Media | `<a>`, `<img>`, `<video>`, `<audio>`, `<iframe>` |
| Lists | `<ul>`, `<ol>`, `<li>`, `<dl>`, `<dt>`, `<dd>` |
| Tables | `<table>`, `<tr>`, `<th>`, `<td>`, `<thead>`, `<tbody>`, `<tfoot>`, `<caption>` |
| Containers | `<div>`, `<span>`, `<section>`, `<article>`, `<header>`, `<nav>`, `<aside>`, `<footer>`, `<main>`, `<figure>`, `<figcaption>` |
| Forms | `<form>`, `<input>`, `<label>`, `<select>`, `<option>`, `<optgroup>`, `<textarea>`, `<datalist>`, `<fieldset>`, `<legend>`, `<button>` |
