---
name: EAST DESIGN
colors:
  surface: "#15161D"
  surface-dim: "#27282F"
  surface-bright: "#363F4A"
  surface-container-lowest: "#15161D"
  surface-container-low: "#27282F"
  surface-container: "#363F4A"
  surface-container-high: "#788795"
  surface-container-highest: "#BFCBD6"
  on-surface: "#BFCBD6"
  on-surface-variant: "#788795"
  inverse-surface: "#FCFDFF"
  inverse-on-surface: "#4D4D4D"
  outline: "#788795"
  outline-variant: "#363F4A"
  surface-tint: "#F34847"
  primary: "#F34847"
  on-primary: "#FFFFFF"
  primary-container: "#F5EFED"
  on-primary-container: "#4D4D4D"
  inverse-primary: "#C84040"
  secondary: "#5AC8FA"
  on-secondary: "#15161D"
  secondary-container: "#D7F2FE"
  on-secondary-container: "#15465A"
  tertiary: "#29CB97"
  on-tertiary: "#15161D"
  tertiary-container: "#D8F6EC"
  on-tertiary-container: "#164C3C"
  error: "#FF2D55"
  on-error: "#FFFFFF"
  error-container: "#FFD7E0"
  on-error-container: "#6A1022"
  primary-fixed: "#FF7A72"
  primary-fixed-dim: "#F34847"
  on-primary-fixed: "#FFFFFF"
  on-primary-fixed-variant: "#6F2323"
  secondary-fixed: "#D7F2FE"
  secondary-fixed-dim: "#5AC8FA"
  on-secondary-fixed: "#082A36"
  on-secondary-fixed-variant: "#15465A"
  tertiary-fixed: "#D8F6EC"
  tertiary-fixed-dim: "#29CB97"
  on-tertiary-fixed: "#0F3128"
  on-tertiary-fixed-variant: "#164C3C"
  background: "#15161D"
  on-background: "#BFCBD6"
  surface-variant: "#27282F"
typography:
  display-lg:
    fontFamily: Raleway
    fontSize: 50px
    fontWeight: "700"
    lineHeight: 56px
    letterSpacing: 0.2em
  headline-lg:
    fontFamily: source-han-serif-japanese
    fontSize: 30px
    fontWeight: "400"
    lineHeight: 45px
    letterSpacing: 0.1em
  headline-md:
    fontFamily: Meiryo
    fontSize: 34px
    fontWeight: "400"
    lineHeight: 42px
  title-md:
    fontFamily: Meiryo
    fontSize: 20px
    fontWeight: "700"
    lineHeight: 32px
  body-lg:
    fontFamily: Meiryo
    fontSize: 16px
    fontWeight: "400"
    lineHeight: 30px
  body-md:
    fontFamily: Meiryo
    fontSize: 15px
    fontWeight: "400"
    lineHeight: 24px
  label-md:
    fontFamily: Raleway
    fontSize: 14px
    fontWeight: "700"
    lineHeight: 20px
    letterSpacing: 0.08em
  label-sm:
    fontFamily: Meiryo
    fontSize: 14px
    fontWeight: "400"
    lineHeight: 22px
rounded:
  sm: 2px
  DEFAULT: 5px
  md: 8px
  lg: 12px
  xl: 20px
  full: 9999px
spacing:
  unit: 8px
  container-max: 1328px
  gutter: 50px
  section-gap: 160px
  section-gap-mobile: 96px
  card-padding: 50px
  card-gap: 57px
  border-accent-width: 8px
components:
  shell-default:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    maxWidth: "{spacing.container-max}"
    paddingInline: "{spacing.gutter}"
  header-fixed:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    borderBottomColor: "{colors.inverse-surface}"
    typography: "{typography.label-md}"
  section-title-primary:
    textColor: "{colors.primary}"
    typography: "{typography.display-lg}"
  section-subtitle-muted:
    textColor: "{colors.on-surface-variant}"
    typography: "{typography.body-lg}"
  hero-statement:
    textColor: "{colors.inverse-surface}"
    typography: "{typography.headline-lg}"
  service-band:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.inverse-surface}"
    typography: "{typography.headline-md}"
    accentRailWidth: "{spacing.border-accent-width}"
  service-card:
    backgroundColor: "{colors.surface-container-low}"
    textColor: "{colors.on-surface}"
    padding: "{spacing.card-padding}"
  feature-box:
    backgroundColor: "{colors.surface-container-low}"
    textColor: "{colors.on-surface}"
    titleBackgroundColor: "{colors.primary}"
    padding: "{spacing.card-padding}"
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.title-md}"
    rounded: "{rounded.DEFAULT}"
    height: 72px
    padding: 0 32px
  button-primary-hover:
    backgroundColor: "{colors.primary-fixed}"
  theme-light-shell:
    backgroundColor: "{colors.inverse-surface}"
    textColor: "{colors.inverse-on-surface}"
  accent-info:
    backgroundColor: "{colors.secondary}"
    textColor: "{colors.on-secondary}"
  accent-warning:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  accent-success:
    backgroundColor: "{colors.tertiary}"
    textColor: "{colors.on-tertiary}"
---

## Overview

This design system is derived from the current public EAST DESIGN site and captures its editorial portfolio tone: dark-first, strongly art-directed, and intentionally structured around contrast between calm information design and one vivid emotional accent.

The core expression is a restrained studio aesthetic. Most surfaces stay quiet in charcoal, off-white, and slate, while a single coral-red accent drives identity, section framing, and calls to action. English labels behave like graphic marks, while Japanese messaging carries warmth and clarity.

The system should feel like a design studio presentation board rather than a SaaS dashboard. Use large negative space, deliberate alignment, and asymmetry supported by strict container widths.

## Colors

The palette is anchored by a dark canvas and a red brand accent.

- `primary` is the defining brand color. Use it for section titles, CTA backgrounds, active markers, and graphic rules.
- `surface` and `surface-container-low` are the default dark layers. These should dominate the page.
- `inverse-surface` supports the site's light mode and selected contrast sections, but should remain secondary to the dark presentation.
- `secondary`, `tertiary`, and the warm yellow implied by the site are supporting accent rails, not replacement brand colors. Use them as category identifiers or structural highlights only.
- Text should default to `on-surface` on dark backgrounds and `inverse-on-surface` on light backgrounds. Avoid pure white except for strong emphasis or hero copy.

When building new screens, preserve the ratio: large dark fields, sparse red emphasis, occasional accent-color segmentation.

## Typography

This system uses role-based typography rather than a single-family voice.

- **Raleway** is the English display face. Use it for navigation, large section labels such as `WORKS` or `SERVICE`, and other brand-signature uppercase text.
- **source-han-serif-japanese** is the emotional voice for the main Japanese statement. Use it for hero copy or rare editorial moments where warmth and gravitas are needed.
- **Meiryo** and equivalent Japanese sans-serif fallbacks are the operational type layer. Use them for descriptions, UI labels, service cards, and button text.

Typography should stay airy and measured:

- English display text should use wide tracking and clear separation from body content.
- Japanese hero copy should be sparse, centered, and never crowded by nearby UI chrome.
- Body copy should remain highly readable, with generous line height close to the site implementation.

## Layout

Layout is based on a controlled desktop editorial frame.

- Use a centered container with a max width of `1328px` and `50px` side gutters.
- Favor long vertical sections with large pauses between them. `section-gap` should remain visibly generous.
- Compose content in alternating text/image or text/block arrangements instead of repetitive equal cards.
- Allow major headings to start flush with a structural edge, then offset supporting content to create rhythm.
- On mobile, simplify the composition rather than shrinking the desktop editorial tension mechanically.

This is not a dense component grid system. It is a curated presentation layout with repeated framing motifs.

## Elevation & Depth

Depth is created more by layering and motion than by shadows.

- Use flat dark planes first. Do not rely on heavy drop shadows to separate content.
- Distinguish layers with background shifts between `surface`, `surface-container-low`, and `inverse-surface`.
- Introduce motion through fade, slide, reveal lines, and staged opacity transitions rather than springy micro-interactions.
- Fixed header behavior should compress gracefully while preserving the brand mark and navigation clarity.

If depth is needed, prefer subtle opacity overlays or thin rule lines over glossy effects.

## Shapes

The shape language is mostly rectilinear and architectural.

- Most sections and cards should feel square-edged or only lightly softened.
- Small radii are acceptable for form inputs and CTAs, but rounded geometry is not a defining brand trait.
- Accent bars, underlines, and left rails are more important than pill shapes or floating chips.
- Imagery and illustration areas can be playful, but the framing system around them should stay disciplined.

## Components

### Header

The header is fixed, centered, and brand-led. Navigation uses `Raleway` with modest tracking and enough spacing to feel like signage. In the scrolled state, the header compresses and becomes more utilitarian without losing contrast.

### Hero

The hero pairs a single symbolic graphic with a short Japanese statement in serif typography. Keep this area quiet. One statement, one supporting paragraph, and a clear scroll affordance are enough.

### Section Titles

Top-level section titles use oversized red English labels with a muted Japanese subtitle beneath. This pattern is mandatory for major page chapters and should remain consistent.

### Service Bands

Service category headers are red horizontal bands with white text and a colored left rail that changes by category. The rail color can vary using `secondary`, a warm yellow equivalent, or `tertiary`, but the red band remains the common parent pattern.

### Service Cards

Service explanation blocks sit on dark panels with large internal padding and a clear split between explanatory copy and visual support. These blocks should feel like presentation boards, not generic product cards.

### Feature Boxes

Feature boxes use dark panels with a red heading strip and a thin colored edge. Staggered reveal timing is appropriate. Keep the geometry crisp and the text comfortably padded.

### Call To Action

The contact CTA is a bold red block with white text and minimal ornament. It should read as a studio invitation, not a generic form control.

## Do's and Don'ts

- Do keep the page dark-first and let `primary` do most of the brand work.
- Do use `Raleway` for English framing text and serif Japanese only for rare high-emotion moments.
- Do preserve long vertical rhythm, asymmetry, and generous whitespace.
- Do use colored rails and line work to differentiate sections before introducing new fill colors.
- Don't turn the system into a soft card-heavy SaaS UI.
- Don't scatter accent colors freely or let them compete with `primary`.
- Don't replace the restrained editorial feel with oversized shadows, glass effects, or rounded components.
- Don't overpopulate hero areas with badges, stats, or multiple competing messages.
