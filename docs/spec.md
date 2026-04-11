# DESIGN.md Format

The DESIGN.md file is a textual representation of a design system. The main
audience of DESIGN.md is design and coding agents, to help them understand the
visual differentiation of a product and avoid producing generic designs. All
parts of the file are human readable and understandable, so that the human can
create and modify it.

# Design Tokens

DESIGN.md may also embed structured design tokens. The system that we use to
describe design tokens is loosely based on the
[Design Token JSON spec](https://www.designtokens.org/tr/2025.10/format/#abstract).
As such, it's easily converted from / to tokens.json, Figma variables, and
Tailwind theme configs.

The yaml may be embedded into DESIGN.md as Front Matter.

Example:

```yaml
---
name: Kindred Spirit
description: Describes the design system for a pet care assistant.
colors:
  primary: "#647D66"
typography:
  headline-lg:
    fontFamily: Google Sans Display
    fontSize: 42px
    fontWeight: 500
    lineHeight: 50px
    letterSpacing: 1.2px
---
```

## Schema

Here's the overall schema for the design tokens:

```yaml
name: <string>
description: <string>
colors:
  token-name: <Color>
typography:
  token-name: <Typography>
rounded:
  level: <Dimension>
spacing:
  level: <Dimension>
components:
  component-name:
    token-name: <string|token reference>
```

**Color**: A color value must start with "#" followed by a hex color code in the
SRGB color space.

**Typography**: A typography value is an object that maps the name of the type
token (e.g., headline-lg) to an object defining its properties. The object may
contain:

- fontFamily (string)
- fontSize (Dimension)
- fontWeight (number)
- lineHeight (Dimension)
- letterSpacing (Dimension)
- fontFeature: (string) - configures
  [font-feature-settings](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-feature-settings).
- fontVariation: (string) - configures
  [font-variation-settings](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/font-variation-settings).

**Dimension**: a dimension value is a string with a unit suffix. Valid units are:
px and rem.

**Token references**: a token reference must be wrapped in curly braces, and
contain an object path to another value in the YAML tree. The referenced object
must be a primitive value, e.g. colors.primary-60, rather than an object, e.g.
colors.

# Sections

Every `DESIGN.md` follows the same structure. Sections can be omitted if they’re not relevant to your project, but the order should be preserved.

## Overview

A holistic overview of the design system. This section explains the look and
feel that the design needs to convey, the brand personality it embodies, and how
it serves the user's goals.

## Colors

This section defines the key color palettes for the design system.

At least one color palette should be defined, and should be referred to as
"primary". If there are other color palettes, we follow the material color
naming convention of calling them "primary", "secondary", "tertiary" and
"neutral".

Example:

```markdown
## Colors

The palette uses a deep "Evergreen" primary to establish authority and
health-sector credibility. This is balanced by a "Sun-Kissed Orange" secondary
color used sparingly for calls to action and playful highlights.

- **Primary:** Represents health, growth, and vitality. Used for key
  navigation and primary actions.
- **Secondary:** Represents warmth and activity. Used for notifications,
  reminders, and "joy" moments.
```

### Design Tokens

```yaml
colors:
  primary: "#ff0000"
  secondary: "#00ff00"
```

The colors section defines the color design tokens. It is a
map\<string, Color\>, that maps the name of the color token to the value.

## Typography

Define typography levels.

Most design systems have 9 - 15 typography levels from headlines, body, to
labels. For each level, choose the font family, size, weight, line height, and
optionally letter spacing.

Example:

```markdown
## Typography

This design system utilizes a dual-font strategy to balance character with
functionality. **Plus Jakarta Sans** provides a friendly, slightly rounded
geometric feel for headlines, making the app feel welcoming at first glance.
**Be Vietnam Pro** is used for all functional text; its clean terminals and
generous x-height ensure that medical notes and pet schedules are legible even
on small mobile screens. Headlines use a tighter letter-spacing to feel more
"designed" and editorial.
```

### Design Tokens

```yaml
typography:
  headline-lg:
    fontFamily: Google Sans Display
    fontSize: 42px
    fontWeight: 500
    lineHeight: 50px
    letterSpacing: 1.2px
  body-lg:
    fontFamily: Roboto
    fontSize: 14px
    fontWeight: 400
    lineHeight: 20px
    letterSpacing: 1.2px
```

The typography section defines the typography design tokens. It is a
map\<string, Typography\>

## Layout

Describe the layout method.

Most design systems follow a grid-based layout. Others, like Liquid Glass, use
margins, safe areas, and dynamic padding. Explain the layout model and spacing
rhythm.

Example:

```markdown
## Layout

The layout follows a **Fluid Grid** model for mobile devices and a
**Fixed-Max-Width Grid** for desktop (max 1200px).

A strict 8px spacing scale (with a 4px half-step for micro-adjustments) is used
to maintain a consistent rhythm. Components are grouped using "containment"
principles, where related items are housed in cards with generous internal
padding (24px) to emphasize the soft, approachable nature of the brand.
```

### Design Tokens

You may provide spacing units that are useful for implementing the layout model.
For example, a fixed grid layout may have spacing units for column spans,
gutters, and margins.

```yaml
spacing:
  gutter-s: 8px
  gutter-l: 16px
```

The spacing section defines the spacing design tokens. It is a
map\<string, Dimension\> that maps the spacing scale identifier to a dimension
value.

## Elevation[^1]

Describe how visual hierarchy is conveyed based on the design style. If
elevation is used, it defines the required styling (spread, blur, color). For
flat designs, this section explains the rationale and any alternative methods
employed (e.g., borders, color contrast).

Example:

```markdown
## Elevation & Depth

Depth is achieved through **Tonal Layers** rather than heavy shadows. The
background uses a soft off-white or very light green, while primary content sits
on pure white cards.
```

## Shapes

Describe the shape language. In particular, describe the rounded corners used in
buttons, cards, and other rectangular shapes.

### Design Tokens

```yaml
rounded:
  regular: 4px
  lg: 8px
  xl: 12px
  full: 9999px
```

The rounded section defines the design tokens for rounded corners used in
buttons, cards, and other rectangular shapes.

## Components

Provides style guidance for component atoms within the design system, focusing
on those most relevant to the application.

- **Buttons**: Covers primary, secondary, and tertiary variants, including
  sizing, padding, and states.
- **Chips**: Covers selection chips, filter chips, and action chips.
- **Lists**: Covers styling for list items, dividers, and leading/trailing
  elements.
- **Tooltips**: Covers positioning, colors, and timing.
- **Checkboxes**: Covers checked, unchecked, and indeterminate states.
- **Radio buttons**: Covers selected and unselected states.
- **Input fields**: Covers text inputs, text areas, labels, helper text, and
  error states.

This section may also suggest additional components particularly relevant to the
app's context.

### Design Tokens

```yaml
components:
  button-primary:
    backgroundColor: "{colors.primary-60}"
    textColor: "{colors.primary-20}"
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    padding: 12px
  button-primary-hover:
    backgroundColor: "{colors.primary-70}"
```

The components section defines a collection of design tokens used to ensure
consistent styling of common components. It's a
map\<string, map\<string, string\>\> that maps a component identifier to a group
of sub token names and values. The design token values may be literal values, or
references to previously defined design tokens.

**Variants**. A component may have a variant for different UI states such as
active, hover, pressed, etc. You may define those variant components under a
different but related key, for example, "button-primary",
"button-primary-hover", "button-primary-active". The agent will consider all
variants and make the appropriate styling decisions.

### Component Property Tokens

Each component has a set of properties that are themselves design tokens:

- backgroundColor: \<Color\>
- textColor: \<Color\>
- typography: \<Typography\>
- rounded: \<Dimension\>
- padding: \<Dimension\>

## Do's and Don'ts

Practical guidelines and common pitfalls. These act as guardrails when creating designs.

```markdown
## Do's and Don'ts

- Do use the primary color only for the single most important action per screen
- Don't mix rounded and sharp corners in the same view
- Do maintain WCAG AA contrast ratios (4.5:1 for normal text)
- Don't use more than two font weights on a single screen
```
