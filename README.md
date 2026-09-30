# Next.js + Tailwind CSS Animated Landing Page ("Metaversus")

A single-page marketing site for a fictional metaverse product, "Metaversus". It's a dark, gradient-heavy design with scroll-triggered animations throughout. I built it with Next.js 13 (App Router), Tailwind CSS, and Framer Motion as a front-end practice project, following a tutorial.

> **Status: complete (tutorial build, 2022).** All page sections and the footer are finished. The navbar's search and menu icons are decorative only, with no search or menu behind them.

## Features
- **Eight page sections plus a navbar and footer:** Hero, About, Explore, Get Started ("How Metaversus Works"), What's New, World ("People on the World"), Insights, and Feedback
- **Scroll-triggered animations with Framer Motion.** Reusable motion variants in `utils/motion.js` (slide-in, fade-in, zoom-in, staggered children, planet and footer variants) run as each section enters the viewport.
- **Letter-by-letter "typing" animation** for the section labels (`TypingText` component)
- **Interactive Explore gallery.** Click a world card to expand it, and the other cards collapse, with an animated flex transition.
- **Responsive layout** built with Tailwind utility classes, stacking vertically on small screens
- **Reusable components and data-driven content:** section content lives in `constants/index.js` and is rendered by components like `ExploreCard`, `StartSteps`, `NewFeatures`, and `InsightCard`
- Custom Tailwind theme colors, a custom easing curve, and gradient and glassmorphism utility classes in `styles/globals.css`

## Tech stack

| Area | Tools |
|---|---|
| Framework | Next.js 13.0 (experimental `app/` directory), React 18 |
| Styling | Tailwind CSS 3, PostCSS, Autoprefixer |
| Animation | Framer Motion 7 |
| Linting | ESLint with the Airbnb config and `eslint-config-next` |
| Language | JavaScript (JSX) |

## Getting started

### Prerequisites
- Node.js and npm (tested with Node 20)

### Run locally
```bash
git clone https://github.com/mackmraz/nextjs-tailwind-landing-page.git
cd nextjs-tailwind-landing-page
npm install
npm run dev
```

Then open [http://localhost:3000](http://localhost:3000).

### Production build
```bash
npm run build   # next build (runs ESLint first)
npm start       # next start
npm run lint    # next lint
```

> **Note:** the strict Airbnb ESLint rules currently flag style problems (spacing, quotes, and similar) in several components. Next.js treats these as errors, so `npm run build` stops at the lint step. Until the lint issues are fixed, `npx next build --no-lint` builds the site successfully.

## Project structure

```
app/
  layout.js        Root layout (global styles, Eudoxus Sans font)
  head.js          Page title and meta tags
  page.js          Composes the navbar, all sections, and the footer
sections/          Hero, About, Explore, GetStarted, WhatsNew, World, Insights, Feedback
components/        Navbar, Footer, CustomTexts (TypingText / TitleText), ExploreCard, StartSteps, NewFeatures, InsightCard
constants/         Content data for the sections
utils/motion.js    Framer Motion animation variants
styles/            Tailwind globals, gradients, and shared class-name helpers
public/            Images and SVG icons
```

The Eudoxus Sans font is loaded from an external stylesheet (`stijndv.com`) in `app/layout.js`, so the site needs an internet connection for its font to render as designed.

## Acknowledgements
Built by following JavaScript Mastery's tutorial [*Build and Deploy a Modern Next.js Website With Framer Motion & Tailwind CSS*](https://www.youtube.com/watch?v=ugCN_gynFYw) (the "Metaversus" design). The design, copy, and image assets come from that tutorial.
