# Prioritized Fix List
## The Reality Check — Post-Panel

---

## P0 — Launch Blockers
*Do not deploy until these are resolved.*

---

### P0-1: Contact form doesn't submit anywhere
**Issue:** The form uses `preventDefault` with no backend. Submissions vanish. No email, no notification, no record.
**Fix:** Connect to Formspree (free, 10 minutes) or Netlify Forms. At minimum, replace the form with a `mailto:` link as a temporary bridge.
**Who flagged it:** Marcus, Ankit, Meera, Rahul

---

### P0-2: Primary CTA ("Get a Reality Check") promises a tool that doesn't exist
**Issue:** The free Reality Check tool — the primary offer, repeated 4 times — links to a static 5-step description. The hero says "In one sitting. Without needing to calm down first." The page delivers a read-only list.
**Fix (Option A):** Build a minimal interactive version — even a simple multi-step form with the JYN worksheet questions and Four Questions.
**Fix (Option B):** Change the CTA to "See how it works" or "Download the process" and offer a PDF. Change the hero promise to match what currently exists.
**Fix (Option C):** Add a "Join the waitlist" state that captures emails until the tool is ready.
**Who flagged it:** Ankit, Meera, Rahul

---

### P0-3: No photo of Henna
**Issue:** The About section has a large grey placeholder box as its dominant visual. It signals the founder isn't ready to stand behind the product yet.
**Fix:** Add a real photo. Any genuine photo is better than the placeholder. It doesn't need to be a professional shoot.
**Who flagged it:** Shreya, Marcus, Meera, Rahul

---

### P0-4: Placeholder testimonials are live
**Issue:** Three testimonials with `[Name], [City]` are visible to all visitors. Fake-looking social proof is worse than no social proof.
**Fix (Option A):** Replace with real testimonials from anyone who has experienced the process with Henna — even informal feedback from a friend or beta user.
**Fix (Option B):** Remove the testimonials section entirely until real ones exist. Add a simple "Be among the first" placeholder instead.
**Who flagged it:** Ankit, Meera, Rahul

---

## P1 — Important
*Fix before significant traffic or promotion.*

---

### P1-1: No pricing for paid session
**Issue:** "Book a Session" with no price creates ambiguity that kills intent. Visitors don't ask — they leave.
**Fix:** Add session price to the service card and/or the contact section. Even a range ("Sessions from $X") reduces friction.
**Who flagged it:** Ankit, Meera, Rahul

---

### P1-2: About section needs one specific personal story
**Issue:** The About copy is competent but impersonal. It lists credentials and traditions rather than showing the moment Henna's life actually changed. Visitors can't connect with a resume.
**Fix:** Write one specific, concrete story — a real moment, a real trigger, what happened when she questioned it. Two paragraphs maximum. This is the trust-builder the section currently lacks.
**Who flagged it:** Shreya, Meera, Rahul

---

### P1-3: Credential tags need context or removal
**Issue:** "Advaita Vedanta," "Guru Granth Sahib," "NVC" as pill tags alienate visitors unfamiliar with these traditions and don't convince visitors who are. They read as a spiritual résumé.
**Fix:** Either remove the tags and weave these traditions naturally into the story copy, or add a one-line tooltip/description so visitors who don't know these terms can orient themselves.
**Who flagged it:** Shreya, Meera

---

### P1-4: SVG logo viewBox mismatched to rendered size
**Issue:** The logo SVG viewBox is `0 0 360 88` but the element renders at `height="40"`. The "Reality Check" wordmark was designed at 28pt within an 88px space — at 40px rendered height it scales to ~12.7pt, likely too small and potentially clipped.
**Fix:** Either trim the viewBox to match actual content bounds (removing dead space left of the mark and right of the wordmark), or set an explicit `width` attribute to match the intended display size.
**Who flagged it:** Marcus

---

### P1-5: No booking path for paid session
**Issue:** "Book a Session →" links to the contact form. The contact form doesn't work (see P0-1). Even after fixing P0-1, a general contact form is a high-friction path to a paid transaction.
**Fix:** After fixing the form, add a Calendly embed or booking link specifically for sessions. Alternatively, gate the session booking with a short "tell me what you're working on" form that feeds directly into a scheduling flow.
**Who flagged it:** Ankit, Meera

---

### P1-6: Missing "no prior experience needed" statement
**Issue:** Visitors unfamiliar with Byron Katie or The Work don't know if this site is for them or requires background knowledge.
**Fix:** Add one line near the hero or at the top of the How It Works section: "No prior experience with The Work needed. You just need a thought that won't let you go."
**Who flagged it:** Meera

---

### P1-7: Before/after table needs horizontal scroll on mobile
**Issue:** At <640px, the table has no `overflow-x: auto` wrapper. Both columns compress and text wraps mid-phrase, breaking the parallel structure that makes the table work.
**Fix:** Wrap the table in a `div` with `overflow-x: auto`.
**Who flagged it:** Marcus

---

## P2 — Nice to Have
*Polish for after launch.*

---

### P2-1: Footer uses old text logo instead of SVG
**Issue:** The nav uses the inline SVG logo. The footer uses the old `<span>RealityCheck</span>` text treatment. Inconsistent.
**Fix:** Replace the footer logo with either the inline SVG (scaled down) or a consistent typographic treatment.
**Who flagged it:** Marcus

---

### P2-2: About accent box clips on tablet breakpoint
**Issue:** At ~960px, the green pull-quote box positioned at `bottom: -1.5rem; right: -1.5rem` may overflow the container when the grid collapses to single column.
**Fix:** Add `overflow: hidden` to `.about__visual` or adjust positioning at the 960px breakpoint.
**Who flagged it:** Marcus

---

### P2-3: Add a favicon
**Issue:** Browser tab shows a blank icon.
**Fix:** Create a 32×32 favicon using the circle+checkmark mark from Logo V1. Add `<link rel="icon">` to the `<head>`.
**Who flagged it:** Marcus

---

### P2-4: Add a "This is for you if…" statement
**Issue:** Cold traffic visitors don't self-select easily. The site implies a target audience but never names her.
**Fix:** Add 2–3 bullet points near the hero or services section: "This is for you if you keep having the same argument / can't stop replaying a situation / feel like someone else needs to change before you can feel better."
**Who flagged it:** Ankit, Meera

---

### P2-5: Remove duplicate smooth-scroll behavior
**Issue:** Both `scroll-behavior: smooth` in CSS and `window.scrollTo({ behavior: 'smooth' })` in JS are active. The JS preventDefault correctly owns anchor click behavior — the CSS declaration is redundant.
**Fix:** Remove `scroll-behavior: smooth` from the `html` rule in styles.css.
**Who flagged it:** Marcus

---

### P2-6: Add session length to paid service card
**Issue:** Visitors don't know how long a session is, which affects both scheduling and perceived value.
**Fix:** Add "60-minute session" (or whatever the actual length is) to the service card description or badge.
**Who flagged it:** Meera

---

## Summary by Priority

| # | Issue | Priority | Effort |
|---|---|---|---|
| P0-1 | Form doesn't submit | P0 | Low (Formspree) |
| P0-2 | Free tool doesn't exist | P0 | High or reframe CTA |
| P0-3 | No photo of Henna | P0 | Low (just add photo) |
| P0-4 | Placeholder testimonials | P0 | Low (remove or replace) |
| P1-1 | No pricing | P1 | Low |
| P1-2 | About needs personal story | P1 | Medium (writing) |
| P1-3 | Credential tags | P1 | Low |
| P1-4 | SVG logo viewBox | P1 | Low |
| P1-5 | No booking path | P1 | Medium |
| P1-6 | "No prior experience needed" line | P1 | Low |
| P1-7 | Table mobile overflow | P1 | Low |
| P2-1 | Footer logo inconsistency | P2 | Low |
| P2-2 | Accent box clip on tablet | P2 | Low |
| P2-3 | Favicon missing | P2 | Low |
| P2-4 | "This is for you if…" section | P2 | Low |
| P2-5 | Duplicate smooth scroll | P2 | Low |
| P2-6 | Session length in card | P2 | Low |

---

*The P0 issues are real launch blockers. The good news: three of the four (form, photo, testimonials) are low-effort and entirely within Henna's control this week. P0-2 (the tool) is the strategic question that shapes everything else.*
