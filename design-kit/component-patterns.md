# Component Patterns

**Last updated:** 2026-04-12

Reusable HTML component specs for skills that generate HTML output. Read `design-kit/design-tokens.md` first — this file uses those CSS variables.

---

## Section Container

Every section gets a mode class + grain texture:

```html
<section class="mode-dark grain" style="position: relative; padding: var(--space-12) var(--space-8);">
  <!-- content here (must have z-index: 2 to sit above grain) -->
  <div style="position: relative; z-index: 2; max-width: 1100px; margin: 0 auto;">
    ...
  </div>
</section>
```

---

## Buttons

### Primary Button (purple)

```css
.btn-primary {
  font-family: var(--font-body);
  font-size: var(--text-base);
  background: var(--purple);
  color: var(--white);
  padding: var(--space-3) var(--space-6);
  border-radius: var(--radius-md);
  border: none;
  cursor: pointer;
  box-shadow: var(--shadow-hard);
  transition: transform var(--duration-fast) var(--spring);
}
.btn-primary:hover {
  transform: translateY(-2px);
}
```

### CTA Button (orange)

```css
.btn-cta {
  font-family: var(--font-body);
  font-size: var(--text-lg);
  background: var(--orange);
  color: var(--white);
  padding: var(--space-4) var(--space-8);
  border-radius: var(--radius-md);
  border: none;
  cursor: pointer;
  box-shadow: var(--shadow-hard-orange);
  transition: transform var(--duration-fast) var(--spring);
}
.btn-cta:hover {
  transform: translateY(-3px) scale(1.02);
}
```

### Outlined Button

```css
.btn-outline {
  font-family: var(--font-body);
  font-size: var(--text-base);
  background: transparent;
  color: var(--purple);
  padding: var(--space-3) var(--space-6);
  border-radius: var(--radius-md);
  border: 2px solid var(--purple);
  cursor: pointer;
  transition: all var(--duration-fast) var(--spring);
}
.btn-outline:hover {
  background: var(--purple);
  color: var(--white);
  transform: translateY(-2px);
}
```

---

## Pills / Badges

The purple pill is a signature element (visible in Sab's LinkedIn banner).

```css
.pill {
  font-family: var(--font-body);
  font-size: var(--text-xs);
  padding: 4px 14px;
  border-radius: var(--radius-pill);
  display: inline-block;
}
.pill-purple {
  background: var(--purple);
  color: var(--white);
}
.pill-orange {
  background: var(--orange);
  color: var(--white);
}
.pill-outline {
  background: transparent;
  border: 2px solid var(--purple);
  color: var(--purple);
}
/* On dark backgrounds */
.pill-outline-light {
  border-color: var(--white);
  color: var(--white);
}
```

---

## Cards

### Dark Card

```css
.card-dark {
  background: var(--black);
  color: var(--white);
  border: 2px solid var(--purple);
  border-radius: var(--radius-lg);
  padding: var(--space-6);
  box-shadow: var(--shadow-hard);
}
```

### Purple Card

```css
.card-purple {
  background: var(--purple);
  color: var(--white);
  border-radius: var(--radius-lg);
  padding: var(--space-6);
}
```

### Light Card

```css
.card-light {
  background: var(--white);
  color: var(--black);
  border: 2px solid var(--lavender);
  border-radius: var(--radius-lg);
  padding: var(--space-6);
  box-shadow: var(--shadow-soft);
}
```

### Peach Card

```css
.card-peach {
  background: var(--peach);
  color: var(--black);
  border-radius: var(--radius-lg);
  padding: var(--space-6);
}
```

---

## Stat Callout

Large number with label — for metrics, proof points, pricing.

```html
<div class="stat">
  <span style="font-family: var(--font-display); font-size: var(--text-3xl); color: var(--orange);">56+</span>
  <span style="font-family: var(--font-body); font-size: var(--text-base); color: var(--white);">skills that run your business</span>
</div>
```

---

## Header Bar

Branded header strip for presentations, infographics, documents:

```html
<header style="
  background: var(--black);
  padding: var(--space-3) var(--space-6);
  display: flex;
  justify-content: space-between;
  align-items: center;
">
  <span class="pill-purple pill" style="font-size: var(--text-xs);">TOPIC LABEL</span>
  <img src="design-kit/assets/logos/black-back-white-logo.png" alt="Unstuck" style="height: 32px;">
</header>
```

---

## Footer Bar

Appears at the bottom of every standalone visual (infographics, pitch decks, one-pagers):

```html
<footer style="
  background: var(--black);
  padding: var(--space-3) var(--space-6);
  display: flex;
  justify-content: space-between;
  align-items: center;
">
  <div style="display: flex; align-items: center; gap: var(--space-3);">
    <img src="design-kit/assets/my-photos/sabahudin-profile-photo.png"
         alt="Sabahudin Murtic"
         style="width: 40px; height: 40px; border-radius: 50%; border: 2px solid var(--purple);">
    <div>
      <div style="font-family: var(--font-display); font-size: var(--text-xs); color: var(--white);">Sabahudin Murtic</div>
      <div style="font-family: var(--font-body); font-size: var(--text-xs); color: var(--lavender);">AI Consultant</div>
    </div>
  </div>
  <img src="design-kit/assets/logos/black-back-white-logo.png" alt="Unstuck" style="height: 28px;">
</footer>
```

---

## Comparison Table

Before/After or Us vs Them:

```css
.comparison {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2px;
  border-radius: var(--radius-lg);
  overflow: hidden;
}
.comparison .col-before {
  background: var(--black);
  color: var(--white);
  padding: var(--space-6);
}
.comparison .col-after {
  background: var(--purple);
  color: var(--white);
  padding: var(--space-6);
}
```

---

## Pricing Table

Three-tier layout:

```css
.pricing-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-4);
}
.price-card {
  background: var(--black);
  color: var(--white);
  border: 2px solid var(--purple);
  border-radius: var(--radius-lg);
  padding: var(--space-6);
  text-align: center;
}
.price-card.featured {
  background: var(--purple);
  border-color: var(--orange);
  transform: scale(1.05);
  box-shadow: var(--shadow-hard-orange);
}
.price-card .tier {
  font-family: var(--font-body);
  font-size: var(--text-sm);
  color: var(--lavender);
  letter-spacing: 2px;
  text-transform: uppercase;
}
.price-card .price {
  font-family: var(--font-display);
  font-size: var(--text-2xl);
  margin: var(--space-4) 0;
}
```

---

## Entrance Animations

Staggered fade-up reveal for slide content:

```css
.reveal {
  opacity: 0;
  transform: translateY(20px);
  animation: revealUp var(--duration-slow) var(--spring) forwards;
}
.reveal:nth-child(1) { animation-delay: 0ms; }
.reveal:nth-child(2) { animation-delay: 100ms; }
.reveal:nth-child(3) { animation-delay: 200ms; }
.reveal:nth-child(4) { animation-delay: 300ms; }
.reveal:nth-child(5) { animation-delay: 400ms; }

@keyframes revealUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```

---

## Slide Container (for Presentations)

```css
.slide {
  width: 1280px;
  height: 720px;
  position: relative;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}
```

Slides alternate modes for rhythm. A typical pattern:
1. Dark (cover) → 2. Light (problem) → 3. Purple (solution) → 4. Light (features) → 5. Dark (proof) → 6. Light (pricing) → 7. Purple (CTA)

---

## Profile Photo Component

```css
.profile-photo {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  border: 3px solid var(--purple);
  object-fit: cover;
}
.profile-photo-lg {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  border: 4px solid var(--purple);
  object-fit: cover;
}
```
