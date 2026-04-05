# Marcus Tan — Product Designer
## Independent Review

---

### Verdict: Visually strong. Several structural issues would hurt real users.

---

### What's Working

The type system is solid. Playfair Display + DM Sans is a pairing that communicates exactly what the brand needs — serif warmth anchored by sans precision. The spacing is generous and the hierarchy reads cleanly on desktop. The dark service card is a strong design decision — it differentiates the paid offering without screaming "premium." The before/after table is the most useful UI on the page and is well-executed.

The scroll-reveal animations are subtle enough not to be annoying — the right call for this brand.

---

### Issues — Ranked by Severity

---

#### CRITICAL

**1. The logo SVG is clipped in the nav.**

The SVG viewBox is `0 0 360 88` but the SVG element height is only `40px`. The logo renders at roughly 164×40 — which means the left portion of the viewBox (the circle mark) lands at about 20px visible and the rest of the wordmark is compressed. At 40px height, "Reality Check" in 28pt Playfair Display is going to be unreadably small or visually off. This needs a `width` attribute set explicitly, or the viewBox needs to be trimmed to match actual content bounds.

**2. The "Get a Reality Check" button links to `#how-it-works` — not an actual tool.**

Both primary CTAs ("Get a Reality Check →") land on the How It Works section — a static description of five steps. There is no actual interactive process on this page. The site promises a self-guided tool that "you can do right now" and then delivers a read-only list. That's a broken promise. Either the tool needs to exist, or the CTA needs to say "See how it works" instead of implying you can start immediately.

---

#### HIGH

**3. No actual email address or booking link.**

The contact form fakes submission (JS preventDefault with no backend). There's no mailto link, no Calendly embed, no real path to get in touch. A visitor who fills this out will receive nothing. This is P0 for launch — but architecturally it's a design issue: the form needs to either connect to a real service (Formspree, Netlify Forms, etc.) or be replaced with a direct email CTA until that's set up.

**4. The footer still uses the old text logo (`RealityCheck` span) — not the SVG.**

The nav uses the inline SVG logo. The footer uses `<span class="footer__logo">Reality<span>Check</span></span>`. Inconsistent. The footer should either use the SVG or a consistent typographic treatment.

**5. The photo placeholder is a large empty grey box — first visual impression of Henna.**

`aspect-ratio: 3/4` on a full column width means this empty box is the dominant visual on the About section. On mobile it collapses but on desktop it's ~400px × 533px of nothing. This actively undermines trust. Needs a real photo before launch, or the layout needs to work without one (content-first single column).

---

#### MEDIUM

**6. The `accent-box` quote overlaps the section padding on mobile at 960px.**

`bottom: -1.5rem; right: -1.5rem` positions the accent box outside the visual column. On tablet breakpoint (960px), the grid collapses to 1 column but the box still overflows right — likely clipping or overflowing the container. Needs `overflow: hidden` on the visual container or adjusted positioning at that breakpoint.

**7. No `font-weight: 450` in DM Sans variable font range.**

`font-weight: 450` is used in `.nav__links a`. DM Sans variable font supports 100–700, so 450 *will* render — but only in browsers that support variable font interpolation. It's a minor edge case but worth normalizing to 400 or 500.

**8. The transform table has no horizontal scroll on mobile.**

At <640px, the table is forced into the viewport with smaller padding but no `overflow-x: auto` wrapper. On narrow phones, both columns will compress awkwardly and text will wrap mid-phrase, breaking the parallel structure that makes the table work.

**9. Process section connector line misalignment.**

The `::before` pseudo-element draws a horizontal line at `top: 1.5rem` — which assumes the step circles are exactly 3rem tall at that position. If any padding or margin shifts (especially on non-standard zoom levels), the line detaches from the circles. Low risk but worth testing.

---

#### LOW

**10. `scroll-behavior: smooth` on `<html>` + JS smooth scroll = double-smooth.**

The CSS has `scroll-behavior: smooth` and the JS also calls `window.scrollTo({ behavior: 'smooth' })`. The JS preventDefault correctly handles anchor clicks, but the CSS declaration is now redundant and could cause conflicts in some browsers. Remove the CSS one and let JS own it.

**11. No `lang` attribute on the HTML element.** Actually it's there — good. ✓

**12. Missing `favicon`.** Browser tab shows a blank icon. Five-minute fix.

---

### Mobile Score: 7/10
Layout collapses correctly at both breakpoints. The hamburger menu works. The main structural issues (table overflow, accent box clip) are fixable. What's missing is any test at 375px — the most common iPhone width.

### Desktop Score: 8/10
Solid. The logo rendering issue is the only thing that would make a designer wince.

---

**Overall: 7/10.** Good bones, real problems at the seams.
