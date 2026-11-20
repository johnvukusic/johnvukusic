# DESIGN.md

A starter template for describing a design system in a form that AI tools can read.
Put this file at the root of a project. Point your design or coding assistant at it
before asking for any interface work. Replace every placeholder value with your own.

## 1. Purpose

One paragraph: what the product is, who uses it, and what the interface must feel like.

> Example: An operations tool for finance teams. Dense, calm and exact. Numbers come
> first. Nothing decorative.

## 2. Tokens

Tokens are the only allowed source for color, type, spacing and shape. Never use a raw
value when a token exists.

### Color

| Token | Value | Use |
| --- | --- | --- |
| `color.brand` | `#0000FF` | Primary actions, links, focus |
| `color.text` | `#111111` | Body text and headings |
| `color.text.muted` | `#666666` | Secondary text, captions |
| `color.surface` | `#FFFFFF` | Page and card backgrounds |
| `color.border` | `#DDDDDD` | Dividers, input borders |
| `color.positive` | `#007A33` | Success, gains |
| `color.negative` | `#C8102E` | Errors, losses |

### Type

| Token | Value | Use |
| --- | --- | --- |
| `font.body` | `Inter, sans-serif` | All interface text |
| `font.numeric` | `JetBrains Mono, monospace` | Figures in tables and charts |
| `size.body` | `14px / 20px` | Default text |
| `size.heading` | `20px / 28px` | Section headings |
| `weight.regular` / `weight.medium` | `400` / `500` | The only two weights |

### Space and shape

| Token | Value |
| --- | --- |
| `space.1` to `space.6` | `4, 8, 12, 16, 24, 32px` |
| `radius.control` | `8px` |
| `radius.pill` | `100px` |

## 3. Components

List each component with when to use it and when not to. Rules matter more than looks.

### Button

- **Primary:** one per view, for the main action.
- **Secondary:** every other action.
- **Never:** two primary buttons side by side; a button that only navigates (use a link).

### Table

- Numbers right-aligned in `font.numeric`. Text left-aligned.
- Show at most seven columns by default. Extra columns go behind a column picker.
- Every table has an empty state and a loading state.

### Form field

- Label above the field, always visible. No placeholder-only labels.
- Error text sits under the field and says how to fix the problem.

## 4. Composition

Rules for putting components together on a screen.

- One primary action per screen.
- Page structure: title, then summary, then detail. Never detail first.
- Use `space.5` between sections and `space.3` inside them.
- Destructive actions ask for confirmation and say what will be lost.

## 5. Accessibility

- Text contrast of at least 4.5:1 against its background.
- Every interactive element reachable and usable by keyboard, with a visible focus ring.
- No meaning carried by color alone.
- Touch targets at least 44 by 44 pixels.

## 6. Review checklist

Check generated work at four levels, in this order. Fix the lowest level first.

1. **Token:** are all colors, sizes and spacing taken from section 2?
2. **Pattern:** does each interaction follow an existing pattern, or invent one?
3. **Component:** is each component used as section 3 allows?
4. **Composition:** does the whole screen follow section 4?

Work that passes all four can ship. Work that fails at the token level usually fails
everywhere above it, so start there.
