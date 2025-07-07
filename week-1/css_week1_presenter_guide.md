# Week 1 Presenter Guide - CSS Fundamentals

## Pre-Session Setup (5 minutes before)
- [ ] Open demo page in browser (share this window)
- [ ] Test screen sharing with demo page
- [ ] Have this presenter guide open on second monitor/window
- [ ] Zoom browser to 125% for better visibility
- [ ] Test interactive elements (buttons, sliders, calculator)

---

## Opening (5 minutes) [0:00-0:05]

**Share screen: Demo page at top**

### Opening Script:
*"Good morning everyone. Today we're starting our CSS fundamentals series. Our goal is to build the foundation you need to quickly fix visual design issues."*

**Key Points to Hit:**
- This is Week 1 of 6-8 week series
- Focus on practical skills for fixing design problems
- Interactive format - encourage questions
- Everyone should bookmark this demo page for reference

**Transition:** *"Let's start with the absolute basics - what is a CSS rule?"*

---

## Section 1: CSS Rule Structure (10 minutes) [0:05-0:15]

**Navigate to: Section 1 on demo page**

### Main Teaching Points:
1. **Show the color-coded CSS example**
   - Point out selector (yellow), property (blue), value (pink)
   - Emphasize the syntax: brackets, colons, semicolons

2. **Key Concepts:**
   - "Every CSS rule follows this exact pattern"
   - "Missing semicolon = broken CSS"
   - "Declarations are property:value pairs"

### Interactive Moment:
*"Let's see this in action. Everyone right-click on this heading and inspect it."*
- Have them find the h1 rule in DevTools
- Show how changing color in DevTools affects the page

**Common Questions:**
- Q: "What happens if I forget a semicolon?"
- A: "The entire declaration breaks - we'll debug this later"

**Transition:** *"Now that we know how rules work, let's talk about how to target elements..."*

---

## Section 2: Selectors Deep Dive (10 minutes) [0:15-0:25]

**Navigate to: Section 2 on demo page**

### Teaching Flow:
1. **Show the three selector examples in the code block**
2. **Point to the live examples below**
   - "See how each paragraph looks different?"
   - "That's because different selectors are targeting them"

### Key Points:
- **Element selector**: Targets ALL paragraphs
- **Class selector**: Targets specific elements (most common)
- **ID selector**: Should be unique (avoid for styling)

### Interactive Demo:
*"Everyone inspect the highlighted paragraph..."*
- Show them how to see class="highlighted" in Elements panel
- Point out the .highlighted rule in Styles panel

**Best Practice Emphasis:**
*"Use classes for styling, IDs for JavaScript. This will save you headaches later."*

**Transition:** *"But what happens when multiple rules target the same element? That's where specificity comes in..."*

---

## Section 3: Specificity & Cascade (10 minutes) [0:25-0:35]

**Navigate to: Section 3 on demo page**

### Critical Teaching Points:
1. **Specificity is like a point system**
   - Read the hierarchy: !important > ID > Class > Element
   - "Higher points always win"

2. **Show the live example**
   - Point to the blue text in the specificity demo
   - "Multiple rules target this, but the more specific one wins"

### Interactive Tool Demo:
**Use the Specificity Calculator:**
- Type in ".button" → show it equals "0,0,1,0"  
- Type in "#header .button" → show it equals "0,1,1,0"
- *"See how adding an ID makes it much more specific?"*

### Most Important Message:
*"When your CSS isn't working, 90% of the time it's a specificity issue. Check this first."*

**Common Problems to Address:**
- "My button styles aren't working" → Check specificity
- "I have to use !important everywhere" → You're fighting high specificity

**Transition:** *"When specificity is equal, order matters. That's the cascade..."*

---

## Section 4: CSS Units (15 minutes) [0:35-0:50]

**Navigate to: Section 7 on demo page**

### Opening Hook:
*"Units are where a lot of visual design problems come from. Wrong units = inconsistent spacing, poor scaling, responsive issues."*

### Teaching Flow:
1. **Show the code examples first**
   - Point out px, rem, em, % examples
   - "Each unit serves a different purpose"

2. **Live comparison demo**
   - Point to the nested div showing different units
   - "Notice how 1em changes based on parent size"

3. **When to use guide**
   - Read through the 4-quadrant guide
   - Emphasize: "px for precision, rem for consistency"

### Interactive Demo - Unit Converter:
**This is the money moment - get everyone engaged:**
- Change pixels to 24 → show rem updates to 1.5
- Change rem to 2 → show pixels becomes 32
- *"This math is happening in your CSS all the time"*

### Real-World Applications:
*"In your Angular apps, use rem for component spacing. It scales better than px when users change font sizes."*

**Key Takeaway:**
*"Consistent unit strategy prevents most spacing issues. Pick rem for most things, px for borders."*

**Transition:** *"Now let's practice with real problems..."*

---

## Section 5: Hands-on Practice (15 minutes) [0:50-1:05]

**Navigate to: Section 5 Interactive Demo**

### Exercise Structure:
1. **Unit Decision Exercise (5 minutes)**
   - Present the button example from agenda
   - Ask: "For button padding - px, rem, or em?"
   - Get answers, explain why rem is best

2. **Specificity Debugging (5 minutes)**
   - Show the p vs .blue-text example
   - Have someone calculate specificity (Class wins: 10 vs 1)
   - Use the interactive buttons to demonstrate

3. **Real Problems (5 minutes)**
   - **Prepare beforehand**: Screenshot from your actual app
   - Show spacing/color/font issue
   - Guide group through: "What selector? What specificity? What fix?"

### Interactive Button Demo:
*"Everyone click the 'Make Red' button while inspecting the element..."*
- Show how class gets added
- Point out the CSS rule that activates
- *"This is exactly how CSS works in your Angular components"*

**Key Learning Moment:**
*"See how we're adding classes, not changing IDs? This is the pattern you want."*

---

## Wrap-up (5 minutes) [1:05-1:10]

**Navigate to: Section 8 Key Takeaways**

### Summary Points:
- **CSS rules**: Simple pattern, but syntax matters
- **Specificity**: Usually why CSS doesn't work
- **Units**: Strategy prevents design problems
- **DevTools**: Your debugging friend

### Assignment:
*"This week, inspect 3 elements in your current projects. Practice identifying selectors and calculating specificity."*

### Next Week Preview:
*"Next week: Box Model - why elements are bigger than expected, and how spacing really works."*

**Final Message:**
*"These fundamentals will make everything else easier. The demo page is your reference - bookmark it."*

---

## Troubleshooting Guide

### If Technology Fails:
- **Demo page won't load**: Have the HTML file saved locally
- **Screen sharing issues**: Use VS Code with the markdown as backup
- **Interactive elements broken**: Focus on static examples, skip calculator

### If Questions Stall Progress:
- *"Great question - let's address that in the practice section"*
- *"That's exactly what we'll cover next week"*
- Keep a parking lot of questions for end

### If Audience Seems Lost:
- Stop and do live DevTools demo
- Ask: *"Everyone inspect this element with me"*
- Slow down, repeat key concepts

### Energy Boosters:
- *"Everyone try clicking this button..."*
- *"Who can tell me the specificity of .header .nav a?"*
- *"Let's all inspect this element together"*

---

## Quick Reference

### DevTools Shortcuts to Teach:
- **F12**: Open DevTools
- **Ctrl+Shift+C**: Inspect element tool
- **Right-click → Inspect**: Most reliable method

### Key Phrases to Use:
- *"This is exactly how it works in your Angular apps"*
- *"When CSS doesn't work, check specificity first"*
- *"Use classes for styling, IDs for JavaScript"*
- *"rem for consistency, px for precision"*

### Time Warnings:
- **0:15**: Should be finishing rule structure
- **0:35**: Should be starting units
- **0:50**: Must start hands-on practice
- **1:05**: Begin wrap-up