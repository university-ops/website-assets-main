# Slide Presentation System

A lightweight JavaScript-based slide presentation system that transforms HTML content into an interactive slide deck with navigation controls and a sidebar menu.

## Overview

This project provides a simple way to convert standard HTML documents (particularly those with `<h1>` and `<h2>` headings) into a navigable slide presentation. It automatically parses the document structure and creates slides based on heading elements.

## Files

| File | Description |
|------|-------------|
| `slides.js` | Core JavaScript that transforms HTML content into slides |
| `slides.css` | Styles for slide presentation mode with sidebar navigation |
| `view.css` | Basic styles for simple view mode |
| `styles.css` | Comprehensive stylesheet with UI components and themes |

## Features

- **Automatic Slide Generation**: Converts `<h1>` and `<h2>` headings into separate slides
- **Sidebar Navigation**: Collapsible menu with links to all slides
- **Keyboard Navigation**: 
  - `Arrow Right` / `Space` / `Page Down` - Next slide
  - `Arrow Left` / `Backspace` / `Page Up` - Previous slide
- **Responsive Design**: Mobile breakpoint at 360px width
- **Theme Support**: Light/dark theme compatibility
- **Mermaid Integration**: Automatic rendering of Mermaid diagrams on slide change

## Usage

### HTML Structure

The system expects HTML content with the following structure:

```html
<div class="content">
    <db-content>
        <h1>Title Slide</h1>
        <!-- Title slide content -->
        
        <h2>Slide 1</h2>
        <!-- Slide 1 content -->
        <hr>
        
        <h2>Slide 2</h2>
        <!-- Slide 2 content -->
        <hr>
    </db-content>
</div>
```

### Including the Scripts and Styles

```html
<link rel="stylesheet" href="styles.css">
<link rel="stylesheet" href="slides.css">
<script src="slides.js"></script>
```

## How It Works

1. **Initialization**: On DOMContentLoaded, the script checks if the window width is above the mobile breakpoint (360px)

2. **Content Transformation**: 
   - Creates a slide container and moves the content area inside it
   - Adds a toggle button for the sidebar menu

3. **Slide Creation**:
   - The `<h1>` element becomes the title slide
   - Each `<h2>` element starts a new slide
   - Content between headings is grouped with their respective headings
   - `<hr>` tags mark the end of a slide section

4. **Navigation**:
   - Builds a sidebar menu with links to each slide
   - Creates previous/next buttons for sequential navigation
   - Highlights the active slide in both the content and menu

5. **Theme Support**: The `.light` class on the `<html>` element switches to light theme

## Customization

### CSS Variables

The styles use various CSS variables for theming:
- `--anchor-color`: Link color
- `--card-border-radius`: Card border radius
- `--scrollbar-thumb-color`: Scrollbar styling

### Mobile Breakpoint

The default mobile breakpoint is set to 360px. To change this, modify the `mobileBreakpoint` variable in `slides.js`.

## Browser Support

Works in all modern browsers that support:
- ES6 JavaScript
- CSS Flexbox
- CSS Transitions

## License

This project is provided as-is without any specific license restrictions.
