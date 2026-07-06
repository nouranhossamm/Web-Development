# Introduction to CSS

### Cascading Style Sheets

**By:** Nouran Hosam

## What is CSS?

CSS stands for Cascading Style Sheets. It is used to define styles for your web pages, including the design, layout, and variations in display for different devices and screen sizes.

### CSS Syntax

```css
selector {
  property1: value1;
  property2: value2;
}
```

## Ways to Write CSS

### Inline CSS

Write the CSS inside the element by using the `style` attribute.

```html
<h1 style="color: red;">welcome</h1>
```

### Internal CSS

Write the CSS inside a `<style>` element in the `<head>` or `<body>` (not recommended). Use a selector to select the element before styling it.

```html
<head>
  <style>
    h1 {
      color: red;
    }
  </style>
</head>
<body>
  <h1>welcome</h1>
  <p>welcome 2</p>
</body>
```

### External CSS

Write CSS in an external file and link it to the HTML document. Create a new file with a `.css` extension (e.g., `style.css`). Use `<link rel="stylesheet" href="path-to-css-file" />`.

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

In `style.css`:

```css
h1 { color: red; }
```

### CSS Priority

1. Inline styles
2. External and internal style sheets (whichever is placed last)

```html
<head>
  <style>
    h1 { color: red; }
  </style>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>welcome</h1>
</body>
```

If `style.css` has `h1 { color: yellow; }`, the text will be yellow.

## CSS Selectors

1. **Simple selectors** (name, id, class)
2. **Universal selector**
3. **Grouping selectors**
4. **Combinatory selectors** (relationship-based)
5. **Pseudo-class selectors**
6. **Pseudo-element selectors**
7. **Attribute selectors**

### Simple Selectors

- **Tag Name**

```html
<h1>welcome</h1>
<style>
  h1 {
    color: red;
  }
</style>
```

- **ID Selector**
Select a specific element with an id. IDs are unique within a page.

```html
<h1 id="heading1">welcome</h1>
<style>
  #heading1 {
    color: red;
  }
</style>
```

- **Class Selector**
Select elements with a specific class. Can select multiple elements.

```html
<h1 class="a">welcome 1</h1>
<p class="a">welcome 2</p>
<button class="a">click here</button>
<style>
  .a {
    color: blue;
  }
</style>
```

### **Universal Selector**

Select all HTML elements on the page.

```css
* {
  color: blue;
}
```

### **Grouping Selectors**

Minimize code by grouping selectors.

```css
h1, .b, #c {
  color: red;
}
```

### Combinatory Selectors

1. **Descendant Selector** (space)

```css
.products h3 {
  color: red;
}
```

1. **Child Selector** (>)

```css
.products > h3 {
  color: red;
}
```

1. **Adjacent Sibling Selector** (+)

```css
div + p {
  color: red;
}
```

1. **General Sibling Selector** (~)

```css
div ~ p {
  color: red;
}
```

### Pseudo-Classes

Define a special state of an element.
Examples: `:hover`, `:first-child`, `:last-child`, `:nth-child(n)`

```css
h1:hover {
  color: red;
}
```

### Pseudo-Elements

Style specified parts of an element.
Examples: `::first-letter`, `::first-line`, `::before`, `::after`

```css
h1::first-letter {
  color: red;
}
```

## CSS Comments

- Single-line comment:

```css
/* comment */
```

- Multi-line comment:

```css
/*
  comment
*/
```

## CSS Units

Used in properties like width, margin, padding, font-size. Length is a number followed by a unit (e.g., `10px`, `2em`). 1em = 16px (default browser size).

## CSS Properties

### 1. Color

- **Value as Name**

```css
h1 {
  color: red;
}
```

- **RGB**
Values range from 0 to 255.

```css
h1 {
  color: rgb(0, 100, 255);
}
```

- **RGBA**
RGBA includes alpha for opacity (0 to 1).

```css
h1 {
  color: rgba(0, 100, 255, 0.5);
}
```

- **Hexadecimal**
Hex values start with `#` followed by six hex digits.

```css
h1 {
  color: #c1b2c3;
}
```

- **HSL**
Hue (0-360), Saturation (%), Lightness (%).

```css
h1 {
  color: hsl(50, 50%, 50%);
}
```

### 2. Backgrounds

- **Background-Color**

```css
h1 {
  background-color: blue;
  background-color: rgb(112, 113, 200);
  background-color: rgba(112, 113, 200, 0.6);
  background-color: hsl(112, 50%, 20%);
}
```

- **Background-Image**

```css
div {
  height: 100vh;
  background-image: url('images/name.jpg');
}
```

- **Background-Repeat**
Options: `repeat-x`, `repeat-y`, `no-repeat`.

```css
div {
  height: 100vh;
  background-image: url('header.jpg');
  background-repeat: no-repeat;
}
```

- **Background-Position**
Options: `top`, `left`, `right`, `bottom`, `center`.

```css
div {
  height: 100vh;
  background-image: url('header.jpg');
  background-repeat: no-repeat;
  background-position: bottom right;
}
```

- **Background-Size**
Options: `cover`, specific dimensions.

```css
div {
  background-image: url('header.jpg');
  background-size: cover;
}
div {
  background-image: url('header.jpg');
  background-size: 1000px 2000px;
}
```

- **Background-Attachment**
Options: `fixed`, `scroll`.

```css
div {
  height: 100vh;
  background-image: url('header.jpg');
  background-repeat: no-repeat;
  background-position: center;
  background-size: 1000px 2000px;
  background-attachment: fixed;
}
```

- **Shorthand**

```css
div {
  height: 100vh;
  background: url('header.jpg') no-repeat fixed center;
}
```

### 3. Box Model

CSS treats each HTML element as if it lives in a box, allowing you to control dimensions, create borders, and set margins and padding.

- **Content**
Set dimensions using width and height.

```css
div {
  width: 200px;
  height: 200px;
  background-color: yellow;
}
```

Use percentages or viewport units.

```css
div {
  width: 20vw;
  height: 20vh;
  background-color: yellow;
}
```

- **Width: fit-content**

The `fit-content` value makes the element’s width adjust to its content, within the available space.

```css
div {
  width: fit-content;
  border: 2px solid red;
  padding: 10px;
}
```

👉 The `div` will only be as wide as needed to fit its content.

You can also use the **function syntax** with limits:

```css
div {
  width: fit-content(300px); /* won’t exceed 300px */
}
```

⚡ Related values:

- `min-content` → the smallest width without breaking words.
- `max-content` → the width needed to show all content in one line.
- **Padding**
The area around the content.

```css
div {
  width: 20vw;
  height: 20vh;
  background-color: yellow;
  padding: 20px;
}
```

Padding on specific sides.

```css
div {
  background-color: yellow;
  padding-top: 10px;
  padding-bottom: 40px;
  padding-left: 20px;
  padding-right: 100px;
}
```

Shorthand for padding.

```css
div {
  padding: 10px 100px 40px 20px; /* top, right, bottom, left */
  padding: 10px 100px 20px; /* top, left & right, bottom */
  padding: 20px 100px; /* top & bottom, left & right */
  padding: 20px; /* all sides */
}
```

- **Border**
Around the padding and content.

```css
h1 {
  border-top-style: dotted;
  border-top-width: 10px;
  border-top-color: red;
  border-top: dotted 10px red; /* shorthand */
}
```

Around the padding and content.

```css
h1 {
  border-style: dotted dotted dashed double;
  border-width: 10px 5px 3px 2px;
  border-color: red blue yellow green;
  border: dotted red 5px; /* shorthand */
}
```

Border-radius for rounded corners.

```css
h1 {
  border: 3px solid blue;
  border-radius: 20px;
}

h1 {
  border: 1px solid blue;
  border-radius: 50%; /* makes a circle */
}
```

### 4. Margin

Area outside the border.

```css
div {
  background-color: yellow;
  width: 100px;
  height: 100px;
  padding: 20px;
  border: 10px solid red;
  margin: 60px;
}
```

### Margin Specific Sides

```css
div {
  background-color: yellow;
  width: 100px;
  height: 100px;
  padding: 20px;
  border: 10px solid red;
  margin-top: 10px;
  margin-bottom: 100px;
  margin-left: 50px;
  margin-right: 30px;
}
```

### Margin Shorthand

```css
div {
  background-color: yellow;
  width: 100px;
  height: 100px;
  padding: 20px;
  border: 10px solid red;
  margin: 10px 30px 100px 50px; /* shorthand */
}
```

### Margin Auto Value Centers the Element

```css
div {
  width: 100px;
  height: 100px;
  background-color: black;
  margin: auto;
}
```

### 5. Opacity Property

```css
div {
  width: 100px;
  height: 100px;
  opacity: 0.5;
}
```

### **6. Float**

- Used to position elements to the **left** or **right** within their container.
- Commonly used for wrapping text around images.
- Values:
    - `left` → Floats the element to the left.
    - `right` → Floats the element to the right.
    - `none` → Default; no floating.
    - `inline-start` / `inline-end` → Respect text direction.

**Example:**

```html
<img src="image.jpg" alt="Example" style="float: right; width: 200px;">
<p>This text will wrap around the floated image.</p>
```

### **7. Clear**

- Used to control the behavior of elements that follow **floated** elements.
- Ensures elements don’t wrap around floated items.
- Values:
    - `left` → No floating elements allowed on the left.
    - `right` → No floating elements allowed on the right.
    - `both` → No floating elements allowed on either side.
    - `none` → Default.

**Example:**

```html
<div style="float: left; width: 200px; background: lightblue;">Sidebar</div>
<div style="clear: both; background: lightgray;">This section clears the float.</div>
```

### **8. calc()**

- The `calc()` function allows you to perform **calculations** for CSS property values.
- Useful for creating **responsive layouts** by mixing units (%, px, em, etc.).
- Spaces around operators (`+`, , , `/`) are **required**.

**Example 1 – Width Calculation:**

```html
<div style="width: calc(100% - 50px); background: lightcoral;">
  This div takes full width minus 50px.
</div>
```

**Example 2 – Font Size Calculation:**

```html
<p style="font-size: calc(16px + 1vw);">
  This text scales with the screen size.
</p>
```

### **9. Position**

- Specifies the positioning method for an element in a document.
- Values:
    - `static` → Default, elements appear in normal flow.
    - `relative` → Positioned relative to its normal position.
    - `absolute` → Positioned relative to the nearest positioned ancestor.
    - `fixed` → Positioned relative to the browser window, does not move on scroll.
    - `sticky` → Toggles between `relative` and `fixed` depending on scroll position.

**Example:**

```html
<div style="position: relative; left: 20px; top: 10px; background: lightblue;">
  Relative Position
</div>

<div style="position: absolute; top: 50px; left: 50px; background: lightgreen;">
  Absolute Position
</div>

<div style="position: fixed; bottom: 10px; right: 10px; background: lightcoral;">
  Fixed Position (always visible)
</div>

<div style="position: sticky; top: 0; background: yellow;">
  Sticky Header
</div>
```

## CSS Display Properties

### Block Elements

Takes full width and breaks the line.

```html
<h1>welcome</h1>
```

### Inline Elements

Takes its natural width.

```html
<a href="#">click here</a>
```

### Changing Display Types

```html
<h1 style="display: inline;">welcome</h1>
<a href="#" style="display: block;">click here</a>
```

### Inline-Block Elements

Mix between block and inline.

```html
<h1 style="display: inline-block; width: 200px;">welcome</h1>
```

### 🔎 What’s happening?

1. **`display: inline-block;`**
    - By default, `<h1>` is a **block-level element** (it takes the full width of the page).
    - Changing it to `inline-block` makes it behave **like text (inline)** but still allows you to set **width, height, padding, margin, etc.** (which you can’t do with pure `inline`).
    - So it flows inline with other elements but keeps block-like styling flexibility.
2. **`width: 200px;`**
    - This forces the `<h1>` to only take up **200px of width**, instead of stretching across the full screen.

### Hiding Elements

### 1.

```html
<h1 style="display: none;">Hidden</h1>
```

- **`display: none;`** → removes the element completely from the page layout.
- It doesn’t take up any **space** on the page.
- It’s as if the element is not there at all.

---

### 2.

```html
<h1 style="visibility: hidden;">Invisible</h1>
```

- **`visibility: hidden;`** → hides the element’s content, but the element still **occupies space** in the layout.
- So the blank space where it should be is still there.

## Text Properties in CSS

### Text Alignment

```html
<h1 style="text-align: right;">Right Aligned</h1>
<p style="text-align: justify;">Justified Text</p>
```

### Text Decoration & Transformation

- **Text Decoration (`text-decoration`)**
    - `underline` → draws a line below text.
    - `overline` → draws a line above text.
    - `line-through` → strikes through text.
- **Text Transformation (`text-transform`)**
    - `uppercase` → makes all letters uppercase.
    - `lowercase` → makes all letters lowercase.
    - `capitalize` → capitalizes the first letter of each word.

```html
<h1 style="text-decoration: underline;">Underlined</h1>
<p style="text-transform: uppercase;">Uppercase Text</p>
```

### Spacing and Shadow

- **`letter-spacing`** → controls space between letters.
- **`word-spacing`** → controls space between words.
- **`line-height`** → controls vertical spacing between lines.
- **`text-shadow`** → adds shadows (can make glowing, 3D, or soft blur effects)

```html
<!-- Letter Spacing -->
<h2 style="letter-spacing: 5px;">Wide Letter Spacing</h2>

<!-- Word Spacing -->
<p style="word-spacing: 20px;">This sentence has extra space between words.</p>

<!-- Line Height -->
<p style="line-height: 2;">
This paragraph has increased line height.<br>
Notice how the lines are further apart.
</p>

<!-- Text Shadow -->
<h1 style="text-shadow: 10px 10px 10px red;">Shadowed Text</h1>
<h2 style="text-shadow: 2px 2px 5px gray;">Subtle Shadow</h2>
<h3 style="text-shadow: -3px -3px 5px blue;">Glow Effect</h3>
```

### **Text Direction** (`direction`)

Controls the reading direction of text.

```css
p {
  direction: rtl; /* ltr | rtl → right to left | left to right */
}
```

Useful for languages like Arabic or Hebrew.

### **Word Break** (`word-break`)

Controls how words wrap onto the next line.

```css
p {
  word-break: break-word; /* normal | break-all | keep-all */
}
```

- `normal` → uses default line break rules.
- `break-word` → breaks long words when needed.
- `break-all` → breaks words at any character (useful for narrow containers).
- `keep-all` → prevents breaking words (used mainly for CJK languages).

### **White Space** (`white-space`)

Controls how spaces, tabs, and line breaks are handled.

```css
p {
  white-space: nowrap; /* normal | pre | pre-wrap | pre-line | nowrap */
}
```

- `normal` → collapses spaces, breaks lines normally.
- `pre` → respects spaces & line breaks (like `<pre>`).
- `pre-wrap` → keeps spaces & wraps lines when needed.
- `pre-line` → collapses spaces but respects line breaks.
- `nowrap` → prevents line breaks.

### **Overflow** (`overflow`)

Controls how overflowing content is handled.

```css
div {
  overflow: hidden; /* visible | hidden | scroll | auto */
}
```

- `visible` → content spills outside.
- `hidden` → extra content is clipped.
- `scroll` → always adds scrollbars.
- `auto` → adds scrollbars only when needed.

---

### **Text Overflow** (`text-overflow`)

Defines what happens when text is clipped. Works with `overflow: hidden;` + `white-space: nowrap;`.

```css
p {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis; /* clip | ellipsis | "custom string" */
}
```

`ellipsis` shows `...` when text is cut off.

### **Cursor Property**

The **`cursor`** property defines the type of mouse cursor displayed when hovering over an element.

**Common Values:**

- `default` → The default arrow.
- `pointer` → A hand icon, usually for links and buttons.
- `text` → An I-beam cursor for text selection.
- `move` → Indicates draggable elements.
- `not-allowed` → A circle with a line, indicating an action is not possible.
- `wait` → Indicates loading (spinning wheel or hourglass).
- `crosshair` → A precision crosshair.
- `help` → A help cursor (usually a question mark).

**Example:**

```css
button {
  cursor: pointer;
}

p {
  cursor: text;
}

div {
  cursor: move;
}
```

## Font Properties

### 1. Font Family

Specifies the font for an element.

```css
font-family: fantasy;
font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
```

### 2. Font-Style

Options: italic, normal, oblique

```css
font-style: italic;
```

### 3. Font-Weight

Options: lighter, normal, bold, bolder
Numeric Range: 100 to 900

```css
font-weight: 500;
```

### 4. Font-Size

Sets the size of the font.

```css
font-size: 100px;
```

### 5. Shorthand Property

Combines style, weight, size/line-height, and family.

```css
font: italic bold 12px/30px Georgia, serif;
```

## Link Styling

### 1. Basic Properties

```css
a {
  color: #fff;
  background-color: #000;
  padding: 10px 20px;
  text-decoration: none;
  text-align: center;
  display: block;
  width: 100px;
  margin: 10px auto;
  font-size: 20px;
}
```

### 2. Pseudo-Classes

```css
a:visited {
  background-color: blue;
}

a:hover {
  background-color: green;
}

a:active {
  background-color: yellow;
}
```

## List Styling

Apply CSS to `ul`, `ol`, `li` elements.

```css
ul {
  background-color: blue;
  padding: 20px;
  list-style-type: none;
  text-align: center;
  width: 40%;
  font-size: 20px;
}

li {
  background-color: brown;
  margin-top: 10px;
}
```

## Table Styling

Apply CSS to `table`, `thead`, `tbody`, `tr`, `th`, `td`.

- **able Borders**

```css
table, th, td {
  border: 1px solid black;
}
```

- **Collapse Borders** (`border-collapse`)

```css
table {
  border-collapse: collapse; /* separate | collapse */
}
```

- **Cell Padding** (`padding`)

```css
td {
  padding: 10px;
}
```

- **Table Width & Height**

```css
table {
  width: 80%;
  height: 200px;
}
```

- **Text Alignment in Cells**

```css
td {
  text-align: center;   /* left | right | center | justify */
  vertical-align: top;  /* top | middle | bottom */
}
```

- **Border Spacing** (`border-spacing`)

```css
table {
  border-collapse: separate; /* required for border-spacing */
  border-spacing: 15px 10px; /* horizontal vertical */
}
```

Controls the space **between table cells** when borders are not collapsed.

- **Table Caption Position** (`caption-side`)

```css
caption {
  caption-side: bottom; /* top | bottom */
}
```

Controls whether the table caption is displayed **above** or **below** the table.

## CSS Position Property

The `position` property specifies the type of positioning method used for an element. Possible values:

1. **Static** (default)
2. **Relative**
3. **Absolute**
4. **Fixed**
5. **Sticky**

---

### 1. Static Position (Default)

Elements are positioned according to the normal flow of the document.

```css
div {
  position: static;
}
```

---

### 2. Relative Position

The element is positioned **relative to its normal position**. Use `top`, `right`, `bottom`, `left` to move it.

```css
div {
  position: relative;
  top: 20px;
  left: 30px;
}
```

👉 It still takes up space in the layout, but visually shifts.

---

### 3. Absolute Position

The element is positioned **relative to its nearest positioned ancestor** (not just the parent, but the closest ancestor with `position` other than `static`).

```css
.parent {
  position: relative;
  width: 300px;
  height: 300px;
  background: lightblue;
}

.child {
  position: absolute;
  top: 20px;
  right: 20px;
  background: yellow;
}
```

👉 If no ancestor is positioned, it will be relative to the `<html>` element.

---

### 4. Fixed Position

The element is positioned **relative to the viewport**. It stays fixed when you scroll.

```css
div {
  position: fixed;
  bottom: 0;
  right: 0;
  background: red;
  color: white;
  padding: 10px;
}
```

👉 Commonly used for **sticky navbars, footers, or buttons**.

---

### 5. Sticky Position

The element toggles between **relative** and **fixed**, depending on the scroll position.

```css
h1 {
  position: sticky;
  top: 0;
  background: orange;
  padding: 10px;
}
```

👉 Useful for **sticky headers** in tables or navigation bars.

---

### Z-Index Property

Controls the **stack order** of elements (which one appears on top).

```css
div {
  position: absolute;
  z-index: 10; /* higher number = front */
}
```

---

⚡ Quick Example:

```html
<div class="box1">Box 1</div>
<div class="box2">Box 2</div>

<style>
  .box1 {
    width: 100px;
    height: 100px;
    background: blue;
    position: absolute;
    top: 50px;
    left: 50px;
    z-index: 1;
  }

  .box2 {
    width: 100px;
    height: 100px;
    background: red;
    position: absolute;
    top: 80px;
    left: 80px;
    z-index: 2;
  }
</style>

```

👉 Here, **Box 2** overlaps **Box 1** because it has a higher `z-index`.

## **Inheritance in CSS**

Some CSS properties are **inherited** by child elements automatically (e.g., `color`, `font-family`), while others are **not inherited** (e.g., `margin`, `padding`, `border`).

You can control inheritance using these keywords:

```css
p {
  color: inherit;   /* takes parent’s value */
  font-size: initial; /* resets to browser’s default */
  direction: unset; /* removes any set value, falls back to inheritance rules */
}
```

- **`inherit`** → forces a property to take the value from its parent.
- **`initial`** → resets to the property’s default (defined by CSS).
- **`unset`** → acts as `inherit` if the property is naturally inherited, otherwise acts as `initial`.

Example:

```css
div {
  color: blue;
}

p {
  color: inherit; /* will also be blue */
}
```
