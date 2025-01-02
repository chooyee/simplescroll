# Scroll Trigger Component

A lightweight JavaScript implementation for triggering content visibility based on scroll position. This component allows you to create scroll-based interactions where elements change their appearance or reveal content when they reach a specific position in the viewport.

## Features

- Automatically detects when elements reach a target scroll position
- Supports multiple scrollable elements on the same page
- Handles content visibility toggling
- Includes CSS transitions and gradient backgrounds
- Responsive design support

## Usage

### HTML Structure

Create scrollable elements using the following structure:

```html
<div class="scrollable" id="uniqueId">
    <h1>Your Title</h1>
    <div class="hide" data-item="mainbox">Your Content</div>
</div>
```

### JavaScript Implementation

Initialize the scroll trigger:

```javascript
const scrollable = new ScrollableElement(".scrollable", 100);
```

Parameters:
- `className`: The CSS selector for scrollable elements
- `targetHeight`: The scroll position (in pixels) where the trigger should activate

### CSS Classes

The component uses the following CSS classes:

- `.scrollable`: Container for scrollable content
- `.hide`: Initially hidden content
- `.content`: Styling for revealed content
- `.scrolled`: Applied to elements when they reach the target scroll position

### Customization

Modify the CSS to customize the appearance:

```css
.scrollable {
    overflow: auto;
    border: 1px solid #ccc;
    margin-bottom: 20px;
    padding: 10px;
}

.content {
    width: 600px;
    height: 300px;
    background: linear-gradient(to bottom right, #ff7eb3, #8ec5fc);
}

.scrolled {
    background-color: lightgreen !important;
}
```

## How It Works

The `ScrollableElement` class:
1. Monitors window scroll events
2. Checks if elements reach the specified target height
3. Toggles visibility and applies styles based on scroll position
4. Manages content reveal animations

```javascript
class ScrollableElement {
    constructor(className, targetHeight) {
        this.className = className;
        this.targetHeight = targetHeight;
        this.elements = document.querySelectorAll(className);
        window.addEventListener("scroll", this.handleScroll.bind(this));
    }
    // ... rest of the implementation
}
```

## Browser Support

This component supports all modern browsers including:
- Chrome
- Firefox
- Safari
- Edge

## License
This project is licensed under the MIT License - see the LICENSE file for details.

