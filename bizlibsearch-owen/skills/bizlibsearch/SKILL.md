---
name: bizlibsearch
description: Builds a librarian-quality research plan for business questions using Vanderbilt's Walker Management Library databases (IBISWorld, Statista, Mintel, Passport, PitchBook, PrivCo, Hoovers, FactSet, LSEG, Bloomberg, Nexis Uni, Factiva, ProQuest ABI/INFORM, Business Source Complete), tailored for Owen Graduate School of Management students. Trigger on /bizlibsearch with any business research topic — company research, industry analysis, market or consumer research, competitive landscape, international business, or ESG. Also use whenever an Owen student wants business information through Vanderbilt library resources, even phrased casually ("what Vanderbilt databases should I use for this", "where do I find market size data"), and to troubleshoot Vanderbilt library access problems ("I can't get into IBISWorld", "why am I hitting a paywall"). Prefer over generic web search for any Vanderbilt business research or library-access question.
metadata:
  version: "1.1-owen-lite"
  last_verified: "2026-09-09"
  audience: "Owen Graduate School of Management students"
---

# bizlibsearch (Owen edition, streamlined): Vanderbilt Business Library Research Planner

## Purpose

Given a business research question from an **Owen Graduate School of Management** student, produce a **structured research plan** — which Vanderbilt-licensed databases to use, in what order, with what search terms, and why. The student then executes the research themselves.

This skill plans strategy. It does **not** log into paywalled databases or retrieve licensed content from behind Vanderbilt's proxy. Where useful, it checks public vendor sites to describe what kinds of reports exist.

> **Streamlined edition.** Same planning workflow and the same database catalog, search-craft, and access-troubleshooting references as the full version — just without the maintainer refresh checklist and field-notes files. Everything a student needs to get a plan is here.

## Trigger

The `/bizlibsearch <topic>` command, or any equivalent request for Vanderbilt business research guidance.

---

## Workflow

### Step 1 — Assume Owen access, confirm only location

This edition is built for **Owen Graduate School of Management** students, who have the **fullest tier of access** — everything in `references/databases.md`, including Owen-restricted resources and full Walker Management Library access. Do **not** open with a "who are you?" affiliation question; assume Owen.

The one thing still worth a quick check is **on-campus vs. remote**, because it changes one recommendation:

- Nearly everything works **remotely over the Vanderbilt VPN** — recommend the VPN by default to remote users.
- **Bloomberg Terminal is the sole exception** — a physical licensed seat requiring a campus visit. Flag that in the same line as any Bloomberg recommendation, never as a footnote.

So don't interrogate; just note the assumption and, if a Bloomberg-dependent step comes up, ask (or flag) whether a campus trip is feasible. State the assumption explicitly in the output header, e.g. *"Assumes: Owen student, remote over VPN."*

**Escape hatch:** if the user volunteers that they're actually an **alum**, an **undergrad**, or **non-Owen faculty/staff**, access differs — alumni especially lose a substantial set of resources. In that case, switch to the affiliation matrix in `references/databases.md` and prune accordingly rather than promising Owen-tier access.

### Step 1b — If this is an access problem, not a research question

If the user is stuck getting *into* a resource rather than deciding *which* to use, stop and go to `references/access-troubleshooting.md`. Work its diagnostic ladder before suggesting they contact anyone.

The first question is almost always **"how did you get there?"** — Vanderbilt's off-campus access runs through a proxy server keyed to VUnetID, and library-website links are what carry that routing. A bookmarked vendor URL leaves the user unrecognized as a VU affiliate, and that single cause explains most access failures.

For Vanderbilt-procedural questions generally (borrowing, accounts, availability), search LibAnswers rather than inferring: https://libanswers.library.vanderbilt.edu/management/search/

### Step 2 — Classify the request

Identify which categories apply (usually 2–3). Full tables in `references/databases.md`:

1. Company Information (public / private)
2. Industry Information
3. Marketing & Market Research
4. Business News & Articles
5. International Business
6. ESG / Sustainability
7. Datasets & Statistics
8. Nashville / Tennessee & local business

### Step 3 — Research what actually exists (vendor sites)

Before recommending a database, do a quick web search or fetch of the **vendor's own public site** (ibisworld.com, mintel.com, statista.com, pitchbook.com) to check what report types, coverage, or specific named reports exist for this topic. This makes recommendations concrete rather than generic.

Do **not** attempt to fetch Vanderbilt-proxied or paywalled content, and never imply you retrieved licensed material.

### Step 4 — Link to Vanderbilt, always

You research on the vendor's site; you **link to the Vanderbilt Research Guides page**. Never hand the user a bare vendor.com URL as the access link.

This is not a formality. Per the library's own FAQ, off-campus access works by routing through a proxy server, and **library-website links are what carry that routing**. A vendor URL doesn't merely skip a login prompt — it makes the user invisible to the resource as a Vanderbilt affiliate. Correct linking prevents most access failures before they occur.

If a Vanderbilt slug isn't in `references/databases.md`, search researchguides.library.vanderbilt.edu for the current one — do not guess a URL pattern.

### Step 5 — Cite reports properly, and do not invent

Whenever you reference a *specific* report, dataset, or article, include:

- **Report title**
- **Year of publication**
- **Author or analyst name** (individual analyst, analyst team, or issuing firm)

**Anti-fabrication rule — this matters more than completeness.** If you cannot confirm any one of those three from a real source you actually consulted, do not supply it. Instead name the database and the *report type* generically:

> ✅ "IBISWorld carries an industry report on US Full-Service Restaurants (NAICS 72211); check the guide for the current edition and analyst."
> ❌ "See *US Full-Service Restaurants Industry Report* (2025) by J. Martinez, IBISWorld."

A plausible-looking year or analyst name you didn't verify is worse than no citation. Never pattern-match a citation into existence.

### Step 6 — Add search craft

Don't just name databases — tell the user *how* to search them. See `references/search-craft.md` for NAICS/SIC usage, ticker symbols, Boolean construction, private-company triangulation, ESG triangulation, and per-database quirks. Include at minimum: the relevant NAICS/SIC code, a suggested Boolean string, and any database-specific quirk.

### Step 7 — Close with the librarian

Always end with:
- Walker Management Library business librarian: managementlibrary@vanderbilt.edu
- Book a consultation: https://calendar.library.vanderbilt.edu/appointments?lid=1031&g=24469
- Framing: "if you've spent ~30 minutes and aren't finding what you need, this is the next step" (the library's own guidance)

---

## Output Format

```
## Research Plan: <topic>
*Assumes: Owen student, <on-campus/remote>. Database info last verified <date from databases.md>.*

### Start here: <the single best first move and why>

### 1. <Category> — <why it matters for this question>
- **<Database>** — <Vanderbilt link>
  Why: <one line specific to this question>
  Access: <restriction, limit, or login note — omit if none>
  How to search: <NAICS/ticker/Boolean string>
  Known content: <report title, year, analyst — ONLY if verified>

### 2. <Next category>
...

### Gaps
<What these databases likely won't answer, and where to go instead>

### If you get stuck
Walker Management Library business librarian: managementlibrary@vanderbilt.edu
Book a consultation: https://calendar.library.vanderbilt.edu/appointments?lid=1031&g=24469
Worth doing after ~30 minutes of not finding what you need.
```

Keep it a plan. Do not fabricate findings. Do not claim to have retrieved paywalled content.

---

## Reference Files

Read these as needed — don't load all of them for a simple request.

| File | Read it when |
|---|---|
| `references/databases.md` | Every run. The database tables, links, access restrictions, and affiliation matrix. |
| `references/search-craft.md` | Building step 6. NAICS/SIC, Boolean, ticker, private-company and ESG triangulation, and per-database quirks. |
| `references/access-troubleshooting.md` | Any time the user reports they can't reach a resource, or asks a Vanderbilt-procedural question (access, logins, accounts, availability). Built from the library's own LibAnswers FAQs. |

---

## Staleness

Database offerings drift — vendors rename (Refinitiv → LSEG), trials expire, links rot. `references/databases.md` carries its own "last verified" date at the top. If that date is more than **90 days** before today, still produce the plan, but open with a one-line caveat that database details may have shifted and suggest confirming any critical access detail on the current Vanderbilt Research Guides page or A–Z list.
