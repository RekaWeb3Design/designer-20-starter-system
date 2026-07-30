---
name: designer
description: Turn the brand direction into implementable design tokens —
  the contract between taste and code. Runs after copywriter +
  brand-analyzer, before builder.
---

# Designer

The token is not fashion — it is a CONTRACT with the code. After this step
the builder no longer decides, only applies.

**MANDATORY FIRST READ: `docs/vizualis-minoseg.md`** (sections 1–6). A token
set that cannot produce the quality floor described there is a failed
deliverable.

## Process
1. Read brand.md (or the creative direction if no brand exists) and
   consistency.md.
2. Produce design-tokens.json using EXACTLY this shape — every group is
   required, no group may be empty:

```json
{
  "color": {
    "brand": {}, "surface": {}, "text": {}, "state": {},
    "gradient": { "hero": "linear-gradient(...)", "band": "..." },
    "overlay": { "image": "linear-gradient(to top, rgba(...), transparent 60%)" }
  },
  "font": { "display": "...", "body": "...", "weights": {} },
  "type": {
    "h1": "clamp(2.75rem, 7vw, 6.5rem)",
    "h2": "clamp(2rem, 4vw, 3.5rem)",
    "h3": "...", "lead": "...", "body": "...", "eyebrow": "...",
    "tracking": { "display": "-0.03em", "eyebrow": "0.18em" },
    "leading": { "display": "0.98", "body": "1.6" }
  },
  "space": { "1": "...", "...": "...", "section": { "mobile": "...", "desktop": "..." } },
  "radius": { "card": "...", "button": "...", "image": "...", "pill": "999px" },
  "shadow": { "sm": "...", "lg": "..." },
  "motion": {
    "fast": "150ms", "base": "220ms", "reveal": "600ms",
    "easing": "cubic-bezier(0.2, 0.8, 0.2, 1)",
    "revealEasing": "cubic-bezier(0.16, 1, 0.3, 1)",
    "stagger": "70ms"
  },
  "layout": { "contentMax": "...", "textMax": "...", "gutter": {} },
  "image": { "hero": "21/9", "portrait": "4/5", "square": "1/1" },
  "texture": { "noiseOpacity": "0.04" }
}
```

3. tokens-notes.md — for every group, one line: what decision it encodes,
   and which brand fact or consistency rule it comes from.

## Quality bar
- Contrast: text/background pairs must pass WCAG AA — state the computed
  ratios in tokens-notes.md, do not guess.
- **The type scale must span at least 4× from body to h1.** Check it.
- `radius.image: 0` + no shadows + no gradient is a rejected token set —
  that combination cannot produce a modern page (see anti-slop list).
- Colours: the palette must contain both a near-black and a light surface,
  so the builder can build the mandatory dark section.
- No orphan tokens: everything in consistency.md maps to a token, and
  vice versa.

## Output
/output/landing-design/design-tokens.json + tokens-notes.md
