# Eduan Prinsloo - Backend Software Engineer Portfolio

## Overview

This is a personal portfolio website for Eduan Prinsloo, a Backend Software Engineer. The project is a static, client-side web application built with vanilla HTML, CSS, and JavaScript. It showcases professional information, skills, projects, and contact details through a modern, responsive single-page application design.

The portfolio features a dark/light theme toggle, smooth scrolling navigation, and a mobile-responsive layout. The application runs entirely in the browser with no backend server or database dependencies.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Technology Stack**: Vanilla JavaScript, HTML5, CSS3
- **Rationale**: Chosen for simplicity and zero build dependencies. A static portfolio doesn't require a framework overhead, making the site lightweight and fast to load.
- **Pros**: No build process, minimal dependencies, fast loading times, easy to deploy
- **Cons**: More verbose code for complex interactions, no component reusability like modern frameworks offer

**Styling Approach**: Custom CSS with CSS Variables
- **Rationale**: CSS custom properties (variables) enable dynamic theming without CSS preprocessors or CSS-in-JS libraries.
- **Implementation**: Theme switching between light and dark modes by toggling the `data-theme` attribute on the body element, which updates all CSS variable values.
- **Pros**: Native browser support, no compilation needed, performant theme switching
- **Cons**: Limited to browsers that support CSS custom properties (all modern browsers)

**Layout Pattern**: Single Page Application (SPA) with Section-Based Navigation
- **Rationale**: All content is loaded on initial page load with smooth scrolling between sections, providing a fluid user experience typical of modern portfolios.
- **Pros**: No page reloads, smooth transitions, better perceived performance
- **Cons**: Entire site content loaded upfront (not an issue for a small portfolio)

**Responsive Design**: Mobile-First Approach
- **Rationale**: Indicated by the presence of hamburger menu functionality and viewport meta tag.
- **Implementation**: Uses CSS media queries and flexible layouts to adapt to different screen sizes.
- **Pros**: Works across all devices, better mobile experience
- **Cons**: Requires testing across multiple viewport sizes

### State Management

**Theme Persistence**: LocalStorage
- **Rationale**: User theme preference (dark/light mode) is saved to browser's localStorage to persist across sessions.
- **Default**: Dark theme is the default if no preference is saved.
- **Pros**: Simple API, persists across browser sessions, no server needed
- **Cons**: Limited to 5-10MB storage, data doesn't sync across devices

**Navigation State**: Event-Driven JavaScript
- **Rationale**: Mobile navigation toggle (hamburger menu) uses event listeners to manage open/closed states.
- **Dynamic Navbar**: Scroll position triggers navbar background opacity changes for visual depth.
- **Pros**: Reactive to user interactions, smooth visual feedback
- **Cons**: Requires JavaScript enabled in browser

### Asset Management

**External CDN Dependencies**:
1. **Google Fonts (Inter)**: Typography with multiple weights (300, 400, 500, 600, 700)
2. **Font Awesome 6.4.0**: Icon library for UI elements (theme toggle, social icons)

**Local Assets**:
- Profile image stored in `assets/` directory (ep-2.png)

**Rationale**: CDN-hosted resources for fonts and icons reduce repository size and leverage browser caching from popular CDNs.
- **Pros**: Faster initial load from CDN caching, reduced hosting bandwidth
- **Cons**: Dependency on external services, potential privacy concerns with Google Fonts

### Design System

**Color Scheme**: Dual-theme CSS variable system
- Dark theme: Slate blue palette (#0f172a to #334155)
- Light theme: White to light gray palette
- Accent colors: Indigo (#6366f1), Purple (#8b5cf6), Pink (#ec4899)

**Gradients**: Linear gradients used for visual depth and modern aesthetic
- Primary gradient: 135-degree angle across accent colors
- Background gradient: Subtle transitions between theme colors

**Shadows**: Layered shadow system
- Standard shadow for cards/elements
- Large shadow for prominent features
- Glow effect for interactive elements using accent color

**Typography**: Inter font family
- Modern, highly legible sans-serif
- Multiple weights for hierarchy

## External Dependencies

### CDN Resources

**Google Fonts API**
- Font family: Inter
- Weights: 300 (light), 400 (regular), 500 (medium), 600 (semi-bold), 700 (bold)
- Purpose: Primary typography across the entire site
- Loading strategy: `display=swap` for optimal font loading performance

**Font Awesome CDN (v6.4.0)**
- Icon library for UI elements
- Icons used: Moon/Sun (theme toggle), social media icons, navigation icons
- Purpose: Consistent iconography without custom SVG management

### Browser APIs

**LocalStorage API**
- Purpose: Theme preference persistence
- Data stored: `theme` key with value of 'light' or 'dark'

**Intersection Observer API** (likely used, not fully visible in provided code)
- Purpose: Scroll-based animations and navigation highlighting
- Common pattern in modern single-page portfolios

### No Backend Dependencies
- No server-side code
- No database
- No API integrations
- Fully static and deployable to any web host or CDN