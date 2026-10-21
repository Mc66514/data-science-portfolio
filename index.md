---
layout: default
title: Data Science Portfolio
---

# Data Science Portfolio

**GUO XIAOCHEN · MC66514 · Class G**  
CISC7204 Analysis of Media and Opinion Data, University of Macau

I work on questions about **media attention and public opinion** — who looks at what, for how long,
and what the shape of that attention tells us. My approach is deliberately small and checkable: one
open dataset, one clear question, code that re-runs from scratch, and figures that state their own
units, scale and source. I care more about a number I can defend than a number that looks impressive.

---

## Technical skills

| Area | Tools I use |
|---|---|
| Data wrangling | Python (`pandas`, `numpy`) — reshaping, resampling, joins, missing-data checks |
| Statistics | Log-linear regression, exponential decay models, block bootstrap confidence intervals |
| Visualisation | `matplotlib` (static, publication-style), `ggplot2` in R, annotation-first chart design |
| Reproducibility | Scripted pipelines, cached raw data, fixed random seeds, `requirements.txt`, Git |
| Publishing | Git and GitHub, GitHub Pages, Markdown, APA 7th referencing |

---

## Project showcase

### How fast does public attention decay? Evidence from 4,152 days of Wikipedia traffic

**Research question.** After the generative-AI surge peaked in 2023, how long did it take for public
attention to halve — and did the decay rate differ between a *product* page (ChatGPT), a *topic* page
(Artificial intelligence) and a *technique* page (Large language model)?

![Daily pageviews for three AI-related Wikipedia articles, November 2022 to September 2026](figures/fig1_attention_timeline.png)

**What the figure shows.** Daily pageviews for three English Wikipedia articles, bots excluded,
2022–2026 (log scale, 7-day centred mean). The ChatGPT article peaked at **347,289 views/day** in
April 2023 and fell to **17,229 views/day** by August 2024 — a **95% loss** — while the two
conceptual articles declined far less (−68% and −54%). Then attention came back: June 2025 was
**8.4×** the 2024 trough, whereas the topic and technique pages moved only ×1.4 and ×1.5. Fitting an
exponential decay over a common window gives a half-life of **258 days** for ChatGPT (95% CI
195–478) and **348 days** for the topic page (95% CI 293–450); the technique page shows no measurable
decay at all (R² = 0.01). The honest reading is that product-level attention behaves like a volatile
cycle, while subject-level attention is quieter and stickier — and that the two confidence intervals
overlap, so the ordering is a direction, not a settled fact.

**One-sentence summary.** Public attention to a product halves in roughly eight months, then can
return; attention to the underlying idea barely moves at all.

**How to read the figure.** The vertical axis is logarithmic, so equal vertical distance means equal
percentage change, and a constant decay rate is a straight line. The three articles differ in traffic
by two orders of magnitude, which is why a linear axis was rejected: it would have pressed the two
smaller series onto the baseline. Dashed vertical lines mark product releases, and the grey band is
the common window used for the half-life fits in Figure 2. No data are filtered out, and no second
y-axis is used, so no correlation is created by the chart form.

**Scripts and notebooks.** `src/fetch_data.py` (API download and tidy table) · `src/analyze.py`
(smoothing, peak/trough detection, log-linear fits, 2,000-resample block bootstrap) ·
`src/make_figures.py` (both figures, with every number read from `outputs/results.json`).

**Code and data.** [github.com/Mc66514/data-science-project](https://github.com/Mc66514/data-science-project)
— Python, `pandas` / `numpy` / `matplotlib`. Data: Wikimedia Pageviews API, **CC0 1.0** (public
domain), no credentials and no personal data.

**Status.** **Completed** — pipeline, figures and documentation are finished and re-runnable.

**What this project does not show.** Three things, stated on the page rather than buried in the
repository. First, pageviews measure *curiosity, not opinion*: opening an encyclopaedia article
records no sentiment, agreement or belief, so this is a measure of attention only. Second, it is
single-platform and single-language — English Wikipedia — and cannot speak for social media,
search, or Chinese-language attention, which may decay at a different rate. Third, the design is
descriptive: the June-2025 rebound is measured but not explained, and the 95% intervals for the
first two half-lives overlap, so the ordering of the three decay rates is a direction rather than a
settled result. A reader should leave with the shape of the decline, not with a causal claim.

---

![Decay curves and half-life estimates with bootstrap confidence intervals](figures/fig2_decay_and_half_life.png)

*Figure 2 — the same data indexed to each article's own July-2023 level, with the fitted decay lines
(left) and the resulting half-lives with 95% bootstrap intervals (right).*

---

## What I am working on next

A cross-language replication: the same measurement on Chinese Wikipedia, to see whether the 2025
rebound is an English-language phenomenon or a general one.

---

*Repository: `data-science-portfolio`. Built with GitHub Pages. Last updated 21 October 2026.*
