# mpanfolio Visual Direction

## Design goal

Present Michael Pantoja as a senior engineer who makes complex systems understandable and dependable. The site should feel precise, calm, credible, and human—not corporate, military-themed, or decorative.

## Principles

1. Lead with role, value, and contact action.
2. Show evidence before long skill lists.
3. Use strong hierarchy and generous spacing for fast scanning.
4. Keep every interaction obvious with keyboard-visible states.
5. Use no animation, stock imagery, fake metrics, or ornamental dashboards at launch.

## Typography

Use fonts already provided by the application:

- **Primary:** Geist Sans
- **Technical labels:** Geist Mono
- **Body:** 18/30 desktop, 17/28 mobile
- **Display:** 64/68 desktop, 42/46 mobile, weight 650
- **Section heading:** 36/44 desktop, 30/36 mobile, weight 650
- **Card heading:** 24/32, weight 600
- **Label:** 13/20, Geist Mono, weight 550, 0.06em tracking

Keep body lines between 55 and 72 characters where practical.

## Color tokens

### Global

- `color.base.ink.900`: `#132238`
- `color.base.slate.700`: `#44546A`
- `color.base.slate.300`: `#BCC5D1`
- `color.base.slate.150`: `#DCE2E8`
- `color.base.paper.100`: `#F6F4EF`
- `color.base.white`: `#FFFFFF`
- `color.base.blue.700`: `#174EA6`
- `color.base.blue.800`: `#123C80`
- `color.base.orange.600`: `#B84A2B`

### Semantic

- `color.bg.default`: `color.base.paper.100`
- `color.bg.surface`: `color.base.white`
- `color.text.primary`: `color.base.ink.900`
- `color.text.muted`: `color.base.slate.700`
- `color.border.default`: `color.base.slate.300`
- `color.border.subtle`: `color.base.slate.150`
- `color.action.primary`: `color.base.blue.700`
- `color.action.primary.hover`: `color.base.blue.800`
- `color.focus`: `color.base.orange.600`

Use blue for actions only. Use orange for focus indicators and small emphasis, not large surfaces.

## Spacing and shape tokens

Use an 8 px base spacing unit.

- `spacing.1`: 4 px
- `spacing.2`: 8 px
- `spacing.3`: 12 px
- `spacing.4`: 16 px
- `spacing.6`: 24 px
- `spacing.8`: 32 px
- `spacing.12`: 48 px
- `spacing.16`: 64 px
- `spacing.24`: 96 px
- `spacing.32`: 128 px
- `radius.sm`: 6 px
- `radius.md`: 12 px
- `radius.pill`: 999 px
- `border.default`: 1 px
- `focus.ring`: 3 px with 3 px offset

Avoid heavy shadows. Use borders and background contrast for grouping.

## Page structure

Launch uses one route, `/`, with this order:

1. Header
2. Hero
3. Selected work
4. Experience
5. Skills
6. About and contact
7. Footer

No blog navigation until a real post exists.

## Desktop composition

Design at 1440 px wide with a 1120 px content container.

### Header

- 72 px minimum height.
- Wordmark: `Michael Pantoja`.
- Anchor links: Work, Experience, Skills, About.
- Text contact action: `Discuss a role`.
- No hamburger menu at desktop width.

### Hero

- Two-column grid, approximately 7/5.
- Left: eyebrow, display heading, supporting copy, primary and secondary actions.
- Right: compact profile panel with clearance, experience, current focus, and location availability only if approved.
- Minimum 120 px top and bottom padding.
- No portrait or decorative illustration.

### Selected work

- Three stacked case-study cards.
- Each card includes problem, contribution, result, technologies, and public-link state.
- Use horizontal composition at desktop width: title and context left, evidence right.
- Clearly label employer work as private when no public link exists.

### Experience

- Vertical list with date column and content column.
- Organization, role, dates, and three to five strongest bullets per entry.
- No decorative timeline line needed.

### Skills

- Grouped text lists in a three-column grid.
- Avoid dozens of pill badges; grouped lists scan faster and carry less visual noise.

### About and contact

- Short biography on left.
- Contact panel on right with primary email action and LinkedIn/GitHub links.
- Repeat primary contact action once.

### Footer

- Name, role, current year, and professional links.
- Keep under 120 px tall.

## Mobile composition

Design at 390 px wide with 20 px page gutters.

- Header uses wordmark plus a visible `Contact` link. Do not hide primary navigation behind JavaScript.
- Optional section links wrap below the header or are omitted if they crowd the first screen.
- Hero becomes one column. Primary action is full width; secondary action remains text-first.
- Case studies, experience rows, skill groups, and contact panel become single-column stacks.
- Dates sit above role headings.
- Use 72 px section spacing and 40 px card padding reduced to 24 px on narrow screens.
- No horizontal scrolling at 320 px or wider.

## Components and states

UI building blocks, named the same in code and in any future Penpot components:

- `navigation/link/default`
- `navigation/link/active`
- `button/primary/default`
- `button/primary/hover`
- `button/primary/focus`
- `button/secondary/default`
- `button/secondary/hover`
- `button/secondary/focus`
- `case-study/card`
- `experience/entry`
- `skills/group`
- `contact/panel`

Interactive elements need default, hover, and keyboard-focus states. Focus uses the orange token and must not depend on color alone.

## Penpot file

Source design: Penpot file **mpanfolio Portfolio** (project “New Project 1”, Personal Projects team on design.penpot.app). The design is the visual reference for implementation; this document is the reference for tokens and rules.

### `01 Foundations`

Board `foundations/overview`:

- Color swatches for every global color token
- Type samples: display, section heading, body, technical label
- Primary and secondary button defaults
- Case-study card sample

The token set `mpanfolio/global` holds the color, spacing, and radius tokens.

### `02 Portfolio`

Boards arranged left to right:

1. `portfolio/home/desktop-1440` (1440 × 2840)
2. `portfolio/home/mobile-390` (390 × 3840)

Known limits of the current file:

- Boards use absolute positioning, not flex layout. Build the page with CSS flex/grid from the spacing rules above, not from absolute coordinates.
- Hover and focus states are not drawn. Implement them from the color and focus tokens.
- No reusable Penpot components exist yet. Create them only if the design is iterated in Penpot again.

## Accessibility acceptance

- Text and controls meet WCAG AA contrast.
- Keyboard focus is visible on every link and button.
- Heading order is one `h1`, then logical `h2` and `h3` levels.
- Tap targets are at least 44 × 44 px.
- Body text remains readable at 200% zoom.
- Content order remains meaningful without layout or color.
- No required motion.
