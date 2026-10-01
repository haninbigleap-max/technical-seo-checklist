# Technical SEO Checklist

A practical technical SEO audit checklist with 81 checks across 11 areas, available as a readable Markdown checklist and as a CSV you can drop into Google Sheets, Excel or a project tracker.

## What it does

It gives you a repeatable structure for auditing any website's technical health. It covers everything from robots.txt and canonicals to Core Web Vitals, hreflang for multi-region sites, and server log analysis. Every check includes:

- **Why it matters**: a one-line explanation you can paste straight into an audit report
- **Priority**: High / Medium / Low, so you know what to fix first
- **How to verify**: the tool or report to use (Search Console, Screaming Frog, PageSpeed Insights, logs, and so on)

## Why it matters

Technical issues are often invisible until traffic drops. One stray `noindex`, a broken hreflang cluster between `en-ae` and `ar-ae`, or a redirect chain left over from a migration can quietly cost rankings for months. A consistent checklist means:

- nothing important gets skipped, even under deadline
- audits are comparable across sites and over time
- juniors and clients can follow the logic behind each recommendation

## Folder structure

```
technical-seo-checklist/
├── README.md        # This file
├── checklist.md     # Full checklist with checkboxes and "why it matters" notes
├── checklist.csv    # Same items: Category, Check, Priority, How to verify
└── LICENSE          # MIT
```

## Sections covered

1. Crawlability
2. Indexation
3. Rendering & JavaScript
4. Site Architecture & Internal Linking
5. Core Web Vitals
6. Mobile
7. Structured Data
8. International SEO (including GCC examples such as `en-ae`, `ar-ae`, `ar-sa`, `en-sa`)
9. Redirects & Status Codes
10. Log File Analysis
11. Security (HTTPS)

## How to use it

**As a Markdown checklist**

1. Open [`checklist.md`](checklist.md).
2. Copy it into a GitHub issue, Notion page or any Markdown editor that supports task lists.
3. Tick items off as you audit the site. Add notes and screenshots under each item.

**As a spreadsheet**

1. Download [`checklist.csv`](checklist.csv).
2. Import it into Google Sheets (File → Import) or open it in Excel.
3. Add your own columns such as `Status`, `Owner`, `Notes` and `Due date`.
4. Filter by `Priority = High` to build the first sprint of fixes.

**Suggested audit order**

Crawlability → Indexation → Rendering → Redirects → Architecture → International → Structured Data → Core Web Vitals → Mobile → Security → Logs. Fixing access and indexation first stops you from optimising pages Google cannot see.

## Example output

A row from `checklist.csv`:

| Category | Check | Priority | How to verify |
|---|---|---|---|
| International SEO | All hreflang annotations have return links | High | hreflang_checker.py 'missing return link' column. |

An item from `checklist.md`:

```markdown
- [ ] **[H] All hreflang annotations have return links**
  _Why it matters:_ Without reciprocal links Google ignores the annotation.
```

## Related tools

Several checks can be automated with my other repositories:

- [hreflang-audit](https://github.com/haninbigleap-max/hreflang-audit) for the International SEO section
- [seo-automation](https://github.com/haninbigleap-max/seo-automation) for status codes, sitemaps and meta tags
- [schema-testing](https://github.com/haninbigleap-max/schema-testing) for structured data

## License

MIT. Free to use, adapt and share.
