# GTM Outbound Strategy — [Client] QA Audit Campaign

> **Rule of the build:** strategy first, tools second. This doc is the thinking layer.
> The tools (AI Ark, Clay, PlusVibe, ScaledMail, Claude Code) are only the execution layer
> that carries out what is decided here. Nothing gets built until this doc is settled.

---

## 0. Outcome (what success looks like)

| | |
|---|---|
| **Primary outcome** | Booked free QA-audit calls with in-ICP healthcare SaaS companies. |
| **The mechanism** | Free QA audit on the prospect's **staging environment** → report of **critical bugs** → prospect sees real business risk → upsell the paid backend QA offer. |
| **Success signal** | Positive replies → audits scheduled → audits delivered → paid conversions. |
| **Review cadence** | Weekly review of all live campaigns. Volume pushed fast; signal runs continuously alongside. |

**Open item:** confirm the exact **paid backend offer** the free audit converts into (ongoing managed QA, automated test-suite build, QA staffing, etc.). This shapes the copy's promise and the report's CTA.

---

## 1. ICP

- **Who:** B2B healthcare SaaS companies.
- **Geo:** USA only.
- **Buyers (title → who to address):** Founder, CEO, CTO, VP Engineering, Product Manager, QA Manager.
- **Why they buy:** healthcare software carries outsized risk — PHI integrity, compliance, uptime, and release velocity all collide. A single critical bug in staging that reaches production is expensive and, in healthcare, dangerous. The free audit makes that risk concrete before they've spent a dollar.

---

## 2. Two-campaign model

Both run at the same time. Volume creates broad coverage fast; signal catches the highest-intent accounts as they surface.

| | **Volume campaign** | **Signal campaign** |
|---|---|---|
| **Goal** | Maximum in-ICP coverage, fast | Reach accounts showing intent *now* |
| **Size** | 3,000–5,000 contacts per campaign | Smaller, rolling lists |
| **Segmentation** | Employee size × sub-vertical × pain point | By the triggering signal |
| **Copy** | Founder-led, 3–4 variations + spintax (segment-level) | Clay/Claygent 1:1 personalization tied to the trigger |
| **Cadence** | Push fast, review weekly | Continuous, added on top of volume |

---

## 3. Segmentation (volume campaign)

### 3a. Employee-size tiers — and how the angle shifts

| Tier | Reality inside the company | Angle |
|---|---|---|
| **1–10** | Usually no QA function. Founder/eng ship fast, test manually or not at all. | "You're shipping fast with no safety net — one critical bug in staging could cost a customer. Free audit, no strings." |
| **11–50** | First QA hire or an eng team stretched thin. Quality is ad-hoc. | "Your team is scaling faster than your test coverage. Here's where the gaps are — free." |
| **51–100** | QA exists but is drowning in release velocity vs. quality tension. | "Your QA team is outnumbered by release velocity. We'll pressure-test staging and hand you the critical list." |

### 3b. Sub-verticals (starter set — prune/edit)

| Sub-vertical | QA-lens pain points | Copy hook |
|---|---|---|
| **EHR / EMR** | Regression bugs across a huge feature surface; HL7/FHIR interoperability breakage; PHI data integrity | "One broken integration and charting stops. We find it in staging first." |
| **Telehealth / virtual care** | Real-time video/session reliability; cross-device & cross-browser QA; peak-load failures | "A dropped session is a missed appointment. We stress-test the call path." |
| **RCM / medical billing & claims** | Claims-calc bugs = direct revenue leakage; payer-integration regressions; edge-case coverage | "A rounding bug in claims is money out the door. We audit the math." |
| **Patient engagement / scheduling** | Notification/reminder delivery bugs; multi-channel (SMS/email) QA; scheduling race conditions | "A reminder that never sends is a no-show. We test every channel." |
| **Practice management** | Complex workflow regressions; role/permission bugs; data-migration issues | "Every workflow branch is a place to break. We map the ones you can't see." |
| **Behavioral / mental-health SaaS** | Consent/privacy flows; assessment-scoring accuracy; compliance | "Scoring and consent can't be 'mostly right.' We verify both." |
| **Clinical workflow / care coordination** | Integration failures; critical-alert reliability | "If an alert doesn't fire, that's the bug that matters. We hunt those." |
| **Health data / interoperability & analytics** | Data-pipeline correctness; report accuracy; interoperability | "Bad data in, bad decisions out. We validate the pipeline." |

> The full **tier × sub-vertical** grid is the campaign map: each cell = one campaign with its own pain point + hook. That's how you keep track week to week.

---

## 4. Signal campaign — intent-signal menu (starter set — prune)

Watch for these; each one builds a rolling list to enrich in Clay and personalize 1:1.

| Signal | Why it's intent | Angle it unlocks |
|---|---|---|
| Hiring **QA / SDET / Test Engineer** | They feel the QA gap and are acting | "Saw you're hiring for QA — want a free audit while the seat's still open?" |
| Hiring **eng at scale** (no QA req) | Velocity rising, quality risk rising | "Team's growing fast — here's what usually breaks at this stage." |
| **New funding** (Seed/A/B) | Pressure to ship + budget to fix | "Congrats on the raise. Now the pressure to ship 2x is on — let's find the risks first." |
| **Product launch / major release** | Fresh surface = fresh bugs | "New release live? Let us pressure-test it before your users do." |
| Job posts mentioning **manual testing / regression / release** | Named the exact pain | Mirror their own words back. |
| **New VP Eng / CTO / Head of Product** | New leader wants quick wins | "New in seat? A free QA audit is an easy early win to show the team." |
| **Public bug/review complaints** (G2, socials) | Pain is visible and admitted | Reference the theme (not the person) tactfully. |
| **SOC2 / HITRUST / HIPAA** compliance pursuit | Quality + audit trail under scrutiny | "Compliance push? Test coverage is the part auditors dig into." |

---

## 5. Copywriting approach

**Confirmed mapping:**
- **Volume → founder-led.** You (Mario) write as the client's founder. 3–4 variations per segment. Spintax everything. The test for every line: *"If this hit my inbox, would I reply?"* Paired with a compelling offer (the free audit).
- **Signal → Clay/Claygent 1:1.** Import the signal list to Clay, run Claygent to scrape the site and pull a personalization angle, then write 1:1 off the trigger.
- **Both** get a Claude Code polish pass before loading.

---

## 6. Execution layer (tools — the "how", after the "what")

| Stage | Tool | Job |
|---|---|---|
| List building | **AI Ark** | Build the in-ICP list (B2B healthcare SaaS, USA) + enrich. Complete list also available via the Claude Code MCP. |
| Secrets | **`.env` + `.gitignore`** | `AI_ARK_API_KEY` and all keys live in `.env`, never committed. |
| Personalization (signal) | **Clay + Claygent** | Site scrape + personalization angles for 1:1 copy. |
| Copy polish | **Claude Code** | Improve variations + generate spintax. |
| Infrastructure | **ScaledMail** *(confirm vendor)* | Purchased domains + inboxes. **Warm every mailbox 21 days before any send** (see §6a). |
| Sequencing | **PlusVibe** | Master sequence + per-tier / per-segment loads. |
| Upstream planning | **GTM systems-thinking agent** (this folder) | The interview step that produces this strategy before the build. |

### 6a. Deliverability — 21-day warmup (gate before launch)

- **Every purchased domain + inbox is warmed for 21 days before a single cold message goes out.** No campaign launches on a cold mailbox.
- Warmup runs automated inbox-to-inbox sends (via ScaledMail / PlusVibe warmup) ramping volume gradually to build a healthy sender reputation and land in the primary inbox.
- Target a **strong health score** before promoting a mailbox to live sending; keep a light warmup running underneath live campaigns to protect the score.
- **Sequencing:** buy domains/inboxes → configure SPF/DKIM/DMARC → start 21-day warmup → *only then* load PlusVibe campaigns and send. The warmup clock runs in parallel with list building and copy, so nothing is idle.

---

## 7. Guardrails (non-negotiable defaults)

- **Human approval gate before any send.** No campaign goes live unreviewed.
- **21-day mailbox warmup gate.** No mailbox sends cold traffic until it has warmed for 21 days and shows a healthy score (see §6a).
- **`logs/` from day one** — track every run, list pull, and send batch.
- **Version control** — private repo, `.gitignore` excludes `.env`, keys, `logs/`, `data/`.

---

## 8. Weekly operating rhythm

1. Review volume campaigns (reply rate, positive rate, meetings booked) per tier × sub-vertical cell.
2. Refresh the signal list from the menu; enrich + personalize the new hits.
3. Kill or double down on segments by performance.
4. Feed learnings back into the strategy (top of the loop).

---

## Open items to confirm
- [ ] Exact **backend/upsell offer**.
- [ ] **ScaledMail** exact vendor name/spelling.
- [ ] Prune sub-vertical + signal starter sets to the final list.
