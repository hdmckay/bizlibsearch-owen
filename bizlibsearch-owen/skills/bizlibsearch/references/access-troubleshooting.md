# Access Troubleshooting

Sourced from Vanderbilt's own LibAnswers FAQs. Use this when a user reports they can't reach a resource — resolve it here before sending them to a librarian.

**Search all management FAQs:** https://libanswers.library.vanderbilt.edu/management/search/
**E-Resources FAQs (access & troubleshooting):** https://libanswers.library.vanderbilt.edu/eresources/

> The LibAnswers search page renders results via JavaScript and blocks automated fetching of filtered views, so it often can't be scraped directly. Individual FAQ pages at `/eresources/faq/<id>` *are* fetchable. Give users the search link to browse themselves, and use the captured FAQs below for actual diagnosis.

---

## The key mechanism: it's the proxy, not the VPN

Vanderbilt's off-campus access runs on a **proxy server** keyed to VUnetID authentication. Per the library's FAQ, most resources are reachable from anywhere — **but you have to enter through a library-website link**, because those links are configured to route through the proxy.

This is the technical reason for the skill's standing rule to always link via Research Guides rather than a vendor URL. A bare `ibisworld.com` link doesn't just lack a login prompt — it makes the user invisible to the resource as a Vanderbilt affiliate. Getting this right prevents most access problems before they happen.

VPN also works and is fine to recommend. But when someone is stuck, **the proxy path is the thing to check first**, because a bookmarked vendor URL is the single most common cause.

Canonical entry points:
- Databases A–Z — https://researchguides.library.vanderbilt.edu/az.php
- Library Search — https://catalog.library.vanderbilt.edu/
- Journal Search — https://catalog.library.vanderbilt.edu/discovery/jsearch?vid=01VAN_INST:vanui

---

## Diagnostic ladder

Work in order; stop when it resolves.

### 1. How did they enter?

Ask this first — it resolves the majority of cases.

If they arrived from Google, a bookmark, an email link, or by typing the vendor's address, **they are likely not being recognized as a Vanderbilt user.** Send them back through the Research Guides link for that database.

### 2. Force the proxy on a URL they already have

Prepend the proxy prefix:

```
http://proxy.library.vanderbilt.edu/login?url=
```

Example: `https://www.jstor.org/stable/42627701` becomes
`http://proxy.library.vanderbilt.edu/login?url=https://www.jstor.org/stable/42627701`

⚠️ This only works for titles Vanderbilt actually licenses. If access still fails, the library may not subscribe — that's a holdings question, not a technical one.

### 3. Install a persistent fix

For users who hit this repeatedly, both of these are better than manual prefixing:

- **LibKey Nomad** browser extension — surfaces instant full-text links from publisher sites for anything VU subscribes to. Guide: https://researchguides.library.vanderbilt.edu/c.php?g=69365&p=7034485
- **Proxy bookmarklet** — reloads the current page through the proxy in one click. Create a bookmark whose URL is:
  ```
  javascript:void(location.href="http://proxy.library.vanderbilt.edu/login?url="+location.href);
  ```

### 4. Clear cache and cookies

Stale cookies are a common cause, especially after a semester rollover or an expired session. VUIT instructions: https://tdx.vanderbilt.edu/TDClient/33/Portal/KB/ArticleDet?ID=144

Relevant FAQs: "How do I clear my browser's cookies and cache?" (faq/298359) · "I got a Cookie Error. What do I do?" (faq/293575)

### 5. Try a different browser

Some resources behave better in one browser than another. Cheap to test, and it works often enough to be worth the step.

### 6. Check resource-specific causes

Before escalating, rule out the known quirks in `databases.md` — these look like access failures but aren't:

| Symptom | Likely cause |
|---|---|
| Session dies mid-research | **Factiva** logs out after 15 minutes of inactivity |
| Login rejected at LSEG Workspace | Personal account **resets each semester** — re-register |
| Downloads suddenly blocked | **PitchBook** cap: 10/day, 25/month. **LSEG**: 150 pp/day, 199 SDC rows/day. **PrivCo**: Excel limits |
| Forrester login loop | Enter VU email in the Business Email field with **no password**, then authenticate with VUnetID; first-time users complete a registration form |
| Content missing at Gartner | Partial subscription — some specialized industry research genuinely isn't licensed |
| Nexis Uni feature unavailable | Some functionality requires a **personal account** |
| Can't reach Bloomberg Terminal remotely | Expected. Physical licensed seat; on-campus only |
| Alum losing access | Alumni entitlements are much narrower — check the Alumni filters on the A–Z list |

### 7. Escalate with detail

If still stuck, submit via Ask a Librarian: https://www.library.vanderbilt.edu/ask/

The FAQ asks for specifics, so prompt the user to include:
- Full citation of what they wanted
- The URL they used
- How they accessed it (catalog / bookmark / database / research guide)
- Whether they were prompted to log in
- Exact error message text
- Screenshots

For business-specific questions, route instead to the Walker Management Library (verified 2026-09-09):
- managementlibrary@vanderbilt.edu
- Book a consultation: https://calendar.library.vanderbilt.edu/appointments?lid=1031&g=24469

---

## Captured FAQs

| Question | URL | Updated |
|---|---|---|
| Can I connect to electronic resources from anywhere, on or off campus? | /eresources/faq/293500 | 2025-10-27 |
| I can't connect to my journal/article/ebook/video/database. What should I do? | /eresources/faq/296104 | 2025-02-05 |
| What is the Library proxy server? | /eresources/faq/293505 | 2020-04-09 |
| How do I clear my browser's cookies and cache? | /eresources/faq/298359 | 2025-02-05 |
| I got a Cookie Error. What do I do? | /eresources/faq/293575 | 2020-04-09 |
| Why do I still appear as a "guest" in HathiTrust despite VUnetID login? | /eresources/faq/294606 | 2020-04-09 |

Prefix all with `https://libanswers.library.vanderbilt.edu`

**Management-group FAQs** (business-specific, tagged "business") are at https://libanswers.library.vanderbilt.edu/management/search/ — they weren't machine-readable at last refresh. When answering a business question where a Vanderbilt-specific FAQ likely exists, search this and cite it.

---

## Standing behavior

- **Search LibAnswers when a question is Vanderbilt-procedural** rather than research-strategic — access, borrowing, account setup, resource availability. The library's own answer beats an inference.
- **Prevent rather than fix**: because every recommendation links through Research Guides, most access failures never happen. Keep that discipline.
- **Never invent an FAQ answer.** If a question seems like it should have an FAQ and one can't be confirmed, point the user to the search page rather than guessing what it says.
