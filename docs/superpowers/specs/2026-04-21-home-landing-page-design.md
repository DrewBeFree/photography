# Home Landing Page — Design Spec
_2026-04-21_

## Goal

Replace the default view (Boogiesnaps section) with a dedicated home landing page that gives visitors an overview of all three photography sections before diving in.

## Changes to `index.html`

### Nav
Add "Home" as the first tab. It is active by default on page load.

Before: `Boogiesnaps | Drew's Doggies | Weddings`  
After: `Home | Boogiesnaps | Drew's Doggies | Weddings`

Clicking the header brand name (`Andrew Webb`) also navigates back to the home section.

### Home section (`#home`)

Becomes the default active section (replaces `boogiesnaps` as the initial `active` class).

Contains two sub-areas stacked vertically:

**1. Photo ticker**
- A horizontally scrolling strip of photos that auto-scrolls on a loop (CSS animation, no JS needed).
- Photos are pulled from a `ticker` array in the JS config — empty for now, owner adds them later.
- When empty, the ticker area is hidden (zero height, no placeholder shown).

**2. Section cards**
- 3 cards in a CSS grid: 3 columns on desktop, 1 column on mobile.
- Each card navigates to its section on click (reuses existing tab-switch logic).
- Card anatomy (top to bottom):
  - **Cover photo area** — fixed-aspect-ratio container (`aspect-ratio: 4/3`). Shows a cover image when one is configured; shows a styled blank area when not.
  - **Title** — section name in Playfair Display.
  - **Description** — short subtitle in Source Sans 3.
- Hover state: amber border glow, subtle image scale (matching `.photo:hover` pattern).
- Cover images are configured via a `homeCards` object in the JS config block — empty by default.

### JS config additions

```js
// Photo ticker — add image paths here
const ticker = [
  // 'images/ticker/photo1.jpg',
];

// Cover photos for home cards — add one path per section
const homeCards = {
  boogiesnaps: { cover: '', label: 'Portraits, events & street — Atlanta, GA' },
  doggies:     { cover: '', label: 'Dogs being dogs' },
  weddings:    { cover: '', label: 'Celebrating love in Atlanta & beyond' },
};
```

## Styles

All new styles use existing CSS variables (`--amber`, `--bg2`, `--border`, `--text-dim`, etc.). No new colors or fonts.

## What Is Not In Scope

- Actual photos (owner adds later)
- Any change to the Boogiesnaps, Doggies, or Weddings sections themselves
- Lightbox behavior changes
- Any backend or build tooling
