# bizlibsearch-owen (streamlined)

A [Claude](https://claude.ai) plugin that builds librarian-quality business research plans using Vanderbilt's Walker Management Library databases — tailored for **Owen Graduate School of Management** students.

This is the **streamlined edition**: the full planning workflow plus the database catalog, search-craft, and access-troubleshooting references — without the maintainer refresh checklist and field-notes files.

## Install (drag into chat)

Download the `bizlibsearch-owen.plugin` file and drag it into a Claude (Cowork) chat, then accept it when the preview appears. Once installed, type `/bizlibsearch <topic>` in any chat — for example:

```
/bizlibsearch market size and competitive landscape for meal-kit delivery in the US
```

## Contents

```
bizlibsearch-owen/
├── .claude-plugin/
│   └── plugin.json
└── skills/
    └── bizlibsearch/
        ├── SKILL.md                       # Workflow logic and triggers
        └── references/
            ├── databases.md               # Database catalog, links, access rules
            ├── search-craft.md            # NAICS/SIC, Boolean, ticker, triangulation
            └── access-troubleshooting.md  # Proxy/login diagnosis from library FAQs
```

## License

MIT. Database details are accurate only as of the "last verified" date in `databases.md` and are specific to Vanderbilt University. Independent, community-built tool — not an official Vanderbilt University Library product, and not affiliated with or endorsed by Anthropic.
