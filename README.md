# YouTube Trails - Web Prototype

A modern web-based prototype for YouTube Trails, an innovative content discovery and organization platform that helps users curate personalized learning paths through YouTube videos.

## 🎯 Features

### Core Functionality
- **Dual Feed System**: Toggle between Regular Feed and Trail Feed
- **Smart Content Balance**: Adjust focus between two topics using an intuitive slider
- **Topic Selection**: Choose main topics and meta tags for personalized content curation
- **Trail Management**: Create, follow, and organize video trails
- **Parked Videos**: Save videos for later viewing
- **Smart Contextual Onboarding**: Help cards appear when you first use each feature
- **Complete Feature Guide**: Comprehensive documentation and tutorials

### UI/UX Highlights
- **YouTube-Inspired Design**: Familiar interface with Material Design principles
- **Responsive Layout**: Mobile-first design with 428px viewport
- **Smart Tooltips**: Edge-detection tooltips that stay within bounds
- **Color Psychology**: Soft pastel colors for regular feed, vibrant colors for trail feed
- **Smooth Animations**: Collapsible slider, scroll-based header visibility, graceful onboarding cards
- **Accessibility**: WCAG-compliant contrast ratios and touch targets

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, or Edge)
- No build tools or dependencies required!

### Installation

1. Clone this repository:
```bash
git clone <your-repo-url>
cd youtube-trails-web
```

2. Open `index.html` in your browser:
```bash
# Windows
start index.html

# macOS
open index.html

# Linux
xdg-open index.html
```

That's it! The app runs entirely in the browser with no server or build step needed.

## 📱 How to Use

### Regular Feed
- Browse mixed content from various topics
- Park videos for later viewing
- Add videos to existing trails

### Trail Feed
1. Toggle to "Trail Feed" using the switch at the top
2. Select a trail (Web Dev, Science, Cooking)
3. Tap the collapsed slider to expand content balance controls
4. Tap topic bubbles to select main topics and meta tags
5. Adjust the slider to balance content between your chosen topics

### My Trails
- View trails you're following or have created
- Access detailed trail information with Videos, Tags, Notes, and Path tabs

### Parked Videos
- View saved videos
- Mark as watched
- Add to trails

## 🛠️ Technology Stack

- **Pure HTML/CSS/JavaScript**: No frameworks or libraries
- **Material Design Icons**: Google Material Icons via CDN
- **Roboto Font**: Google Fonts for typography
- **Modern CSS**: Flexbox, Grid, Custom Properties, Animations

## 📐 Architecture

### State Management
- Centralized `state` object manages all application state
- Simple screen-based routing
- Event-driven UI updates

### Key Components
- Header with YouTube branding
- Trail toggle bar with collapsible slider
- Dynamic chip bar for trail selection
- Video cards with tags and actions
- Bottom navigation
- Modal overlays (topic maps, onboarding, help)
- Smart tooltip system with edge detection

### Mock Data
- 3 sample trails (Web Development, Science, Cooking)
- Topic maps with main topics and meta tags
- Sample videos for each trail
- Regular feed videos

## 🎨 Design System

### Colors
- Primary: YouTube Red (#FF0000)
- Secondary: Material Blue (#065FD4)
- Trail Colors: Purple, Teal, Coral
- Text: #0F0F0F (primary), #606060 (secondary)

### Typography
- Font Family: Roboto
- Sizes: 10px - 24px
- Weights: 300, 400, 500, 700

### Spacing
- 8pt baseline grid system
- Consistent padding and margins

### Touch Targets
- Minimum 48x48px for interactive elements

## 📝 Version History

- **v5.2** - Fixed bubble labels to show "Tap to select"
- **v5.1** - Added visible labels to topic bubbles
- **v5.0** - Implemented smart tooltip system with edge detection
- **v4.x** - Multiple tooltip improvements and refinements
- **v3.x** - Added onboarding flow and feature documentation
- **v2.x** - Implemented dual-topic slider and topic maps
- **v1.x** - Initial prototype with basic functionality

## 🤝 Contributing

This is a prototype project. Feel free to fork and experiment!

## 📄 License

This project is for educational and demonstration purposes.

## 🆕 Recent Updates (v5.5)

### Major Onboarding System Overhaul
- **Smart Contextual Help**: Onboarding cards now appear when you first use each feature, not all at once
- **Visual Polish**: Enhanced empty states, trail cards with creator details, and consistent Material Icons
- **Smooth Animations**: Graceful card appearances with fade-in and slide-in effects
- **Better Navigation**: Breadcrumb navigation and improved profile organization
- **Bug Fixes**: Fixed trail card clickability and content separation between Following/Created tabs

### Key Improvements
- ✅ **Reduced cognitive load** - Help appears exactly when needed
- ✅ **Professional feel** - Smooth animations and consistent visual language  
- ✅ **Better engagement** - Non-intrusive contextual guidance
- ✅ **Enhanced content** - Rich trail cards with detailed information

## 👨‍💻 Author

Built as part of MS HCI coursework at DePaul University

---

**Note**: This is a functional prototype demonstrating UI/UX concepts. All data is mock data stored in JavaScript. No backend or real YouTube API integration.

