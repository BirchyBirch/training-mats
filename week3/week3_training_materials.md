# CSS Advanced Selectors & Modern Properties Training - Week 3

## Session Agenda (60 minutes)

### Opening (5 minutes)
- Welcome back and Week 2 recap
- Objectives: Master advanced selectors and modern CSS property approaches
- Preview: Logical properties, pseudo-elements, and pseudo-classes

### Logical vs Physical Properties (20 minutes)

#### The Problem with Physical Properties
Traditional CSS uses physical directions (top, right, bottom, left) that don't adapt to different writing modes or international layouts.

```css
/* Physical properties - old approach */
.card {
    margin-top: 16px;
    margin-right: 20px;
    margin-bottom: 16px;
    margin-left: 20px;
    padding-left: 24px;
    border-left: 3px solid blue;
}
```

#### Logical Properties - Modern Approach
Logical properties use abstract directions that adapt to writing direction and text flow.

```css
/* Logical properties - modern approach */
.card {
    margin-block: 16px;        /* top and bottom */
    margin-inline: 20px;       /* left and right */
    padding-inline-start: 24px; /* left in LTR, right in RTL */
    border-inline-start: 3px solid blue;
}
```

#### Key Logical Property Mappings
- **block-start/end** = top/bottom (in horizontal writing)
- **inline-start/end** = left/right (in LTR), right/left (in RTL)
- **block-size** = height (in horizontal writing)
- **inline-size** = width (in horizontal writing)

#### Why Use Logical Properties?
1. **Internationalization** - Automatically adapts to RTL languages
2. **Writing modes** - Works with vertical text
3. **Future-proof** - Modern CSS standard
4. **Semantic clarity** - Express intent, not just direction

### Pseudo-elements Deep Dive (15 minutes)

#### What Are Pseudo-elements?
Pseudo-elements let you style specific parts of an element or create virtual elements.

#### Essential Pseudo-elements

**::before and ::after**
```css
.quote::before {
    content: """;
    font-size: 2em;
    color: #666;
}

.quote::after {
    content: """;
    font-size: 2em;
    color: #666;
}
```

**::first-line and ::first-letter**
```css
.article::first-letter {
    font-size: 3em;
    float: left;
    line-height: 1;
    margin-right: 8px;
}

.paragraph::first-line {
    font-weight: bold;
    color: #2c3e50;
}
```

**::placeholder**
```css
input::placeholder {
    color: #999;
    font-style: italic;
}
```

#### Common Use Cases
- **Decorative elements** without extra HTML
- **Icons and symbols** using content property
- **Tooltips and overlays**
- **Typography enhancements**

### Pseudo-classes Mastery (15 minutes)

#### State-based Pseudo-classes
```css
/* Interactive states */
.button:hover { background-color: #0056b3; }
.button:focus { outline: 2px solid #007bff; }
.button:active { transform: translateY(1px); }

/* Form states */
input:valid { border-color: green; }
input:invalid { border-color: red; }
input:required { border-left: 3px solid orange; }
```

#### Structural Pseudo-classes
```css
/* Position-based selection */
li:first-child { margin-top: 0; }
li:last-child { margin-bottom: 0; }
li:nth-child(odd) { background-color: #f5f5f5; }
li:nth-child(3n) { color: blue; }

/* Content-based selection */
p:empty { display: none; }
div:not(.special) { opacity: 0.8; }
```

#### Advanced Structural Selectors
```css
/* Flexible nth-child patterns */
.grid-item:nth-child(3n+1) { margin-left: 0; }
.card:nth-of-type(even) { background: #f9f9f9; }
.link:target { background: yellow; }
```

### Live Demo: Building with Modern CSS (10 minutes)

#### Demo 1: Logical Properties in Action
1. Create a card component using physical properties
2. Convert to logical properties
3. Test with different writing directions
4. Show RTL language adaptation

#### Demo 2: Pseudo-element Magic
1. Add decorative elements with ::before/::after
2. Create custom bullet points
3. Build a tooltip with pure CSS
4. Style form placeholders

#### Demo 3: Interactive Pseudo-classes
1. Build enhanced button states
2. Create zebra-striped tables
3. Style form validation states
4. Implement focus management

### Hands-on Practice (10 minutes)

#### Exercise 1: Property Conversion
Convert this physical property CSS to logical properties:
```css
.sidebar {
    margin-top: 20px;
    margin-right: 0;
    margin-bottom: 20px;
    margin-left: 16px;
    padding-left: 24px;
    border-left: 2px solid #ddd;
    width: 300px;
}
```

#### Exercise 2: Pseudo-element Challenge
Using only CSS (no additional HTML), add:
1. A "★" symbol before each .featured item
2. A "NEW" badge after .new-item elements
3. Custom quotation marks around .testimonial text

#### Exercise 3: Advanced Selectors
Write selectors for:
1. Every 3rd product card starting from the 2nd
2. All invalid required form inputs
3. The first paragraph that's not inside a .intro section

### Wrap-up (5 minutes)
- Key takeaways review
- Preview next week: Layout with Flexbox and Grid
- Assignment: Refactor one component using logical properties

---

## Advanced CSS Selectors & Properties Cheat Sheet

### Logical vs Physical Properties

#### Spacing Properties
```css
/* Physical (old) */
margin-top: 16px;
margin-right: 20px;
margin-bottom: 16px;
margin-left: 20px;
padding-top: 12px;
padding-right: 16px;
padding-bottom: 12px;
padding-left: 16px;

/* Logical (modern) */
margin-block-start: 16px;     /* top */
margin-inline-end: 20px;      /* right in LTR */
margin-block-end: 16px;       /* bottom */
margin-inline-start: 20px;    /* left in LTR */

/* Shorthand logical properties */
margin-block: 16px;           /* top and bottom */
margin-inline: 20px;          /* left and right */
padding-block: 12px;          /* top and bottom */
padding-inline: 16px;         /* left and right */
```

#### Border Properties
```css
/* Physical */
border-top: 1px solid #ddd;
border-right: 2px solid blue;
border-bottom: 1px solid #ddd;
border-left: 3px solid red;

/* Logical */
border-block-start: 1px solid #ddd;    /* top */
border-inline-end: 2px solid blue;     /* right in LTR */
border-block-end: 1px solid #ddd;      /* bottom */
border-inline-start: 3px solid red;    /* left in LTR */
```

#### Size Properties
```css
/* Physical */
width: 300px;
height: 200px;

/* Logical */
inline-size: 300px;    /* width in horizontal writing */
block-size: 200px;     /* height in horizontal writing */
```

#### Quick Reference: Logical Mappings
| Physical | Logical | Description |
|----------|---------|-------------|
| top | block-start | Start of block direction |
| bottom | block-end | End of block direction |
| left | inline-start | Start of inline direction (LTR) |
| right | inline-end | End of inline direction (LTR) |
| width | inline-size | Size in inline direction |
| height | block-size | Size in block direction |

### Pseudo-elements Reference

#### Essential Pseudo-elements
```css
/* ::before and ::after - virtual elements */
.element::before {
    content: "★";           /* Required for ::before/::after */
    display: inline-block;  /* Often needed for positioning */
    margin-right: 8px;
}

.element::after {
    content: "";            /* Can be empty for decorative shapes */
    position: absolute;
    width: 100%;
    height: 2px;
    background: blue;
    bottom: 0;
    left: 0;
}

/* ::first-letter - drop cap effect */
.article::first-letter {
    font-size: 3em;
    float: left;
    line-height: 0.8;
    margin: 0.1em 0.1em 0 0;
    font-weight: bold;
}

/* ::first-line - emphasize opening */
.paragraph::first-line {
    font-weight: bold;
    color: #2c3e50;
    text-transform: uppercase;
}

/* ::placeholder - form styling */
input::placeholder {
    color: #999;
    font-style: italic;
    opacity: 1; /* Firefox needs this */
}

/* ::selection - text selection styling */
::selection {
    background-color: #007bff;
    color: white;
}
```

#### Pseudo-element Use Cases
- **Icons without images**: Use content property with Unicode symbols
- **Decorative shapes**: Create triangles, circles with CSS
- **Tooltips**: Position absolute pseudo-elements
- **Clearfix**: Classic clearfix uses ::after
- **Typography effects**: Drop caps, quotation marks

### Pseudo-classes Reference

#### Interactive States
```css
/* Hover, focus, active states */
.button:hover { background-color: #0056b3; }
.button:focus { 
    outline: 2px solid #007bff; 
    outline-offset: 2px;
}
.button:active { transform: translateY(1px); }

/* Link states (remember LVHA order) */
a:link { color: blue; }
a:visited { color: purple; }
a:hover { color: red; }
a:active { color: orange; }
```

#### Form States
```css
/* Validation states */
input:valid { border-color: green; }
input:invalid { border-color: red; }
input:required { border-left: 3px solid orange; }
input:optional { opacity: 0.8; }

/* Interactive states */
input:focus { border-color: #007bff; }
input:disabled { opacity: 0.5; cursor: not-allowed; }
checkbox:checked { /* Custom checkbox styles */ }
```

#### Structural Pseudo-classes
```css
/* Position-based */
:first-child { margin-top: 0; }
:last-child { margin-bottom: 0; }
:only-child { text-align: center; }

/* nth-child patterns */
:nth-child(odd) { background: #f5f5f5; }    /* 1, 3, 5... */
:nth-child(even) { background: white; }     /* 2, 4, 6... */
:nth-child(3n) { color: blue; }             /* 3, 6, 9... */
:nth-child(3n+1) { margin-left: 0; }        /* 1, 4, 7... */
:nth-child(3n+2) { color: red; }            /* 2, 5, 8... */

/* Type-based (same element type) */
h2:first-of-type { font-size: 2em; }
h2:last-of-type { margin-bottom: 0; }
p:nth-of-type(2) { font-weight: bold; }

/* Content-based */
:empty { display: none; }
:not(.special) { opacity: 0.8; }
```

#### Advanced Pseudo-classes
```css
/* Target pseudo-class for anchor links */
:target { 
    background: yellow; 
    animation: highlight 2s ease-in-out;
}

/* Root pseudo-class for CSS variables */
:root {
    --primary-color: #007bff;
    --secondary-color: #6c757d;
}

/* Language-based styling */
:lang(en) { quotes: """ """; }
:lang(fr) { quotes: "« " " »"; }
```

### nth-child Formula Guide

The `nth-child(an+b)` formula:
- **a**: The cycle size
- **n**: Counter (0, 1, 2, 3...)
- **b**: The offset

#### Common Patterns
```css
/* Every 3rd element */
:nth-child(3n) { /* 3, 6, 9, 12... */ }

/* Every 3rd element, starting from the 1st */
:nth-child(3n+1) { /* 1, 4, 7, 10... */ }

/* Every 3rd element, starting from the 2nd */
:nth-child(3n+2) { /* 2, 5, 8, 11... */ }

/* First 5 elements */
:nth-child(-n+5) { /* 1, 2, 3, 4, 5 */ }

/* All but the first 3 */
:nth-child(n+4) { /* 4, 5, 6, 7... */ }

/* Last 3 elements (when parent has known count) */
:nth-last-child(-n+3) { /* Last 3 */ }
```

---

## Common Use Cases & Patterns

### Modern Card Component
```css
.card {
    /* Use logical properties for international sites */
    padding-block: 24px;
    padding-inline: 20px;
    margin-block-end: 16px;
    border-inline-start: 3px solid var(--primary-color);
    
    /* Add decorative element */
    position: relative;
}

.card::before {
    content: "";
    position: absolute;
    inset-block-start: 0;
    inset-inline-start: 0;
    inline-size: 100%;
    block-size: 4px;
    background: linear-gradient(90deg, #007bff, #28a745);
}

.card:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}
```

### Form Enhancement
```css
.form-field {
    position: relative;
    margin-block-end: 20px;
}

.form-field input {
    inline-size: 100%;
    padding-block: 12px;
    padding-inline: 16px;
    border: 1px solid #ddd;
}

.form-field input:focus {
    border-color: #007bff;
    outline: none;
}

.form-field input:invalid {
    border-color: #dc3545;
}

.form-field input::placeholder {
    color: #6c757d;
    font-style: italic;
}

/* Required field indicator */
.form-field.required label::after {
    content: " *";
    color: #dc3545;
}
```

### Table Styling
```css
.data-table {
    inline-size: 100%;
    border-collapse: collapse;
}

.data-table th,
.data-table td {
    padding-block: 12px;
    padding-inline: 16px;
    text-align: start;
    border-block-end: 1px solid #ddd;
}

.data-table tbody tr:nth-child(even) {
    background-color: #f8f9fa;
}

.data-table tbody tr:hover {
    background-color: #e9ecef;
}

.data-table th {
    background-color: #007bff;
    color: white;
    font-weight: 600;
}

/* Highlight specific columns */
.data-table td:nth-child(3) {
    font-weight: bold;
    color: #007bff;
}
```

---

## Common Problems & Solutions

### Problem: Decorative Elements Require Extra HTML
**Old Approach:**
```html
<div class="card">
    <span class="icon">★</span>
    <h3>Title</h3>
    <p>Content</p>
</div>
```

**Better with Pseudo-elements:**
```css
.card h3::before {
    content: "★";
    margin-inline-end: 8px;
    color: #ffc107;
}
```

### Problem: International Sites Look Broken
**Physical Properties:**
```css
.sidebar {
    margin-left: 20px;  /* Always left, even in RTL */
    border-left: 3px solid blue;
}
```

**Logical Properties Solution:**
```css
.sidebar {
    margin-inline-start: 20px;  /* Adapts to text direction */
    border-inline-start: 3px solid blue;
}
```

### Problem: Inconsistent Interactive States
**Better Approach:**
```css
.interactive-element {
    transition: all 0.2s ease;
}

.interactive-element:hover {
    transform: translateY(-1px);
}

.interactive-element:focus {
    outline: 2px solid #007bff;
    outline-offset: 2px;
}

.interactive-element:active {
    transform: translateY(0);
}
```

---

## Debugging Tips

### Pseudo-element Issues
1. **Missing content property**: ::before/::after need `content: "";`
2. **Display issues**: May need `display: block` or `inline-block`
3. **Positioning**: Often need `position: relative` on parent
4. **Z-index conflicts**: Pseudo-elements can stack unexpectedly

### Logical Property Browser Support
- **Modern browsers**: Full support
- **Legacy support**: Use CSS feature queries
```css
.element {
    margin-left: 20px; /* fallback */
}

@supports (margin-inline-start: 20px) {
    .element {
        margin-left: unset;
        margin-inline-start: 20px;
    }
}
```

### nth-child Debugging
- **Use browser DevTools**: Hover over selectors to see matches
- **Test incrementally**: Start with simple patterns
- **Count from 1**: nth-child is 1-indexed, not 0-indexed

---

## Week 3 Assignment

### Practice Tasks
1. **Convert a component** from physical to logical properties
2. **Add pseudo-elements** to enhance visual design without extra HTML
3. **Implement interactive states** using pseudo-classes
4. **Create a pattern** using nth-child selectors

### Real-world Application
Find a component in your current project and:
1. Identify opportunities for logical properties
2. Add one pseudo-element for visual enhancement
3. Improve interactive states with pseudo-classes
4. Test with different writing directions (if applicable)

---

## Next Week Preview

**Topic:** Layout Mastery with Flexbox and Grid
**Focus:** Modern layout techniques for responsive design
**Prep:** Identify layout challenges in your current projects

**Preview Questions:**
- How do you center elements perfectly?
- When should you use Flexbox vs Grid?
- How do you create responsive layouts without media queries?