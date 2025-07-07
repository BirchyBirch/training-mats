# CSS Fundamentals Training - Week 1

## Session Agenda (60 minutes)

### Opening (5 minutes)
- Welcome and series overview
- Objectives: Build solid CSS foundation to fix visual design issues quickly
- Format: Interactive learning with hands-on practice

### CSS Rule Structure (10 minutes)

#### Anatomy of a CSS Rule
```css
selector {
    property: value;
    property: value;
}
```

#### Key Components
- **Selector**: What element(s) to style
- **Property**: What aspect to change (color, size, spacing, etc.)
- **Value**: How to change it
- **Declaration**: A property-value pair
- **Rule**: Complete selector + declarations

#### Live Demo
1. Show basic rule structure in demo page
2. Demonstrate how changing values affects appearance
3. Show syntax errors and their effects

### Selectors Deep Dive (10 minutes)

#### Three Main Selector Types
1. **Element Selector**: `p { }` - targets all `<p>` tags
2. **Class Selector**: `.highlighted { }` - targets `class="highlighted"`
3. **ID Selector**: `#unique { }` - targets `id="unique"`

#### Best Practices
- Use classes for styling (reusable)
- Use IDs for JavaScript targets (unique)
- Avoid styling with IDs
- Keep selectors simple

#### Interactive Demo
- Show examples of each selector type
- Demonstrate how they target different elements
- Show DevTools Elements panel highlighting

### Specificity & The Cascade (10 minutes)

#### Specificity Hierarchy
1. **!important** - 10,000 points (avoid!)
2. **ID selectors** - 100 points
3. **Class selectors** - 10 points  
4. **Element selectors** - 1 point

#### The Cascade Rules
1. **Specificity** - Higher specificity wins
2. **Source order** - Later rules override earlier ones (when specificity is equal)
3. **Inheritance** - Some properties inherit from parent elements

#### Common Problems
- "My CSS isn't working" → Check specificity
- "Styles are being overridden" → Check cascade order
- "I have to use !important" → You probably don't

### CSS Units - Getting Values Right (15 minutes)

#### CSS Units Deep Dive
**Absolute Units:**
- **px** - Pixels, exact size
- **pt** - Points (print media)

**Relative Units:**
- **rem** - Relative to root font-size (usually 16px)
- **em** - Relative to parent element font-size
- **%** - Percentage of parent element
- **vw/vh** - Viewport width/height

#### When to Use Each Unit
- **px**: Borders, small gaps, pixel-perfect designs
- **rem**: Font sizes, component spacing, consistent scaling
- **%**: Container widths, responsive layouts
- **em**: Component-relative spacing (use carefully)

#### Live Demo
1. Demonstrate unit converter tool
2. Show how rem vs px affects scaling
3. Demonstrate common unit mistakes
4. Show real examples of good unit choices

### Hands-on Practice (15 minutes)

#### Exercise 1: Unit Decisions
Present real scenarios:
```css
/* Which unit should you use? */
.button { 
    padding: ?; /* 8px, 0.5rem, or 0.5em? */
    border: ?; /* 1px, 0.1rem, or 1pt? */
    font-size: ?; /* 16px, 1rem, or 1em? */
}
```

#### Exercise 2: Specificity Debugging
Present CSS that isn't working:
```css
p { color: red; }
.blue-text { color: blue; }
```
```html
<p class="blue-text">What color is this?</p>
```

#### Exercise 3: Real-world Problem
Show a screenshot from your application where:
- Font sizes look inconsistent
- Spacing doesn't scale properly
- Button styles aren't applying

Have team members:
1. Identify the unit/selector issue
2. Calculate specificity
3. Suggest the fix with appropriate units

### Wrap-up (5 minutes)
- Key takeaways review
- Preview next week: Box Model
- Assignment: Inspect 3 elements in your current projects using DevTools

---

## CSS Fundamentals Cheat Sheet

### Rule Structure
```css
/* This is a comment */
selector {
    property: value;
    another-property: another-value;
}
```

### CSS Units Reference

#### Absolute Units
```css
/* Pixels - exact size */
font-size: 16px;
border: 1px solid black;
margin: 20px;
```

#### Relative Units
```css
/* REM - relative to root font-size (usually 16px) */
font-size: 1rem;     /* = 16px */
padding: 0.5rem;     /* = 8px */
margin: 2rem;        /* = 32px */

/* EM - relative to parent font-size */
font-size: 1.2em;    /* 20% larger than parent */
padding: 0.5em;      /* Half the parent font-size */

/* Percentage - relative to parent */
width: 50%;          /* Half the parent width */
height: 100%;        /* Full parent height */
```

#### Unit Decision Guide
- **1px borders**: Always use px
- **Font sizes**: Use rem for consistency
- **Component spacing**: Use rem for scalability
- **Container widths**: Use % for responsiveness
- **Small adjustments**: Use em within components

#### Common Unit Mistakes
```css
/* DON'T: Mix units inconsistently */
.bad-example {
    font-size: 14px;
    margin: 1rem;
    padding: 0.5em;
    border: 0.1rem solid black;
}

/* DO: Use consistent unit strategy */
.good-example {
    font-size: 1rem;      /* 16px */
    margin: 1rem;         /* 16px */
    padding: 0.5rem;      /* 8px */
    border: 1px solid black;
}
```
```css
/* Element selector */
p { color: black; }

/* Class selector */
.warning { color: red; }

/* ID selector */
#header { font-size: 24px; }

/* Multiple selectors */
h1, h2, h3 { font-weight: bold; }
```

### Specificity Values
- **!important**: 10,000 (avoid)
- **ID**: 100
- **Class**: 10
- **Element**: 1

### Common Specificity Examples
```css
/* Specificity: 0,0,0,1 */
p { color: red; }

/* Specificity: 0,0,1,0 */
.text { color: blue; }

/* Specificity: 0,1,0,0 */
#main { color: green; }

/* Specificity: 0,0,1,1 */
p.text { color: purple; }
```

### DevTools Shortcuts
- **F12**: Open DevTools
- **Ctrl+Shift+C**: Inspect element
- **Elements tab**: See HTML structure
- **Styles panel**: See applied CSS rules

---

## Common Problems & Solutions

### Problem: "My CSS isn't working"
**Causes:**
- Syntax error (missing semicolon, bracket)
- Selector doesn't match element
- Specificity too low
- Rule is overridden later

**Debug Steps:**
1. Check DevTools console for errors
2. Inspect element in DevTools
3. Look at Styles panel to see which rules apply
4. Check specificity and cascade order

### Problem: "I have to use !important everywhere"
**Why this happens:**
- Fighting with existing high-specificity rules
- Misunderstanding cascade order
- Not using proper selectors

**Solutions:**
- Use more specific selectors instead
- Organize CSS with proper cascade order
- Refactor existing overly-specific rules

### Problem: "Styles are inconsistent"
**Causes:**
- Multiple rules with same specificity
- Unexpected cascade order
- Missing base styles

**Solutions:**
- Use consistent class naming
- Organize CSS logically
- Document style patterns

---

## Debugging Workflow

### Step 1: Identify the Problem
- What element isn't styled correctly?
- What should it look like vs. what does it look like?

### Step 2: Inspect the Element
- Right-click → Inspect Element
- Find the element in DevTools
- Look at the Styles panel

### Step 3: Check Applied Rules
- Which rules are applied?
- Which rules are crossed out (overridden)?
- What's the specificity of each rule?

### Step 4: Test Solutions
- Modify values in DevTools
- Add new rules to test
- Check if changes work

### Step 5: Apply the Fix
- Update your CSS file
- Test in multiple browsers
- Verify no other elements are affected

---

## Week 1 Assignment

### Practice Tasks
1. **Inspect 3 elements** in your current project using DevTools
2. **Identify the selectors** being used for each element
3. **Calculate specificity** for the main rule affecting each element
4. **Find one style issue** and determine what type of selector problem it is

### Questions to Answer
- Which selector types are used most in your current CSS?
- Can you find any places where !important is used unnecessarily?
- Are there any elements where you can't figure out why certain styles apply?

---

## Next Week Preview

**Topic:** Box Model & Layout Basics
**Focus:** Understanding spacing, padding, margins, and borders
**Prep:** Look for spacing/alignment issues in your current projects

**Preview Questions:**
- Why are elements larger than expected?
- How do padding and margin differ?
- Why don't elements align properly?