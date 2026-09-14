# bizlibsearch (Owen edition) — three ways to use it

A [Claude](https://claude.ai) helper that turns a business-research question into a
librarian-quality plan using Vanderbilt's Walker Management Library databases
(IBISWorld, Statista, PitchBook, Mintel, Factiva, Nexis Uni, and more) — tailored
for **Owen Graduate School of Management** students. It plans the strategy: which
databases to use, in what order, how to search them, and how to fix access
problems. You run the searches.

# Important Tip about db access
Use the [Management Library website's Databases A - Z list](https://bit.ly/wmldbs) as the access point and look up the databases by name.
(The llm links don’t always work).

**Pick whichever fits — you don't need all three:**

| Option | Best for | Setup |
|---|---|---|
| **1. Plugin** (marketplace) | People who want the `/bizlibsearch` command *and* automatic updates from this repo | Two commands |
| **2. Standalone skill** (`.skill`) | People who want the command but don't use plugins | Upload one file in Settings |
| **3. Copy-paste prompt** | People who want zero setup, or don't have plugins/skills enabled | Paste text into a chat |

All three use the same underlying skill and the same database catalog, so students get the same quality of plan whichever they choose.

---

## Option 1 — Install as a plugin if you use Claude cowork or code

This repository is a Claude plugin marketplace. In Claude (Claude Code, or Cowork with plugins enabled), run:

```
/plugin marketplace add hdmckay/bizlibsearch-owen
```
```
/plugin install bizlibsearch-owen@owen-library
```

Then type `/bizlibsearch` plus your topic, e.g. `/bizlibsearch competitive landscape for ready-to-drink coffee`. To pull a later update: `/plugin marketplace update owen-library`.

## Option 2 — Install as a standalone skill (no plugin)

1. Download **[`standalone-skill/bizlibsearch.skill`](standalone-skill/bizlibsearch.skill)** (open the file on GitHub and click **Download raw file**).
2. In Claude, go to **Settings → Capabilities → Skills** and choose **Upload skill** (drag the file in).
3. Use it the same way: `/bizlibsearch <topic>`.

Skill upload depends on your Claude plan; if you don't see it, use Option 3.

## Option 3 — Copy-paste prompt (zero setup)

Open **[`copy-paste-prompt.md`](copy-paste-prompt.md)**, copy the boxed text into a new Claude chat (regular app or web is fine — no plugin or skill needed), and add your topic on the last line. Save it as a skill to reuse it in future chats.

The prompt carries a trimmed database list so it fits in one paste; the plugin and skill options carry the full verified catalog.

## Contents

```
.
├── .claude-plugin/marketplace.json          # makes this repo a plugin marketplace (Option 1)
├── bizlibsearch-owen/                        # the plugin (Option 1) — source of truth for the skill
│   ├── .claude-plugin/plugin.json
│   ├── README.md
│   └── skills/bizlibsearch/
│       ├── SKILL.md
│       └── references/{databases,search-craft,access-troubleshooting}.md
├── standalone-skill/bizlibsearch.skill       # prebuilt upload file (Option 2)
├── copy-paste-prompt.md                      # zero-setup prompt (Option 3)
├── README.md
└── LICENSE
```

## License & disclaimer

MIT. Database details are accurate only as of the "last verified" date in
`databases.md` and are specific to Vanderbilt University. This is an independent,
community-built tool — not an official Vanderbilt University Library product, and
not affiliated with or endorsed by Anthropic.
