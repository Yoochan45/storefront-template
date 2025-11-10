# Storefront Template

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A compact, single-page storefront template built with plain HTML, CSS, and minimal JavaScript. This repository provides the markup and styles for a hero slider, product cards, horizontal product slider, and category grid intended as a starter template for small e-commerce landing pages.

## Quick start

1. Clone the repository:
   ```bash
   git clone https://github.com/Yoochan45/Yoo.git
   cd Yoo
   ```
2. Open `index.html` in a browser, or serve locally:
   - Python 3: `python -m http.server 8000`
   - Node: `npx http-server . -p 8000`
3. Visit `http://localhost:8000` (if serving).

## Project overview

This template includes:
- Hero slider with prev/next controls and indicators
- Horizontal product slider (scrollable row) with nav buttons
- Reusable product cards (badge, image area, title, price, rating, actions)
- Category cards and footer layout
- Responsive CSS with breakpoints for mobile and tablet

## File structure
```
/
├── index.html        # Main page and markup
├── style.css         # Core styles for layout, slider, cards
├── script.js         # Slider and UI scripts (expected, not present)
├── assets/           # Images, icons, fonts
└── README.md
```


## Component reference

Hero slider
- Container: `.hero-slider-container`
- Slides wrapper: `.hero-slider`
- Each slide: `.slide` (use `.slide.active` for visible slide)
- Background: `.slide-bg` currently uses CSS background-image
- Controls: `.slider-nav.prev-slide` and `.slider-nav.next-slide`
- Indicators: `.slider-indicators > button.indicator` with `data-slide` attribute

Product card
- Wrapper: `.product-card`
- Badge: `.product-badge` (modifiers: `.sale`, `.new`, `.featured`)
- Image area: `.product-img` (prefer using `<img>` for actual product images)
- Info: `.product-info` (title, `.product-price`, `.product-rating`)
- Actions: `.product-actions` (`.add-to-cart`, `.add-to-wishlist`)

Product slider
- Container: `.product-slider-container`
- Scrollable row: `.product-slider` (flex row, `overflow-x: auto`)
- Nav buttons: `.product-nav.prev-product`, `.product-nav.next-product`

Category card
- Wrapper: `.category-card`
- Image: `.category-img`
- Title/link: `.category-link`

## Initialization (script expectations)

Place `script.js` with defer attribute or include it at the end of `<body>`:

```html
<script src="script.js" defer></script>
```

Minimal init pattern:
```javascript
document.addEventListener('DOMContentLoaded', () => {
  // Example helpers that your script should provide or implement:
  // initHeroSlider({ container: '.hero-slider-container', interval: 6000, pauseOnHover: true });
  // initProductSlider('.product-slider-container', { step: 300 });
});
```

## Accessibility notes

- Provide meaningful `alt` text for all product and slide images. Replace purely decorative background-image slides with `<img>` when the image conveys information.
- Ensure `.slider-nav`, `.indicator`, and product-nav buttons are keyboard focusable and operable (Enter/Space).
- Consider an `aria-live` element to announce slide changes for screen readers:
  ```html
  <div id="slider-status" class="sr-only" aria-live="polite"></div>
  ```
  Update it when the slide changes: `"Slide 2 of 3: Exclusive Offers"`.
- Respect user preferences for reduced motion with `prefers-reduced-motion`.

## Theming and customization

- Centralize brand colors using CSS variables at the top of `style.css` for easy theme changes:
  ```css
  :root {
    --brand-1: #49664a;
    --accent: #b2edb4;
    --bg: #f5f8f5;
    --text: #333;
  }
  ```
- Replace inline style color attributes with utility classes or data-driven classes to keep markup clean.
- For responsive images, use `srcset` and `loading="lazy"` on `<img>` tags.

## Contributing

- Fork the repo, create a branch, make changes, and open a PR.

## License

Add a `LICENSE` file (MIT recommended) to make reuse and attribution explicit.

## Author

Created by Aisiya Qutwatunnada — GitHub: @Yoochan45
