# Pre-Built Site Playbook — Design Spec

**Date:** 2026-04-17
**Author:** Brayan (with Claude)
**Status:** Approved design, pre-implementation

---

## Context

The existing `index.html` cold call playbook is built around a model where the cold call books a 20-minute discovery zoom, a deposit gets taken, then the site gets built. That model is obsolete for our new approach.

**New business model:** pre-build (or plan to pre-build) a custom site for the lead before the cold call. The cold call claims the site already exists. A second meeting (5 minutes, Google Meet) reveals the site and closes the sale. Unsold sites become portfolio pieces — no wasted work.

**Why the pivot:**
- AI-assisted development makes building a real custom site cheap enough to front-load.
- A tangible deliverable converts dramatically better than a pitch.
- Discovery is redundant — the scraper pre-qualifies leads and tells us what they're missing.
- Fewer calls per deal. One cold call, one reveal.

## Goal

Rewrite `index.html` to reflect the new flow while keeping the current visual design (Inter font, sectioned tabs, collapsible objection accordions, sticky nav, minimal ink-on-paper aesthetic).

---

## Overall Flow

```
Cold call (30-60 sec, phone)
    → Book Google Meet 24+ hrs out
    → Send calendar invite + blaztly.com link during the call
    ↓
The Gap (24+ hrs)
    → Build the site if not already built
    → Prospect vets us via blaztly.com
    → Protect the gap (don't move it closer than ~18 hrs)
    ↓
Reveal call (5 min, Google Meet, screen share)
    → Show → their reaction → price → close
    ↓
Yes  → payment link, live in ≤7 days
No   → portfolio piece, follow up in 60 days
Custom → separate quote, send after call
```

**Business rules that govern the whole flow:**
- Goal per call: cold call books the meeting, reveal closes the sale. Nothing else counts.
- Never say the price on the cold call.
- Always show before telling the price.
- Site is "already built" in how we talk about it, regardless of actual build state.
- Target: local restaurants and services (landscapers, barbers, contractors, etc).

---

## Playbook Structure (6 tabs)

Replacing the current 7-tab structure (pre-call, opener, discovery, pivot, close, objections, mindset) with:

1. **Pre-call** — scraper prep + decision-maker check + offer sheet + build SOP
2. **Cold call** — combined opener + close (one 30-60s flow)
3. **The gap** — new. Post-call hygiene, build window, gap rules
4. **Reveal** — new. 5-min Google Meet structure
5. **Objections** — updated. Split by phase: cold-call objections vs. reveal objections
6. **Mindset** — updated rewires for the new business model

**Removed:** discovery tab, pivot tab (the site is the pivot).

---

## Tab 1: Pre-Call

Keeps existing scraper-observation pill group, business-type check, decision-maker confirmation. Updates the offer sheet. Adds a build SOP subsection.

### Scraper surfaces (unchanged pills)
no website · not mobile-friendly · no Google Business listing · 0 reviews · site loads slow · no booking button · site outdated 3+ yrs · competitor outranking them · social only, no site

### Three-item checklist
1. Read the scraper observation — that's the ONE thing you know about them.
2. Know their business type (restaurant vs. service). Shapes the build.
3. Confirm who the decision maker is.

### Offer sheet (updated)
| | |
|---|---|
| Setup (one-time) | $700 — April discount, bumps after April 30 |
| Hosting + support | $39/mo |
| Live in | ≤7 days from paid |
| Includes | domain, hosting, SSL, branding, SEO setup, Netlify email form, unlimited small edits |
| Custom tier | extra pages, CRM, ordering integrations — separate quote |
| Real client example | amigolandscaping.com |

### Build SOP (new subsection)

What gets built during the gap. Base tier only.

**Mandatory sections (4):**
- Hero: business name + one-line value prop + CTA
- Services or menu (swap based on business type)
- About / photos (pull from Google Business or social)
- Contact: Netlify email form

**Tie build to scraper observation.** One deliberate choice that shows homework:
- "not mobile-friendly" → aggressively mobile-first, demo on phone
- "no Google Business" → include hours/location/map section
- "site outdated" → modern minimal aesthetic, emphasize load speed
- "no booking button" → prominent CTA as the hero action

**Do NOT build on spec:** CRM hooks, ordering integrations, custom domain email, blog, multi-language, animations beyond basics. All upsell.

**When to pre-build vs. build-in-gap:**
- High-probability lead (active Google Business, bad existing site, visible budget) → pre-build before cold call.
- Cold unknown → build after booking, during the gap.
- Cold call always treats the site as already made.

### Restaurant ordering note
Toast, Square for Restaurants, Clover, ChowNow. Don't build — embed their widget or link out. If they don't have one, recommend ChowNow or Square. Upsell conversation, not base-tier.

---

## Tab 2: Cold Call

One 30-60s flow. Framed as **flow + natural phrasing** (not verbatim script). Four beats.

### Beat 1 — Opener
> *"Hey, our team made you guys a website. Are you the right person to talk to about that? I was hoping to show someone something like that."*

No self-introduction, no company name. Pattern interrupt comes from the sentence itself. "Our team" because the company has multiple people.

### Beat 2 — Gatekeeper branch (if not decision maker)
> *"No worries — who's the right person? Any chance they're around right now?"*

Don't pitch the gatekeeper. Get a name + callback window.

### Beat 3 — Close (once they confirm)
> *"Cool — it'll take 5 minutes to walk you through it. We're kind of busy today — how does tomorrow around 10 or 3 work?"*

Two specific times, both 24+ hrs out. "Kind of busy today" justifies the gap AND plants the "in demand" frame.

### Beat 4 — Book it
> *"Perfect — what's your email? I'll send the Google Meet invite now. I'll also send you blaztly.com so you can see what we do in the meantime."*

Calendar invite goes out during the call. Blaztly.com in the invite description.

### Rules
- Stop talking the moment they say yes to a time.
- Never give a price on the cold call.
- "Just send me the link" is in objections — use the scripted answer.
- Goal = booked Google Meet + email captured. Nothing else counts.

---

## Tab 3: The Gap

New tab. Three sub-sections.

### Immediate post-call (within 5 min of hanging up)
- Send Google Meet calendar invite. Title: *"Blaztly x [Business Name] — quick site walkthrough (5 min)"*
- Include blaztly.com in the invite description: *"Here's what we do — have a look when you get a chance."*
- Optional: follow-up text 30 min later. *"Sent the invite + our site. See you [time]."*

### The build
- If not already built, this is the window.
- Follow Build SOP from pre-call tab.
- One deliberate choice tied to the scraper observation.
- Don't over-build. Base tier is base tier.

### Gap rules
- **"Can you send the link now?"** → *"Not live yet — hosting costs money before you've committed. I'll screen-share on our call."*
- **"Can we move it up?"** → *"Let me check — we have a few of these booked this week, but I'll see."* Never move closer than ~18 hrs.
- Protect the gap. It's your build window, your perception play, and your trust buffer.

---

## Tab 4: Reveal

New tab. 5-min Google Meet. Five beats.

### Beat 1 — Warm-up (~30 sec)
Small talk while they join. Confirm screen share works. No pitch.

### Beat 2 — Walkthrough (~2-3 min)
Share screen, load their site, walk top to bottom. Narrate lightly.
- Hero → services/menu → about/photos → contact form (show Netlify email flow: *"this hits your inbox directly"*)
- If scraper observation was mobile-related, flip to phone view and demo on mobile.
- **Differentiator, dropped once naturally:** *"This is hand-coded — AI-assisted, but not a template. Not WordPress, not Wix. Means you can customize literally anything down the line."*

### Beat 3 — Their reaction (~30 sec)
Stop narrating. *"So — what do you think?"* Let them talk.
- **They like it** → Beat 4.
- **Lukewarm or quiet** → *"What would you change?"* Small changes (colors/copy/photos) are free, base tier. Big changes = custom tier, flag but don't price mid-reveal.

### Beat 4 — Price (~30 sec)
> *"Here's how it works — starts at $700 right now, that's our April discount. $39/month covers hosting, domain, SSL, unlimited small edits. If you want custom work — extra pages, ordering, CRM — that's a separate conversation. But what's on your screen right now? $700."*

Deliver the price. Shut up. First person to talk loses.

### Beat 5 — Close (~1 min)
- **Yes** → *"Perfect. Sending a payment link. Live in 7 days. What email should the invoice go to?"*
- **"Let me think about it"** → *"Totally fair. Heads up — $700 discount ends April 30, bumps up after that. Want me to hold the rate until [date before April 30]?"*
- **"I want to change X, Y, Z" (upsell)** → *"Cool — let me put together a quick quote for the custom work, send it tonight. Sound good?"* Don't price custom live.
- **No / not now** → *"No worries. Mind if I keep you on our list? If this works for someone else as a portfolio piece, I'll let you know."*

### Rules
- Show before you tell the price. Always.
- Don't price custom work live. Promise a quote, send after.
- Once price is out, stop talking.
- "Why $700?" → *"Because we hand-code everything. Not a template."* One sentence, back to close.

---

## Tab 5: Objections

Collapsible accordion pattern (same as current). Split into two groups.

### Cold-call objections

1. **"Just send me the link"** → *"Can't — it's not live yet. Custom coded, and hosting it before you've committed costs us money. I'll screen-share it on Google Meet — takes 5 minutes."*

2. **"How much is it?"** → *"I'd rather show you first — takes 5 minutes. Once you see it, I'll walk you through the numbers. Tomorrow 10 or 3?"*

3. **"Why did you build me a site without asking?"** (portfolio back-pocket) → *"Honestly? We build these for local businesses we think look promising. If you love it, great. If not, we keep it as an example of our work. No pressure either way."*

4. **"I already have a website"** → *"Cool — we looked at it. When's the last time someone found you through Google vs. someone you already knew? That's what the 5 minutes is for."*

5. **"Not interested"** → *"Totally fair. One second — do you get any customers from Google searches, or mostly word of mouth?"*

6. **"I'll think about it / call me back"** → *"Sure — but I won't have these slots open next week. Tomorrow 10 or 3 — pick one and I'll hold it. If it's bad, you cancel."*

### Reveal objections

1. **"It's too expensive"** → *"$700 is the April rate — goes up May 1. You'd pay that for a Wix template someone set up in an afternoon. This is hand-coded, yours forever, live in 7 days."*

2. **"Can you do it cheaper?"** → *"The $700 is already the discount. What I can do is hold the rate past April 30 if you commit today."*

3. **"I want to show my partner"** → *"Of course. Want to loop them in right now? Otherwise I'll send a recording — when can you talk it over?"* (Get specific follow-up time.)

4. **"What if I don't like the edits I want?"** → *"Small stuff — colors, copy, photos — unlimited edits included. Big stuff — new sections, integrations — custom quote, not locked in. We do that after you're live."*

5. **"What happens if I cancel hosting later?"** → *"Site comes down. You own the code — we hand it off. Most people stay because $39 covers hosting, domain, SSL, and edits — hard to beat."*

---

## Tab 6: Mindset

### Rewires that stay (from old playbook)
- Rejection is timing, not personal.
- One outcome beats ten features.
- Volume beats perfection.

### Rewires to update
| Old | New |
|---|---|
| Intangible product, slow ROI | Product is on the screen. Show it. |
| Build rapport for weeks before closing | The built site is your rapport. |
| Close on the call | Close on the reveal. Cold call just books it. |

### New rewires
- **Worst case is a portfolio piece.** Front-loading work isn't risk. Unsold sites become marketing assets.
- **Act busy even when you're not.** The 24-hr gap is the whole model. Don't break the frame.
- **Show, then tell the price.** Always in that order. Never inverted.

### Daily reminders (updated)
- Volume beats perfection — make the calls, fix the flow after.
- Show before you say a price.
- Stop talking the second they say yes.
- No-show is a follow-up, not a loss.
- Unsold ≠ wasted. Portfolio ≠ failure.

---

## Visual Design Constraints

Keep the existing aesthetic from `index.html`:
- Inter font (weights 400, 500, 600)
- White background, minimal borders, soft surface gray for notes
- Green "say this" / red "never say" / amber "tip" color coding
- Sticky tab nav at top
- Collapsible accordions for objections
- Max width 680px
- Mobile-responsive (single-column on <500px)

**Minor additions:**
- New tabs ("the gap", "reveal") follow existing tab styling.
- Build SOP subsection on pre-call tab uses the existing `.check-item` pattern.
- Objections tab gets a visual separator or sub-heading between "cold call" and "reveal" groups.
- Pricing table uses the existing `.offer` + `.offer-row` pattern.

---

## Open Items (to resolve before or during implementation)

1. **Post-April price.** What does $700 become on May 1? ($900? $1000? $1200?) Script currently says "bumps up after that" without a number. Pick one before launch — the urgency is hollow without a concrete delta.
2. **Blaztly.com readiness.** Confirm blaztly.com is live and presentable as a trust-buffer link. If not, that's step zero before this playbook can be used.
3. **Domain spelling.** Script uses "blaztly.com" (with Z, matching repo and current HTML). Voice-to-text has rendered it as "blastly.com" — confirm the actual live domain.
4. **Lead-slot calendar template.** Gap tab references "tomorrow 10 or 3" — whether these are literal defaults or just examples should be decided. A real calendar with bookable slots would simplify the close.

---

## Success Criteria

- Playbook reads as a flow, not a verbatim script. Caller can internalize the shape and adapt wording.
- Cold call fits in 60 seconds.
- Reveal fits in 5 minutes.
- Price is never mentioned on cold call.
- Every objection has a scripted answer that resolves in one line.
- Portfolio back-pocket is available but not required.
- Visual design preserves the existing ink-on-paper minimalism.
