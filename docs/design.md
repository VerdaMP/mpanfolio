# mpanfolio Visual Direction

## Design goal

Present Michael Pantoja as a senior engineer who makes complex systems understandable and dependable. The site should feel precise, calm, credible, and human—not corporate, military-themed, or decorative. The palette follows Michael's Omarchy theme, Gilded Graphite: dark graphite surfaces, gold type, and an amethyst accent, for a refined, slightly luxurious tone.

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

Source: Omarchy theme `gilded-graphite` (`~/.config/omarchy/themes/gilded-graphite/colors.toml`). The site is dark-only, matching the theme's `mode = "dark"`.

### Global

| Token | Value | Theme source |
| --- | --- | --- |
| `color.base.graphite.975` | `#100F13` | `darker_background` |
| `color.base.graphite.900` | `#1C1B1F` | `background` |
| `color.base.graphite.800` | `#28262D` | `lighter_background` |
| `color.base.graphite.700` | `#302B38` | `selection` |
| `color.base.graphite.500` | `#5C5566` | `muted` |
| `color.base.gold.100` | `#F5E6B0` | `bright_foreground` |
| `color.base.gold.200` | `#E8C877` | `bright_yellow` |
| `color.base.gold.300` | `#E0C87E` | `foreground` |
| `color.base.gold.400` | `#CDB469` | `light_foreground` |
| `color.base.gold.600` | `#A6936A` | derived; `dark_foreground` (`#8C7B4E`) fails AA for text |
| `color.base.amethyst.400` | `#A488E0` | `accent` |
| `color.base.amethyst.300` | `#C7A3E6` | `bright_magenta` |
| `color.base.orange.500` | `#C8944A` | `orange` |

### Semantic

- `color.bg.default`: `color.base.graphite.900`
- `color.bg.surface`: `color.base.graphite.800`
- `color.bg.inset`: `color.base.graphite.975`
- `color.text.heading`: `color.base.gold.100`
- `color.text.body`: `color.base.gold.400`
- `color.text.muted`: `color.base.gold.600`
- `color.text.label`: `color.base.amethyst.400`
- `color.text.emphasis`: `color.base.amethyst.300`
- `color.text.on-action`: `color.base.graphite.975`
- `color.border.default`: `color.base.graphite.500`
- `color.border.subtle`: `color.base.graphite.700`
- `color.action.primary`: `color.base.amethyst.400`
- `color.action.primary.hover`: `color.base.amethyst.300`
- `color.focus`: `color.base.gold.200`
- `color.status.private`: `color.base.orange.500`

Gold carries reading; amethyst marks actions, labels, and results. Use orange only for the private-work tag.

### Contrast (WCAG 2.x)

| Pair | Ratio |
| --- | --- |
| Heading gold on graphite | 13.7:1 |
| Body gold on graphite / surface | 8.4:1 / 7.4:1 |
| Muted gold on graphite / surface | 5.7:1 / 5.0:1 |
| Amethyst label on graphite / surface | 5.9:1 / 5.1:1 |
| Text on amethyst button | 6.5:1 |
| Focus gold on graphite | 10.6:1 |

Do not use theme `muted` (`#5C5566`, 2.4:1) or `dark_foreground` for text.

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

Launch uses two routes.

`/` (home), in this order:

1. Header
2. Hero
3. Selected work
4. Experience
5. Skills
6. Contact
7. Footer

`/about` (professional biography), in this order:

1. Header, with About marked active
2. Intro and at-a-glance panel
3. My path
4. How I work
5. Beyond the day job
6. Call to action
7. Footer

No blog navigation until a real post exists.

## Desktop composition

Design at 1440 px wide with a 1120 px content container.

### Header

- 72 px minimum height.
- Wordmark: `Michael Pantoja`, linking to `/`.
- Links: Work, Experience, and Skills jump to sections on `/` (`/#work`, `/#experience`, `/#skills`). They act as the page's table of contents. About routes to `/about`.
- The current page's link uses heading gold, weight 600, and a 2 px amethyst underline.
- Contact action: `Discuss a role` primary button.
- No hamburger menu at desktop width.

### Hero

- Two-column grid, approximately 7/5.
- Left: eyebrow, display heading, supporting copy, and one primary action. No secondary "view experience" action; the header already links to every section.
- Right: compact profile panel with experience, current focus, stack, and location.
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

### Contact

- One-line prompt with the primary `Discuss a role` action.
- The longer biography lives on `/about`.

### About page

- Intro: `ABOUT` eyebrow, display heading, lead paragraph on the left; at-a-glance panel on the right (location, experience, education, current focus).
- My path: section title on the left; career narrative paragraphs on the right.
- How I work: three principle cards in a row.
- Beyond the day job: interest rows with a title column and a description column, separated by dividers.
- Call to action: inset panel with prompt, Email · LinkedIn · GitHub links, and the `Discuss a role` button.

### Footer

- Name, role, current year, and professional links.
- Keep under 120 px tall.

## Mobile composition

Design at 390 px wide with 20 px page gutters.

- Header uses the wordmark plus visible `About` and `Contact` links. Do not hide primary navigation behind JavaScript.
- Section links (Work, Experience, Skills) are omitted on mobile; the page is short enough to scroll.
- Hero becomes one column with a full-width primary action.
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
- `case-study/card`
- `experience/entry`
- `skills/group`
- `contact/panel`

Button labels are centered horizontally and vertically within the button.

Interactive elements need default, hover, and keyboard-focus states. Focus uses the `color.focus` gold ring and must not depend on color alone.

## Penpot file

Source design: Penpot file **mpanfolio Portfolio** (project “New Project 1”, Personal Projects team on design.penpot.app). The design is the visual reference for implementation; this document is the reference for tokens and rules.

### `01 Foundations`

Board `foundations/overview`:

- Color swatches for every global color token
- Type samples: display, section heading, body, technical label
- Primary button default
- Case-study card sample

The token set `mpanfolio/global` holds the color, spacing, and radius tokens.

### `02 Portfolio`

Boards arranged left to right:

1. `portfolio/home/desktop-1440` (1440 × 2840)
2. `portfolio/home/mobile-390` (390 × 3840)

### `03 About`

1. `about/desktop-1440` (1440 × 2711)
2. `about/mobile-390` (390 × 3800)

Known limits of the current file:

- Boards use absolute positioning, not flex layout. Build the page with CSS flex/grid from the spacing rules above, not from absolute coordinates.
- Hover and focus states are not drawn. Implement them from the color and focus tokens.
- No reusable Penpot components exist yet. Create them only if the design is iterated in Penpot again.
- Navigation is not wired as a Penpot prototype; Penpot prototype links cannot cross pages. Routes are defined above.

## Accessibility acceptance

- Text and controls meet WCAG AA contrast.
- Keyboard focus is visible on every link and button.
- Heading order is one `h1`, then logical `h2` and `h3` levels.
- Tap targets are at least 44 × 44 px.
- Body text remains readable at 200% zoom.
- Content order remains meaningful without layout or color.
- No required motion.
