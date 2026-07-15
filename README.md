# Spotlight Carousel

A dependency-free, auto-scrolling image carousel where one image grows into a large "spotlighted" hero
while the rest recede into a smooth horizontal filmstrip. Built as a single self-contained HTML file —
no build step, no npm packages, no framework.

## Features

- **Hero + filmstrip layout** — the active image scales up to a large hero frame; the others shrink and
  slide along a horizontal strip.
- **Auto-play** with a configurable interval, plus pause-on-hover so users can browse manually.
- **Click any thumbnail** to jump straight to it — the strip animates to the new position.
- **Keyboard navigation** — Left/Right arrow keys move to the previous/next slide.
- **Synced content panel** — heading and description fade in/out in step with the active slide.
- **Responsive breakpoint** included for tablet-width screens (800–1200px).
- **Pure HTML/CSS/JS** — copy the file, drop it anywhere (a WordPress page/post via a Custom HTML
  block, a static site, an iframe) with no dependencies to install.

## Usage

Download `index.html` and open it in a browser — that's the whole setup:

```
git clone https://github.com/<your-username>/spotlight-carousel.git
```

Or just download the single file directly and open it.

### Using it in WordPress

Paste the contents of `index.html` into a **Custom HTML** block (or a Custom HTML widget), or save it as
a template file in your theme and include it. The carousel doesn't touch any global styles — every class
name is scoped to `.container`/`.images`/`.content-section`, so it's safe to drop into an existing page.

## Customizing

All slide data lives in two places inside `index.html`, and they're index-matched (position 1 in one
must match position 1 in the other):

1. **Images** — the `<img>` elements inside `#imageContainer`. Add, remove, or reorder `<img>` tags;
   each needs a unique `data-index`.
2. **Text content** — the `content` array inside the `SmoothImageSlider` class, where each entry has a
   `title` and `description` shown when that slide becomes active.

Other knobs worth knowing about:

- `autoScrollDelay` (ms) — how long each slide stays before auto-advancing. Defaults to `4000`.
- `slideWidth` — pixel distance the filmstrip shifts per slide; kept in sync with the responsive
  breakpoint in `setSlideWidth()`.
- Navigation buttons (`.nav-button.prev` / `.nav-button.next`) and the play/pause + progress bar
  controls are implemented but commented out in the markup — uncomment the relevant `<button>` /
  `<div class="controls">` block and its matching CSS/JS references to enable them.

## Browser support

Uses standard CSS transitions/transforms and vanilla JS (ES6 classes) — works in all modern evergreen
browsers. No polyfills included.

## License

No license file is included — all rights reserved by default. Contact the repository owner if you'd
like to use this beyond personal reference.
