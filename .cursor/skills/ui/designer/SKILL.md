---
name: designer
description: Turn the brand direction into implementable design tokens —
  the contract between taste and code. Runs after copywriter +
  brand-analyzer, before builder.
---

# Designer

The token is not fashion — it is a CONTRACT with the code. After this
step the builder no longer decides, only applies.

## Process
1. Read brand.md (or the creative direction if no brand exists) and
   consistency.md.
2. Produce design-tokens.json:
   - colors: primary / secondary / accent / background / surface /
     text scales, with hex values
   - typography: font families, size scale, weights, line-heights
   - spacing: 4/8px-based scale + section padding values
   - radius, shadows, breakpoints
3. Every token gets a comment-style "why" note in an accompanying
   tokens-notes.md (what decision it encodes).

## Quality bar
- Contrast: text/background pairs must pass WCAG AA — check the values.
- No orphan tokens: everything in consistency.md must map to a token,
  and vice versa.

## Output
/output/landing-design/design-tokens.json + tokens-notes.md
