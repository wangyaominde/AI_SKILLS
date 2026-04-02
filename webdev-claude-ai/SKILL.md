---
name: webdev
description: "Comprehensive frontend design quality skill — creates distinctive, production-grade UIs and iteratively improves them. Merges 20 design operations (audit, polish, animate, typeset, colorize, arrange, adapt, harden, etc.) into one unified workflow. Use when building, reviewing, improving, or polishing any frontend: websites, dashboards, components, landing pages, React apps, HTML/CSS. Also triggers on: responsive design, accessibility, animation, typography, color, layout, UX review, performance, design system alignment, onboarding flows, error handling, i18n, or any request to make UI look less AI-generated. Even if the user just says 'make it look better' or 'polish this', use this skill."
---

# WebDev — Frontend Design Quality Skill

One skill, 5 modes, 12 enhance sub-modes. Every frontend task flows through: **Create → Audit → Enhance → Polish → Ship**.

## Mode Selection

| User Intent | Mode |
|---|---|
| build / create / make / design | **CREATE** |
| audit / check / review / score | **AUDIT** |
| animate / motion / hover / transition | **ENHANCE:animate** |
| color / palette / theme / dark mode | **ENHANCE:colorize** |
| font / type / heading / text size | **ENHANCE:typeset** |
| layout / spacing / grid / rhythm | **ENHANCE:arrange** |
| responsive / mobile / breakpoint | **ENHANCE:adapt** |
| bold / amplify / punch / stronger | **ENHANCE:bolder** |
| softer / calmer / quieter / tone down | **ENHANCE:quieter** |
| delight / joy / playful / surprise | **ENHANCE:delight** |
| onboard / empty state / first-run | **ENHANCE:onboard** |
| copy / wording / label / UX writing | **ENHANCE:clarify** |
| error / i18n / edge case / harden | **ENHANCE:harden** |
| performance / speed / bundle / lazy | **ENHANCE:optimize** |
| extract / component / token / reuse | **ENHANCE:extract** |
| consistency / design system / drift | **ENHANCE:normalize** |
| wow / shader / physics / 3D / ambitious | **ENHANCE:overdrive** |
| polish / final / ship / cleanup | **POLISH** |
| simplify / strip / minimal / essential | **DISTILL** |
| critique / UX / heuristic / persona | **CRITIQUE** |

Ambiguous → **CREATE** for new, **AUDIT** for existing.

---

## CREATE Mode

Before code, commit to a **bold aesthetic direction**:

1. **Purpose** — Problem? Audience? Context?
2. **Tone** — Pick ONE: brutally minimal / maximalist / retro-futuristic / organic / luxury / playful / editorial / brutalist / art-deco / pastel / industrial / neo-Memphis / Swiss-modernist / cyberpunk
3. **Signature** — The ONE unforgettable thing
4. **Constraints** — Framework, a11y, performance budget

### Typography Rules
- **BANNED as primary**: Inter, Roboto, Arial, Poppins, Montserrat, Open Sans, system-ui
- **DO**: Distinctive display + refined body pairing. Vertical rhythm on 4/8px grid. Fluid `clamp()` sizing. `font-display: swap` + `size-adjust` fallback.
- **Display picks**: Fraunces, Clash Display, Cormorant Garamond, Space Mono, Cabinet Grotesk, Newsreader
- **Body picks**: DM Sans, Source Sans 3, Literata, Plus Jakarta Sans, Outfit
- **Scale**: Use modular ratio (1.2–1.333). Min 3 weights. Max line width 45-75ch.

### Color Rules
- **BANNED**: Purple-blue gradient hero on white. Pure grays. Rainbow dashboards. Pure #000 on #fff.
- **DO**: ONE dominant hue → 9-step OKLCH lightness scale. ONE accent (120°–150° offset). Tinted neutrals (add 2-5% primary chroma to grays). CSS custom properties for full palette + dark mode. WCAG AA: 4.5:1 body, 3:1 large text.

```css
/* Tinted neutral example */
--neutral-100: oklch(96% 0.01 250);
--neutral-500: oklch(55% 0.02 250);
--neutral-900: oklch(12% 0.01 250);
```

### Motion Rules
- **BANNED**: All elements animate simultaneously. Linear easing. Infinite pulsing. Bounce on forms.
- **DO**: ONE orchestrated page-load with stagger (80-150ms gap, max 5 items). Hover/focus surprises. CSS-only for HTML, Framer Motion for React.
- **Duration**: micro 150-300ms, transition 300-500ms, page 500-800ms
- **Easing**: `cubic-bezier(0.16, 1, 0.3, 1)` for enter, `cubic-bezier(0.55, 0, 1, 0.45)` for exit
- **ALWAYS** include `prefers-reduced-motion: reduce` media query.

### Layout Rules
- **BANNED**: 3 identical cards ("AI triptych"). Uniform padding everywhere. Cards in cards in cards. Fixed px widths.
- **DO**: Asymmetric grids, intentional overlap, grid-breaking heroes. 8px spacing scale with CSS properties. `min()` / `clamp()` for responsive containers. Touch targets ≥44px.

### Visual Details Rules
- **BANNED**: Flat white/gray backgrounds. Random drop shadows. Glassmorphism without function.
- **DO**: Atmosphere via gradient meshes, noise, geometric patterns, layered transparencies. Custom cursors, grain overlays, decorative borders — IF they serve the aesthetic.

---

## AUDIT Mode

Score 5 dimensions (1-10):

1. **Visual Hierarchy** — Primary action identifiable in <2s?
2. **Consistency** — Spacing/colors/type follow a system?
3. **Accessibility** — Contrast, focus, keyboard, screen reader?
4. **Responsiveness** — Works at 320/768/1024/1440px?
5. **Performance** — No CLS, fast LCP, optimized assets?

Each issue gets severity: **P0** (blocks function/a11y) → **P1** (UX degradation) → **P2** (noticeable) → **P3** (polish).

Output: structured action plan sorted by severity.

---

## ENHANCE Sub-Modes (Quick Reference)

**animate**: Add staggered entrance, hover states, scroll reveals. Duration scale: 150/300/500ms. Always `prefers-reduced-motion`.

**colorize**: Build OKLCH palette from one hue. Tinted neutrals. Dark mode variant. Verify contrast.

**typeset**: Replace banned fonts. Apply modular scale. Set line-height to grid. Fluid `clamp()`. Preload critical fonts.

**arrange**: Fix spacing to 8px scale. Break symmetric grids. Add asymmetry/overlap. Test all breakpoints.

**adapt**: Mobile-first breakpoints (640/768/1024/1280). Fluid containers via `min()`. Stack→grid pattern. Touch targets 44px+.

**bolder**: Increase contrast ratios, type scale jumps, color saturation, whitespace. Make the design have an opinion.

**quieter**: Reduce saturation, animation intensity, shadow depth, type scale contrast. Elegant restraint.

**delight**: Add one surprise: custom cursor, easter egg hover, playful loading state, satisfying micro-interaction on key action.

**onboard**: Design empty states as onboarding. Show dimmed preview of filled state + ONE clear CTA. Never blank white pages.

**clarify**: Labels = what it IS ("Email" not "Enter email"). Buttons = specific verbs ("Save draft" not "Submit"). Errors = what happened + how to fix. Max 1 exclamation per page.

**harden**: 4 states per async op (empty/loading/success/error). Skeleton loaders not spinners. Text overflow with `line-clamp`. Logical properties for RTL. 30% text expansion tolerance. Double-click prevention. Keyboard nav.

**optimize**: Target LCP <2.5s, CLS <0.1. WebP/AVIF images with dimensions. Lazy load below-fold. Preload hero + critical fonts. CSS `contain` on complex components. Animate only `transform`/`opacity`. Max 2 font families, 3-4 weights.

**extract**: Identify repeated patterns → create reusable components. Pull colors/spacing/radii into CSS custom properties as design tokens.

**normalize**: Align to design system. Unified spacing scale, color tokens, border-radius scale, shadow elevation system, icon sizing.

**overdrive**: Shaders, spring physics, scroll-driven animations, 3D transforms, particle effects, SVG morphing. GPU-composited, 60fps target, graceful fallback.

---

## POLISH Mode (Pre-Ship Checklist)

- [ ] Alignment: every element on grid, no 1px drift
- [ ] Spacing: all from scale, no magic numbers
- [ ] Typography: all from type scale, no orphans in key copy
- [ ] Colors: all from CSS custom properties, no hardcoded hex
- [ ] States: hover/focus/active/disabled + focus-visible
- [ ] Transitions: all state changes animated 150-300ms ease-out
- [ ] Icons: consistent size, stroke, style
- [ ] Borders: consistent radius scale
- [ ] Shadows: one coherent elevation system
- [ ] Dark mode: fully tested, no contrast failures
- [ ] Responsive: no horizontal scroll, touch targets ≥44px
- [ ] Loading: skeleton for async, no layout shift

---

## DISTILL Mode

1. List every visual element + its purpose
2. Remove decorative-only elements that don't reinforce message
3. Merge similar components (3 variants → 1 with props)
4. Reduce palette to minimum effective set
5. Keep only 2-3 strongest animations
6. Result feels "inevitable" — nothing to add or remove

---

## CRITIQUE Mode

1. **Nielsen's 10** — Score 1-5 each, flag violations
2. **Persona Walk** — Power user, first-timer, accessibility-dependent
3. **Cognitive Load** — Decisions per screen (flag >3 competing CTAs)
4. **IA** — Content hierarchy logical? Users find what they need?
5. **Emotion** — Does design evoke intended feeling?

Output: prioritized issues + specific fix recommendations.

---

## Universal Anti-Patterns (NEVER Generate)

**Typography**: Inter/Roboto/Arial only · single weight · 1-2 sizes · default line-height
**Color**: purple-blue gradient hero · pure grays · rainbow palette · failing WCAG
**Layout**: 3 identical cards · cards in cards · perfect symmetry · uniform padding · everything centered
**Component**: giant stat number + tiny label + glow · purposeless glassmorphism · border-radius:9999px everywhere · gradient on buttons hurting readability
**Motion**: simultaneous load animations · linear easing · bounce on forms · infinite pulse on non-critical elements

---

## Implementation Defaults

- CSS custom properties for all theming values
- Semantic HTML elements
- `prefers-reduced-motion` + `prefers-color-scheme` media queries
- `clamp()` for fluid typography and spacing
- `focus-visible` on all interactive elements
- Test at: 320, 375, 768, 1024, 1440, 1920px
