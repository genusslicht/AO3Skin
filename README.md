# AO3Skin

Skin for AO3. Fully themable through variables.

## Features

- Slim Header that stays with you when you scoll (Except when you're in the middle of a reading session!)
- Sticky Dashboard navigation (Desktop only) and Filters
- Custom icons for required tag
- Individual tag category colors
- Styled statistics graph
- Customizable through CSS variables

## Installation / Setup (AO3 Skin editor)

1. Create parent skin with basic styling
   - Name: `<your-username> My Skin (screen)`
   - Paste the [screen CSS](AO3Skin-screen.css)
   - Check: "Parent skin only"
   - Choose media: `screen`
2. Create parent skin for tablet
   - Name: `<your-username> My Skin (tablet)`
   - Paste the [tablet CSS](AO3Skin-tablet.css)
   - Check: "Parent skin only"
   - Add the previously created screen skin as parent
   - Choose media: `only screen and (max-width: 62em)` and `only screen and (max-width: 42em)`
3. Create parent skin for mobile
   - Name: `<your-username> My Skin (mobile)`
   - Paste the [mobile CSS](AO3Skin-mobile.css)
   - Check: "Parent skin only"
   - Add the previously created tablet skin as parent
   - Choose media: `only screen and (max-width: 42em)`
4. (optional) Create light / dark mode skin
   - Name: `<your-username> My Skin (light / dark)` (choose the one that isn't your default mode)
   - Paste the light or dark theme skin of your choice
   - Choose media: `(prefers-color-scheme: light / dark)`
5. Create the master skin
   - Name: `<your-username> My Skin`
   - Paste the theme css you want to use (different to step 4.!)
   - Add the previously created skin in the same order as parent skins
   - optional: add light / dark mode skin
   - Choose media: `screen` (or if you choose to do step 4., pick the other one of `(prefers-color-scheme: light / dark)` option now!)
6. Save and hit "Use" :)

## Variables

Reference table of all CSS custom properties used by the skin and their intended uses. You usually don't need to change any of those.

| Variable                | Use / purpose                                                                                           |
| ----------------------- | ------------------------------------------------------------------------------------------------------- |
| `--color-dark-rgba070`  | Modal/dialog background overlay color (semi‑transparent overlay).                                       |
| `--color-dark-rbga025`  | Reusable dark color at 25% alpha used for shadows and subtle overlays.                                  |
| `--color-dark-rbga010`  | Reusable dark color at 10% alpha for very subtle overlays.                                              |
| `--offset-x`            | X offset for shadow calculations.                                                                       |
| `--offset-y`            | Y offset for drop shadows.                                                                              |
| `--inset-y`             | Y offset (negative) for reverse/inset shadows.                                                          |
| `--blur-radius`         | Blur radius for shadows.                                                                                |
| `--shadow`              | Convenience shadow shorthand (drop shadow).                                                             |
| `--shadow-inset`        | Convenience inset shadow shorthand.                                                                     |
| `--comment-img-size`    | Fixed size used for comment avatar / image elements (default 50px / 45px for tablet / 40px for mobile). |
| `--border-radius`       | Corner radius applied across UI elements.                                                               |
| `--tag-border-radius`   | Corner radius applied to tags elements.                                                                 |
| `--earmark-corner-size` | Corner size for colored "earmark" on rated fics in list view. Set to `0` to disable.                    |

### Theme Colors

All colors used for creating your own color theme.

| Variable                    | Use / purpose                                                                            |
| --------------------------- | ---------------------------------------------------------------------------------------- |
| `--bg-base`                 | Page background seen in header, dashboard, footer.                                       |
| `--bg-highlight`            | Highlight color — form input elements, odd fav tag rows, header underlines, some borders |
| `--bg-primary`              | Main background.                                                                         |
| `--bg-secondary`            | Background for content boxes.                                                            |
| `--bg-tertiary`             | Background for nested content boxes (inner panels).                                      |
| `--text-highlight`          | Highlight color for interactive text (links, buttons, some dropdown rows).               |
| `--text-primary`            | Primary text color for general content.                                                  |
| `--color-red`               | Semantic red (errors, excluded filters).                                                 |
| `--color-orange`            | Semantic orange (caution notices).                                                       |
| `--color-yellow`            | Semantic yellow (informational notices).                                                 |
| `--color-green`             | Semantic green (included filters, success accents).                                      |
| `--color-purple`            | Semantic purple (alerts, flashes).                                                       |
| `--color-blue`              | Semantic blue.                                                                           |
| `--color-link-action-hover` | Hover/focus color for interactable links and actions.                                    |
| `--color-selection`         | Accent used for current selection.                                                       |
| `--element-bg`              | Background for invalid notice panels and help elements.                                  |
| `--color-fg-question`       | Foreground color for help questions/labels.                                              |

### Tag Colors

| Variable                 | Use / Default                                  |
| ------------------------ | ---------------------------------------------- |
| `--color-fandom-tags`    | `--color-selection`                            |
| `--color-mature-tags`    | `--color-red`                                  |
| `--color-warning-tags`   | `--color-orange`                               |
| `--color-platonic-tags`  | & Relationships. Default: `--color-yellow`     |
| `--color-explicit-tags`  | Slash relationships. Default: `--color-purple` |
| `--color-character-tags` | `--color-green`                                |
| `--color-freeform-tags`  | `--color-blue`                                 |

### Rating Colors

Colors are used for tags in reading view and earmarks in list view.

| Variable                  | Default          |
| ------------------------- | ---------------- |
| `--color-explicit-rating` | `--color-purple` |
| `--color-mature-rating`   | `--color-red`    |
| `--color-teen-rating`     | `--color-yellow` |
| `--color-gen-rating`      | `--color-green`  |

### Notice Box Colors

| Variable              | Use / Default                                        |
| --------------------- | ---------------------------------------------------- |
| `--color-notice`      | General notice box. Default: `--color-yellow`        |
| `--color-caution`     | Warnings / Reqired. Default: `--color-yellow`        |
| `--color-error`       | Errors. Default: `--color-yellow`                    |
| `--color-alert-flash` | Whatever that is. Default: `--color-yellow`          |
| `--color-collection`  | Collection page banner. Default: `--color-selection` |

### Stat Chart Colors

Any value not defined, will use its default AO3 value. Use This site: https://codepen.io/sosuke/full/Pjoqqp to calculate any color you want.

> [!IMPORTANT]
> Make sure to set `brightness(0)` as the very first value in the calculatd filter chain for optimal results.

See: [My Github Gist](https://gist.github.com/genusslicht/9910dfeb496f20dacac42945b9b17ff7) for details.

| Variable                      | Use / purpose                                                                                                                 |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `--filter-chart-bg`           | Filter applied to chart background images (suggestion: `opacity(0)` to hide).                                                 |
| `--filter-chart-text`         | Image filter used to render chart text/icons so they contrast on theme backgrounds. (suggestion: `--primary-text` equivalent) |
| `--filter-chart-tooltip`      | Filter used for chart tooltips. (suggestion: `--bg-highlight` equivalent)                                                     |
| `--filter-chart-accent`       | Accent filter used for chart bars. (suggestion: `--color-selection` equivalent)                                               |
| `--filter-chart-accent-hover` | Accent filter variant for hover state on chart bars. (suggestion: `--color-link-action-hover`)                                |
| `--filter-chart-guide-even`   | Filter for even guide lines in chart. (suggestion: ignore, or `opacity(0.2)` for dark, a higher `0.x` for light theme)        |
| `--filter-chart-guide-odd`    | Filter for odd guide lines in chart. (suggestion: ignore, or `opacity(0.1)` for dark, a higher `0.x` for light theme)         |

### Custom Required Icon Colors

`--filter-icons` - Define a filter chain to tint replaced icons a little closer to used theme colors. Play around with it in the Browser dev tools. `brightness`, `contrast` and `saturate` are your friends.
