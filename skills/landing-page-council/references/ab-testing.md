# A/B Testing & Measurement for Landing Pages

How to turn the council's disagreements into a testing plan that's actually runnable on the user's traffic. Hopkins would insist on testing and Laja would insist it be done properly, so this file serves both.

## Contents
1. [Test, ship, or research?](#test-ship-or-research)
2. [Traffic viability check](#traffic-viability-check)
3. [Writing hypotheses](#writing-hypotheses)
4. [Prioritization: ICE, PIE, PXL](#prioritization-ice-pie-pxl)
5. [What to test first on a landing page](#what-to-test-first-on-a-landing-page)
6. [Running tests properly](#running-tests-properly)
7. [Low-traffic alternatives](#low-traffic-alternatives)
8. [Instrumentation spec](#instrumentation-spec)
9. [Backlog and test-log templates](#backlog-and-test-log-templates)

---

## Test, ship, or research?

Not everything needs an A/B test.

| Situation | Action |
|---|---|
| Something is broken (form errors, CTA missing on mobile, 6s LCP, broken link) | **Ship the fix.** Testing a bug fix wastes traffic |
| A clear best-practice gap with low risk (no labels on form fields, "Submit" button, no message match) | **Ship it**, monitor before/after, and test later if needed |
| A genuine council disagreement (long vs. short, clever vs. clear, single vs. transitional CTA) | **A/B test it**, if traffic allows |
| Not enough traffic for a test | **Research** (see low-traffic alternatives), then ship the best-evidenced version |
| Unclear *why* the page underperforms | **Research first** (analytics funnel, recordings, surveys, user tests) to generate hypotheses |

---

## Traffic viability check

Before proposing any test, estimate whether the page can finish it in a reasonable time (≤ 4–6 weeks).

**Rule of thumb** (two variants, α = 0.05 two-sided, 80% power; Lehr's approximation):

> **n per variant ≈ 16 × p × (1 − p) ÷ δ²**
> where *p* = baseline conversion rate and *δ* = the absolute difference you want to detect (baseline × relative MDE).

Approximate **visitors needed per variant**:

| Baseline CR | Detect +10% relative | Detect +20% relative | Detect +30% relative |
|---|---|---|---|
| 1% | ~158,000 | ~39,600 | ~17,600 |
| 2% | ~78,000 | ~19,600 | ~8,700 |
| 3% | ~51,700 | ~12,900 | ~5,700 |
| 5% | ~30,400 | ~7,600 | ~3,400 |
| 10% | ~14,400 | ~3,600 | ~1,600 |

Below a 1% baseline, compute with the formula; at 0.5%, even a +30% lift needs ~71,000 visitors per variant, so plan on research methods or bold changes.

**Weeks needed** ≈ (n × number of variants) ÷ weekly visitors to the page.

**Interpretation:**
- If the page can't detect a 20–30% lift within about 6 weeks, **micro-tests (button color, small copy tweaks) are off the table**. Only bold changes (new offer, new value proposition, new page structure) can show a detectable effect. Otherwise, use research methods.
- Use a proper calculator for the final number (e.g., Evan Miller's sample size calculator, or the testing tool's built-in one), and show the user the inputs.
- If the user hasn't shared traffic and conversion numbers, ask for them before finalizing the backlog, or mark each test "traffic check needed."

---

## Writing hypotheses

Every test needs a hypothesis tied to evidence, not a hunch:

```
Because we observed [evidence: data, research finding, or audit issue],
we believe that [change] for [audience / traffic segment]
will [increase/decrease] [primary metric],
because [the mechanism, often the advisor's framework].
We'll know it worked when [metric] changes by at least [MDE]
after [sample size / duration], without hurting [guardrail metric].
```

**Example:**
> Because the hero headline names the category ("AI-powered CRM") but 70% of traffic comes from problem-aware Meta ads, we believe a headline that leads with the problem in customers' words ("Stop losing deals in your inbox") for paid social visitors will increase demo-form submits, because problem-aware visitors need the problem framed before the product (Schwartz's awareness levels). We'll know when submit rate rises ≥ 20% relative after ~13k visitors per variant, without lowering the sales-qualified rate.

Each council disagreement in the disagreement map should become at least one hypothesis.

---

## Prioritization: ICE, PIE, PXL

Pick one framework per backlog and say which one you used.

**ICE** (popularized by Sean Ellis): score 1–10 each for **Impact** (effect on the primary metric if it wins), **Confidence** (strength of evidence behind it), and **Ease** (effort and time to build and run). Score = average (or product). Fast, but subjective.

**PIE** (Chris Goward, WiderFunnel): **Potential** (how much room for improvement this page or element has), **Importance** (how valuable the traffic is: volume and cost), **Ease**. Good for choosing *which page* to test.

**PXL** (CXL / Peep Laja): replaces subjective 1–10 scores with mostly yes/no questions. Examples: Is the change above the fold? Is it noticeable within 5 seconds? Does it add or remove an element? Is it backed by user testing, qualitative feedback, analytics or heatmap findings? Ease is a graded time estimate. Higher is better. *(Criteria here are approximate. Point users to CXL's PXL article for the current sheet.)*

**Default:** use **ICE** for quick backlogs. Use **PXL** when the user has research data and wants rigor, since it rewards evidence-backed ideas. Always weight *Confidence* by real evidence (analytics, recordings, survey quotes), not by how much the council liked an idea.

---

## What to test first on a landing page

Typical leverage, from highest to lowest. Bigger, more meaningful changes produce detectable effects with less traffic.

1. **The offer**: free trial vs. demo, lead-magnet type, guarantee, pricing presentation, bundle
2. **Value proposition / headline**: different angle (outcome vs. problem vs. mechanism vs. identity), matched to awareness
3. **Page structure and length**: long-form vs. short-form, section order, proof placement
4. **Hero composition**: product screenshot vs. outcome image vs. video; form in the hero vs. a CTA button
5. **Social proof**: type (logos vs. testimonials vs. numbers), placement near the CTA
6. **Form**: number of fields, single vs. multi-step, field order
7. **CTA**: copy (value-specific vs. generic), microcopy, sticky mobile CTA
8. **Friction removers**: nav removal (attention ratio), a FAQ near the CTA
9. **Visual details**: colors, imagery style, button shape. **Last**, and only with large traffic

### Seed hypotheses from common council disagreements

| Disagreement | Test |
|---|---|
| Ogilvy/Schwartz (long copy) vs. Krug (cut half) | Long-form control vs. condensed variant with the same hero |
| Clever (Ogilvy's Big Idea, Godin's remarkable) vs. clear (Miller, Krug) | Distinctive headline vs. plain-outcome headline |
| Gardner (1:1 attention) vs. Miller (transitional CTA) | Single CTA vs. primary plus secondary "download the guide" CTA. Measure total leads *and* qualified leads |
| Cialdini (urgency with real scarcity) vs. Godin (trust) | Real deadline messaging vs. none. Guardrail: refund or unsubscribe rate |
| Wiebe (VOC language) vs. current brand copy | VOC-mined headline vs. current headline |
| Hopkins (sampling) vs. a demo-gated product | Interactive demo or free tier vs. "Book a demo" only |

---

## Running tests properly

- **One primary metric** per test (e.g., form submit rate), decided before launch.
- **Guardrail metrics**: lead quality (SQL rate), revenue per visitor, refund or churn rate, page speed. A test that adds leads but halves quality is a loss.
- **Run full weeks** (at least 1–2 full business cycles) to cover day-of-week effects, even if significance arrives sooner.
- **Don't peek and stop early.** Stopping at the first significant result inflates false positives. Use a fixed sample size, or a tool with sequential or Bayesian methods designed for continuous monitoring.
- **Check sample ratio mismatch (SRM):** if a 50/50 split shows, say, 52/48 on large samples, the test is likely broken (redirects, bots, flicker). Investigate before trusting results.
- **Avoid flicker:** client-side tools can flash the control. Use anti-flicker snippets or server-side or edge testing.
- **Segment carefully:** look at device (mobile vs. desktop) and traffic source after the fact as *hypothesis generators*, not as new wins (multiple-comparison risk).
- **Watch novelty effects** on returning-visitor-heavy pages.
- **Change one concept per variant** (a concept can include several elements). Use multivariate tests only with very high traffic.
- **Document everything**, including losers. A losing test is a learning about the audience.

**Tools** (pick what's already in the stack): VWO, Optimizely, Convert, AB Tasty, GrowthBook, Statsig, PostHog experiments, Unbounce, or the builder's native testing (e.g., Webflow Optimize). *Don't recommend Google Optimize: it was sunset in September 2023.*

---

## Low-traffic alternatives

When the traffic check fails, these methods still produce evidence:

| Method | What it answers | Typical tools |
|---|---|---|
| **5-second test** | Is the hero clear? What do people remember? | Lyssna (formerly UsabilityHub) |
| **Message testing with target audience** | Do the right people understand and care about the value proposition? | Wynter (B2B), panel surveys |
| **Moderated or unmoderated usability tests** (about 3–5 users per round, Krug) | Where do people hesitate or get confused? | Maze, Lookback, UserTesting, or a video call |
| **On-page survey** (one question) | "What's stopping you from signing up today?" | Hotjar, Clarity, PostHog surveys |
| **Customer interviews / review mining** | Real language, objections, motivations (Wiebe's VOC) | Sales calls, reviews, support tickets |
| **Session recordings and heatmaps** | Scroll depth, rage clicks, ignored CTAs | Microsoft Clarity (free), Hotjar |
| **Preference test** | Which of 2–3 headlines or heroes resonates and why | Lyssna |
| **Before/after with caution** | Rough directional read after a bold change | Analytics. Control for seasonality and channel mix, and say it's not causal |

Low-traffic sites should make **bold, research-backed changes** and measure before and after, rather than running underpowered A/B tests.

---

## Instrumentation spec

Define these events before launching any page or test. Use the analytics tool already installed. GA4 names are shown where GA4 has a recommended event.

| Event | When it fires | Key parameters |
|---|---|---|
| `page_view` | Page load (automatic in most tools) | utm_source, utm_medium, utm_campaign, variant |
| `cta_click` | Any primary or secondary CTA click | cta_text, cta_position (hero/mid/final/sticky), variant |
| `form_start` | First interaction with a form field | form_id, variant |
| `form_error` | Validation error shown | field_name, error_type |
| `generate_lead` (GA4 recommended) / `form_submit` | Successful submit (fire on success, not on click) | form_id, lead_type, variant |
| `scroll` (depth) | 25 / 50 / 75 / 90% | percent |
| `video_start` / `video_complete` | Hero or demo video engagement | video_title |
| `sign_up` / `purchase` (GA4 recommended) | Trial signup or purchase | method, value, currency |

Also: pass UTM parameters and the `variant` ID into hidden form fields so CRM lead quality can be analyzed per source and variant, and respect consent requirements (Consent Mode or a CMP) where applicable.

---

## Backlog and test-log templates

**A/B test backlog** (include in every audit output):

```
| # | Hypothesis (short) | Evidence | Page area | Primary metric | Guardrail | I | C | E | ICE | Traffic check |
|---|--------------------|----------|-----------|----------------|-----------|---|---|---|-----|---------------|
| 1 | Problem-led headline beats category headline for paid social | 70% traffic problem-aware; 5-sec test fails | Hero | Demo submit rate | SQL rate | 8 | 7 | 9 | 8.0 | ~13k/variant → ~5 wks at 5k/wk ✓ |
| 2 | … |
```

**Test log** (for each finished test):

```
Test: [name] · Dates: [start–end] · Variants: [A/B]
Hypothesis: …
Result: [primary metric A vs B, relative change, confidence/probability, sample sizes]
Guardrails: …
Decision: [ship / iterate / discard]
Learning about the audience: [the reusable insight]
```
