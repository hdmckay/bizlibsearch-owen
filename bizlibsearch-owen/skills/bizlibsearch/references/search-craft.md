# Search Craft

The part that separates a database list from a research plan. Include at least a code, a Boolean string, and one database-specific quirk in every plan.

---

## 1. Industry codes: use them, don't just mention them

Codes make results *comparable across databases*. Searching "restaurants" in three databases gives three different universes; searching NAICS 72211 gives the same one.

**NAICS** (North American Industry Classification System) — current standard, use by default.
Hierarchy narrows as digits increase:
- `72` Accommodation and Food Services
- `722` Food Services and Drinking Places
- `7221` Full-Service Restaurants
- `72211` Full-Service Restaurants

**SIC** (Standard Industrial Classification) — older, but still what some databases and most historical data use:
- `5` Retail Trade
- `58` Eating and Drinking Places
- `581` Eating and Drinking Places
- `5812` Eating Places

Lookup: NAICS https://www.naics.com/search.htm · SIC https://www.ehso.com/siccodes.php

**How to choose the digit level:**
- Too broad (2-digit) → report exists but says nothing about the actual question
- Too narrow (6-digit) → no report exists; IBISWorld may have nothing
- Start at 4-digit, move up one level if empty, down one if the report is too general

**Tell the user both codes** when the research spans current and historical data.

---

## 2. Ticker symbols for company work

Always identify and use the **stock ticker**, not the company name. Names collide, subsidiaries share branding, and databases disagree about which entity is "the" company. The ticker guarantees you're comparing the same legal entity across Hoovers, FactSet, LSEG, and Bloomberg.

Watch for:
- Parent vs. subsidiary (the subsidiary often has no separate financials)
- Multiple share classes (GOOG vs. GOOGL) — pick one and stay consistent
- Foreign listings and ADRs — the ADR ticker and home-market ticker pull different data
- Recently renamed or merged entities — check the ticker's effective date

---

## 3. Boolean construction

Most business databases support standard operators. A usable pattern:

```
("industry term" OR "synonym") AND ("concept" OR "synonym") AND (geography)
```

Worked example — market size for plant-based dairy alternatives in the US:

```
("plant-based" OR "plant based" OR "non-dairy" OR "dairy alternative")
AND ("market size" OR "market share" OR "revenue" OR "forecast")
AND (US OR "United States" OR domestic)
```

Practical guidance:
- **Quotation marks** force phrase matching — essential for multi-word concepts
- **Truncation** (`*`) catches variants: `consum*` → consumer, consumers, consumption
- **Synonyms in OR-blocks** matter more than in general web search; business vocabulary is inconsistent ("market size" vs. "market value" vs. "revenue")
- **Start broad, then filter** — most of these databases have better post-search filters (date, source type, industry, geography) than query syntax
- **Date-limit deliberately.** Business info goes stale fast; the library's own guidance is that business research needs current, reliable sources. Default to last 2–3 years unless the question is historical.

---

## 4. Private company triangulation

Private companies don't file with the SEC, so no single source works. Layer instead:

1. **PitchBook** — funding rounds, valuations, investors, comparables. Best starting point if VC/PE-backed. (Mind the 10/day download cap; plan what you actually need before opening it.)
2. **PrivCo** — financials on larger private firms: family-owned, PE-owned, VC-backed, international unlisted.
3. **Nexis Uni** — litigation, regulatory filings, and news mentions. Lawsuits often expose revenue and operational detail nothing else publishes.
4. **Factiva** — trade press. Niche trade publications routinely print figures the company never announced.
5. **Industry reports (IBISWorld)** — if the company is a named major player, the report may size it or give its market share.
6. **State-level filings** — incorporation records, licensing, UCC filings. Free and underused.
7. **Trade associations** — often publish aggregate industry data that lets you bracket a single firm's size.

**Bracketing method:** when no direct figure exists, establish an upper bound (total market size from IBISWorld) and a lower bound (known contracts, employee count × industry revenue-per-employee), and state the range with reasoning rather than guessing a point estimate.

---

## 5. ESG triangulation

Structurally similar to private-company triangulation, but for a different reason. With private companies you layer sources because no one has the answer. With ESG you layer them because **the providers disagree, and the disagreement is itself the finding.**

Vanderbilt's three ESG sources — FactSet, LSEG Workspace, Bloomberg — draw on different data and methodologies. Never present one score as *the* score.

Capture for each: **provider, score, scale, as-of date.** Then compare at pillar level (E, S, G separately) rather than headline, since divergence usually concentrates in one pillar. Report the spread and explain it; averaging destroys the signal.

Common causes of divergence worth naming in a plan:
- **Materiality weighting** — providers disagree on which issues matter for a given sector
- **Disclosure vs. estimation** — some score only reported data, others impute gaps
- **Peer-relative vs. absolute** — a peer-relative score changes when the peer group is redefined
- **Controversy weighting and lag** — how heavily incidents count, and how fast they're reflected

**Access:** LSEG and FactSet both work remotely over the Vanderbilt VPN for eligible users, so two-provider comparison is possible off-site. Bloomberg needs an on-campus terminal — worth a trip if the divergence between the first two is large or the question is high-stakes.

---

## 6. Database-specific quirks worth passing along

| Database | Tell the user |
|---|---|
| IBISWorld | Search by NAICS code, not name, for reliable retrieval. Key Statistics page has downloadable data — often the fastest defensible number. |
| Factiva | 15-minute inactivity logout. Save or export as you go. |
| PitchBook | Downloads capped at 10/day, 25/month. Scraping is prohibited and risks permanent revocation. Plan extraction before opening. |
| LSEG Workspace | Account resets every semester — expect to re-register. 150 pp/day report limit. |
| RKMA | International content is buried: scroll → "Click here to view archive titles" → INTERNATIONAL CONSUMER MARKETS. |
| Forrester | Log in with VU email in the Business Email field and *no password*. Do not contact analysts — not licensed. |
| Gartner | Partial subscription; some specialized industry research is simply not there. Don't send users hunting for it. |
| Nexis Uni | Default search lands on News; switch source type via the dropdown next to the search bar for company or legal content. |
| Statista | Every statistic cites its underlying source — follow through to the original for anything going into a graded or published document. |
| Business Source Complete | Route to Harvard Business Review and Datamonitor/SWOT reports. Filter by document type to isolate SWOTs. |

---

## 7. Sequencing principle

Order the plan by **cost of effort vs. likelihood of payoff**:

1. **Fast orientation** — Statista or First Research for a quick shape of the market (minutes)
2. **Structural backbone** — IBISWorld industry report for the framework (30–45 min)
3. **Company specifics** — Hoovers/Gale/PitchBook depending on public vs. private
4. **Consumer texture** — Mintel/Passport if the question touches behavior or segmentation
5. **Current developments** — Factiva/Nexis Uni/Business Source Complete for news and scholarship
6. **On-campus heavy tools** — Bloomberg/FactSet last, since they require a physical trip

Front-load whatever is likeliest to answer the question, and say plainly when a later step is optional.
