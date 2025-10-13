# 🔍 Tooltip Visibility Checklist - Systematic Approach

## The Problem

Tooltips can be hidden even with high z-index because:
- Parent element has lower z-index
- Parent has `overflow: hidden`
- Sibling element creates new stacking context
- Positioned elements in different stacking contexts
- Sticky/fixed positioning on parents

---

## ✅ Systematic Checklist for Every Tooltip

### **Step 1: Check Parent Element Hierarchy**

For each tooltip, trace up the DOM tree:

```
Tooltip
└─ Immediate Parent
   └─ Grandparent
      └─ Great-grandparent
         └─ ... (up to .app root)
```

**Check each level for:**
- [ ] `overflow: hidden` (KILLS tooltips)
- [ ] `overflow: auto` or `overflow: scroll` (can clip)
- [ ] `position: relative` with z-index (creates stacking context)
- [ ] `position: sticky` (can create issues)
- [ ] `transform`, `filter`, `opacity < 1` (creates stacking context)

---

### **Step 2: Check Sibling Elements**

For each tooltip's parent, check siblings:

```
Parent Container
├─ Sibling 1 (z-index: X?)
├─ Sibling 2 (z-index: Y?)
└─ Tooltip's Parent (z-index: Z?)
    └─ Tooltip (z-index: 10000)
```

**Questions:**
- [ ] Do siblings have higher z-index?
- [ ] Are siblings positioned (absolute/relative/fixed)?
- [ ] Do siblings create new stacking contexts?
- [ ] Are siblings rendered after tooltip in DOM order?

---

### **Step 3: Check Tooltip's Own Positioning**

- [ ] Is `position: absolute` with proper parent having `position: relative`?
- [ ] Is `position: fixed` to escape parent constraints?
- [ ] Is z-index high enough (10000+)?
- [ ] Is `pointer-events: none` set (prevents blocking)?
- [ ] Does tooltip have proper offset (`bottom: calc(100% + 8px)`)?

---

### **Step 4: Check for Stacking Context Issues**

**Elements that create new stacking contexts:**
- [ ] `position: absolute/relative/fixed` with z-index
- [ ] `opacity < 1`
- [ ] `transform` (any value)
- [ ] `filter` (any value)
- [ ] `will-change`
- [ ] `contain: layout/paint`
- [ ] `isolation: isolate`

**If parent has any of these, tooltip z-index is RELATIVE to that context, not global!**

---

### **Step 5: Visual Placement Check**

- [ ] Is tooltip positioned ABOVE element? (`bottom: calc(100% + 8px)`)
- [ ] Or BELOW if needed? (`top: calc(100% + 8px)`)
- [ ] Is it centered? (`left: 50%; transform: translateX(-50%)`)
- [ ] Does it have proper clearance (8px+)?
- [ ] Is arrow pointing correctly?

---

### **Step 6: Overflow Chain Check**

Starting from tooltip, check every ancestor:

```css
.tooltip { overflow: ? }
  └─ .parent { overflow: ? }
     └─ .grandparent { overflow: ? }
        └─ .container { overflow: hidden ❌ } ← PROBLEM!
```

**If ANY ancestor has `overflow: hidden`, tooltip will be clipped!**

**Solution:**
- Change to `overflow: visible`
- Or use `position: fixed` on tooltip to escape

---

### **Step 7: Specific Element Checks**

#### **For .yt-chips-bar:**
- [ ] `overflow-x: auto` (for scrolling) ← OK
- [ ] `overflow-y: visible` (for tooltips) ← REQUIRED!
- [ ] Extra padding for tooltip space

#### **For .trail-toggle-bar:**
- [ ] `overflow: visible` ← REQUIRED!
- [ ] Extra top padding for tooltips
- [ ] `z-index` not too low

#### **For .yt-bottom-nav:**
- [ ] Tooltips appear ABOVE nav (not below)
- [ ] `overflow: visible`
- [ ] Clear space above nav bar

#### **For tabs (.detail-tabs, .yt-chips-bar):**
- [ ] Tooltips don't get clipped by sticky positioning
- [ ] Parent container allows overflow

---

## 🛠️ Fixing Process

### **When Tooltip is Hidden:**

**Step 1: Identify the tooltip**
- Where is it supposed to appear?
- What element is it attached to?

**Step 2: Check the DOM hierarchy**
```html
<div class="container" style="overflow: hidden"> ← FOUND THE PROBLEM!
  <div class="parent">
    <button class="has-tooltip-small">
      Label
      <div class="tooltip-small">Text</div> ← Hidden by ancestor overflow
    </button>
  </div>
</div>
```

**Step 3: Fix the issue**
- Change container to `overflow: visible`
- OR use `position: fixed` on tooltip
- OR move tooltip higher in DOM tree

**Step 4: Verify visually**
- Check in browser
- Hover over element
- Confirm tooltip appears

---

## 🎯 Common Issues & Solutions

### **Issue 1: Parent has `overflow: hidden`**
**Solution:** Change to `overflow: visible` or `overflow-y: visible`

### **Issue 2: Sticky parent clips tooltip**
**Solution:** Add padding-top to parent to make space

### **Issue 3: Tooltip behind sibling**
**Solution:** Increase tooltip z-index or change sibling z-index

### **Issue 4: Stacking context issue**
**Solution:** Use `position: fixed` to escape context

### **Issue 5: Tooltip off-screen (top edge)**
**Solution:** Position below element instead of above

---

## 📋 Audit Checklist for Existing Tooltips

### **Feed Toggle:**
- [ ] Parent: `.toggle-group` (position: relative?)
- [ ] Grandparent: `.trail-toggle-bar` (overflow: visible?)
- [ ] Tooltip appears above toggle
- [ ] Not clipped by header or sticky bar

### **Collapsed Slider:**
- [ ] Parent: `.focus-slider-section`
- [ ] Grandparent: `.trail-toggle-bar` (overflow: visible?)
- [ ] Tooltip appears above slider bar
- [ ] Not clipped by sticky positioning

### **Trail Chips (Web Dev, Science, Cooking):**
- [ ] Parent: `.yt-chips-bar` (overflow-y: visible?)
- [ ] Tooltip appears above chip
- [ ] Not clipped when chips scroll horizontally
- [ ] Clear space above chips bar

### **Bottom Nav Icons:**
- [ ] Parent: `.yt-bottom-nav` (overflow: visible?)
- [ ] Tooltip appears ABOVE nav bar
- [ ] Not cut off by bottom edge of phone container
- [ ] Clear space above icons

### **Trail Detail Tabs:**
- [ ] Parent: `.detail-tabs` (overflow: visible?)
- [ ] Tooltip appears above tab
- [ ] Not clipped by content area below

### **My Trails Tabs (Following/Created):**
- [ ] Parent: `.yt-chips-bar` (overflow-y: visible?)
- [ ] Tooltip appears above chip
- [ ] Not clipped by sticky bar above

### **Parked Tabs:**
- [ ] Parent: `.yt-chips-bar` (overflow-y: visible?)
- [ ] Tooltip appears above
- [ ] Clear visibility

### **Park/Trail Buttons:**
- [ ] Parent: `.yt-video-actions` (position: relative?)
- [ ] Grandparent: `.yt-video-card`
- [ ] Tooltip appears above button
- [ ] Not clipped by card boundaries

### **Topic Bubbles:**
- [ ] Parent: `.topic-bubbles`
- [ ] Grandparent: `.focus-slider-expanded`
- [ ] Great-grandparent: `.focus-slider-section` (z-index: 101!)
- [ ] Tooltip visible despite dropdown positioning

---

## 🔧 Recommended CSS Standards

### **For All Tooltip Parents:**
```css
.tooltip-parent-container {
    position: relative; /* Create positioning context */
    overflow: visible; /* Don't clip tooltips */
    /* OR */
    overflow-y: visible; /* If horizontal scroll needed */
}
```

### **For All Tooltips:**
```css
.tooltip-small {
    position: absolute; /* Relative to parent */
    /* OR */
    position: fixed; /* Escape all parents - use sparingly */
    
    z-index: 10000; /* Very high */
    pointer-events: none; /* Don't block interactions */
    
    /* Safe positioning */
    bottom: calc(100% + 8px); /* Above element with clearance */
    left: 50%;
    transform: translateX(-50%); /* Center horizontally */
}
```

### **For Sticky/Fixed Containers:**
```css
.sticky-container {
    position: sticky;
    overflow: visible !important; /* Critical! */
    padding-top: 12px; /* Space for tooltips */
    z-index: 100; /* High enough but not too high */
}
```

---

## 🎯 My Promise

**Going forward, for EVERY tooltip I add, I will:**

1. ✅ Check parent element overflow properties
2. ✅ Check all ancestor overflow up to root
3. ✅ Verify z-index hierarchy
4. ✅ Check for stacking context creators
5. ✅ Ensure proper positioning context
6. ✅ Add padding to parents if needed
7. ✅ Use appropriate position type (absolute vs fixed)
8. ✅ Test visibility mentally before confirming
9. ✅ Document which containers need `overflow: visible`
10. ✅ Provide clear test instructions

---

## 📊 Current Known Issues to Fix

Let me audit ALL existing tooltips systematically:

1. **Feed Toggle** - Need to verify
2. **Collapsed Slider** - Need to verify
3. **Trail Chips** - Already fixed (overflow-y: visible)
4. **Bottom Nav** - Need to check bottom edge
5. **Trail Detail Tabs** - Need to verify
6. **My Trails Tabs** - Need to verify (reported as hidden)
7. **Parked Tabs** - Need to verify
8. **Park/Trail Buttons** - Need to verify
9. **Topic Bubbles** - Need to verify (in dropdown with z-index: 101)

---

## 🔧 Next Steps

I will now:
1. Go through EACH tooltip systematically
2. Check all 9 steps of the checklist
3. Fix any issues found
4. Document what was wrong and how I fixed it
5. Provide test instructions for each

**Shall I proceed with the systematic audit and fix all tooltip visibility issues?**

