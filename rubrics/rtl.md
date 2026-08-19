# RTL / ASIC / FPGA resume rubric

Encodes the judgment of a working RTL engineer — 10+ years in silicon, 25+ engineers mentored — built from real resumes and real screening outcomes. Applied by `SKILL.md`.

**How to read an entry.** `Signature` is the checkable condition — it must be decidable from any resume, never from a memorised example. `Reads as` is what the reader concludes. `Probe` is the interview question the finding implies. `Weight` and `Layer` drive the report.

**Weights — closed set, single value, nothing else.**

| Weight | Meaning |
|---|---|
| `reject` | this alone loses the screen |
| `reject-contributing` | not fatal alone; three or more is a rejection |
| `probe` | a panel will push here; be ready |
| `advisory` | worth fixing, never counts against the candidate |
| `strength` | working for the candidate — surface it, never flag it |

Escalation lives in its own field (`Escalates to:`), never inside the weight.

**Layers.** `0` pre-check · `1` ATS parser · `2` non-technical recruiter, ~30 seconds · `3` technical hiring manager. Reported at the layer where it is fatal.

**Illustrations are invented.** No example below is quoted from a real resume.

---

## Scoring — the funnel score

Score **each layer separately**, out of 100. Every layer starts at 100 and loses points for what fires in it:

| Weight | Points |
|---|---|
| `reject` | −40 |
| `reject-contributing` | −12 |
| `probe` | −5 |
| `advisory` | −2 |
| `strength` | +4, capped at +12 per layer |

Clamp each layer to 0–100.

**The overall score is the lowest layer score, never the average.** A resume travels exactly as far as its weakest filter — averaging lets a clean parse hide a dead layer 3, which is the specific lie this rubric exists to stop telling. The layer holding the minimum **is** the stop layer, and it must be named in the report next to the number: *"Stops at layer 2 — recruiter."*

**Confidentiality is a ceiling, not a deduction.** Any unresolved leak caps the overall at **40**, whatever the layers say. It is fatal, invisible to the candidate, and free to fix — so it should dominate the number and then vanish from it entirely on the next run.

**Mistargeting never deducts.** Archetype or discipline mismatch is reported as aim, not quality, and takes no points off. A strong signoff engineer chasing design roles scores as the strong engineer they are, with the mismatch named beside the score. Scoring aim as weakness would reproduce the exact error this rubric was built to correct.

### The projected score

Recompute the whole thing with every `reject`, `reject-contributing` and confidentiality finding resolved — leaving `probe` items in place, because a probe is a question to prepare for, not a defect to erase.

**Cap the projection at 85.** A rewrite that has not been written yet is not evidence, and a tool that promises 95 for an afternoon's editing is lying to keep someone happy. 85 is "gets calls" — the honest ceiling for fixes that are already listed and not yet done.

Report both numbers together: **where they are now, and where the fixes in this report put them.** The gap is the point. A candidate at 34 who can reach 79 by fixing what is already listed will edit the document and run the review again, which is the only way this tool improves anything. Never report the current score alone — a bare number is a verdict, and a verdict is not actionable.

**Band names for the overall score:**

| Score | Band |
|---|---|
| 85–100 | Clears all three screens |
| 70–84 | Gets calls — expect pressure in the room |
| 50–69 | Stalls at *{stop layer}* |
| 30–49 | Stops at *{stop layer}* |
| 0–29 | Does not survive first contact |

`{stop layer}` is substituted, never printed literally. Use these labels exactly:

| Layer | Label |
|---|---|
| 1 | the parser |
| 2 | the recruiter screen |
| 3 | the technical screen |

So a resume scoring 40 whose minimum sits at layer 3 is banded **"Stops at the technical screen"** — never "stops at the named layer", which is an instruction to you, not a phrase for a reader.

### The score note — fixed sentences

The note under the layer row is **assembled from fixed sentences with numbers substituted**, not written fresh. It states arithmetic, so it must read identically for every candidate and must never invent specifics like how many words an edit takes.

1. Always: *"Your layers score `{L1}` / `{L2}` / `{L3}`. The overall is the lowest of the three, not the average."*
2. Only when the confidentiality ceiling is binding: *"The confidentiality finding below caps any resume at 40 until it is removed — without it, this page scores `{uncapped}`."*
3. Always: *"Clearing what is flagged below projects to `{projected}`. Fix it and run this review again."*

Nothing else goes in the note.

---

## Gate A · Tenure band — resolve before anything else

Total years of relevant experience determines which entries apply and, for several, **reverses their polarity**. Getting this wrong is the single largest source of wrong advice.

| Band | Years | What changes |
|---|---|---|
| **Fresher** | 0–2 | Academic projects, coursework and GPA are *assets*, not padding. Education may lead. Depth expectations do not apply. Ownership language is not expected. |
| **Early** | 2–5 | Transition band. Academic content should be receding; one strong project may remain. Education moves below experience. |
| **Mid** | 5–10 | Full rubric applies. Academic content is padding. Ownership and outcomes expected. |
| **Senior** | 10+ | Additionally expects scope, judgment and cross-team evidence. Absence of leadership signal becomes a finding in itself. |

**Polarity switches for 0–2 years — these entries invert or are suppressed:**

| Entry | Fresher behaviour |
|---|---|
| Education placed above experience | **suppressed** — correct at this band |
| Seniority-inappropriate credentials | **suppressed** — course certificates and ranks are assets |
| Volunteering a weak metric | `advisory` only — a GPA is expected; a weak one is a positioning problem, not a defect |
| Output volume below tenure | **suppressed** |
| Placement-cell template padding | reduced to `advisory` for Hobbies/Languages; Declaration block still `reject-contributing` |
| Academic projects | scored by *Academic project indistinguishable from a course exercise* below, not as padding |

**Contract and services time counts as full experience** for banding. Whether it transfers is a separate question handled by *Services-to-product transition*.

---

## 0 · Pre-check — runs before layer analysis

### Confidentiality exposure

**Signature:** The resume discloses any of — an internal project codename; a process node paired with a foundry or IP vendor; an unannounced product's purpose or target market; the identity of an employer's customer against specific work; internal block, tool or organisation names not public.
Three rungs, ascending: **(1)** own-employer internals — codename, node/vendor pairing, unannounced roadmap. **(2)** a customer named against any work. **(3)** a customer named against an unannounced programme.
**Reads as:** A judgment failure about commercial confidence, not carelessness — *if they published that about their current employer, they will publish it about us.* Customer lists and programme assignments are what competitors pay to learn. It is never raised in an interview, so the candidate cannot learn it any other way.
### THE DISCLOSURE BOUNDARY — one rule, cited by every naming entry

Several entries reward naming and this one rejects it. The boundary is not *specific vs vague*; it is:

> **Name a party or product only if (a) the product is publicly announced or shipped, or (b) you were embedded on that organisation's team as your de facto employer and say so plainly.**

Everything else is described by type. Under this rule: a shipped consumer platform is an asset (*Shipped silicon buried*); an unannounced codename is a reject; a client you sat inside for two years is nameable with the arrangement stated (*Recognisable client buried behind the staffing employer*); a customer your employer merely builds for is not.
**Safe rewrites, which lose nothing:** codename → "a 7nm data-centre IO chiplet"; customer → "a leading EV manufacturer's AI accelerator programme"; internal tool → the standard it implements. Public architecture (AMBA, UCIe, PCIe, Arm MMU-700) stays.
**Probe:** —
**Weight:** `reject` · report first, above the layer analysis, and mark it urgent — exposure continues while the document circulates
**Layer:** 0

---

## 1 · ATS parser

*It cannot judge merit. It can only fail to read the candidate — after which nobody else gets the chance. Every entry here shares one root cause: damage that exists only in the extraction layer, which nobody inspects because the rendered page looks correct.*

**Report rule:** emit **one** "extraction test" finding enumerating every instance below, taking its weight from the most severe. Do not list four separate findings.

### Broken word spacing on export

**Signature:** Extracted text contains merged words ("as wellas", "duringNoC"), missing spaces after punctuation ("Optimization.Involved"), joined date tokens ("March2024"), or spaces inserted mid-word.
**Reads as:** Parsers segment on whitespace to find sections, read dates and isolate skill tokens. Joined tokens do not yield the skill; joined dates do not parse. The extracted profile is built from damaged input.
**Probe:** —
**Weight:** `reject` — and the cheapest fix available to any candidate
**Layer:** 1

### Unsupported glyphs

**Signature:** Extracted text contains replacement characters or unmapped codepoints, typically from decorative icons in the header.
**Reads as:** The glyph renders correctly on screen and extracts as garbage. When it sits inside the title line it corrupts the token an ATS uses to classify the applicant.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 1

### Contact links present only as icons

**Signature:** A LinkedIn, GitHub or portfolio link exists as a clickable icon with no URL or handle rendered as text.
**Reads as:** Extraction returns the anchor, not the destination — so to a parser, and to anyone reading a printed or converted copy, the profile does not exist. Distinct from the glyph entry: the character may extract cleanly and the *destination* still be invisible.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 1

### Blank or near-empty page in the exported file

**Signature:** The document contains a page with no content, or a final page under ~15% full.
**Reads as:** The artifact was never opened after export. Visible in the page count before a word is read.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 1

---

## 2 · Recruiter

*Thirty seconds, no domain knowledge, matching against a requisition. Everything that helps them must be plain and early.*

### Years of experience never stated

**Signature:** No total years-of-experience figure appears anywhere; it can only be derived by summing employment date ranges.
**Reads as:** Every downstream judgment — is this claim proportionate, is this title earned — depends on the tenure number. Withholding it forces arithmetic before assessment, and a screener under load does not do arithmetic.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Unfilled template placeholder

**Signature:** A sentence retains an unedited placeholder — most commonly a missing number, as in "with years of experience in…".
**Reads as:** An unedited blank in the first line of substance, on the document the candidate controls most tightly. Whatever care they claim over sign-off discipline, they did not re-read their own opening sentence.
**Probe:** —
**Weight:** `reject-contributing`, near-fatal on a senior resume where the claim is judgment
**Layer:** 2

### Summary paragraph with no heading

**Signature:** Prose sits between the contact block and the first section heading, unlabelled, while every other section is labelled.
**Reads as:** The reader meets prose with no signpost saying what it is or whether it can be skipped — from the one section whose job is to orient them.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Career objective instead of a summary

**Signature:** A section headed "Objective" or "Career Objective", or a summary written in the first person describing what the candidate seeks rather than what they offer.
**Reads as:** Candidate-centric where the reader needs reader-centric. "Passionate about contributing to innovative projects" is true of every applicant and therefore evidence of nothing. The convention is decades out of date, which also dates the document.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Education placed above experience by a working professional

**Signature:** The education section precedes professional experience on a resume showing two or more years of relevant employment. Aggravated by a "Relevant Coursework" line.
**Reads as:** Campus-placement ordering kept past its usefulness. It says the candidate still identifies as a recent graduate and delays their strongest evidence past the point where a scan decides. Frequently a concealment tell — education leads because the early career is weak — which trades the strongest card for the weakest.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Recognisable client buried behind the staffing employer

**Signature:** In a contract or staffing arrangement, the payroll company occupies the prominent employer line while a well-known client appears only inside the role line or a parenthetical.
**Reads as:** A technical manager reads the whole entry and registers the client's silicon. A recruiter reads employer names where employer names live, does not recognise the firm, and moves on — so the one word that would have bought attention never lands.
**Fix is placement, not concealment.** "Client (via Staffing Firm) — SoC Team" keeps the arrangement honest; misrepresenting a contract as direct employment is a worse failure and it gets caught.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Experience and projects in divorced sections

**Signature:** Employment entries carry little or no content, and a separate projects section carries the substance without naming which employer each project belongs to.
**Reads as:** To place any piece of work the reader must hold employment date ranges against project date ranges across pages. A screener does not do that, and forms an impression of vagueness instead. This is what produces the question *"so where exactly are you working?"*.
**Note:** when this fires, it supersedes *Prior role left undescribed* — the empty roles are a layout consequence, not selective silence.
**Probe:** "Which of these were at your current employer and which were not?"
**Weight:** `reject-contributing`
**Layer:** 2

### Training listed as professional experience

**Signature:** A course, bootcamp or certification programme is given a dated entry inside the experience section, alongside employers — often with the section renamed to accommodate it.
**Reads as:** Honest and self-defeating. It invites training and employment onto the same scale and dilutes the section carrying the case. A section renamed to fit weaker content is a section that should have excluded it.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Prior role left undescribed

**Signature:** **Selective** silence — some employment entries carry bullets and at least one carries only a title and dates.
**Reads as:** Silence beside description reads as concealment even when the truth is only irrelevance, and the reader invents the explanation. Where *no* role carries content, this does not fire — see *Experience and projects in divorced sections*.
**Probe:** "What were you doing in that role, and what made you move?"
**Weight:** `probe`
**Layer:** 2

### Contact block over-disclosure

**Signature:** The contact block contains any of — date of birth, full residential address, marital status, nationality, photograph, or a national identity number. Ascending: city only is correct; a full street address is advisory; **date of birth and above is a reject-contributor**.
**Reads as:** Date of birth invites age-based filtering the moment it is visible and, with a name and phone number, is a standing identity-fraud exposure on a document circulated to strangers. None of it serves any hiring purpose in any market, and all of it dates the template.
**Probe:** —
**Weight:** `reject-contributing` at DOB or above; advisory below · flag removal as urgent
**Layer:** 2

### Volunteering a weak metric

**Signature:** A below-average quantitative credential is stated unprompted years after it stopped being requested — most often an undergraduate GPA on a resume with three or more years of experience.
**Reads as:** Self-inflicted. Nobody at that stage is asked for a grade, and a weak one supplied voluntarily creates a doubt that would never otherwise have formed — often standing directly beside the employer name that was doing the real work.
**Rule:** state a metric only if it argues for you. Degree, institution and year suffice.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Seniority-inappropriate credentials

**Signature:** Listed achievements that are entry-level, academic, or non-professional, on a resume with substantial experience — introductory course certificates, entrance-exam ranks, class rank, sports or social awards.
**Reads as:** Not merely irrelevant — *wrong for the level*. The same certificate is an asset on a graduate resume. Here it says the candidate cannot judge what is noteworthy at their own seniority, on the document whose job is judging noteworthiness. Everything listed should clear the bar set by the strongest item.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Placement-cell template padding

**Signature:** Sections carrying no hiring information — Declaration with place/signature, Personal Traits ("Adaptable", "Team Player"), Hobbies, Languages Known, Marital Status.
**Reads as:** A college placement template never revised for industry. Self-asserted traits are unfalsifiable and therefore worthless, and the block consumes space that should carry technical depth.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Unexplained gap in the timeline

**Signature:** A gap of twelve months or more between education and first employment, or between roles, that the document never addresses. Gaps under twelve months do not fire.
**Reads as:** A senior reader always notices, and silence invites the least generous explanation. The gap is rarely disqualifying — the silence is, because it starts the reader hunting for reasons, after which minor flaws that were invisible begin to count.
**Probe:** "What were you doing during that period?"
**Weight:** `probe` — the trigger that converts a pause into a search for reasons
**Layer:** 2

### Title velocity inside one employer, unexplained

**Signature:** A promotion materially faster than the level normally implies — for example two levels inside twelve months — with nothing accounting for it.
**Reads as:** Ambiguous by construction, resolved by the reader alone. Either an exceptional promotion, which is among the strongest signals a resume can carry, or a local title convention that will not travel and will be silently discounted.
**Probe:** "What were you trusted with after the promotion that you were not before?"
**Weight:** `probe` — frequently a buried strength
**Layer:** 2

---

## 3 · Technical hiring manager

### THE SPINE — apply before any entry below

Every bullet must answer: **what did *you* do, what was hard about it, and what happened?**

Most entries in this section are named diagnoses of *how* a bullet evaded that question. Run the spine first; reach for a specific entry only to explain the evasion.

| Evasion | Entry |
|---|---|
| says too little — names territory, claims nothing | *Scope statement posing as accomplishment* |
| answers about proximity, not authorship | *Coordination verbs without artifacts* |
| answers about the artifact, not the engineer | *Specification register* |
| answers about nothing at all | *Experience section carries no information* |

### Scope statement posing as accomplishment

**Signature:** A bullet names domain-specific territory a specialist would recognise — a subsystem, protocol, deliverable or check — but attributes no action, decision or outcome to the author. Test: the bullet would be **false** on an engineer's resume in a different domain, yet **true** for every engineer on this candidate's own team.
**Reads as:** The role's job description, not this person's contribution. Broad and bold reads as senior; it is actually the absence of a claim, because nothing stated can be attributed.
**Probe:** "Which of these did you own end to end, and what decision did you make that another engineer might have made differently?"
**Weight:** `probe` → `reject` if unanswerable
**Layer:** 3

### Coordination verbs without artifacts

**Signature:** Bullets led by Led, Drove, Defined, Coordinated, Managed, Partnered, Contributed, Supported — naming no artifact that was built. Fires when a majority of bullets in a role take this form.
**Reads as:** Coordination language describes proximity to work, not authorship of it. At senior level the reader wants what you personally designed and what was hard about it; polished verbs about driving and partnering answer a different question. Where the shift to coordination is real, the fix is to own it and evidence it as leadership — scope, headcount, decisions, delivery — rather than to claim leadership verbs with neither artifacts nor outcomes.
**Probe:** "Of everything here, what did you build with your own hands, and what was the hardest decision inside it?"
**Weight:** `probe` → `reject` if unanswerable
**Layer:** 3

### Specification register

**Signature:** A bullet contains three or more technical noun phrases — components, interfaces, standards, parameters, modes — and **zero** statements of difficulty, decision, or outcome. Reads as an extract from a design document.
**Reads as:** Specificity about the artifact is not evidence about the engineer. The reader learns exactly what the block is and nothing about who built it — not what nearly failed, not what was chosen, not whether it shipped. High decode cost, low signal yield: dense technical writing feels like proof of depth to the author and is impenetrable to everyone else.
**Also diagnostic of archetype:** spec register is a block owner's native language, written for people who already share the context. Integration and lead roles are translation jobs, so writing that never translates is evidence about the kind of engineer this is, independent of content.
**Probe:** "Take the block you are proudest of. What nearly went wrong, what did you change, and how did you know it worked?"
**Weight:** `probe` · `reject-contributing` for integration and lead roles, where communication is the job
**Layer:** 3

### Experience section carries no information

**Signature:** Bullets contain **no domain-specific noun** at all — no subsystem, protocol, tool, standard or artifact. Test: the bullet would be equally true on a resume from an unrelated engineering discipline. Typical forms: "delivering high-quality systems", "managing projects to meet deadlines", "staying updated with industry standards", "engaged in continuous learning".
**Reads as:** The section would be unchanged with another engineer's name on it. "Staying updated" and "continuous learning" are not accomplishments; they describe holding a job. Uniform, hedged, specificity-free phrasing increasingly reads as machine-generated, which is its own signal.
**Aggravator:** where a separate projects section carries the real content, the reader meets the emptiest section first and many never reach the substance.
**Probe:** "Pick one week from last year. What were you actually doing?"
**Weight:** `reject` where this is the primary content; `reject-contributing` where a projects section rescues it
**Layer:** 3

### Primary identity claim unevidenced

**Signature:** The **single** competence named first in the summary — or echoed by the job title — appears nowhere in the body as something the candidate personally did. Fires on exactly one item.
**Reads as:** The document's organising premise, unsupported. The reader does not conclude the claim is false; they conclude something quieter and worse — that the candidate no longer does this, or never did it in a way they could defend. At senior level that is close to fatal, because seniority *is* the claim to have done the thing deeply.
**Invisible to the author,** who knows what they have done and assumes it will be inferred.
**Probe:** "What is the last thing you personally built in that discipline? What did it do, and what did you have to decide?"
**Weight:** `reject`
**Layer:** 3

### Summary claim unevidenced

**Signature:** Any summary assertion **other than** the primary identity claim — a quantified achievement, a secondary competence, a leadership claim — that the body never supports. Checkable claims (tapeout counts, team sizes, percentages) fire hardest.
**Reads as:** A summary is a set of promises the body has to keep. The strongest quantified claim asserted once, where claims are cheapest, and then abandoned, inverts its own value — a reader who wants to believe it has nowhere to go.
**Boundary:** the first-named competence is *Primary identity claim unevidenced* and weighs `reject`. Everything else is here.
**Probe:** "You mention that in your summary — walk me through one instance."
**Weight:** `probe`
**Layer:** 3

### Role archetype mismatch, unbridged

**Signature:** The evidence base sits in a different archetype from the role applied for, and nothing on the document bridges the two. Within RTL the archetypes are: **block/IP design** (depth), **SoC integration** (depth *and* breadth), **verification**, **physical design**, **signoff/quality** (lint, CDC, LEC, UPF, synthesis), and **architecture**.
Common misreads: block-internal integration is not SoC integration; running quality checks on RTL is not designing RTL.
**Reads as:** Quality does not transfer between archetypes. The failure is not the mismatch — specialists move constantly and it often works — it is that the document shows no awareness the target is a different job.
**Report as a fit finding, never a quality judgment.** The candidate may be excellent. What failed was aim.
**Probe:** "What is the largest number of IP owners you have had to align in one delivery, and what broke at the seams?"
**Weight:** `reject` **for the role**, never for the candidate
**Layer:** 3

### Role-critical experience is the least developed item

**Signature:** The bullet most relevant to the target role is shorter, less specific, and positioned lower than surrounding bullets about other work.
**Reads as:** A targeting failure, not a quality failure — and invisible to the candidate, who is proudest of their deepest work. Depth and ordering are how a reader infers what you consider central; when the role-relevant material is thinnest, they correctly conclude it is peripheral to you.
**Probe:** "How much of your time in the last two years touched that area?"
**Weight:** `reject-contributing` for the role
**Layer:** 3

### Ownership claim immediately hedged

**Signature:** A bullet opens with an ownership verb (Owned, Led, Designed) and, in the same bullet, retreats to participation ("Involved in", "Supported", "Assisted with", "Part of").
**Reads as:** Offered both readings, a reader takes the weaker one — because the candidate volunteered it. This punishes the scrupulous: honest hedging withdraws the claim precisely where they were strongest.
**Fix:** separate them. What you owned gets its own bullet with the outcome attached; what you contributed to goes elsewhere or nowhere.
**Probe:** "On the ones you owned — who did you have to convince, and what happened when it broke?"
**Weight:** `probe`
**Layer:** 3

### Passive voice removing the actor

**Signature:** An accomplishment written with no agent — "was analysed", "were implemented", "has been optimised".
**Reads as:** Coordination verbs name the wrong action; passive voice deletes the person from their own sentence. It clusters around work the candidate is least confident defending, which is itself a tell.
**Probe:** "Who did that work?"
**Weight:** `probe`
**Layer:** 3

### Uniform bullet framing

**Signature:** A majority of bullets open with the **identical construction** while the content after the opener is genuinely differentiated.
**Reads as:** Discipline for three bullets, monotony by the eighth. Every item lands at the same altitude, so there are no landmarks — nothing marks which was hard, which shipped, which would survive a deep dive. The deepest work is penalised by the formatting around it.
**Boundary:** if the *whole bullet* repeats rather than just the opener, this does not fire — see *Boilerplate recycled across entries*.
**Probe:** "Which two of these were genuinely hard, and what made them hard?"
**Weight:** `probe`
**Layer:** 3

### Boilerplate recycled across entries

**Signature:** Whole bullets duplicated near-verbatim under two or more projects or roles, with no differentiation.
**Reads as:** Apparent volume inflated and then destroyed — a reader who notices duplication stops trusting the rest of the page. It also answers the question it was meant to avoid: if your contribution to four programmes is described identically, the honest reading is that your role was the same routine each time, which may be true and is not disqualifying, but repeating it makes it the headline.
**Boundary:** repeated *openers* with differentiated content is *Uniform bullet framing*.
**Probe:** "These read identically. What was different about the hardest one?"
**Weight:** `probe` → `reject` combined with thin differentiated content
**Layer:** 3

### Output volume below tenure

**Signature:** Total substantive bullets across the document divided by years of experience falls below roughly two per year, counting only bullets naming a domain-specific artifact.
**Reads as:** Either the work was thin or the candidate cannot articulate it. At screening those are indistinguishable and nobody spends the time to find out, so both resolve identically.
**Probe:** "Take your hardest quarter. What were you doing week to week?"
**Weight:** `probe` → `reject` combined with unattributable bullets
**Layer:** 3

### Concreteness gradient running backwards

**Signature:** The oldest role contains the most technically specific bullets and the most recent contains the vaguest.
**Reads as:** The reader wants recency depth and finds the reverse, which raises a question the document never answers: are you still doing engineering? Three explanations fit — the role drifted to coordination, confidentiality constrains the current work, or the candidate stopped updating with care — and the reader picks one alone.
**Probe:** "What is the last thing you personally designed and signed off, and when?"
**Weight:** `probe` → `reject` for a hands-on design role
**Layer:** 3

### Capability list with no depth ranking

**Signature:** A flat list of six or more tools, protocols or methodologies presented at equal weight, with no indication of depth per item.
**Reads as:** Capabilities at equal weight signal none of them. The reader cannot distinguish where you are the person the team asks from where you have run the flow twice, so they assume the latter throughout — the safe read, and the wrong one for anyone with genuine depth. Listing more actively costs you: it dilutes the two items that would have earned the interview.
**Probe:** "Of these, which two would you defend in a deep dive, and which are exposure only?"
**Weight:** `probe`
**Layer:** 3

### Company-internal tooling as transferable skill

**Signature:** Proprietary in-house tool names listed in a skills section alongside industry-standard tools, with no explanation of what they do.
**Reads as:** Meaningless outside the company that built them, and their prominence says the candidate has not considered which skills actually transfer. It also raises the quiet worry behind any long single-employer tenure — that the expertise is flow-specific.
**Fix:** name the internal tool only with the standard it implements — "an internal IP-XACT-equivalent register description flow" travels; the bare product name does not.
**Probe:** "How much of your methodology would survive a move to a different flow?"
**Weight:** `probe`
**Layer:** 3

### Technical inaccuracy inside a skills list

**Signature:** A tool, standard or methodology assigned to the wrong category — a synthesis tool listed as a CDC tool, a simulator listed as a linter, an IP vendor named as a foundry.
**Reads as:** Categorically worse than a typo. A misspelling says the document was not proofread; a category error says the candidate may not know what the tool does — and it usually sits directly beside the claim it undercuts. An interviewer who spots it opens there.
**Probe:** "Walk me through that flow — which tool at which stage, and what does each actually check?"
**Weight:** `reject-contributing`, and a guaranteed interview trap
**Layer:** 3

### Unquantified improvement claim

**Signature:** A performance, power, area or timing improvement stated as a percentage or multiple with no baseline, no mechanism and no scope.
**Reads as:** Could be a genuine architectural win, could be one constraint fix. Without the mechanism the reader cannot tell, and unverifiable numbers read as decoration.
**Probe:** "What was the critical path, and what specifically did you change?"
**Weight:** `probe`
**Layer:** 3

### Flow-breadth claim disproportionate to tenure

**Signature:** A claim to own an end-to-end flow — RTL-to-GDSII, concept-to-tapeout, full-chip signoff — on a resume with fewer than roughly five years of experience, or with no stage described in detail.
**Reads as:** They touched one or two stages, not the whole flow. Breadth claimed without a single stage evidenced converts into a doubt about all of them.
**Probe:** "Which stage did you personally own? What broke, and how did you debug it?"
**Weight:** `probe`
**Layer:** 3

### Services-to-product transition, unbridged

**Signature:** Employment history moves from services, staffing or client-embedded work into a product company, with claims of ownership or architecture after the move and nothing on the document connecting the two phases.
**Reads as:** Services work is usually scoped execution; product ownership means deciding what gets built. Both can be true of one person and the transition is common and legitimate — but presented as checking work *then* architecture leadership with no account of how, a senior reader senses a discontinuity they cannot resolve, and unresolved discontinuity becomes hesitation.
**Probe:** "What changed when you moved? What were you trusted with in year one there that nobody would have handed you before?"
**Weight:** `probe` — **never reject on this alone**; it is frequently a real promotion the candidate failed to narrate
**Layer:** 3

### Divided-intent signals

**Signature:** Credentials, publications or a stated-interests block pointing at a domain the candidate has never worked in and which differs from the role applied for, with no line connecting it to the hardware work.
**Reads as:** Adjacency matters — AI credentials reinforce an NPU or accelerator profile; unrelated domains do not. A stated interest in work the candidate has never done reads as where they would rather be, and a hiring manager registers departure risk without ever asking about it.
**Probe:** "Where do you want to be in this field in three years?"
**Weight:** `reject-contributing`
**Layer:** 3

### Tapeout or silicon claim without phase or scale

**Signature:** A tapeout, bring-up or "full-chip" claim with no milestone named (RTL freeze, tapeout, first silicon, bring-up, production), no role stated, and no scale (block, subsystem, full chip).
**Reads as:** Tapeout is the most checkable claim in the field and the most casually inflated — "part of a team that taped out" and "owned the freeze checklist" are written identically. Naming the phase costs one clause and converts an unverifiable boast into evidence.
**Escalates to:** `reject-contributing` when the claimed count is arithmetically implausible against the stated dates — a tapeout cycle is rarely under twelve months, so four tapeouts in three years needs explaining.
**Probe:** "Which milestone were you present for, and what did you personally debug on first silicon?"
**Weight:** `probe`
**Layer:** 3

### Adjacent-discipline evidence under an RTL banner

**Signature:** The title and summary claim RTL design, but the evidence base sits in an adjacent discipline: verification, physical design/STA, DFT, or signoff-quality (lint, CDC, RDC, LEC, UPF, synthesis runs, waivers). Test: no bullet names an RTL deliverable the candidate authored — a block, an FSM, a datapath, a protocol implementation.
**Reads as:** Each adjacency reads differently and none is a weakness in itself. Signoff-quality is in demand and routinely disowned by the people doing it; DV-heavy evidence under a design banner reads as someone who wants to move and hasn't yet; PD/STA evidence suggests implementation rather than authorship.
**Report as fit, not quality** — and pair it with the strength inverse: the discipline they actually have is usually marketable, and naming it is the redirect.
**Probe:** "What is the last RTL you authored — the block, not the checks on it?"
**Weight:** `probe` · `reject` for a hands-on RTL role when no owned RTL deliverable appears anywhere
**Layer:** 3

### FPGA-only evidence against an ASIC requisition

**Signature:** All evidence is FPGA — bitfiles, board bring-up, vendor toolchains, LUT counts — against a role requiring ASIC flow, with nothing bridging the two.
**Reads as:** The disciplines share a language and not a discipline. ASIC RTL passes gates FPGA RTL never meets: DFT insertion, power intent, multi-corner timing closure, and a freeze after which mistakes cost a mask set. A reader wants to know the candidate has worked under irreversibility.
**Inverse is milder** — ASIC engineers moving to FPGA are rarely questioned, so do not fire this in that direction.
**Probe:** "What gate did your RTL have to clear before release, and who owned sign-off?"
**Weight:** `probe` · `reject-contributing` for a senior ASIC requisition
**Layer:** 3

### Stint length below a project cycle

**Signature:** Multiple roles shorter than roughly eighteen months, with no single role spanning a full design cycle.
**Reads as:** Silicon runs on long cycles, and someone who has never seen one from freeze to bring-up has not met the part of the job where decisions come back. It is a real question, not a character judgment — and it is answered instantly by naming one project carried end to end.
**Escalates to:** `reject-contributing` where no role spans a cycle *and* the resume claims tapeout ownership.
**Probe:** "Which project did you see from freeze to silicon, and what happened after tapeout?"
**Weight:** `probe`
**Layer:** 2

### Employment structure unstated

**Signature:** It cannot be determined from the document whether roles were direct employment, contract, or agency placement.
**Reads as:** Readers weight these differently — rightly or not — and ambiguity is resolved pessimistically. Stating it plainly costs a parenthetical and removes a doubt the candidate cannot otherwise address. It also pre-empts the *services-to-product* discontinuity by making the shape of the career legible.
**Probe:** "Were those direct roles or through a partner?"
**Weight:** `advisory`
**Layer:** 2

### Academic project indistinguishable from a course exercise

**Signature:** *(Fresher and early bands only.)* A project entry naming a canonical teaching artifact — synchronous/asynchronous FIFO, UART, traffic-light FSM, basic ALU, single-cycle RISC-V — with no statement of what the candidate changed, what their testbench caught, or whether it synthesised.
**Reads as:** At 0–2 years a project is the whole case, and a reader assumes the reference implementation unless told otherwise. Three clauses convert an exercise into evidence: what you changed from the reference, what your bench caught, and what clock it closed at.
**Probe:** "What did you change from the reference design, and what did your testbench catch that surprised you?"
**Weight:** `reject-contributing` *(fresher band only — never fires above 3 years, where the entry is superseded by academic content being padding)*
**Layer:** 3

### Verifiable public work absent or buried

**Signature:** No GitHub, open-hardware contribution, patent or publication link anywhere — or one present but unlinked, or linked and buried below the fold.
**Reads as:** Not a defect for most silicon engineers, whose work is legitimately unpublishable. But it is the **cheapest available fix for an NDA-bound candidate with no attributable evidence** — the exact bind the confidentiality rule creates. A public repo, however small, is the one artifact a reader can inspect without asking anyone's permission.
**Probe:** "Which repo would you want me to read, and what is the hardest thing in it?"
**Weight:** `advisory` when absent · `strength` when present and surfaced
**Layer:** 3

### Administrative content that does not belong

**Signature:** The document carries current or expected compensation, notice period, a photograph, third-party referee names and contact details, or marital/nationality status.
**Reads as:** Compensation and notice belong in a conversation, not a document that circulates — stating them sets an anchor before any leverage exists. A photograph is expected in some markets and a liability in others, and it frequently breaks text extraction at layer 1. Publishing referees' phone numbers exposes other people's data without their control and is checked by nobody at screening stage.
**Probe:** —
**Weight:** `reject-contributing` for compensation, notice, or third-party contact details · `advisory` for a photograph, market-dependent
**Layer:** 2

### Location and work authorisation unstated

**Signature:** For a role with a location requirement or a cross-border application, the document states no current city, no willingness to relocate, and no work-authorisation status.
**Reads as:** A recruiter cannot progress an application they cannot place. This is one of the few things layer 2 genuinely needs and candidates routinely omit, assuming it will be asked — it usually isn't; the application is simply set aside.
**Probe:** —
**Weight:** `advisory` domestically · `reject-contributing` for a cross-border application
**Layer:** 2

### Career break stated but currency not addressed

**Signature:** A break is **disclosed** — caregiving, health, study, relocation, returnship — and the document says nothing about what re-established currency on return.
**Reads as:** **The break itself is never a defect and must never be reported as one.** What a technical reader wants is one line on currency: refresher work, a returnship, a personal project, tool versions used since. Absent that, they guess, and the guess is not generous.
**Distinct from *Unexplained gap in the timeline***, which fires on silence. Disclosure is the correct behaviour and this entry never penalises it.
**Probe:** "What did you do to get current again?"
**Weight:** `probe` — on currency only, never on the break
**Layer:** 2

### First page carrying no claim

**Signature:** The upper portion of page one is occupied by structure that asserts nothing — an unlabelled or unquantified summary, employer/duration blocks with no content beneath them, an undifferentiated keyword line — such that a reader of the top third learns where to look rather than what the candidate can do.
**Reads as:** The scarcest real estate on the document spent on scaffolding. **The working rule: roughly 60% of the first page should do about 80% of the crucial talking.**
**Not triggered by these sections existing** — a summary, a skills line and employer headers all belong on page one. It fires when they carry no claim.
**Probe:** "If I read only the top third of your first page, what would I know about what you can do?"
**Weight:** `reject`
**Layer:** 2

---

## Strengths — surface these, never flag them

*Four of seven resumes in the calibration corpus buried their single strongest asset. The material was present and mis-weighted; in one case the same facts read as a defect until reframed. Report strengths at the top, above the flags — a defect list is what every commodity tool produces.*

### Shipped silicon buried

**Signature:** Publicly announced, shipped products the candidate worked on are named anywhere below the summary — as a sub-heading, a parenthetical, or a mid-page line.
**Reads as:** Rare, checkable, impossible to fake, and it answers *did any of this survive contact with reality* before a reader has to ask. It is the only finding that pays at **all three layers**: searchable tokens for the parser, brand-adjacent recognition for the recruiter, shipped-not-testchip proof for the manager.
**Prescription:** move it into the first two lines. Not a sub-heading, not page two.
**General rule this instantiates:** whatever is rare, checkable and hard to fake belongs in the opening lines. Most candidates order by chronology or category, never by strength.
**Weight:** `strength`
**Layer:** 1, 2 and 3

### Latent qualifying experience never framed as such

**Signature:** Work described by its components which, named differently, is the exact capability the target role requires — for example BIST, loopback, PRBS and calibration work that is never called *debug capability*.
**Reads as:** The candidate holds what would make them viable for the role and does not know it counts. This is the highest-value thing a reviewer returns: not a defect to fix but capability already owned, which converts a rejection into a redirect.
**Probe:** "Describe the nastiest bug you found through that path. How did you localise it?"
**Weight:** `strength`
**Layer:** 3

### Career pivot narrative left unsurfaced

**Signature:** Dates show a deliberate transition into the field — retraining overlapping an unrelated job, a domain switch, a self-funded qualification — presented as bare dates with no narrative.
**Reads as:** As written, overlapping dates read as sloppiness. Framed, the identical facts show someone who identified a gap, funded the retraining themselves and executed the switch fast — which is the thing employers cannot teach.
**Probe:** "Why the switch, and what did it cost you?"
**Weight:** `strength`
**Layer:** 2

---

## Combination rules

*These are not independent findings. They fire only when their components fire, and they absorb them.*

### Template → thin → template

**Signature:** *Education/summary scaffolding before substance* **and** *placement-cell padding* both fire, and bullets naming a domain-specific artifact make up under roughly 40% of the document.
**Reads as:** The structural verdict, faster than reading: what fraction of this document is load-bearing? Two pages filled while saying very little reads as padding to anyone who screens at volume.
**Report rule:** when this fires it **absorbs** its components as evidence and suppresses them as separate findings — otherwise the report opens with two independent rejections describing one problem.
**Weight:** `reject`
**Layer:** 2

### Ambiguous concurrent dates

**Signature:** Two or more entries carry overlapping or open-ended date ranges with no explanation.
**Reads as:** Either genuine parallel ownership — a strength worth stating outright — or dates never updated. The reader defaults to the second.
**Prevented entirely** by dating the employer and not the project — see below.
**Probe:** "Are you running both of these concurrently?"
**Weight:** `probe` — frequently a buried strength
**Layer:** 2

### Projects ordered by date rather than by strength

**Signature:** Projects inside a role appear in chronological order, and/or carry individual date ranges, so the top slot is assigned by date rather than by what the work demonstrates.
**Reads as:** A reader works top-down and stops early; the first project in a role gets the most attention that role will ever receive, and chronology assigns it at random with respect to quality.
**Rule: date the employer, not the project.** Employment dates are chronological and non-negotiable — they establish tenure, progression and the absence of gaps. Project order inside a role is editorial. Projects in a role usually overlap anyway, so their sequence carries no claim and nothing is misrepresented. Removing project dates also eliminates *Ambiguous concurrent dates* entirely.
**Order strongest first:** (1) shipped, owned and hard; (2) rare or differentiating technology, even if smaller; (3) clear depth demonstrations; (4) routine work — and if it does not earn its line, cut it.
**Exception:** keep a project date when the date is the point — first silicon on a new node, or work predating a technology becoming common.
**Weight:** `reject-contributing`
**Layer:** 3

---

## Mechanics

### Typo location over typo count

**Signature:** Errors in repeated structural labels, headings, or the contact block — as opposed to errors buried in prose.
**Reads as:** Nobody rejects on one typo. The inference comes from *where* it sits: an error in a label typed once and duplicated means the document was never re-read start to finish. On resumes claiming lint cleanliness and sign-off discipline, that lands harder — the candidate asserts precisely the quality the artifact disproves.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Tense and voice shifting within an entry

**Signature:** One role or project moves between past, present-participle and passive constructions across its bullets.
**Reads as:** Minor alone, corrosive in aggregate. It says the bullets were written at different times and never read together — the artifact was assembled rather than composed. Convention: past tense for completed work, present for the current role, one voice throughout.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2

### Domain-alien filler in the summary

**Signature:** A sentence in the summary drawn from an unrelated professional vocabulary, or unfalsifiable self-praise — "recognised for effectively addressing challenges", "strong grasp of core economic principles".
**Reads as:** It occupies the position of maximum attention and reads as borrowed or generated boilerplate. Both available explanations damage the candidate: either the summary is not theirs, or they do not know what signals competence in their own field.
**Related tell:** first-person voice in a summary whose bullets carry no pronouns — inconsistent register inside one document usually means the parts came from different sources.
**Probe:** —
**Weight:** `reject-contributing`
**Layer:** 2
