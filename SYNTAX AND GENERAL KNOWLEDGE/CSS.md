
# CSS Syntax Reference 🎨
> A comprehensive guide to CSS for ProgrammingClub67

---

## Table of Contents
1. [How CSS Works](#1-how-css-works)
2. [Selectors](#2-selectors)
3. [Colors](#3-colors)
4. [Typography & Fonts](#4-typography--fonts)
5. [The Box Model](#5-the-box-model)
6. [Display & Visibility](#6-display--visibility)
7. [Positioning](#7-positioning)
8. [Flexbox](#8-flexbox)
9. [CSS Grid](#9-css-grid)
10. [Backgrounds](#10-backgrounds)
11. [Borders & Outlines](#11-borders--outlines)
12. [Sizing & Units](#12-sizing--units)
13. [Spacing — Margin & Padding](#13-spacing--margin--padding)
14. [Overflow](#14-overflow)
15. [Transforms](#15-transforms)
16. [Transitions](#16-transitions)
17. [Animations](#17-animations)
18. [Pseudo-classes](#18-pseudo-classes)
19. [Pseudo-elements](#19-pseudo-elements)
20. [Variables (Custom Properties)](#20-variables-custom-properties)
21. [Media Queries & Responsive Design](#21-media-queries--responsive-design)
22. [Cascade, Specificity & Inheritance](#22-cascade-specificity--inheritance)
23. [Filters & Effects](#23-filters--effects)
24. [Lists & Tables](#24-lists--tables)
25. [Useful Utility Patterns](#25-useful-utility-patterns)

---

## 1. How CSS Works

### Three ways to add CSS

```html
<!-- 1. External stylesheet (BEST — use this) -->
<link rel="stylesheet" href="styles.css" />

<!-- 2. Internal styles (okay for small projects) -->
<style>
  p { color: red; }
</style>

<!-- 3. Inline styles (avoid — hard to maintain) -->
<p style="color: red;">Text</p>
```

### Basic syntax

```css
selector {
  property: value;
  another-property: another-value;
}

/* Example */
h1 {
  color: navy;
  font-size: 32px;
  font-weight: bold;
}
```

---

## 2. Selectors

```css
/* Universal selector — targets everything */
* {
  box-sizing: border-box;
}

/* Type selector — targets all <p> elements */
p {
  color: gray;
}

/* Class selector — targets class="card" */
.card {
  background: white;
}

/* ID selector — targets id="header" */
#header {
  background: navy;
}

/* Multiple selectors — comma separated */
h1, h2, h3 {
  font-family: sans-serif;
}

/* Descendant selector — <p> inside a .card */
.card p {
  font-size: 14px;
}

/* Direct child selector — only direct children */
.nav > li {
  display: inline;
}

/* Adjacent sibling — element immediately after */
h2 + p {
  font-weight: bold;
}

/* General sibling — all siblings after */
h2 ~ p {
  color: gray;
}

/* Attribute selector — has the attribute */
input[required] {
  border: 2px solid red;
}

/* Attribute equals */
input[type="text"] {
  border: 1px solid gray;
}

/* Attribute starts with */
a[href^="https"] {
  color: green;
}

/* Attribute ends with */
a[href$=".pdf"] {
  color: orange;
}

/* Attribute contains */
a[href*="github"] {
  font-weight: bold;
}

/* :not() — excludes matching elements */
p:not(.intro) {
  color: gray;
}

/* :is() — matches any selector in the list */
:is(h1, h2, h3) {
  line-height: 1.2;
}

/* :has() — parent has matching child */
.card:has(img) {
  padding: 0;
}
```

---

## 3. Colors

```css
/* Named colors */
color: red;
color: navy;
color: tomato;
color: coral;
color: transparent;

/* Hex */
color: #ff0000;       /* red */
color: #00ff00;       /* green */
color: #0000ff;       /* blue */
color: #fff;          /* shorthand white */
color: #000;          /* shorthand black */
color: #ff000080;     /* hex with 50% opacity */

/* RGB */
color: rgb(255, 0, 0);
color: rgb(0, 128, 255);

/* RGBA — with alpha/opacity 0–1 */
color: rgba(0, 0, 0, 0.5);    /* 50% transparent black */
color: rgba(255, 0, 0, 0.8);

/* HSL — hue (0-360), saturation %, lightness % */
color: hsl(0, 100%, 50%);     /* red */
color: hsl(200, 80%, 50%);    /* blue */
color: hsl(120, 60%, 40%);    /* green */

/* HSLA — with alpha */
color: hsla(0, 100%, 50%, 0.5);

/* CSS Color Level 4 — modern syntax */
color: rgb(255 0 0);
color: rgb(255 0 0 / 50%);
color: hsl(0 100% 50% / 0.5);

/* currentColor — inherits current text color */
border: 2px solid currentColor;

/* Common color properties */
color: red;                    /* text color */
background-color: lightblue;   /* background */
border-color: gray;            /* border */
outline-color: blue;           /* outline */
```

---

## 4. Typography & Fonts

```css
/* Font family — always include fallbacks */
font-family: 'Inter', Arial, sans-serif;
font-family: Georgia, 'Times New Roman', serif;
font-family: 'Courier New', Courier, monospace;

/* Font size */
font-size: 16px;
font-size: 1rem;       /* relative to root (usually 16px) */
font-size: 1.5em;      /* relative to parent */
font-size: 120%;
font-size: large;
font-size: clamp(1rem, 2.5vw, 2rem); /* responsive font */

/* Font weight */
font-weight: normal;   /* 400 */
font-weight: bold;     /* 700 */
font-weight: 100;      /* thin */
font-weight: 300;      /* light */
font-weight: 500;      /* medium */
font-weight: 600;      /* semi-bold */
font-weight: 800;      /* extra-bold */
font-weight: 900;      /* black */

/* Font style */
font-style: normal;
font-style: italic;
font-style: oblique;

/* Line height */
line-height: 1;        /* same as font-size */
line-height: 1.5;      /* 1.5× font-size (recommended) */
line-height: 24px;
line-height: 150%;

/* Letter spacing */
letter-spacing: 0.05em;
letter-spacing: 2px;
letter-spacing: -1px;  /* tighter */

/* Word spacing */
word-spacing: 4px;

/* Text alignment */
text-align: left;
text-align: center;
text-align: right;
text-align: justify;

/* Text decoration */
text-decoration: none;
text-decoration: underline;
text-decoration: overline;
text-decoration: line-through;
text-decoration: underline dotted red;

/* Text transform */
text-transform: uppercase;
text-transform: lowercase;
text-transform: capitalize;
text-transform: none;

/* Text indent */
text-indent: 2rem;

/* White space */
white-space: normal;
white-space: nowrap;       /* no wrapping */
white-space: pre;          /* preserve spaces and newlines */
white-space: pre-wrap;     /* preserve + wrap */

/* Word break */
word-break: break-word;
overflow-wrap: break-word;

/* Text overflow — needs overflow: hidden and white-space: nowrap */
text-overflow: ellipsis;   /* adds ... when text overflows */
text-overflow: clip;

/* Vertical alignment (inline/table) */
vertical-align: top;
vertical-align: middle;
vertical-align: bottom;
vertical-align: baseline;

/* Font shorthand */
font: italic bold 18px/1.5 'Inter', sans-serif;
/*    style weight size/line-height family */

/* Custom Google Font */
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');

/* Custom local font */
@font-face {
  font-family: 'MyFont';
  src: url('myfont.woff2') format('woff2'),
       url('myfont.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}
```

---

## 5. The Box Model

Every HTML element is a box made of:

```
┌──────────────────────────────┐
│           MARGIN             │
│  ┌────────────────────────┐  │
│  │        BORDER          │  │
│  │  ┌──────────────────┐  │  │
│  │  │     PADDING      │  │  │
│  │  │  ┌────────────┐  │  │  │
│  │  │  │  CONTENT   │  │  │  │
│  │  │  └────────────┘  │  │  │
│  │  └──────────────────┘  │  │
│  └────────────────────────┘  │
└──────────────────────────────┘
```

```css
/* By default, width/height only sets content size.
   Use border-box to include padding and border in the size. */

/* ALWAYS put this at the top of your CSS */
*, *::before, *::after {
  box-sizing: border-box;
}

.box {
  width: 300px;
  height: 200px;
  padding: 20px;
  border: 2px solid black;
  margin: 10px;
}
```

---

## 6. Display & Visibility

```css
/* Block — full width, new line */
display: block;

/* Inline — flows with text, no width/height */
display: inline;

/* Inline-block — flows with text, but accepts width/height */
display: inline-block;

/* Flex — flexbox container */
display: flex;

/* Grid — grid container */
display: grid;

/* None — removes element from layout entirely */
display: none;

/* Table displays */
display: table;
display: table-row;
display: table-cell;

/* Visibility — hides visually but keeps space */
visibility: visible;
visibility: hidden;

/* Opacity — 0 (invisible) to 1 (fully visible) */
opacity: 0;
opacity: 0.5;
opacity: 1;

/* Pointer events — disable mouse interaction */
pointer-events: none;
pointer-events: auto;
```

---

## 7. Positioning

```css
/* Static — default, no special positioning */
position: static;

/* Relative — offset from its normal position */
position: relative;
top: 10px;
left: 20px;

/* Absolute — positioned relative to nearest positioned ancestor */
position: absolute;
top: 0;
right: 0;
bottom: 0;
left: 0;

/* Fixed — positioned relative to viewport (stays on scroll) */
position: fixed;
top: 0;
left: 0;
width: 100%;

/* Sticky — relative until scroll threshold, then fixed */
position: sticky;
top: 0;         /* sticks to top when scrolled to */

/* Z-index — stacking order (higher = in front) */
z-index: 1;
z-index: 10;
z-index: 999;
z-index: -1;    /* behind everything */

/* Centering with absolute positioning */
.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* Full-cover overlay */
.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  z-index: 100;
}
```

---

## 8. Flexbox

Apply `display: flex` to the **parent** container:

```css
/* ── CONTAINER (parent) ── */
.container {
  display: flex;

  /* Direction */
  flex-direction: row;            /* → default */
  flex-direction: row-reverse;    /* ← */
  flex-direction: column;         /* ↓ */
  flex-direction: column-reverse; /* ↑ */

  /* Wrapping */
  flex-wrap: nowrap;    /* default — all on one line */
  flex-wrap: wrap;      /* wraps to next line */
  flex-wrap: wrap-reverse;

  /* Shorthand */
  flex-flow: row wrap;

  /* Align along main axis (horizontal if row) */
  justify-content: flex-start;     /* default */
  justify-content: flex-end;
  justify-content: center;
  justify-content: space-between;  /* equal gaps between */
  justify-content: space-around;   /* equal space around */
  justify-content: space-evenly;   /* truly equal gaps */

  /* Align along cross axis (vertical if row) */
  align-items: stretch;     /* default — fills height */
  align-items: flex-start;
  align-items: flex-end;
  align-items: center;
  align-items: baseline;

  /* Align wrapped lines */
  align-content: flex-start;
  align-content: center;
  align-content: space-between;

  /* Gap between items */
  gap: 16px;
  gap: 16px 24px;    /* row-gap column-gap */
  row-gap: 16px;
  column-gap: 24px;
}

/* ── ITEMS (children) ── */
.item {
  /* Grow to fill available space */
  flex-grow: 0;    /* default — don't grow */
  flex-grow: 1;    /* grow proportionally */

  /* Shrink when not enough space */
  flex-shrink: 1;  /* default — can shrink */
  flex-shrink: 0;  /* never shrink */

  /* Base size before growing/shrinking */
  flex-basis: auto;
  flex-basis: 200px;
  flex-basis: 50%;

  /* Shorthand: grow shrink basis */
  flex: 1;           /* flex: 1 1 0 */
  flex: 0 0 200px;   /* fixed size */
  flex: 1 1 auto;

  /* Override align-items for single item */
  align-self: center;
  align-self: flex-start;
  align-self: stretch;

  /* Order — default is 0, lower = earlier */
  order: 0;
  order: -1;   /* moves to front */
  order: 1;    /* moves to end */
}

/* Common pattern: center one item */
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Common pattern: space nav items */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

/* Common pattern: equal-width columns */
.columns .col {
  flex: 1;
}
```

---

## 9. CSS Grid

Apply `display: grid` to the **parent** container:

```css
/* ── CONTAINER (parent) ── */
.grid {
  display: grid;

  /* Define columns */
  grid-template-columns: 200px 200px 200px;
  grid-template-columns: 1fr 1fr 1fr;          /* equal fractions */
  grid-template-columns: 1fr 2fr 1fr;          /* unequal fractions */
  grid-template-columns: repeat(3, 1fr);       /* shorthand */
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); /* responsive */
  grid-template-columns: 200px auto 100px;     /* mix of units */

  /* Define rows */
  grid-template-rows: 100px auto 60px;
  grid-template-rows: repeat(3, 1fr);

  /* Gap */
  gap: 16px;
  column-gap: 24px;
  row-gap: 16px;

  /* Align all items */
  justify-items: start | end | center | stretch;
  align-items: start | end | center | stretch;

  /* Align the grid in its container */
  justify-content: start | end | center | space-between | space-around;
  align-content: start | end | center | space-between;

  /* Auto rows height */
  grid-auto-rows: 200px;
  grid-auto-rows: minmax(100px, auto);

  /* Named template areas */
  grid-template-areas:
    "header header header"
    "sidebar main main"
    "footer footer footer";
}

/* ── ITEMS (children) ── */
.item {
  /* Place by line numbers */
  grid-column: 1 / 3;       /* from line 1 to line 3 */
  grid-column: 1 / -1;      /* full width */
  grid-column: span 2;      /* span 2 columns */

  grid-row: 1 / 3;
  grid-row: span 2;

  /* Place by named area */
  grid-area: header;
  grid-area: sidebar;
  grid-area: main;
  grid-area: footer;

  /* Override alignment for one item */
  justify-self: center;
  align-self: end;
}

/* Named areas example */
.layout {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
  grid-template-columns: 250px 1fr;
  grid-template-rows: 60px 1fr 60px;
  min-height: 100vh;
}
.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.footer  { grid-area: footer; }
```

---

## 10. Backgrounds

```css
/* Background color */
background-color: lightblue;
background-color: transparent;

/* Background image */
background-image: url('image.jpg');
background-image: url('image.png'), url('overlay.png'); /* multiple */

/* Background size */
background-size: auto;
background-size: cover;    /* fills element, may crop */
background-size: contain;  /* fits inside, may leave gaps */
background-size: 200px 100px;
background-size: 50%;

/* Background position */
background-position: center;
background-position: top right;
background-position: 50% 50%;
background-position: 20px 40px;

/* Background repeat */
background-repeat: repeat;     /* default */
background-repeat: no-repeat;
background-repeat: repeat-x;
background-repeat: repeat-y;

/* Background attachment */
background-attachment: scroll;  /* default */
background-attachment: fixed;   /* parallax effect */
background-attachment: local;

/* Background origin */
background-origin: padding-box;
background-origin: border-box;
background-origin: content-box;

/* Background clip */
background-clip: border-box;
background-clip: padding-box;
background-clip: content-box;
background-clip: text;  /* clips to text — use with color: transparent */

/* Shorthand */
background: url('image.jpg') center/cover no-repeat;
background: #f0f0f0 url('pattern.png') top left repeat;

/* CSS Gradients */

/* Linear gradient */
background: linear-gradient(red, blue);
background: linear-gradient(to right, red, blue);
background: linear-gradient(45deg, red, blue);
background: linear-gradient(to right, red, yellow, blue);
background: linear-gradient(to right, red 0%, yellow 50%, blue 100%);

/* Radial gradient */
background: radial-gradient(circle, red, blue);
background: radial-gradient(ellipse at center, red, blue);
background: radial-gradient(circle at top left, red 20%, blue 80%);

/* Conic gradient */
background: conic-gradient(red, yellow, green, blue, red);
background: conic-gradient(from 0deg, red 90deg, blue 180deg, green 360deg);

/* Repeating gradients */
background: repeating-linear-gradient(45deg, red 0px, red 10px, white 10px, white 20px);
```

---

## 11. Borders & Outlines

```css
/* Border shorthand: width style color */
border: 1px solid black;
border: 2px dashed red;
border: 4px dotted blue;

/* Individual sides */
border-top: 1px solid black;
border-right: 1px solid black;
border-bottom: 1px solid black;
border-left: 1px solid black;

/* Individual properties */
border-width: 2px;
border-width: 1px 2px 3px 4px; /* top right bottom left */

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

border-color: red;

/* Border radius — rounded corners */
border-radius: 4px;
border-radius: 50%;            /* circle (on square element) */
border-radius: 8px 0 8px 0;   /* top-left, top-right, bottom-right, bottom-left */
border-radius: 16px 4px;       /* top-left+bottom-right, top-right+bottom-left */
border-top-left-radius: 10px;
border-top-right-radius: 10px;

/* Outline — like border but outside, doesn't affect layout */
outline: 2px solid blue;
outline: none;                 /* remove focus outline (accessibility warning!) */
outline-offset: 4px;          /* space between element and outline */

/* Box shadow */
box-shadow: 2px 4px 8px rgba(0, 0, 0, 0.2);
/* x-offset y-offset blur-radius color */
box-shadow: 0 4px 16px rgba(0, 0, 0, 0.15);

/* Multiple shadows */
box-shadow: 0 2px 4px rgba(0,0,0,0.1), 0 8px 24px rgba(0,0,0,0.15);

/* Inset shadow (inner shadow) */
box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.2);

/* Text shadow */
text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
text-shadow: 0 0 10px rgba(255, 255, 0, 0.8); /* glow effect */
```

---

## 12. Sizing & Units

```css
/* Absolute units */
width: 200px;       /* pixels */
width: 5cm;         /* centimetres */
width: 2in;         /* inches */
width: 12pt;        /* points (1pt = 1/72 inch) */

/* Relative units */
width: 50%;         /* % of parent */
width: 50vw;        /* % of viewport width */
height: 100vh;      /* % of viewport height */
font-size: 1rem;    /* relative to root font size */
font-size: 1.5em;   /* relative to parent font size */
width: 10vmin;      /* % of smaller viewport dimension */
width: 10vmax;      /* % of larger viewport dimension */

/* Modern units */
height: 100dvh;     /* dynamic viewport height (mobile-friendly) */
width: 100svw;      /* small viewport width */
width: 100lvw;      /* large viewport width */

/* min(), max(), clamp() */
width: min(500px, 100%);           /* smaller of the two */
width: max(200px, 50%);            /* larger of the two */
font-size: clamp(1rem, 2.5vw, 2rem); /* min, preferred, max */
width: clamp(300px, 50%, 800px);

/* Width and height */
width: auto;
width: 100%;
width: fit-content;
width: min-content;
width: max-content;

min-width: 200px;
max-width: 1200px;
min-height: 100px;
max-height: 500px;

/* Aspect ratio */
aspect-ratio: 16 / 9;
aspect-ratio: 1;        /* square */
aspect-ratio: 4 / 3;
```

---

## 13. Spacing — Margin & Padding

```css
/* Padding — space INSIDE the element */
padding: 16px;                      /* all sides */
padding: 16px 24px;                 /* top/bottom  left/right */
padding: 8px 16px 24px 32px;        /* top right bottom left */
padding-top: 16px;
padding-right: 24px;
padding-bottom: 16px;
padding-left: 24px;

/* Margin — space OUTSIDE the element */
margin: 16px;
margin: 16px 24px;
margin: 8px 16px 24px 32px;
margin-top: 16px;
margin-right: 24px;
margin-bottom: 16px;
margin-left: 24px;

/* Auto margin — center block elements */
margin: 0 auto;          /* center horizontally */
margin-left: auto;       /* push to right */
margin-right: auto;      /* push to left */

/* Negative margin */
margin-top: -10px;       /* pull element up */

/* Margin collapse — top and bottom margins of adjacent elements merge */
/* This is a common CSS gotcha! */
h1 { margin-bottom: 20px; }
p  { margin-top: 10px; }
/* Actual gap = 20px (the larger one), not 30px */
```

---

## 14. Overflow

```css
overflow: visible;    /* default — content spills out */
overflow: hidden;     /* clips overflow content */
overflow: scroll;     /* always shows scrollbars */
overflow: auto;       /* scrollbar only when needed */
overflow: clip;       /* clips with no scroll */

overflow-x: hidden;   /* horizontal only */
overflow-y: scroll;   /* vertical only */

/* Scroll behavior */
scroll-behavior: smooth;
scroll-snap-type: y mandatory;
scroll-snap-align: start;
```

---

## 15. Transforms

```css
/* Translate — move */
transform: translateX(50px);
transform: translateY(-20px);
transform: translate(50px, -20px);
transform: translateZ(100px);       /* 3D */

/* Scale */
transform: scale(1.5);             /* 150% of original */
transform: scaleX(2);
transform: scaleY(0.5);
transform: scale(1.2, 0.8);

/* Rotate */
transform: rotate(45deg);
transform: rotate(-90deg);
transform: rotateX(45deg);         /* 3D */
transform: rotateY(45deg);

/* Skew */
transform: skewX(20deg);
transform: skewY(10deg);
transform: skew(20deg, 10deg);

/* Multiple transforms */
transform: translate(-50%, -50%) rotate(45deg) scale(1.2);

/* Transform origin — pivot point */
transform-origin: center;          /* default */
transform-origin: top left;
transform-origin: 50% 50%;
transform-origin: 0 0;

/* 3D perspective */
perspective: 1000px;               /* on parent */
transform: perspective(1000px) rotateY(30deg);

/* Backface visibility */
backface-visibility: hidden;
```

---

## 16. Transitions

```css
/* Syntax: property duration timing-function delay */
transition: all 0.3s ease;
transition: opacity 0.3s ease;
transition: background-color 0.2s linear;
transition: transform 0.5s ease-in-out;

/* Multiple transitions */
transition: opacity 0.3s ease, transform 0.3s ease;

/* Timing functions */
transition-timing-function: ease;          /* slow-fast-slow (default) */
transition-timing-function: linear;        /* constant speed */
transition-timing-function: ease-in;       /* slow start */
transition-timing-function: ease-out;      /* slow end */
transition-timing-function: ease-in-out;   /* slow start and end */
transition-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);

/* Delay */
transition-delay: 0.2s;

/* Common hover transition pattern */
.button {
  background-color: navy;
  transition: background-color 0.2s ease, transform 0.2s ease;
}
.button:hover {
  background-color: royalblue;
  transform: translateY(-2px);
}
```

---

## 17. Animations

```css
/* Define the animation */
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes bounce {
  0%   { transform: translateY(0); }
  50%  { transform: translateY(-20px); }
  100% { transform: translateY(0); }
}

@keyframes spin {
  from { transform: rotate(0deg); }
  to   { transform: rotate(360deg); }
}

@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50%       { transform: scale(1.05); }
}

/* Apply the animation */
.element {
  animation-name: fadeIn;
  animation-duration: 0.5s;
  animation-timing-function: ease;
  animation-delay: 0s;
  animation-iteration-count: 1;      /* or infinite */
  animation-direction: normal;       /* or reverse, alternate */
  animation-fill-mode: forwards;     /* keeps end state */
  animation-play-state: running;     /* or paused */

  /* Shorthand: name duration timing delay iterations direction fill */
  animation: fadeIn 0.5s ease 0s 1 normal forwards;
  animation: spin 1s linear infinite;
  animation: bounce 0.6s ease infinite;
}

/* Multiple animations */
animation: fadeIn 0.3s ease, slideUp 0.5s ease;
```

---

## 18. Pseudo-classes

```css
/* User interaction */
a:hover   { color: blue; }          /* mouse over */
a:active  { color: red; }           /* being clicked */
a:focus   { outline: 2px solid; }   /* keyboard focused */
a:visited { color: purple; }        /* visited link */

/* Form states */
input:focus        { border-color: blue; }
input:disabled     { opacity: 0.5; }
input:checked      { accent-color: green; }
input:required     { border-color: red; }
input:valid        { border-color: green; }
input:invalid      { border-color: red; }
input:placeholder-shown { border-color: gray; }
input:read-only    { background: #f5f5f5; }

/* Structure — child selectors */
li:first-child      { font-weight: bold; }
li:last-child       { border-bottom: none; }
li:nth-child(2)     { color: red; }        /* 2nd child */
li:nth-child(odd)   { background: #eee; }  /* 1,3,5... */
li:nth-child(even)  { background: #fff; }  /* 2,4,6... */
li:nth-child(3n)    { color: blue; }       /* every 3rd */
li:nth-child(3n+1)  { color: blue; }       /* 1,4,7... */
li:only-child       { margin: 0; }
li:nth-last-child(1){ font-style: italic; }

/* Type selectors */
p:first-of-type  { font-size: 1.2em; }
p:last-of-type   { margin-bottom: 0; }
p:nth-of-type(2) { color: gray; }
p:only-of-type   { text-align: center; }

/* Negation */
p:not(.intro)    { color: gray; }
li:not(:last-child) { border-bottom: 1px solid #eee; }

/* Empty element */
div:empty { display: none; }

/* Target — element with matching id in URL hash */
section:target { background: yellow; }

/* Root */
:root { --primary: navy; }
```

---

## 19. Pseudo-elements

```css
/* ::before and ::after — insert content */
.button::before {
  content: "→ ";
}

.required-field::after {
  content: " *";
  color: red;
}

/* content values */
content: "";              /* empty (common for decorative shapes) */
content: "text";
content: attr(data-tooltip);  /* pulls from HTML attribute */
content: url('icon.svg');
content: counter(section);

/* ::placeholder */
input::placeholder {
  color: gray;
  font-style: italic;
}

/* ::selection — user's text selection */
::selection {
  background: navy;
  color: white;
}

/* ::first-line */
p::first-line {
  font-weight: bold;
}

/* ::first-letter */
p::first-letter {
  font-size: 2em;
  float: left;
}

/* ::marker — list item bullets/numbers */
li::marker {
  color: navy;
  font-weight: bold;
}

/* ::backdrop — behind <dialog> */
dialog::backdrop {
  background: rgba(0, 0, 0, 0.5);
}

/* Common decorative pattern with ::before */
.card::before {
  content: "";
  display: block;
  width: 100%;
  height: 4px;
  background: linear-gradient(to right, navy, royalblue);
}
```

---

## 20. Variables (Custom Properties)

```css
/* Define variables in :root to make them global */
:root {
  /* Colors */
  --color-primary: #1a3c5e;
  --color-secondary: #4a90d9;
  --color-accent: #f5a623;
  --color-text: #333333;
  --color-background: #ffffff;
  --color-gray: #666666;

  /* Typography */
  --font-family: 'Inter', sans-serif;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.25rem;
  --font-size-xl: 1.5rem;
  --font-size-2xl: 2rem;

  /* Spacing */
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 48px;

  /* Border radius */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 16px;
  --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 1px 3px rgba(0,0,0,0.1);
  --shadow-md: 0 4px 12px rgba(0,0,0,0.15);
  --shadow-lg: 0 8px 24px rgba(0,0,0,0.2);

  /* Transitions */
  --transition: 0.2s ease;
}

/* Use variables with var() */
.button {
  background-color: var(--color-primary);
  font-family: var(--font-family);
  padding: var(--space-sm) var(--space-md);
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-sm);
  transition: all var(--transition);
}

/* Fallback value */
color: var(--color-primary, navy);   /* uses navy if variable not defined */

/* Override in a component scope */
.dark-card {
  --color-background: #1a1a1a;
  --color-text: #ffffff;
  background-color: var(--color-background);
  color: var(--color-text);
}

/* Override with JavaScript */
/* document.documentElement.style.setProperty('--color-primary', '#ff0000'); */
```

---

## 21. Media Queries & Responsive Design

```css
/* Basic syntax */
@media (max-width: 768px) {
  .sidebar {
    display: none;
  }
}

/* Common breakpoints */
/* Mobile first (recommended) — start small, add complexity */
/* Base styles: mobile (< 480px) */

@media (min-width: 480px) {
  /* Small phones landscape */
}

@media (min-width: 640px) {
  /* Large phones */
}

@media (min-width: 768px) {
  /* Tablets */
}

@media (min-width: 1024px) {
  /* Laptops */
}

@media (min-width: 1280px) {
  /* Desktops */
}

@media (min-width: 1536px) {
  /* Large screens */
}

/* Range queries */
@media (min-width: 768px) and (max-width: 1024px) {
  /* Tablets only */
}

/* Modern range syntax */
@media (768px <= width <= 1024px) {
  /* Tablets only */
}

/* Orientation */
@media (orientation: portrait) { }
@media (orientation: landscape) { }

/* Dark mode */
@media (prefers-color-scheme: dark) {
  :root {
    --color-background: #121212;
    --color-text: #ffffff;
  }
}

/* Reduced motion — respect user accessibility settings */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}

/* Print styles */
@media print {
  .navbar, .footer { display: none; }
  body { font-size: 12pt; }
}

/* High resolution screens */
@media (-webkit-min-device-pixel-ratio: 2), (min-resolution: 192dpi) {
  /* Use higher-res images */
}

/* Responsive layout example */
.grid {
  display: grid;
  grid-template-columns: 1fr;    /* 1 column on mobile */
  gap: 16px;
}

@media (min-width: 768px) {
  .grid {
    grid-template-columns: 1fr 1fr;    /* 2 columns on tablet */
  }
}

@media (min-width: 1024px) {
  .grid {
    grid-template-columns: repeat(3, 1fr);  /* 3 columns on desktop */
  }
}
```

---

## 22. Cascade, Specificity & Inheritance

### Specificity — how browsers decide which rule wins

```
Inline styles         > IDs      > Classes/Attributes/Pseudo-classes  > Elements
style=""                #id         .class  [attr]  :hover              div  p  h1
  1000                  100               10                               1
```

```css
/* Specificity = 0,0,0,1 */
p { color: red; }

/* Specificity = 0,0,1,0 */
.intro { color: blue; }

/* Specificity = 0,1,0,0 */
#title { color: green; }

/* Specificity = 0,1,1,1 */
#title.intro p { color: purple; }

/* !important — overrides everything (avoid if possible) */
p { color: red !important; }
```

### Inheritance

```css
/* These properties ARE inherited by default */
color, font-family, font-size, font-weight,
line-height, text-align, letter-spacing,
list-style, cursor, visibility

/* These are NOT inherited */
margin, padding, border, background,
width, height, display, position,
overflow, float, box-shadow

/* Force inheritance */
.child {
  border: inherit;
  background: inherit;
}

/* Reset to default */
.element {
  all: initial;      /* reset all properties */
  all: unset;        /* unset all properties */
  all: revert;       /* revert to browser default */
}
```

---

## 23. Filters & Effects

```css
/* filter — visual effects on element */
filter: blur(4px);
filter: brightness(1.5);      /* > 1 = brighter */
filter: contrast(1.2);
filter: grayscale(100%);       /* black and white */
filter: grayscale(0%);         /* color */
filter: hue-rotate(90deg);
filter: invert(100%);
filter: opacity(50%);
filter: saturate(200%);
filter: sepia(100%);
filter: drop-shadow(2px 4px 8px rgba(0,0,0,0.3));

/* Multiple filters */
filter: brightness(1.1) contrast(1.1) saturate(1.2);

/* backdrop-filter — applies filter to what's behind element */
backdrop-filter: blur(10px);
backdrop-filter: blur(10px) brightness(0.9);
/* Great for frosted glass effects! */

/* Frosted glass card */
.glass-card {
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 16px;
}

/* mix-blend-mode */
mix-blend-mode: normal;
mix-blend-mode: multiply;
mix-blend-mode: screen;
mix-blend-mode: overlay;
mix-blend-mode: darken;
mix-blend-mode: lighten;
mix-blend-mode: color-dodge;
mix-blend-mode: difference;
mix-blend-mode: exclusion;

/* cursor */
cursor: default;
cursor: pointer;      /* hand — use on clickable elements */
cursor: text;
cursor: move;
cursor: grab;
cursor: grabbing;
cursor: not-allowed;
cursor: wait;
cursor: crosshair;
cursor: zoom-in;
cursor: zoom-out;
cursor: none;
```

---

## 24. Lists & Tables

```css
/* List styles */
list-style: none;                   /* remove bullets */
list-style-type: disc;              /* bullet */
list-style-type: circle;
list-style-type: square;
list-style-type: decimal;           /* 1, 2, 3 */
list-style-type: lower-alpha;       /* a, b, c */
list-style-type: upper-alpha;       /* A, B, C */
list-style-type: lower-roman;       /* i, ii, iii */
list-style-type: upper-roman;       /* I, II, III */
list-style-image: url('bullet.svg');

list-style-position: inside;
list-style-position: outside;       /* default */

/* Remove default list styling */
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

/* Table styles */
table {
  width: 100%;
  border-collapse: collapse;    /* merge borders */
  border-spacing: 0;
}

th, td {
  padding: 12px 16px;
  text-align: left;
  border-bottom: 1px solid #eee;
}

th {
  background-color: #f5f5f5;
  font-weight: 600;
}

/* Zebra striping */
tr:nth-child(even) {
  background-color: #f9f9f9;
}

tr:hover {
  background-color: #f0f4ff;
}

/* Table layout */
table-layout: auto;     /* default */
table-layout: fixed;    /* equal column widths */
```

---

## 25. Useful Utility Patterns

```css
/* ── Reset ── */
*, *::before, *::after { box-sizing: border-box; }
body { margin: 0; padding: 0; }

/* ── Center anything ── */
/* Flexbox center */
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Absolute center */
.absolute-center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* ── Truncate text with ellipsis ── */
.truncate {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

/* ── Multi-line clamp ── */
.clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

/* ── Visually hidden (accessible) ── */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

/* ── Sticky footer ── */
body {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
main { flex: 1; }

/* ── Full-screen section ── */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* ── Responsive container ── */
.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 16px;
}

/* ── Aspect ratio box ── */
.video-wrapper {
  position: relative;
  padding-bottom: 56.25%; /* 16:9 */
  height: 0;
}
.video-wrapper iframe {
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
}

/* Modern aspect ratio */
.video {
  aspect-ratio: 16 / 9;
  width: 100%;
}

/* ── Custom scrollbar ── */
::-webkit-scrollbar { width: 8px; }
::-webkit-scrollbar-track { background: #f1f1f1; }
::-webkit-scrollbar-thumb { background: #888; border-radius: 4px; }
::-webkit-scrollbar-thumb:hover { background: #555; }

/* ── Smooth scroll ── */
html { scroll-behavior: smooth; }

/* ── CSS reset for buttons ── */
button {
  background: none;
  border: none;
  padding: 0;
  cursor: pointer;
  font: inherit;
}

/* ── Image fill ── */
img {
  max-width: 100%;
  height: auto;
  display: block;
}
```

---

## Quick Reference Card

```css
/* Selectors */
*  .class  #id  element  parent > child  el + el  el ~ el  [attr]

/* Box model */
margin | border | padding | content   (outside → in)

/* Display */
block | inline | inline-block | flex | grid | none

/* Position */
static | relative | absolute | fixed | sticky

/* Flexbox */
display:flex  justify-content  align-items  flex-wrap  gap  flex:1

/* Grid */
display:grid  grid-template-columns:repeat(3,1fr)  gap  grid-area

/* Most used properties */
color  background  font-size  font-weight  padding  margin
border  border-radius  width  height  display  position
top/right/bottom/left  z-index  opacity  overflow  cursor
transform  transition  animation  box-shadow  flex  gap
```

---

*ProgrammingClub67 — Web Development Semester 2026* 🎨
