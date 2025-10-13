# 🎬 YouTube Trails - Complete Functional Prototype

## 🚀 Quick Start

**Simply double-click `index.html` to launch the app!**

No installation, no dependencies, no build tools - just open and explore!

---

## ✨ What's This?

A **fully functional mobile app prototype** that adds "Trails" feature to YouTube - allowing users to organize their viewing into topic-specific learning journeys.

---

## 🎯 Complete Feature Set

### 📱 6 Full Screens (All Connected!)

1. **Home/Feed** - Browse videos with regular or trail-focused feed
2. **My Trails** - Manage trails you follow and create
3. **Trail Details** - Deep dive into trail content, tags, notes, and path
4. **Parked Videos** - Save videos for later with notes
5. **Create Trail** - Full form to create custom trails
6. **Profile/Settings** - Manage preferences and account

### 🎮 Every Button Works!

✅ **Toggle switches** - Regular ↔ Trail Feed, Notifications  
✅ **Sliders** - Focus ratio (0-100%) with live updates  
✅ **Chips/Filters** - Content filtering, tab switching  
✅ **Navigation** - Bottom nav, back buttons, screen transitions  
✅ **Actions** - Park, Follow, Add to Trail, Create, Submit  
✅ **Forms** - Full validation, real-time feedback  

### 🎨 Exact YouTube UI

- ✅ YouTube's colors, spacing, and typography
- ✅ Material Design icons
- ✅ Roboto font
- ✅ Authentic shadows and hover states
- ✅ Mobile phone frame (428×926px)
- ✅ 16:9 video thumbnails
- ✅ Smooth animations

---

## 📖 How to Explore

### **Try These Flows:**

1. **Browse & Park**
   - View home feed
   - Click "Park" on any video
   - Navigate to Parked tab (bottom nav)
   - See your parked videos with notes

2. **Create a Trail**
   - Click "Create Trail" button or center "+" in bottom nav
   - Fill in name, description, topic
   - Adjust focus slider
   - Submit → See it in My Trails

3. **Follow & Explore**
   - Go to "Trails" tab (bottom nav)
   - Click any trail card
   - View details, videos, tags, notes
   - Click "Follow" button
   - Toggle notifications

4. **Toggle Trail Feed**
   - On home screen, toggle "Trail Feed" switch
   - See topic header appear
   - Adjust focus slider
   - Watch video recommendations change context

5. **Configure Settings**
   - Go to "You" tab (bottom nav)
   - Toggle notifications
   - Set default focus ratio
   - View trail statistics

---

## 🎯 Information Architecture

```
Home (Feed)
├── Regular Feed
├── Trail Feed
│   ├── Focus Slider
│   ├── Video Cards
│   ├── Trail Banner
│   └── Create Trail

My Trails
├── Following
├── Created
└── Trail Details
    ├── Videos
    ├── Tags
    ├── Notes
    └── Trail Path

Parked Videos
├── To Watch
├── Watched
└── Add to Trail

Create Trail
├── Trail Name
├── Description
├── Filters (Topic, Skill)
├── Focus Slider
└── Create CTA

Profile / Settings
├── Notification Settings
├── My Trails Summary
├── Focus Defaults
└── Privacy & Log Out
```

---

## 🔧 Technical Details

- **File**: Single HTML file (1 file, ~1000 lines)
- **Framework**: Vanilla JavaScript (no dependencies!)
- **Styling**: Pure CSS with YouTube design system
- **Icons**: Material Icons (Google CDN)
- **Fonts**: Roboto (Google Fonts)
- **State Management**: Simple JavaScript object
- **Routing**: State-based screen switching

---

## 📊 Mock Data Included

- **3 Sample Trails** (Web Dev, Quantum Physics, Mediterranean Cooking)
- **2 Feed Videos** with trail relevance badges
- **3 Parked Videos** (to watch and watched)
- All with realistic metadata (views, duration, tags, etc.)

---

## 🎨 Design Compliance

### Material Design 3
- ✅ 8pt spacing grid
- ✅ 48px minimum touch targets
- ✅ Elevation & shadows
- ✅ Typography scale
- ✅ Color system

### YouTube Brand
- ✅ Red (#FF0000) primary
- ✅ Blue (#065FD4) accent
- ✅ 56px header/footer
- ✅ Chip navigation
- ✅ Card layouts

### WCAG Accessibility
- ✅ 4.5:1 text contrast
- ✅ Large touch targets
- ✅ Clear visual hierarchy
- ✅ Readable typography

---

## 📱 Responsive Design

- Mobile-first approach (428×926px)
- Displayed in realistic phone frame
- Scrollable content areas
- Fixed headers and bottom navigation
- Optimized for single-hand use

---

## 🌟 Key Interactions

| Element | Action | Result |
|---------|--------|--------|
| Toggle Switch | Click | Switches Regular ↔ Trail Feed |
| Focus Slider | Drag | Updates ratio 0-100% |
| Video Card | Click "Park" | Adds to Parked Videos |
| Trail Card | Click | Opens Trail Details |
| Follow Button | Click | Toggles follow state |
| Bottom Nav | Click icons | Switches screens |
| Create Button | Click | Opens Create Trail form |
| Submit Form | Click | Creates trail, shows in My Trails |
| Chips | Click | Filters content |
| Tabs | Click | Switches views |

---

## 📝 Notes

- This is a **prototype/demo** - no backend
- Alerts simulate some actions (trail selection, etc.)
- State resets on page reload
- Perfect for presentations, user testing, or portfolio

---

## 📂 Files

```
youtube-trails-web/
├── index.html      # Complete app (open this!)
├── README.md       # This file
└── FEATURES.md     # Detailed feature documentation
```

---

## 🎓 Educational Use

Perfect for:
- UX/UI Design portfolios
- HCI coursework
- Design system demonstrations
- Prototyping examples
- User testing sessions
- Presentation demos

---

## 💻 Browser Compatibility

Works in all modern browsers:
- ✅ Chrome
- ✅ Firefox
- ✅ Safari
- ✅ Edge

---

## 🎉 Credits

**Built for DePaul MS HCI**

Design System: Material Design 3 + YouTube Brand Guidelines  
Icons: Material Icons by Google  
Fonts: Roboto by Google

---

## 📧 Questions?

This is a complete, self-contained prototype. Everything you need is in `index.html`!

**Just double-click and start exploring!** 🚀
