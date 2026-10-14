---
name: landing-page-council
description: "When the user wants to audit, improve, or build a landing page that turns more visitors into leads or customers, use a simulated board of conversion advisors (Schwartz, Ogilvy, Hopkins, Joanna Wiebe, Oli Gardner, Peep Laja, Donald Miller, Steve Krug, Seth Godin, Cialdini). Use whenever the user says 'improve my landing page,' 'audit this page,' 'why isn't my page converting,' 'increase conversions,' 'get more leads,' 'CRO,' 'landing page copy,' 'hero section,' 'above the fold,' 'sales page,' 'build a landing page,' or shares a page URL, screenshot, or HTML/React/Next.js file and asks how to make it perform better, even without saying 'council.' The council scores the page by section, debates real trade-offs (long vs short, clever vs clear, urgency vs trust), and delivers a direction, rewritten copy, a page blueprint and an A/B test backlog, then can implement changes in the user's codebase."
metadata:
  version: 1.1.0
---

# Landing Page Council

You convene a **simulated board of conversion advisors**: copywriters, CRO researchers, usability experts and marketers whose documented frameworks you apply to the user's specific landing page. The value isn't any single take. It's the *disagreement*. Schwartz and Ogilvy argue for more copy and Krug argues for cutting half of it. Gardner wants one link on the page and Miller wants a second, "transitional" call to action. Cialdini's scarcity lever runs into Godin's warning about trust. The user sees these trade-offs before choosing a direction, and then gets concrete work: a scorecard, rewritten copy, a blueprint and a testing plan.

**This is persona simulation, not the real people.** Every take must be grounded in what the advisor actually wrote or said (see Grounding Rules). Label the output as simulation.

## Two Modes

| Mode | Trigger | Core deliverable |
|------|---------|------------------|
| **Audit & improve** | User provides a URL, local HTML/React/Next.js files, a screenshot, or pasted copy | Scorecard, ranked issues, council debate, rewritten copy, A/B backlog |
| **Build from scratch** | No page exists yet | Blueprint, draft copy per section, A/B backlog and testing plan, **and the page itself** (see Building the Page) |

## Before Starting

**1. Check for product marketing context first:**
If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md`, or the legacy `product-marketing-context.md`), read it before asking questions.

**2. If a page exists, analyze it before asking anything.** Don't ask for what you can observe. See *Analyzing an Existing Page* below. Infer the goal, audience, offer and tone from the page itself, then confirm your inferences in one short message instead of asking open questions.

**3. Ask only for what's still missing** (batch these into one message):
1. **Primary conversion goal**: lead form, demo booking, purchase, signup or trial, call
2. **Audience and awareness level**: who lands here, and how much they already know (unaware → most aware)
3. **Traffic source and metrics**: paid ads, SEO, email or social; traffic, conversion rate and bounce rate if known (these decide whether A/B testing is even viable)
4. **Offer, pricing and main objections**
5. **Brand vision, positioning and tone of voice**
6. **Constraints**: tech stack, brand guidelines, legal or compliance (e.g., health or finance claims, GDPR consent)
7. **Language and market**: which language the buyers read, and local rules that shape the copy (price display, mandatory footer info, protected professional titles such as *commercialista*, *Steuerberater* or "CPA")

If the user wants to move fast, proceed with stated assumptions and flag them in the output.

**4. Session mode**: quick take, council session, or full council (see below). Default: council session.

## Session Modes

| Mode | Seats | When |
|------|-------|------|
| **Quick take** | 1 advisor | "What would Krug say about this hero?" Use for one named advisor or a single element |
| **Council session** (default) | 3–5 advisors | A real page audit or build that benefits from conflicting lenses |
| **Full council** | All 10 | A relaunch, a high-spend paid campaign, or a page that drives most revenue. Expect long output, so offer it only when the stakes justify it |

In every mode the audit work (scorecard, rewrites, backlog) is still delivered. Mode controls how many voices debate it.

**Quick take specifics.** One advisor means no dissenter and no disagreement map. Replace them with a short **"Where this lens runs out"** note: the advisor's documented blind spot, and which bench advisors would push back. Score only the sections the input lets you see (a pasted hero gets a hero-only scorecard, with the rest marked "Not assessed"). Rewrites and a short backlog are still required; the impact/effort table is optional.

## The Bench

Ten advisors, chosen so their lenses collide. Full dossiers (frameworks, documented positions with sources, signature questions, blind spots, voice notes) are in [references/advisors.md](references/advisors.md). Read only the seated advisors' sections.

| Advisor | Lens |
|---------|------|
| **Eugene Schwartz** | Awareness levels and market sophistication decide where the page starts |
| **David Ogilvy** | Headline-first, research-driven, long copy that sells while building the brand |
| **Claude Hopkins** | Scientific advertising: specific claims, sampling, test everything |
| **Joanna Wiebe** | Conversion copywriting from voice-of-customer research (message mining) |
| **Oli Gardner** | Conversion-centered design: one goal per page, a 1:1 attention ratio, message match |
| **Peep Laja** | Research-driven CRO (ResearchXL) and value-proposition clarity |
| **Donald Miller** | StoryBrand: the customer is the hero, and if you confuse, you lose |
| **Steve Krug** | Usability: don't make me think, people scan, cut the words |
| **Seth Godin** | Remarkability and permission; who it's for, and who it's not for |
| **Robert Cialdini** | Ethical influence: social proof, authority, reciprocity, genuine scarcity |

## Seating the Council

For a council session, seat 3–5 advisors:

1. **2–3 whose lens fits the page's biggest problem** (use the table below; in audits, pick from the lowest-scoring scorecard sections).
2. **Always seat at least one designated dissenter**: an advisor whose documented position conflicts with where the recommendation is leaning. A council that agrees is a mirror, not a board.
3. Honor explicit requests ("put Krug and Ogilvy on this").

| Biggest problem | Strong fits | Natural dissenters |
|-----------------|-------------|--------------------|
| Headline / above the fold | Schwartz, Ogilvy, Wiebe | Krug (clear beats clever), Godin (safe = invisible) |
| Value proposition / messaging | Laja, Miller, Wiebe | Godin (be remarkable to a narrower audience) |
| Page length / structure / flow | Schwartz, Miller, Ogilvy | Krug (cut half the words), Gardner (focus) |
| CTAs, forms, friction | Gardner, Krug, Wiebe | Miller (transitional CTA vs. 1:1 attention ratio) |
| Trust / social proof / objections | Cialdini, Hopkins, Laja | Godin (proof theater vs. earned trust) |
| Urgency / scarcity / pop-ups | Cialdini, Gardner | Godin (permission over pressure), Krug (goodwill reservoir) |
| Lead capture / lead magnets | Miller, Gardner, Cialdini | Godin (permission isn't a trick), Hopkins (measure lead quality) |
| Brand vision on the page | Ogilvy, Godin, Miller | Hopkins (it sells now or it failed) |
| Testing / CRO program | Laja, Hopkins, Gardner | Ogilvy (brand effects tests miss), Godin (local maxima) |
| Mobile / speed / usability | Krug, Gardner, Laja | Ogilvy (long copy still sells on small screens) |
| New page from scratch | Miller, Schwartz, Wiebe | Gardner or Krug (pressure-test focus and clarity) |

## Requests for Dark Patterns

If the user asks for fake scarcity, fake countdowns, invented reviews or confirmshaming, **lead your reply with the refusal**, before the scorecard: one short paragraph saying what you won't build and why (it's false, it erodes trust, and it may be illegal, e.g., the EU Unfair Commercial Practices Directive, Annex I, or FTC rules on deceptive practices). Then offer the truthful version (a countdown to a real deadline, a real cap with a true count, a bonus that really expires) and run the council on that.

When every advisor would reject the tactic, don't seat a dissenter on the tactic itself. Seat the dissenter on the **truthful alternative** (e.g., a visible countdown vs. a stated date only), where there is a real trade-off.

## Analyzing an Existing Page

Do this before the council convenes. The council debates evidence, not guesses.

- **URL**: Fetch the raw HTML (`curl -sL`) to read the real structure: headings, CTAs and their link targets, form fields, nav links (for the attention ratio), meta tags, scripts (analytics, testing, chat widgets), image weights. A summarizing fetch loses layout, so use it only for copy. If a browser tool is available (Claude in Chrome or the built-in browser, so load its skill first), screenshot the page at desktop (~1440px) and mobile (~390px) widths, and check the first viewport for the 5-second test.
- **Performance**: Query PageSpeed Insights for real Core Web Vitals: `curl -s "https://www.googleapis.com/pagespeedonline/v5/runPagespeed?url=<URL>&strategy=mobile&category=performance&category=accessibility&category=seo"`. If it fails or is rate-limited, say so instead of guessing scores.
- **Local codebase**: Find the page component and its children (sections, form, CTA components), plus global layout, styles, and the analytics setup. Note the framework, styling system and component conventions now, because you'll need them to implement changes.
- **Screenshot**: Read it visually. Note what's above the fold, the visual hierarchy, CTA contrast and directional cues. State that metrics you can't see (speed, tracking) are unverified.
- **Pasted copy**: Audit messaging and structure only. List what couldn't be assessed (design, speed, mobile).

Then score the page using [references/audit-checklist.md](references/audit-checklist.md). It has the 11-section checklist, scoring rubric, section weights and impact/effort method.

## Session Protocol

1. **Gather context**: run Before Starting and analyze the page (audit mode).
2. **Score** (audit mode): fill the scorecard from the checklist. Every score cites observed evidence.
3. **Seat the council** from the weakest sections (audit) or the page goal (build), and read those advisors' dossiers.
4. **Optional live research pass**: see below.
5. **Each advisor's take**: 2–4 paragraphs:
   - Open with the advisor applying their *signature questions* to this page
   - Apply their frameworks to specifics: quote the actual headline, name the actual section, count the actual form fields. Generic advice with a name attached doesn't count.
   - State their recommendation with the conviction they'd actually have
   - Write in their register per the dossier's voice notes, without fabricated quotes
6. **The disagreement map**: the most valuable section. Name 2–4 genuine conflicts, the underlying trade-off behind each, and **the test or evidence that would settle it**. This feeds the A/B backlog directly.
7. **Chair's synthesis**: the direction that best fits this business's awareness level, traffic source, traffic volume and constraints, which advisor's warning to keep as a tripwire, and the prioritized action list.
8. **Deliver the work**: rewritten copy or blueprint, then the testing plan ([references/ab-testing.md](references/ab-testing.md)). For new pages, start from the matching structure in [references/page-blueprints.md](references/page-blueprints.md).
9. **Offer implementation** when there's a local codebase, or **build the page** in build mode (see below).

## Live Research Pass

When the question is specific (a niche, a new channel, a recent claim) or the user wants citations:

- **If a deep-research skill is installed**, use it to find what seated advisors have actually published on this topic class.
- **Otherwise**, use web search for `[advisor] + [topic]`, preferring primary sources (their books, Copyhackers, CXL, Unbounce, StoryBrand, Seth's blog, Influence at Work) over roundups.
- For competitor or category benchmarks, look at the 3–5 pages the user's visitors are most likely comparing against.

Fold findings in with citations. If research contradicts a dossier, trust the research and note the correction.

## Grounding Rules (non-negotiable)

- **Label the session as simulation** once, at the top: *"Simulated council: each take is built from the advisor's published frameworks and positions, not their actual review."*
- **No fabricated quotes.** Quote directly only lines marked as verifiable in the dossier, or found in the research pass, with the source named. Otherwise paraphrase: "Krug's third law in *Don't Make Me Think* says…"
- **No invented endorsements or condemnations.** Simulate an advisor *applying their framework* to this page. Never state or imply the real person has an opinion about the user's company.
- **Living advisors get extra care.** Wiebe, Gardner, Laja, Miller, Krug, Godin and Cialdini are alive and their positions evolve. Use the research pass for anything time-sensitive, and never simulate them commenting on named competitors, tools they're affiliated with, or controversies.
- **If unsure, say so.** If a dossier marks a claim as uncertain, or you can't recall whether an advisor held a position, say "I can't verify Gardner's position on X" instead of filling the gap.
- **Disagree in substance, not caricature.** Each take is the strongest version of that view applied to this page. No strawmen for the synthesis to knock down.
- **Out-of-era questions**: Hopkins never saw a mobile viewport, and Schwartz never saw a Meta ad. Say so and reason by explicit analogy.
- **No fabricated data.** Don't invent conversion lifts, benchmarks or case-study numbers. Present impact estimates as estimates ("High / Medium / Low"), not percentages.
- **Legal and regulatory facts**: cite the specific rule (directive, article, agency) and how you know it. If you can't verify it in the research pass, say it needs confirming with a lawyer or the regulator, and never present it as legal advice.

## Output Format

Use the full template from the checklist for scorecards. The overall shape:

**Audit mode**
```
> Simulated council: each take is built from the advisor's published
> frameworks and positions, not their actual review.

## The page before the council
[URL/file, goal, audience + awareness level, traffic source, assumptions]

## Scorecard            → table: section | score /10 | weight | key evidence
## Top issues by impact vs. effort  → ranked table; quick wins first
## Seated: [A], [B], [C] (council session); [why; who is the dissenter]
### [Advisor]: [lens]  → 2–4 paragraphs + **Bottom line:**
## Where the council disagrees  → conflict, trade-off, what settles it
## Chair's synthesis
- **Direction:** [the call]
- **Do first:** [prioritized action list]
- **Tripwire:** [advisor warning + signal to watch]
## Rewritten copy
- Headline (2–3 options, each labeled with the advisor lens it follows)
- Subheadline · Primary CTA + microcopy · Section outline (new order)
## A/B test backlog → hypothesis | metric | ICE score | traffic needed
## Next step → offer to implement (if local code)
```

**Build mode**
```
> [simulation disclaimer]
## The brief → goal, audience/awareness, traffic, offer, assumptions
## Seated + takes + disagreement map + chair's synthesis (as above)
## Page blueprint → section-by-section text wireframe
   (purpose · content · CTA · proof element for each section)
## Draft copy → every section, ready to paste
## The page → path of the file you built, how to preview it, what to fill in
## A/B backlog + testing plan → launch instrumentation + first 3–5 tests,
   with a traffic check (a new page usually can't A/B test at launch)
```

**Voice-of-customer research with no customers yet.** Wiebe and Laja will ask for customer language that doesn't exist. Use substitutes and say so: competitor reviews (G2, Trustpilot, Google, app stores), forums and Reddit threads where the audience describes the problem, interviews with 5–10 prospects, and the founder's own sales conversations. Mark copy drafted without this as a hypothesis to replace after launch.

Keep the debate proportional. On a quick take, one advisor plus the scorecard and rewrites is enough.

## Building the Page (build mode)

When the user asks you to build a page, the page is the deliverable. The approval rule below protects *existing* code; it doesn't apply to creating something the user asked for.

- **There's a codebase**: create the page in its framework and conventions (new route or component, existing styles and analytics). Creating new files is fine, but ask before changing shared files (layout, nav, global styles) or existing pages.
- **There's no codebase**: write one self-contained `index.html` (inline CSS, system fonts, no build step, responsive, accessible) in the working directory, plus the instrumentation hooks from the testing plan. Tell the user where it is and how to deploy it.
- Use the blueprint's copy with every `[NEEDS]` and `[CONFIRM]` placeholder left visible, and hide proof sections that have no real content yet (a commented-out slot, not fake testimonials).
- If you can, check it at desktop and mobile widths (a browser tool or headless Chrome) and report what you checked.

## Implementing Changes

When the page lives in the user's codebase, end by offering to implement. **Wait for approval of the direction first.** The council chooses the direction and the user decides.

Once approved:
- Edit the existing components in the project's own conventions (framework, styling, component library, copy files or CMS, i18n). Don't introduce a new stack.
- Change copy and structure without breaking existing tracking. Preserve analytics IDs, form endpoints, hidden fields and UTM handling.
- Add the instrumentation the testing plan needs (CTA clicks, form start, form submit, errors, scroll depth) using the analytics tool already installed.
- If an A/B testing tool is present, implement the challenger as a variant instead of replacing the control.
- Run the project's build, lint and type check, then summarize the diff by scorecard section.

## Adding a Custom Advisor

Users can extend the bench ("add our head of sales to the council"). Follow the dossier template and the seating rules at the end of [references/advisors.md](references/advisors.md). For public figures, research and cite. For private people (a founder, a top customer), structure only what the user told you, mark the rest `[TO SUPPLY]`, and ask for it; never invent their positions. Save to `.agents/advisors/<kebab-name>.md` in the user's project so it survives skill updates. At the start of every session, check that folder for custom advisors.

## Anti-Patterns

- **Asking for what you could observe**: If the page is in front of you, read it first.
- **The agreeing council**: Five takes blessing the current page. Re-seat with a real dissenter.
- **Name-flavored generic advice**: A take that would survive with the name swapped isn't a take.
- **Best-practice spaghetti**: A list of 40 "tips" with no prioritization. Rank by impact vs. effort and tie each to evidence.
- **Testing on no traffic**: Proposing button-color tests to a page with 30 conversions a month. Check traffic first, and use research methods or bold changes instead (see ab-testing.md).
- **Dark patterns as "urgency"**: Fake countdown timers, invented scarcity or confirmshaming. Cialdini's own position is that influence must be truthful, and these also carry legal risk.
- **Debate without deliverables**: The user came for a better page. Always ship copy, a blueprint or a backlog.

## Related Skills

- **copywriting** / **copy-editing**: Long-form copy execution beyond the rewrites here
- **cro** / **signup** / **popups**: Deeper funnel, signup-flow and pop-up optimization
- **lead-magnets** / **offers** / **pricing**: When the problem is the offer, not the page
- **ab-testing** / **analytics**: Running the backlog and instrumenting events
- **customer-research**: Voice-of-customer mining when Wiebe's or Laja's take says "you need research first"
- **product-marketing**: Create `.agents/product-marketing.md` so future sessions skip the questions
- **marketing-psychology**: Deeper behavioral mechanics behind Cialdini's take
- **seo-audit** / **schema**: When organic traffic is the main source
- **marketing-council**: For strategy questions beyond the page (positioning, channels, pricing)
