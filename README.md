# RTL Resume Reviewer

A free, open resume reviewer for **RTL / ASIC / FPGA engineers** that reads a resume the way a hiring panel does — not the way an ATS scores it.

It runs on **your** AI subscription. Nothing is uploaded, nothing is stored, and no account is required.

---

## Why this exists

Keyword checkers are a commodity. What they cannot tell you is what a line actually *signals* to someone who has sat on the other side of the table — that "worked on RTL to GDSII flow" at three years' experience reads as having touched one stage, or that naming your employer's unannounced project codename ends the conversation before anyone reads your bullets.

This rubric encodes that judgment — 10+ years in silicon and 25+ engineers mentored, built from real resumes and real outcomes and written down as explicit, checkable rules.

**It is deliberately open.** Read it, fork it, argue with it. It tells you the questions a panel will ask. It cannot tell you whether your answers survive.

---

## What it does

Your resume is screened three times, by three readers with different powers. The review tells you **where yours stops**:

| Layer | Reader | Kills you by |
|---|---|---|
| **1** | ATS parser | being unparseable |
| **2** | Recruiter, ~30 seconds, no domain knowledge | not matching the requisition fast enough |
| **3** | Technical hiring manager | not convincing someone who knows the work |

Most tools only see layer 1. Most advice only addresses layer 3. The gap between them is where good engineers disappear.

You get a self-contained HTML report — open it, print to PDF, no install — with every finding quoted against your actual text, the probing question each one implies, and the strengths you are already carrying and under-using.

**It also finds what you have buried.** Resumes routinely carry their strongest asset already on the page and mis-weighted — shipped silicon below the fold, debug capability never named as debug, a career pivot showing only as overlapping dates. That is usually the most valuable output.

---

## Install

**Claude Code** — clone into your skills directory:

```bash
git clone https://github.com/iam-palash/rtl-resume-reviewer ~/.claude/skills/rtl-resume-review
```

Then just ask: *"review my resume"* with the PDF attached.

**Any other assistant** — open [`PROMPT.md`](PROMPT.md), paste it, attach your resume. Same rubric, no install. You lose the generated HTML report and get structured markdown instead.

---

## Scope

**Built for:** RTL design, ASIC, FPGA, SoC integration, and directly adjacent silicon roles.

**Not built for:** software, non-hardware engineering, or management résumés. It will tell you so rather than give you confidently wrong advice.

**Partially useful for** verification, physical design and DFT — layers 1 and 2 are discipline-neutral, but the layer-3 judgment is RTL-shaped and will say where it is out of its depth.

**Experience bands matter.** The rubric switches behaviour below two years — academic projects are the whole case for a fresher, not padding. It resolves your band before applying anything.

---

## Privacy

Your resume is processed by your own AI assistant and goes nowhere else. This repository contains no data, no telemetry, and no network calls. Nothing in the rubric was copied from anyone's resume — every illustration is invented.

---

## Contributing

The rubric lives in [`rubrics/rtl.md`](rubrics/rtl.md) as plain markdown. Each entry has a checkable `Signature`, what it `Reads as`, the `Probe` it implies, a `Weight` and a `Layer`.

**Adding a discipline.** Physical design, DV and DFT deserve their own rubrics, written by people who interview for those roles — not by an RTL engineer guessing. If that is you, open a PR with `rubrics/<discipline>.md` in the same format. That is the main thing this repo needs.

**Disagreeing with an entry** is welcome, especially with a counter-example. The rubric was built inductively from real resumes and is shaped by that; entries that turn out to be local rather than general should be cut.

---

## Limits, stated plainly

Built inductively from real resumes, so it is sharper on some failure modes than others. Treat it as one engineer's judgment written down and made checkable, not as a validated instrument.

It reviews a document. It cannot assess your engineering, and a resume it likes is not a job offer.

---

MIT licensed. Built alongside the mentorship practice at **[hwthinking.in](https://hwthinking.in)**.
