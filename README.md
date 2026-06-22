# Present Tense — Medical Oral Presentation Trainer

A free, browser-based **oral presentation** trainer for medical students and residents. Work through a realistic case, deliver your presentation (typed or dictated), and get instant rubric-based feedback.

> ⚠️ **Alpha testing.** Cases, scoring, and feedback are still being actively refined and may contain errors. For educational use only — not medical advice.

**Live site:** _(add your URL here after deploying)_

## Tracks

The landing page lets you choose a specialty track:

- **Emergency Medicine** (`index.html`) — **live.** 11 realistic ED cases presented track-board style (chief complaint and vitals only, no diagnosis given). You build and deliver a focused EM oral presentation.
- **Internal Medicine** (`im.html`) — **live.** Opens to a format chooser:
  - **H&P Presentation** — live. 5 bread-and-butter admission cases (decompensated heart failure, COPD exacerbation, community-acquired pneumonia, DKA, upper GI bleed). You present a full admission H&P, from summary statement through assessment & plan.
  - **Progress Note Presentation** — *coming soon.* Presenting a daily SOAP update on rounds.
- **Surgery** — *coming soon.*

Both Internal Medicine formats are **presentation** trainers (practicing how you present on rounds), not note-writing trainers.

## What it does

Shared across tracks:

- Each case gives you the **full chart** — for EM: HPI, exam, labs, imaging; for the IM H&P: HPI, review of systems, past history, medications, allergies, family/social history, exam, and data.
- Trainees **type or dictate** their oral presentation.
- **Instant rubric-based scoring (100 points)** with a per-category breakdown:
  - **EM (9 categories):** one-liner, HPI, pertinent history, physical exam, workup, most likely diagnosis, can't-miss differentials, plan/disposition, and flow/order.
  - **IM H&P (10 categories):** summary statement, HPI, review of systems, PMH/meds/allergies, family & social history, physical exam, data & studies, assessment, plan, and flow/order.
- **Flow & order** is scored by where each section first appears in the presentation, compared against the expected sequence — so presenting your assessment before the data costs points.
- Committing to an **assessment / most likely diagnosis** is required — omitting it is flagged as a critical miss.
- **Attending-style follow-up questions** that probe clinical reasoning, with model answers.
- A full **model presentation** for every case.

## Privacy

No login, no accounts, no analytics, no backend. Scoring runs entirely client-side — nothing typed or dictated ever leaves the browser.

## Notes & development

- Static site — no build step, no dependencies. Each track is a self-contained HTML file.
- **Voice dictation** uses the Web Speech API and works in **Chrome and Edge** (requires HTTPS, which any modern static host provides).
- To add or edit **EM** cases, edit the `CASES`, `SCORING`, and `ATTENDING_QUESTIONS` objects in `index.html`.
- To add or edit **IM H&P** cases, append to the `CASES` array in `im.html` — each case carries its own `scoring` keyword groups (one per rubric category) plus attending `questions`. The rubric weights live in the `RUBRIC` array.

## Deploying

This is a static site. Any of the following work:

- **GitHub Pages:** Settings → Pages → deploy from `main`
- **Netlify Drop:** drag this folder onto [netlify.com/drop](https://app.netlify.com/drop)
- **Cloudflare Pages / Vercel:** point at this repo (recommended for room to add a backend and free privacy-friendly analytics later)

## Disclaimer

For educational use only. Not medical advice. All cases are fictional. Currently in alpha testing.
