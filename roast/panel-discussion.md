# Panel Discussion
## The Reality Check — Expert Review

*All five panelists have submitted their independent reviews. They now discuss.*

---

**Ankit:** I want to lead with the thing that I think everyone danced around but didn't name directly: this site is marketing a product that doesn't exist yet. The free Reality Check tool — the primary CTA, repeated four times — links to a static five-step description. That's not a tool. That's a brochure. Before we talk about voice or visual hierarchy or credibility, we have to acknowledge that the core value proposition is a promise the site can't currently keep.

**Marcus:** Agreed. And it compounds — because the contact form also doesn't submit anywhere. So the *paid* path is broken too. A visitor who wants the free thing gets a description. A visitor who wants to pay has nowhere to go. There's no functioning conversion path on this entire page.

**Meera:** I noticed that, and it's what stopped me from filling out the form. But I want to say — I almost did. The copy in the hero is genuinely good. That first line worked on me in a real way. I put the site down, and then I picked it up again. That doesn't happen often.

**Shreya:** That's important. The hero is punching above its weight. The line *"A thought is running you right now"* is the kind of copy that gets shared. But then the site slowly loses what made that line work. By the time we're in the About section, it sounds like someone *describing* Henna's story rather than Henna telling it. The photo placeholder is the most visible symptom, but the writing underneath it has the same problem.

**Rahul:** Let me be direct about the photo, because I think it's more than a design issue. The absence of a face on the About section isn't just visually weak — it signals that the founder isn't fully ready to stand in front of this yet. That's a credibility signal I read before I read a word of copy.

**Marcus:** The grey box is a full-height 3:4 aspect ratio column on desktop. It's the dominant visual element of that section. It's not a gap — it's a feature that's currently a void.

**Meera:** And the credential tags made me feel slightly talked-at. "Guru Granth Sahib" and "Advaita Vedanta" — I Googled one of them while reading. I don't know if that means I'm not the audience, but it made me feel like the site was written for someone who already knows Henna, not someone discovering her for the first time.

**Shreya:** That's the core tension in the About section. The credential tags are for people who already respect those traditions — and those people will evaluate Henna on the depth of her practice, not the name of the tradition. So they don't really serve anyone. What serves everyone is specificity: *what did this practice actually change for her, and when?*

**Ankit:** From a conversion standpoint, the testimonials are the other big problem. Three `[Name], [City]` placeholders at the exact moment a visitor is deciding whether to trust the site. Placeholder testimonials are worse than no testimonials — they actively signal: this product has no proven customers yet.

**Rahul:** I'd add: no pricing anywhere. Not even a range. "Book a Session" with no price means I don't know if I can afford this, and I'm not going to ask. Ambiguity on price kills intent.

**Marcus:** Can I flag something more technical? The SVG logo — the viewBox is `0 0 360 88` but the rendered height is only `40px`. Without an explicit `width`, the browser calculates proportional width from the viewBox ratio: 360/88 × 40 ≈ 163px. So the logo is 163px wide in the nav — which *might* be okay, but the type inside was designed at 28pt within an 88px-tall space. At 40px height, that text is rendering at roughly 12.7pt, which will be small and potentially misaligned. It needs to be tested and the viewBox should be trimmed to actual content bounds.

**Ankit:** Pull back to the funnel question: what's the MVP of this site that could actually launch and convert? I'd say: fix the form (10 minutes on Formspree), add a price, swap placeholder testimonials for a "launching soon" honest state, and change the primary CTA to "See how it works" until the tool actually exists. That's a launchable site.

**Shreya:** Or — and I think this is the stronger move — change the free offer to something that *does* exist right now. A downloadable PDF of the process. An email sequence. Something that can be delivered. Then the free CTA becomes a real lead capture and the promise is kept.

**Meera:** What I wanted was simpler. I wanted to know: *is this for me, specifically?* One sentence near the hero that names my situation. I kept wondering if I needed to have done The Work before. I kept wondering if my problem was "big enough." Those questions kept me at arm's length.

**Rahul:** The positioning question underneath all of this is: who is the first 10 clients? Because the site right now reads like it was built for a warm audience — people who already know Henna, who already trust Byron Katie's work. That's fine as a starting point. But if the goal is cold traffic, the site needs considerably more trust-building infrastructure before it can do that job.

**Shreya:** One thing I want to say in closing — the bones are genuinely good. The concept is clear. The design is better than 90% of coach and wellness sites I review. The hero has a real voice. The before/after table is smart. This isn't a rebuild — it's a finish. The gap between where this is and where it needs to be is mostly: a photo, a working form, real testimonials, a price, and one honest personal story in the About section.

**Marcus:** And fix the logo viewBox.

**Ankit:** And build the tool. Or change the promise until you have.

---

### Points of Agreement Across All Five Reviewers

1. **Hero headline is the strongest element on the page.** Don't touch it.
2. **The free tool doesn't exist yet** — the CTA promises something that can't be delivered.
3. **Contact form doesn't submit** — no conversion path exists in any direction.
4. **Photo placeholder actively damages trust** in the About section.
5. **Placeholder testimonials are worse than no testimonials.**
6. **No pricing** for the paid session creates friction that kills intent.
7. **About section voice** drops off after a strong hero — needs one specific personal story.
