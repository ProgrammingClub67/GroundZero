HTML Syntax Reference 🏗️
A comprehensive guide to HTML for ProgrammingClub67

## Table of Contents
1. [Basic Structure](#1-basic-structure)
2. [Headings](#2-headings)
3. [Text & Paragraphs](#3-text--paragraphs)
4. [Links](#4-links)
5. [Images](#5-images)
6. [Lists](#6-lists)
7. [Tables](#7-tables)
8. [Forms & Inputs](#8-forms--inputs)
9. [Semantic Elements](#9-semantic-elements)
10. [Divs & Spans](#10-divs--spans)
11. [Media](#11-media)
12. [Meta & Head Tags](#12-meta--head-tags)
13. [Comments](#13-comments)
14. [Inline vs Block Elements](#14-inline-vs-block-elements)
15. [Entities & Special Characters](#15-entities--special-characters)
16. [HTML Attributes](#16-html-attributes)
17. [Data Attributes](#17-data-attributes)
18. [Accessibility (ARIA)](#18-accessibility-aria)
19. [Scripting](#19-scripting)
20. [Deprecated Tags (Avoid These)](#20-deprecated-tags-avoid-these)

---

## 1. Basic Structure

Every HTML file starts with this boilerplate:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Page Title</title>
  </head>
  <body>
    <!-- Your content goes here -->
  </body>
</html>
```

| Tag | Purpose |
|-----|---------|
| `<!DOCTYPE html>` | Tells the browser this is HTML5 |
| `<html>` | Root element of the page |
| `<head>` | Metadata, styles, scripts — not visible |
| `<body>` | Everything the user sees |

---

## 2. Headings

There are 6 levels of headings. Only use one `<h1>` per page.

```html
<h1>Heading 1 — Page Title</h1>
<h2>Heading 2 — Section Title</h2>
<h3>Heading 3 — Sub-section</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6 — Smallest</h6>
```

---

## 3. Text & Paragraphs

```html
<!-- Paragraph -->
<p>This is a paragraph of text.</p>

<!-- Line break (no closing tag) -->
<p>Line one<br />Line two</p>

<!-- Horizontal rule / divider -->
<hr />

<!-- Bold -->
<strong>Bold and important</strong>
<b>Just visually bold</b>

<!-- Italic -->
<em>Italic and emphasized</em>
<i>Just visually italic</i>

<!-- Underline -->
<u>Underlined text</u>

<!-- Strikethrough -->
<s>Strikethrough</s>
<del>Deleted text</del>

<!-- Highlighted -->
<mark>Highlighted text</mark>

<!-- Superscript and subscript -->
<p>H<sub>2</sub>O</p>
<p>E = mc<sup>2</sup></p>

<!-- Small text -->
<small>Fine print or small text</small>

<!-- Preformatted text — preserves spaces and line breaks -->
<pre>
  This    spacing
    is    preserved
</pre>

<!-- Inline code -->
<code>console.log("hello")</code>

<!-- Keyboard input -->
<kbd>Ctrl + C</kbd>

<!-- Block quotation -->
<blockquote cite="https://example.com">
  This is a long quoted passage from another source.
</blockquote>

<!-- Inline quotation -->
<q>This is a short inline quote.</q>

<!-- Abbreviation with tooltip -->
<abbr title="HyperText Markup Language">HTML</abbr>

<!-- Citation -->
<cite>The Great Gatsby</cite>

<!-- Definition -->
<dfn>HTML</dfn> stands for HyperText Markup Language.

<!-- Address -->
<address>
  123 Main Street<br />
  Accra, Ghana
</address>

<!-- Word break opportunity — hint browser where to break long words -->
<p>superlongword<wbr />thatmightoverflow</p>
```

---

## 4. Links

```html
<!-- Basic link -->
<a href="https://example.com">Visit Example</a>

<!-- Open in new tab -->
<a href="https://example.com" target="_blank" rel="noopener noreferrer">Open in new tab</a>

<!-- Link to a section on the same page (anchor) -->
<a href="#section-id">Jump to section</a>

<!-- The target section needs a matching ID -->
<h2 id="section-id">This Section</h2>

<!-- Email link -->
<a href="mailto:club@example.com">Email Us</a>

<!-- Phone link -->
<a href="tel:+1234567890">Call Us</a>

<!-- Download link -->
<a href="file.pdf" download>Download PDF</a>

<!-- Download with custom filename -->
<a href="file.pdf" download="club-notes.pdf">Download Notes</a>

<!-- Link with no destination (placeholder) -->
<a href="#">Placeholder link</a>
```

---

## 5. Images

```html
<!-- Basic image — alt text is required for accessibility -->
<img src="image.jpg" alt="Description of image" />

<!-- With width and height (prevents layout shift) -->
<img src="logo.png" alt="Club Logo" width="200" height="100" />

<!-- Lazy loading — only loads when near viewport -->
<img src="photo.jpg" alt="Photo" loading="lazy" />

<!-- Responsive image with multiple sources -->
<picture>
  <source srcset="image-large.jpg" media="(min-width: 800px)" />
  <source srcset="image-medium.jpg" media="(min-width: 400px)" />
  <img src="image-small.jpg" alt="Responsive image" />
</picture>

<!-- Image with caption -->
<figure>
  <img src="chart.png" alt="Growth chart" />
  <figcaption>Fig 1. Growth over time</figcaption>
</figure>

<!-- Image as a link -->
<a href="https://example.com">
  <img src="banner.jpg" alt="Click to visit" />
</a>

<!-- SVG inline image -->
<img src="icon.svg" alt="Icon" />
```

---

## 6. Lists

```html
<!-- Unordered list (bullets) -->
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>

<!-- Ordered list (numbers) -->
<ol>
  <li>Step one</li>
  <li>Step two</li>
  <li>Step three</li>
</ol>

<!-- Ordered list starting at a different number -->
<ol start="5">
  <li>Item five</li>
  <li>Item six</li>
</ol>

<!-- Reversed ordered list -->
<ol reversed>
  <li>Last item</li>
  <li>Second to last</li>
</ol>

<!-- Nested list -->
<ul>
  <li>Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
    </ul>
  </li>
  <li>Backend</li>
</ul>

<!-- Description / definition list -->
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language — structure of web pages</dd>

  <dt>CSS</dt>
  <dd>Cascading Style Sheets — styling of web pages</dd>
</dl>
```

---

## 7. Tables

```html
<!-- Basic table -->
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Role</th>
      <th>Language</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Alice</td>
      <td>Frontend</td>
      <td>JavaScript</td>
    </tr>
    <tr>
      <td>Bob</td>
      <td>Backend</td>
      <td>Python</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="3">End of table</td>
    </tr>
  </tfoot>
</table>

<!-- Spanning columns -->
<tr>
  <td colspan="2">This cell spans 2 columns</td>
</tr>

<!-- Spanning rows -->
<tr>
  <td rowspan="2">This cell spans 2 rows</td>
  <td>Row 1</td>
</tr>
<tr>
  <td>Row 2</td>
</tr>

<!-- Table with caption -->
<table>
  <caption>Club Members 2026</caption>
  <tr>
    <th>Name</th>
    <th>Year</th>
  </tr>
</table>
```

---

## 8. Forms & Inputs

```html
<!-- Basic form -->
<form action="/submit" method="POST">

  <!-- Text input -->
  <label for="username">Username:</label>
  <input type="text" id="username" name="username" placeholder="Enter username" required />

  <!-- Password -->
  <label for="password">Password:</label>
  <input type="password" id="password" name="password" />

  <!-- Email -->
  <input type="email" name="email" placeholder="you@example.com" />

  <!-- Number -->
  <input type="number" name="age" min="1" max="100" />

  <!-- Range slider -->
  <input type="range" name="volume" min="0" max="100" value="50" />

  <!-- Date -->
  <input type="date" name="dob" />

  <!-- Time -->
  <input type="time" name="meeting-time" />

  <!-- Color picker -->
  <input type="color" name="fav-color" value="#ff0000" />

  <!-- Checkbox -->
  <input type="checkbox" id="agree" name="agree" value="yes" />
  <label for="agree">I agree to the terms</label>

  <!-- Radio buttons (only one can be selected) -->
  <input type="radio" id="html" name="language" value="html" />
  <label for="html">HTML</label>

  <input type="radio" id="css" name="language" value="css" />
  <label for="css">CSS</label>

  <!-- Dropdown select -->
  <select name="level">
    <option value="">-- Select level --</option>
    <option value="beginner">Beginner</option>
    <option value="intermediate" selected>Intermediate</option>
    <option value="advanced">Advanced</option>
  </select>

  <!-- Grouped dropdown -->
  <select name="topic">
    <optgroup label="Frontend">
      <option value="html">HTML</option>
      <option value="css">CSS</option>
    </optgroup>
    <optgroup label="Backend">
      <option value="node">Node.js</option>
    </optgroup>
  </select>

  <!-- Textarea -->
  <textarea name="bio" rows="4" cols="50" placeholder="Tell us about yourself..."></textarea>

  <!-- File upload -->
  <input type="file" name="avatar" accept="image/*" />

  <!-- Multiple file upload -->
  <input type="file" name="files" multiple />

  <!-- Hidden input -->
  <input type="hidden" name="csrf_token" value="abc123" />

  <!-- Search input -->
  <input type="search" name="q" placeholder="Search..." />

  <!-- URL input -->
  <input type="url" name="website" placeholder="https://example.com" />

  <!-- Tel input -->
  <input type="tel" name="phone" placeholder="+233 XX XXX XXXX" />

  <!-- Datalist — autocomplete suggestions -->
  <input type="text" list="languages" name="lang" />
  <datalist id="languages">
    <option value="HTML" />
    <option value="CSS" />
    <option value="JavaScript" />
  </datalist>

  <!-- Submit button -->
  <button type="submit">Submit</button>

  <!-- Reset button -->
  <button type="reset">Reset</button>

  <!-- Regular button -->
  <button type="button" onclick="doSomething()">Click Me</button>

  <!-- Fieldset and legend — group related inputs -->
  <fieldset>
    <legend>Personal Info</legend>
    <label for="fname">First Name:</label>
    <input type="text" id="fname" name="fname" />
  </fieldset>

</form>

<!-- Input attributes reference -->
<!--
  required       — field must be filled before submit
  disabled       — field is not editable, not submitted
  readonly       — field is not editable, is submitted
  autofocus      — field is focused on page load
  autocomplete   — "on" or "off"
  pattern        — regex the value must match
  min / max      — for number, date, range
  minlength / maxlength — for text inputs
  multiple       — allow multiple values (file, email)
  step           — increment for number/range inputs
-->
```

---

## 9. Semantic Elements

Semantic tags give meaning to your HTML structure. Use them instead of generic `<div>` tags where possible.

```html
<!-- Page layout -->
<header>
  <!-- Logo, nav, top-of-page content -->
</header>

<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
  </ul>
</nav>

<main>
  <!-- Main content of the page — only one per page -->

  <article>
    <!-- Self-contained content: blog post, news story -->
    <h2>Article Title</h2>
    <p>Article content...</p>
  </article>

  <section>
    <!-- Thematic grouping of content with a heading -->
    <h2>Section Title</h2>
    <p>Section content...</p>
  </section>

  <aside>
    <!-- Sidebar, related links, ads -->
    <p>Related articles...</p>
  </aside>

</main>

<footer>
  <!-- Copyright, links, contact info -->
  <p>&copy; 2026 ProgrammingClub67</p>
</footer>

<!-- Other semantic tags -->
<time datetime="2026-03-26">March 26, 2026</time>

<details>
  <summary>Click to expand</summary>
  <p>Hidden content revealed on click.</p>
</details>

<dialog id="myDialog">
  <p>This is a dialog box!</p>
  <button onclick="document.getElementById('myDialog').close()">Close</button>
</dialog>

<progress value="70" max="100">70%</progress>

<meter value="0.7" min="0" max="1">70%</meter>
```

---

## 10. Divs & Spans

```html
<!-- div — block-level generic container -->
<div class="card">
  <h2>Card Title</h2>
  <p>Card content.</p>
</div>

<!-- span — inline generic container -->
<p>My favorite color is <span style="color: red;">red</span>.</p>

<!-- Divs with IDs and classes -->
<div id="unique-element" class="box highlight">
  Content
</div>

<!-- Multiple classes on one element -->
<div class="card large featured">
  Content
</div>
```

---

## 11. Media

```html
<!-- Video -->
<video width="640" height="360" controls>
  <source src="video.mp4" type="video/mp4" />
  <source src="video.webm" type="video/webm" />
  Your browser does not support video.
</video>

<!-- Video with more options -->
<video
  src="video.mp4"
  width="640"
  height="360"
  controls
  autoplay
  muted
  loop
  poster="thumbnail.jpg"
>
</video>

<!-- Audio -->
<audio controls>
  <source src="audio.mp3" type="audio/mpeg" />
  <source src="audio.ogg" type="audio/ogg" />
  Your browser does not support audio.
</audio>

<!-- Embed another webpage (iframe) -->
<iframe
  src="https://example.com"
  width="600"
  height="400"
  title="Embedded page"
  loading="lazy"
>
</iframe>

<!-- Embed a YouTube video -->
<iframe
  width="560"
  height="315"
  src="https://www.youtube.com/embed/VIDEO_ID"
  title="YouTube video"
  allowfullscreen
>
</iframe>

<!-- Canvas — for drawing with JavaScript -->
<canvas id="myCanvas" width="400" height="200"></canvas>

<!-- SVG inline -->
<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg">
  <circle cx="50" cy="50" r="40" fill="blue" />
</svg>
```

---

## 12. Meta & Head Tags

```html
<head>
  <!-- Character encoding — always include -->
  <meta charset="UTF-8" />

  <!-- Responsive viewport — always include -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <!-- Page title — shows in browser tab -->
  <title>ProgrammingClub67</title>

  <!-- Page description — used by search engines -->
  <meta name="description" content="ProgrammingClub67 web dev semester repo." />

  <!-- Author -->
  <meta name="author" content="ProgrammingClub67" />

  <!-- Keywords (less important today but still used) -->
  <meta name="keywords" content="html, css, javascript, web development" />

  <!-- Prevent search engines from indexing -->
  <meta name="robots" content="noindex, nofollow" />

  <!-- Refresh page after 5 seconds -->
  <meta http-equiv="refresh" content="5" />

  <!-- Redirect after 3 seconds -->
  <meta http-equiv="refresh" content="3;url=https://example.com" />

  <!-- Favicon -->
  <link rel="icon" href="favicon.ico" type="image/x-icon" />
  <link rel="icon" href="favicon.png" type="image/png" />

  <!-- Apple touch icon -->
  <link rel="apple-touch-icon" href="apple-icon.png" />

  <!-- Link external CSS -->
  <link rel="stylesheet" href="styles.css" />

  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Inter&display=swap" rel="stylesheet" />

  <!-- Open Graph — for social media previews -->
  <meta property="og:title" content="ProgrammingClub67" />
  <meta property="og:description" content="Web dev semester." />
  <meta property="og:image" content="https://example.com/preview.jpg" />
  <meta property="og:url" content="https://example.com" />
  <meta property="og:type" content="website" />

  <!-- Twitter card -->
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="ProgrammingClub67" />
  <meta name="twitter:description" content="Web dev semester." />
  <meta name="twitter:image" content="https://example.com/preview.jpg" />

  <!-- Canonical URL — prevents duplicate content issues -->
  <link rel="canonical" href="https://example.com/page" />

  <!-- Inline styles (prefer external CSS) -->
  <style>
    body {
      font-family: sans-serif;
    }
  </style>

  <!-- Script in head (use defer to not block rendering) -->
  <script src="app.js" defer></script>
</head>
```

---

## 13. Comments

```html
<!-- This is a single-line comment -->

<!--
  This is a
  multi-line comment
-->

<!-- TODO: Add navigation here -->
<!-- NOTE: This section is temporary -->
```

---

## 14. Inline vs Block Elements

**Block elements** start on a new line and take up full width.  
**Inline elements** flow within text and only take up as much space as needed.

| Block Elements | Inline Elements |
|----------------|-----------------|
| `<div>` | `<span>` |
| `<p>` | `<a>` |
| `<h1>`–`<h6>` | `<strong>` |
| `<ul>`, `<ol>`, `<li>` | `<em>` |
| `<table>` | `<img>` |
| `<form>` | `<code>` |
| `<header>`, `<footer>`, `<main>` | `<label>` |
| `<section>`, `<article>` | `<button>` |
| `<blockquote>` | `<input>` |
| `<pre>` | `<kbd>` |

---

## 15. Entities & Special Characters

Use these when you need to display reserved or special characters:

```html
&amp;    <!-- & -->
&lt;     <!-- < -->
&gt;     <!-- > -->
&quot;   <!-- " -->
&apos;   <!-- ' -->
&nbsp;   <!-- Non-breaking space -->
&copy;   <!-- © -->
&reg;    <!-- ® -->
&trade;  <!-- ™ -->
&mdash;  <!-- — (em dash) -->
&ndash;  <!-- – (en dash) -->
&hellip; <!-- … (ellipsis) -->
&euro;   <!-- € -->
&pound;  <!-- £ -->
&cent;   <!-- ¢ -->
&deg;    <!-- ° -->
&times;  <!-- × -->
&divide; <!-- ÷ -->
&frac12; <!-- ½ -->
&frac14; <!-- ¼ -->
&frac34; <!-- ¾ -->
&hearts; <!-- ♥ -->
&spades; <!-- ♠ -->
```

---

## 16. HTML Attributes

### Global Attributes (work on ANY element)

```html
<!-- id — unique identifier -->
<div id="header"></div>

<!-- class — for CSS and JS targeting -->
<div class="card highlighted"></div>

<!-- style — inline CSS (avoid where possible) -->
<p style="color: red; font-size: 18px;">Red text</p>

<!-- title — tooltip on hover -->
<p title="This is a tooltip">Hover over me</p>

<!-- lang — language of element content -->
<p lang="fr">Bonjour le monde</p>

<!-- dir — text direction -->
<p dir="rtl">Right to left text</p>
<p dir="ltr">Left to right text</p>

<!-- hidden — hides element (like display: none) -->
<div hidden>You can't see me</div>

<!-- tabindex — controls tab key order -->
<button tabindex="1">First</button>
<button tabindex="2">Second</button>
<div tabindex="0">Focusable div</div>

<!-- contenteditable — makes element editable -->
<p contenteditable="true">Click to edit this text</p>

<!-- draggable -->
<img src="logo.png" draggable="true" alt="Draggable logo" />

<!-- spellcheck -->
<textarea spellcheck="true"></textarea>

<!-- translate — hint to translation tools -->
<p translate="no">ProgrammingClub67</p>
```

---

## 17. Data Attributes

Custom attributes for storing extra data on elements — great for JavaScript:

```html
<!-- Define a data attribute -->
<div data-user-id="42" data-role="admin">Alice</div>

<button data-action="delete" data-target="post-1">Delete Post</button>

<!-- Access in JavaScript -->
<script>
  const btn = document.querySelector('button');
  console.log(btn.dataset.action);  // "delete"
  console.log(btn.dataset.target);  // "post-1"
</script>
```

---

## 18. Accessibility (ARIA)

ARIA attributes help screen readers understand your content:

```html
<!-- Role — describes what an element is -->
<div role="button" tabindex="0">Click me</div>
<div role="navigation">...</div>
<div role="alert">Error: something went wrong</div>

<!-- aria-label — text label for screen readers -->
<button aria-label="Close menu">X</button>

<!-- aria-labelledby — points to another element as label -->
<div id="dialog-title">Confirm Delete</div>
<dialog aria-labelledby="dialog-title">...</dialog>

<!-- aria-describedby — points to description -->
<input type="password" aria-describedby="pwd-hint" />
<p id="pwd-hint">Must be at least 8 characters.</p>

<!-- aria-hidden — hides from screen readers -->
<span aria-hidden="true">🚀</span>

<!-- aria-expanded — for toggleable elements -->
<button aria-expanded="false" aria-controls="menu">Menu</button>
<ul id="menu" hidden>...</ul>

<!-- aria-required -->
<input type="text" aria-required="true" />

<!-- aria-disabled -->
<button aria-disabled="true">Disabled</button>

<!-- aria-live — announce dynamic content changes -->
<div aria-live="polite">Loading results...</div>
<div aria-live="assertive">Critical error!</div>

<!-- Skip navigation link — accessibility best practice -->
<a href="#main-content" class="skip-link">Skip to main content</a>
<main id="main-content">...</main>

<!-- Always use alt on images -->
<img src="photo.jpg" alt="Team photo at hackathon" />

<!-- Decorative images get empty alt -->
<img src="divider.png" alt="" />
```

---

## 19. Scripting

```html
<!-- External script — at end of body or with defer -->
<script src="app.js"></script>

<!-- Defer — runs after HTML is parsed -->
<script src="app.js" defer></script>

<!-- Async — runs as soon as downloaded (order not guaranteed) -->
<script src="analytics.js" async></script>

<!-- Inline script -->
<script>
  console.log("Hello from ProgrammingClub67!");
  alert("Welcome!");
</script>

<!-- noscript — shown if JavaScript is disabled -->
<noscript>
  <p>Please enable JavaScript to use this site.</p>
</noscript>

<!-- Script with type module — for ES6 modules -->
<script type="module" src="main.js"></script>
```

---

## 20. Deprecated Tags (Avoid These)

These tags still technically work in browsers but should **never** be used. Use CSS instead.

| Deprecated Tag | Use Instead |
|----------------|-------------|
| `<center>` | `text-align: center` in CSS |
| `<font>` | CSS `font-family`, `color`, `font-size` |
| `<b>` for importance | `<strong>` |
| `<i>` for emphasis | `<em>` |
| `<u>` for styling | CSS `text-decoration: underline` |
| `<strike>` | `<s>` or CSS `text-decoration: line-through` |
| `<big>` | CSS `font-size` |
| `<tt>` | `<code>` or CSS `font-family: monospace` |
| `<frame>`, `<frameset>` | Nothing — just don't |
| `bgcolor` attribute | CSS `background-color` |
| `align` attribute | CSS `text-align` or `flexbox` |
| `border` attribute on `<table>` | CSS `border` |

---

## Quick Reference Card

```html
<!-- Page shell -->
<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><title>Title</title></head><body></body></html>

<!-- Common text tags -->
<h1>–<h6>  <p>  <strong>  <em>  <br>  <hr>  <span>  <div>

<!-- Links & images -->
<a href="url">text</a>
<img src="url" alt="description">

<!-- Lists -->
<ul><li></li></ul>
<ol><li></li></ol>

<!-- Table -->
<table><thead><tr><th></th></tr></thead><tbody><tr><td></td></tr></tbody></table>

<!-- Form -->
<form><input type="text"><button type="submit">Go</button></form>

<!-- Semantic layout -->
<header> <nav> <main> <section> <article> <aside> <footer>
```

---

*ProgrammingClub67 — Web Development Semester 2026* 🚀
