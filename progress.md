# Progress Log

Claude Code Cohort Project by Mario Okhiria. Last updated 2026-08-31.

> Latest: landing page storytelling pass. Hero reworked to a problem led hook ("Why do you need what I build?"). The 8 stage pipeline is now a scroll animated center spine chapter timeline, chapters alternating left and right. Diagram trimmed of two engineer only nodes (the env key note and SPF DKIM DMARC), both copies kept identical and rewired. Stack marquee dropped Excalidraw and Mermaid. Verified live in browser, pushed to main, auto deployed to Vercel.

---

## What this project is

Full go to market and outbound engine, built strategy first, as the Claude Code cohort project.

- **Offer:** a free QA audit on a prospect staging environment. Surface the critical bugs, hook the buyer, then upsell the paid backend QA.
- **ICP:** B2B healthcare SaaS in the USA. Buyers: Founder, CEO, CTO, VP Engineering, Product Manager, QA Manager.
- **Rule of the build:** strategy first, tools as the execution layer.

---

## Done so far

### 1. Strategy and planning
- Ran the planning thinking and wrote the full strategy doc before touching any tool.
- Confirmed the two campaign model: volume for coverage, signal for timing.
- Confirmed copy mapping: volume uses founder led copy plus spintax, signal uses Clay and Claygent one to one.
- Added the 21 day mailbox warmup gate and the human approval gate.

### 2. Deliverables in the repo
| File | What it is |
|------|------------|
| `strategy.md` | The strategy doc. The brain of the system, written before any tool was opened. Includes the tier by subvertical pain point grid, the intent signal menu, the tool layer, and the guardrails. |
| `diagram.html` | Interactive workflow diagram. Mermaid, fit to width, zoom and scroll. Opens in a browser. |
| `workflow.mmd` | The Mermaid source for the diagram. |
| `workflow.excalidraw` | The same flow as an Excalidraw canvas. Import at excalidraw.com. Verified it imports and renders. |
| `landing/index.html` | The animated landing page for this project. |
| `landing/diagram.html` | Copy of the diagram, embedded by the landing page. |
| `.env.example` | Template for the AI Ark key. |
| `.env` | Real env file. Git ignored, never committed. |
| `.gitignore` | Excludes `.env`, keys, `logs/`, `data/`, `.DS_Store`. |
| `data/` `logs/` `copy/` | Working folders for lists, run logs and copy. |
| `README.md` | Repo overview. |
| `gtm-systems-thinking-agent/` | The upstream planning agent that produces the strategy before the build. |

### 3. Landing page
- Standout, heavily animated GTM Engineer portfolio page for the cohort project.
- Live node network canvas background, animated grid, gradient headlines, typed role cycler, scroll reveals, glowing pipeline cards, a stack marquee, and glass cards.
- Sections: hero, the build, 8 stage pipeline, flow, two engine model, stack, guardrails, deliverables, contact.
- A dedicated flow section embeds `diagram.html` in a browser style frame with an open full screen link, so a viewer can see and explore the flowchart in the page.
- Zero dashes in all visible copy, on the page and inside the embedded diagram.

### 4. Hosting
- Live on Vercel: **https://claude-code-cohort-project.vercel.app**
- The Vercel project is git linked to the GitHub repo with root directory `landing/`, so every push to `main` auto deploys.
- Verified live: the flow section and the embedded interactive diagram both render on the deployed URL.

### 5. Source control
- Pushed to GitHub: **https://github.com/mareopuzo/claude-code-cohort-project**
- The repo is scoped to this project folder only. The home folder is a separate git repo and was not touched.
- `.env` stayed out of the commit.

### 6. Cleanup
- Deleted the earlier stale Vercel project `mariogtmcohort` from the first manual deploy. The git linked project is now the single canonical one.

---

## Conventions locked in
- No dashes in any visible web copy. Rephrase instead.
- Secrets live in `.env`, which is git ignored. Only `.env.example` is committed.
- The whole project stays self contained in this folder. No cross folder references.

---

## Open items and next steps
- Confirm the exact paid backend offer that the free audit upsells into.
- Confirm the exact ScaledMail vendor name and spelling.
- Prune the starter subverticals and the intent signal menu to the final list.
- Begin the execution layer: build the first list in AI Ark, then segment, then draft the founder led copy.
- Optional: point a custom domain at the Vercel site.
