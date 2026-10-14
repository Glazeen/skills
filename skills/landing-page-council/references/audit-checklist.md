# Landing Page Audit Checklist

Use this to score an existing page before the council convenes, and as a quality bar for pages built from scratch. Every score must cite observed evidence: the actual headline, the actual field count, the actual LCP. If something can't be observed (e.g., speed from a screenshot), mark it **"Not assessed"** and exclude it from the weighted total rather than guessing. If only part of a section can be observed (e.g., mobile layout from CSS but no Core Web Vitals), score it from what you saw and mark it **"Partial: [what was missing]"**. It counts in the total, but the gap is stated next to the score.

## Contents
1. [Scoring method](#scoring-method)
2. [The 5-second test](#the-5-second-test)
3. [The 11 sections](#the-11-sections)
4. [Impact vs. effort ranking](#impact-vs-effort-ranking)
5. [Scorecard template](#scorecard-template)

---

## Scoring method

Score each section **0–10**:

| Score | Meaning |
|-------|---------|
| 9–10 | Exemplary. A competitor would copy it. Minor polish only |
| 7–8 | Solid. Clear and functional, with specific improvements available |
| 5–6 | Mixed. Some elements work, and at least one meaningful conversion leak |
| 3–4 | Weak. Multiple leaks, actively costing conversions |
| 0–2 | Missing or broken |

**Weights** (default; adjust and say so when the goal demands it. E-commerce pages weight trust and mobile higher, and B2B demo pages weight value proposition and objections higher):

| # | Section | Weight |
|---|---------|--------|
| 1 | Above the fold | 15% |
| 2 | Value proposition & messaging | 15% |
| 3 | Page structure & flow | 10% |
| 4 | Attention & engagement | 5% |
| 5 | Trust & social proof | 10% |
| 6 | Objection handling | 5% |
| 7 | CTAs & forms | 15% |
| 8 | Lead capture optimization | 5% |
| 9 | Mobile & performance | 10% |
| 10 | Tracking & testing | 5% |
| 11 | Accessibility & SEO basics | 5% |

Overall = Σ(score × weight) over assessed sections ÷ Σ(weights of assessed sections). Report it as **X.X / 10**, and state which sections were not assessed.

---

## The 5-second test

Look only at the first viewport (desktop and mobile) and answer:
1. **What is this?** (product or service, in plain words)
2. **Who is it for?**
3. **Why should I care?** (the end benefit, or what's different)
4. **What do I do next?** (the primary action)

If any answer requires scrolling, reading body copy or guessing, the hero fails. This is Krug's "don't make me think," Miller's Grunt Test and Laja's clarity heuristic in one check. State that this is a simulated heuristic, and recommend a real 5-second test with target users (e.g., Lyssna, formerly UsabilityHub, or Wynter for B2B messaging) for validation.

---

## The 11 sections

Each section lists the checks, the evidence to collect, common red flags, and the advisors whose lens fits it best.

### 1. Above the fold
*Lenses: Schwartz, Ogilvy, Wiebe, Krug, Miller*

- [ ] **Headline** states a specific outcome or benefit (not a category label or a slogan), matched to the visitor's awareness level
- [ ] **Subheadline** explains what it is, for whom, and how, in 1–2 sentences
- [ ] **Hero visual** shows the product, the outcome or the customer, not decorative stock
- [ ] **Primary CTA** is visible without scrolling on desktop *and* mobile, with action-specific copy
- [ ] **Message match** with the traffic source (ad headline, email subject, search query)
- [ ] **Passes the 5-second test**
- [ ] A **proof element** near the hero (rating, logo strip, customer count) where credible

**Evidence:** Exact headline, subheadline and CTA text; viewport screenshots; traffic-source copy if available.
**Red flags:** "Welcome to…", "The future of X," "All-in-one platform," a headline that could fit any competitor, a CTA below the fold on mobile, a carousel or slider hero.

### 2. Value proposition & messaging
*Lenses: Laja, Wiebe, Miller, Godin, Hopkins*

- [ ] The **core value proposition** is explicit: end benefit + what + for whom + why it's better than the alternative
- [ ] **Specificity**: numbers, timeframes, named outcomes instead of adjectives ("cut reporting from 6 hours to 20 minutes" vs. "save time")
- [ ] **Benefits over features**: each feature is translated into "so you can…"
- [ ] **Customer-centric language**: "you" over "we," customer vocabulary (VOC) over internal jargon
- [ ] **Differentiation**: what's unique vs. the visitor's real alternatives (competitors, spreadsheets, an agency, doing nothing)
- [ ] **Brand vision expressed as visitor benefit**: the mission or vision appears as what it changes *for the visitor*, not as a corporate manifesto
- [ ] **Who it's for (and not for)** is clear enough for self-selection
- [ ] **Market sophistication**: in a crowded category, a distinct mechanism instead of the category's tired claim

**Evidence:** Value proposition sentences quoted; the count of "we/our" vs. "you/your" in the hero and first sections; jargon list.
**Red flags:** Feature lists with no outcomes, a vision statement in the hero, superlatives without proof ("best-in-class"), messaging identical to competitors'.

### 3. Page structure & flow
*Lenses: Miller, Schwartz, Ogilvy, Gardner*

- [ ] A **narrative arc** that fits the awareness level. Typically: hook → problem/stakes → solution/mechanism → how it works (plan) → proof → offer → objections → final CTA
- [ ] **Section order** answers questions in the order visitors have them
- [ ] **Scannability**: descriptive section headings (they tell the story on their own), short paragraphs, bullets, bolded key phrases
- [ ] **Attention ratio**: links ÷ conversion goals. Target close to 1:1 for campaign pages. Count nav, footer and inline links
- [ ] **One primary goal**: secondary CTAs (if any) are visually subordinate and deliberate (e.g., Miller's transitional CTA)
- [ ] **Length matches awareness**: short for most-aware or retargeting traffic, longer for cold, problem-aware traffic or high-consideration offers
- [ ] CTA **repeated** at natural decision points (after proof, after the offer, at the end)

**Evidence:** Section-by-section outline of the current page; link count by type; total word count.
**Red flags:** Full site navigation on a paid landing page, sections ordered by org chart (About Us first), a wall of text, the same CTA buried once at the bottom.

### 4. Attention & engagement
*Lenses: Gardner, Krug, Ogilvy*

- [ ] **Visual hierarchy**: headline > subheadline > CTA > supporting content, so the eye lands where intended
- [ ] **CTA contrast and encapsulation**: the CTA is the most visually distinct interactive element
- [ ] **Whitespace** isolates key elements
- [ ] **Directional cues** (gaze, arrows, layout flow) point toward the CTA or form
- [ ] **Motion** is purposeful (demonstrates the product) and not distracting. Respects `prefers-reduced-motion`
- [ ] **Media**: product video or demo where it helps, with captions and an explanatory thumbnail; no autoplay with sound
- [ ] **Copy length vs. awareness** (cross-check with section 3)

**Evidence:** Squint test (blur the screenshot: what stands out?), CTA color vs. surroundings, motion inventory.
**Red flags:** Multiple competing bright buttons, a hero image pulling the eye away from the CTA, auto-rotating carousels, decorative animation delaying content.

### 5. Trust & social proof
*Lenses: Cialdini, Hopkins, Ogilvy, Laja*

- [ ] **Testimonials** that are specific (outcome + context), attributed (name, role, company, photo), and from people *similar* to the target visitor
- [ ] **Logos** of recognizable customers, partners or media, relevant to the audience
- [ ] **Case studies or results** with real numbers
- [ ] **Quantified proof**: customer count, ratings (with source, e.g., G2 or Trustpilot), usage stats, all real and current
- [ ] **Authority**: certifications, awards, security or compliance badges (SOC 2, GDPR), expert endorsements
- [ ] **Risk reversal**: guarantee, free trial, cancel anytime, refund policy, stated clearly
- [ ] **Proof placement**: near the CTA and next to the claims it supports
- [ ] **Human presence**: real team or founder, contact info, physical address for local businesses

**Evidence:** Inventory of every proof element and its position; flag anything unattributed or unverifiable.
**Red flags:** Anonymous testimonials ("— John D."), generic praise ("Great product!"), stale numbers, fake-looking stock photos on testimonials, no guarantee for a purchase page.

### 6. Objection handling
*Lenses: Wiebe, Laja, Hopkins, Miller*

- [ ] The **top 3–5 objections** are identified (price, time to value, switching cost, trust, "will it work for me") and addressed in the page body, not only in the FAQ
- [ ] An **FAQ** answers real pre-purchase questions (from sales or support), not filler
- [ ] **Comparison** vs. alternatives where visitors are actively comparing (table or "why us")
- [ ] **Pricing clarity**: price or price range shown, or a clear reason it isn't. No surprise costs. Clear what's included
- [ ] **Stakes**: the cost of inaction is made concrete (Miller), without fear-mongering
- [ ] **"Is this for me?"** answered: use cases, segments, sizes

**Evidence:** List of objections the page addresses vs. likely objections (from context file, reviews, sales notes).
**Red flags:** No pricing information on a self-serve offer, FAQs that are disguised feature lists, "Contact us for pricing" with no range for SMB audiences.

### 7. CTAs & forms
*Lenses: Gardner, Krug, Wiebe, Cialdini*

- [ ] **CTA copy** is specific and value-oriented ("Get my free audit," "Start free trial") rather than generic ("Submit," "Learn more")
- [ ] **CTA placement**: in the hero, after key proof, and at the end; sticky on mobile where appropriate
- [ ] **Microcopy** under or near the CTA reduces risk ("No credit card required," "Takes 2 minutes," "We'll never share your email")
- [ ] **Number of fields** is the minimum needed for the next step. Each field justifies itself (enrich later or use progressive profiling)
- [ ] **Field design**: visible labels (not placeholder-only), correct input types (`email`, `tel`), `autocomplete` attributes, sensible defaults
- [ ] **Errors**: inline, specific and polite. Input is preserved on error
- [ ] **Friction audit**: no forced account creation before value, no CAPTCHA unless necessary (prefer invisible bot protection)
- [ ] **What happens next** is stated (e.g., "You'll get a calendar invite within 1 business day")
- [ ] **Thank-you page** confirms, sets expectations and offers a next step (book a call, share, download)
- [ ] **Consent**: checkboxes and privacy links compliant with the user's jurisdiction (GDPR, CAN-SPAM, TCPA for SMS) and not pre-ticked where the law forbids it

**Evidence:** Every CTA's text and target; the field list with required/optional; submit flow walkthrough.
**Red flags:** "Submit," 8+ fields for a top-of-funnel offer, phone required without a reason, a dead-end thank-you page, a CTA that links to a different goal than the page's.

### 8. Lead capture optimization
*Lenses: Miller, Cialdini, Godin, Gardner*

- [ ] **Lead magnet** (if used) is specific, quick to consume and tied to the paid offer (checklist, template, calculator, audit, mini-course), not a generic "newsletter"
- [ ] **Offer-to-friction fit**: the value of the offer justifies the ask (email only for a checklist; more fields for a custom audit or demo)
- [ ] **Multi-step forms** for longer forms: start with an easy, engaging question, then ask for contact details (commitment and consistency)
- [ ] **Transitional CTA** for visitors not ready for the main ask, if it doesn't break page focus (resolve the Miller vs. Gardner trade-off explicitly)
- [ ] **Exit intent or scroll-triggered offers** are used sparingly, offer genuine alternative value, are easy to dismiss and avoid confirmshaming
- [ ] **Follow-up flow**: immediate confirmation email, delivery of the promised asset, a nurture sequence, and speed-to-lead for sales leads (routing, notifications)
- [ ] **Lead quality**: qualification fields or routing so sales isn't flooded with poor-fit leads

**Evidence:** Lead magnet inventory, pop-up behavior, what happens after submit (test it if possible).
**Red flags:** "Subscribe to our newsletter" as the only capture, a pop-up on page load, no confirmation email, a sales demo request that waits days for a reply.

### 9. Mobile & performance
*Lenses: Krug, Gardner, Laja*

- [ ] **Responsive layout**: no horizontal scroll, readable text without zoom (16px+ body), sensible stacking order (the hero CTA stays near the top)
- [ ] **Core Web Vitals** (field data if available, lab otherwise), "good" thresholds: **LCP ≤ 2.5s**, **INP ≤ 200ms**, **CLS ≤ 0.1**. *(INP replaced FID as a Core Web Vital in March 2024.)*
- [ ] **Load speed**: optimized hero image (modern format, correct size, preloaded or prioritized, not lazy-loaded), minimal render-blocking scripts, fonts with `font-display`
- [ ] **Third-party scripts**: count and weight (chat widgets, pixels, heatmaps). Defer what's not critical
- [ ] **Thumb-friendly CTAs**: tap targets at least 24×24 CSS px (WCAG 2.2 AA minimum), and ideally about 44–48px for primary actions (Apple HIG 44pt, Material 48dp), with spacing between targets
- [ ] **Mobile forms**: correct keyboards (`type="email"`, `inputmode="numeric"`), autofill works, and the CTA is visible when the keyboard is open
- [ ] **Sticky mobile CTA** where the page is long (doesn't cover content, dismissible if large)

**Evidence:** PageSpeed Insights mobile results (performance score, LCP/INP/CLS, top opportunities), mobile screenshot.
**Red flags:** LCP > 4s, a hero image > 500KB, layout shift from late-loading banners, cookie banners covering the CTA on mobile.

### 10. Tracking & testing
*Lenses: Hopkins, Laja*

- [ ] **Analytics** installed and firing (GA4, PostHog, Plausible or similar), with **conversion events** defined: CTA click, form start, form submit or `generate_lead`, purchase, scroll depth, video engagement
- [ ] **Attribution**: UTM parameters preserved into form submissions or CRM, and ad platform conversions configured (with consent mode where required)
- [ ] **Behavior tools**: heatmaps, scroll maps and session recordings (e.g., Microsoft Clarity, Hotjar), consent-compliant
- [ ] **Funnel visibility**: the drop-off between visit → CTA click → form start → submit → qualified lead can be measured
- [ ] **A/B testing capability** (VWO, Optimizely, Convert, GrowthBook, Statsig, PostHog experiments, or a platform builder's native testing) and enough traffic to use it
- [ ] **An A/B test plan** with hypotheses and prioritization (see `ab-testing.md`)

**Evidence:** Scripts found in the HTML, event names in code, the user's reported metrics.
**Red flags:** Only pageviews tracked, form submits not tracked, conflicting duplicate tags, recommending Google Optimize (sunset in September 2023).

### 11. Accessibility & SEO basics that affect conversion
*Lenses: Krug, Laja*

- [ ] **Contrast**: text at least 4.5:1 (large text 3:1); UI components and focus indicators at least 3:1 (WCAG 2.x AA)
- [ ] **Semantic structure**: one `h1` (the headline), logical heading order, landmarks
- [ ] **Forms**: associated `<label>`s, error messages announced, keyboard navigable, visible focus
- [ ] **Images**: meaningful `alt` text for product and proof images, and empty `alt` for decorative ones
- [ ] **Buttons vs. links**: actions are `<button>`, navigation is `<a>`, and both have descriptive accessible names
- [ ] **Title tag and meta description** match the page promise (they affect CTR from search and shares)
- [ ] **Open Graph / social preview** image and text for shared links
- [ ] **Indexing intent**: paid-only variants `noindex` where duplicate, canonical tags correct, and organic pages target a clear query
- [ ] **Structured data** where relevant (Product, FAQPage, LocalBusiness, Event)

**Evidence:** HTML inspection, PageSpeed Insights accessibility and SEO categories.
**Red flags:** Text baked into images, placeholder-as-label, a missing or duplicate `h1`, a generic `<title>` ("Home").

---

## Impact vs. effort ranking

For every issue found, rate:
- **Impact** (H/M/L): how much it plausibly affects the primary conversion. Weigh by position (above the fold > below), by how many visitors it touches (mobile share), and by severity (a broken form beats awkward copy).
- **Effort** (H/M/L): copy-only change = L; design/layout change = M; new assets, research, dev or integration work = H.

Sort into quadrants and present them in this order:
1. **Quick wins**: high impact, low effort. Do now, often without testing if clearly broken (bugs, missing CTA on mobile, a broken form)
2. **Big bets**: high impact, high effort. Plan and test
3. **Fill-ins**: low impact, low effort. Batch them
4. **Money pits**: low impact, high effort. Deprioritize and say so

Never present impact as a fabricated percentage lift.

---

## Scorecard template

```
## Scorecard: [page], overall X.X / 10 ([N] of 11 sections assessed)

| # | Section | Score | Weight | Key evidence |
|---|---------|-------|--------|--------------|
| 1 | Above the fold | 4/10 | 15% | Headline "The all-in-one growth platform": fails 5-sec test (who/why unclear); CTA below fold on mobile |
| 2 | Value proposition | … | 15% | … |
| … |
| 9 | Mobile & performance | Not assessed | — | Screenshot only; run PageSpeed Insights |

**5-second test:** What: ✗ · Who: ✗ · Why: ~ · Next step: ✓

## Top issues: impact vs. effort
| Rank | Issue | Section | Impact | Effort | Quadrant | Fix |
|------|-------|---------|--------|--------|----------|-----|
| 1 | … | Above the fold | H | L | Quick win | … |
```
