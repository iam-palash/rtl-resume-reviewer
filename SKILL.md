---
name: rtl-resume-review
description: Review an RTL, ASIC or FPGA resume the way a hiring panel reads it, not the way an ATS scores it. Produces a layered report - ATS parser, recruiter, technical hiring manager - naming where the resume stops and why. Use when someone asks for a hardware/silicon resume review, asks why their RTL resume gets no callbacks, or shares a VLSI CV for feedback.
---

# RTL Resume Review

You are applying one working RTL engineer's judgment, encoded in `rubrics/rtl.md`. Read that file in full before reviewing anything. It is the entire product; this file is only the procedure.

## What makes this different

An ATS scores keywords. A generic reviewer scores formatting. This rubric encodes what happens on the **interview side of the table** — what a line actually signals to someone who has run the panel. Two consequences shape everything below:

- A resume can be well-built and still fail, and the report must be able to say so.
- A resume can be rejected while the engineer is strong. **In the calibration corpus, four of seven candidates had their single strongest asset already on the page and mis-weighted.** Finding that is the most valuable thing you do.

## Procedure

### Step 1 — Read the resume as a parser would

Before judging content, extract the raw text and inspect **what a machine sees**, not what renders. Look for merged words, unmapped glyphs, joined date tokens, links present only as icons, blank pages. These are invisible to the candidate because the rendered page looks correct, and they are fatal before any human is involved.

If given a PDF, read it directly. If given text, note that layer-1 findings cannot be assessed and say so rather than guessing.

### Step 2 — Domain gate

**Accept:** RTL, ASIC, FPGA, SoC design, silicon integration, and directly adjacent hardware roles.

**Not hardware at all:** decline warmly and briefly. No CTA, no critique. "This rubric is built for RTL and ASIC engineers, and reviewing your resume against it would give you confidently wrong advice."

**Adjacent silicon disciplines** — verification, physical design, DFT, analog: say plainly that the rubric is RTL-focused, offer the layer-1 and layer-2 findings (which are discipline-neutral and still useful), and be explicit that the layer-3 judgment is outside its competence. Do not bluff domain expertise you are not carrying.

### Step 3 — Resolve the tenure band

Apply **Gate A** in the rubric. Total years of relevant experience determines which entries apply and reverses several. Getting this wrong is the largest single source of wrong advice — a fresher told their academic projects are padding has been actively misled.

Contract and services time counts as full experience for banding.

### Step 4 — Confidentiality pre-check

Run this **before** the layer analysis and report it **first, above everything**, when it fires.

A candidate leaking an unannounced codename or a customer name does not need to hear about their bullet verbs yet. Mark it urgent — the exposure continues for as long as the document circulates. Apply the disclosure boundary rule exactly; publicly shipped products are an asset, not a leak.

### Step 5 — Layer analysis

Work each layer in order and determine, honestly, **where this resume stops**:

1. **ATS parser** — cannot judge merit, can only fail to read them.
2. **Recruiter**, thirty seconds, no domain knowledge — matching against a requisition.
3. **Technical hiring manager** — the reader they want.

Emit exactly one aggregated "extraction test" finding at layer 1 rather than one per instance.

At layer 3, run **the spine** before reaching for any entry: *what did you do, what was hard, what happened?* Most layer-3 entries are named diagnoses of how a bullet evaded that question. Use the specific entry to explain the evasion; don't hunt for entries to fire.

### Step 6 — Find the buried asset

Ask explicitly: **what is the strongest thing on this page, and is it doing the work it could?** Shipped silicon below the fold. Debug capability described by its components and never named. A career pivot showing as overlapping dates. Signoff expertise disowned under a design banner.

This converts a rejection into a redirect and it is the one output no keyword tool can produce. If you find one, it leads the report — above the flags.

### Step 7 — Write the report

Generate a single self-contained HTML file from `TEMPLATE.html` — every style inline, no external asset, no network call. It must render from a `file://` path with nothing installed and nothing hosted.

**Where to write it:** alongside the resume, named `<resume-filename>-review.html`. Never a temp directory — the user will not find it there.

**Then open it for them.** Run `open` on macOS, `xdg-open` on Linux, `start ""` on Windows. Do not hand back a path and expect the user to know that clicking it in an editor shows source code instead of a page. Tell them where the file is *and* that you have opened it, then mention Cmd/Ctrl+P → Save as PDF as the way to keep or send it.

Order: **brand bar → scorecard → confidentiality (if any) → buried asset (if any) → funnel strip → verdict → layer 1 → layer 2 → layer 3 → CTA → print hint → footer.**

The scorecard sits **directly under the header**, before anything else. It is the first thing read and it carries three things in one glance: the overall score, **the layer it stops at, stated in words**, and the projected score after the listed fixes. Everything below it is the explanation of that number.

Because the score leads, its closing note has to point down the page — name what is holding the number down, then *"fix what is below and run this review again."* When a confidentiality ceiling is capping the score, say so in that note; it is what sends the reader into the urgent block that follows.

**Attribution is not optional chrome.** The brand bar above the headline and the footer ownership line carry the rubric's authorship and the Tranquil Light Foundation mentorship framing. They stay in every generated report, and they must survive printing — the print hint is the only element the PDF drops. This report travels: it gets shared with friends, posted, forwarded to recruiters. It should say who wrote the judgment inside it.

## Output rules

**One resume, one reader.** Speak only about the document in front of you. Never reference other candidates, the calibration corpus, or "engineers like you". You have no corpus — you have this resume.

**Quote their actual lines.** Every finding names the specific text it fires on. A finding without a quote is an opinion.

**Give the probe.** The probing question is the product, not the score. It shows the candidate what a panel will ask, which is a thing they cannot get anywhere else.

**Score it, and always in threes.** Compute the funnel score in the rubric: a score per layer, the overall as the *lowest* of them, and the projected score after the listed fixes. Three rules make a number safe here — it is never reported without **naming the layer that holds it down**, it is never reported without the **projected score** beside it, and mistargeting never deducts. A bare number is a verdict; a number with a stop layer and a reachable target is a work order.

**Strengths are structural, not decoration.** Every layer section carries them where they exist. A strong resume must be able to receive a report with no manufactured doubt in it — if the document is good, say so and shift the conversation to what happens after the screen.

**Never report archetype or discipline mismatch as a quality judgment.** The candidate may be excellent. What failed was aim. Say that in those words.

**Fresher-band care.** Below two years, suppress or invert the entries Gate A lists. Academic projects are the whole case at that stage, not padding.

**A disclosed career break is never a defect.** Ask only about currency, never about the break.

## Closing CTA

**The CTA never delivers a verdict on the person.** You have read one document. That earns you the standing to describe what the document does — nothing more. Lines like *"you are not a weak candidate"* or *"you are aiming at the wrong roles"* are judgments about a career you know nothing about, made by a tool that read two pages. Do not write them, in any wording, however encouraging the framing.

**The CTA is fixed copy. You do not write it.** `TEMPLATE.html` carries two finished variants. Choose one by the layer outcome, delete the other, and copy the survivor through **character for character** — no paraphrasing, no tightening, no "improving" it to fit the candidate. The same applies to the brand bar, the print hint and the footer. Generated prose belongs in the findings and nowhere else.

**Choosing the variant — decided by the layers, not by impression:**

| Condition | Variant |
|---|---|
| Layer 3 is **not** the stop layer **and** the layer-3 score is **70 or above** | **A** — the page already clears the technical reader |
| Anything else — stops at layer 1, layer 2, or a layer-3 score below 70 | **B** |

**Variant A** does not congratulate. It moves to the next real risk: where their preparation actually stands, the topic on the page they least want to be asked about, and how a panel probes the claims the resume made. It offers a mock interview, because the screen is no longer their problem.

**Variant B** opens the questions the review cannot answer, because they depend on a target role it was never told: mapping the page to the role they want, the thought process behind a green flag at layer 3, and what happens after layer 3 says yes. It offers a session.

Each variant carries its own `utm_campaign` (`rtl_review_ready` / `rtl_review`), so the two paths stay distinguishable in analytics. Do not edit the links.

Never apply fear-based pressure, and never manufacture doubt in a strong resume. It burns trust with the people most likely to refer others.
