# Technical SEO Checklist

A practical, 81-point technical SEO audit checklist. Each item has a short note on why it matters.
Priority and verification steps for every item are in [`checklist.csv`](checklist.csv).

Legend: **[H]** high priority, **[M]** medium, **[L]** low.

## Contents

1. [Crawlability](#crawlability)
2. [Indexation](#indexation)
3. [Rendering & JavaScript](#rendering--javascript)
4. [Site Architecture & Internal Linking](#site-architecture--internal-linking)
5. [Core Web Vitals](#core-web-vitals)
6. [Mobile](#mobile)
7. [Structured Data](#structured-data)
8. [International SEO](#international-seo)
9. [Redirects & Status Codes](#redirects--status-codes)
10. [Log File Analysis](#log-file-analysis)
11. [Security (HTTPS)](#security-https)

## Crawlability

- [ ] **[H] robots.txt is reachable at /robots.txt and returns 200**  
  _Why it matters:_ A 5xx on robots.txt can make Google pause crawling the whole host; a 404 means 'crawl everything'.
- [ ] **[H] robots.txt does not block important sections, CSS or JS**  
  _Why it matters:_ Blocked resources stop Google rendering pages correctly; blocked sections cannot be crawled.
- [ ] **[M] XML sitemap is referenced in robots.txt**  
  _Why it matters:_ Helps all crawlers discover the sitemap without manual submission.
- [ ] **[H] XML sitemap(s) submitted in Search Console with no errors**  
  _Why it matters:_ Sitemaps speed up discovery and give you indexing coverage data per sitemap.
- [ ] **[H] Sitemaps only contain 200, indexable, canonical URLs**  
  _Why it matters:_ Redirects, 404s and noindexed URLs in sitemaps send mixed signals and waste crawl budget.
- [ ] **[M] No orphan pages (important pages have internal links)**  
  _Why it matters:_ Pages only reachable via sitemap are crawled less and receive no internal link equity.
- [ ] **[H] Faceted navigation and URL parameters are controlled**  
  _Why it matters:_ Uncontrolled filters can create millions of near-duplicate URLs and exhaust crawl budget.
- [ ] **[M] Server responds quickly and reliably to Googlebot**  
  _Why it matters:_ Slow or erroring servers reduce crawl rate.
- [ ] **[M] Pagination links are crawlable &lt;a href> links**  
  _Why it matters:_ Google does not click buttons; 'Load more' without links hides deeper content.

## Indexation

- [ ] **[H] Important pages are indexed**  
  _Why it matters:_ If it is not indexed it cannot rank.
- [ ] **[H] No accidental noindex on important pages**  
  _Why it matters:_ A stray noindex (often left from staging) removes pages from search.
- [ ] **[H] Canonical tags are present, absolute and self-referencing on canonical pages**  
  _Why it matters:_ Canonicals consolidate duplicate signals to the preferred URL.
- [ ] **[H] Canonical targets return 200 and are indexable**  
  _Why it matters:_ Canonicals pointing to redirects, 404s or noindexed pages are usually ignored.
- [ ] **[H] Duplicate content variants consolidated (http/https, www/non-www, trailing slash, case)**  
  _Why it matters:_ Duplicates split link signals and confuse canonical selection.
- [ ] **[M] Thin, low-value or empty pages are noindexed or improved**  
  _Why it matters:_ Large volumes of low-quality pages can drag down overall site quality.
- [ ] **[M] Google-selected canonical matches user-declared canonical**  
  _Why it matters:_ A mismatch means Google disagrees with your setup.
- [ ] **[M] Internal search result pages are not indexable**  
  _Why it matters:_ Search result pages create infinite low-quality URL spaces.

## Rendering & JavaScript

- [ ] **[H] Main content is present in the rendered HTML**  
  _Why it matters:_ If content only appears after interaction, Google may never see it.
- [ ] **[H] Critical content and links do not depend on user events**  
  _Why it matters:_ Googlebot does not scroll, click or hover.
- [ ] **[H] Title, meta description, canonical and robots are in the initial HTML**  
  _Why it matters:_ Changing these with JS is processed later and less reliably.
- [ ] **[H] JS and CSS files return 200 and are not blocked**  
  _Why it matters:_ Failed resources lead to incomplete rendering.
- [ ] **[H] Internal links use &lt;a href> with real URLs**  
  _Why it matters:_ onclick handlers and javascript: links are not followed.
- [ ] **[M] No reliance on URL fragments (#) for unique content**  
  _Why it matters:_ Google generally ignores fragments; #-routed pages collapse into one URL.
- [ ] **[M] Server-side rendering or static generation for key templates**  
  _Why it matters:_ SSR/SSG removes the render queue delay and reduces risk.
- [ ] **[M] Soft 404s handled correctly in client-side apps**  
  _Why it matters:_ SPAs often return 200 for missing pages, creating soft 404s.

## Site Architecture & Internal Linking

- [ ] **[H] Important pages are within 3 clicks of the homepage**  
  _Why it matters:_ Shallow depth improves crawl frequency and passes more internal link equity.
- [ ] **[M] Logical URL structure that mirrors the site hierarchy**  
  _Why it matters:_ Clear structures help users and search engines understand relationships.
- [ ] **[M] Breadcrumbs present on deep templates (with BreadcrumbList schema)**  
  _Why it matters:_ Breadcrumbs add contextual internal links and can show in results.
- [ ] **[M] Descriptive anchor text on internal links**  
  _Why it matters:_ Anchor text tells Google what the target page is about.
- [ ] **[H] No internal links to redirects or 4xx pages**  
  _Why it matters:_ Each hop wastes crawl budget and leaks equity.
- [ ] **[M] Key money pages receive the most internal links**  
  _Why it matters:_ Internal link count is a strong signal of importance.
- [ ] **[M] Hub/category pages link to all relevant children**  
  _Why it matters:_ Hubs distribute authority and help discovery.
- [ ] **[L] Navigation and footer links are crawlable and not bloated**  
  _Why it matters:_ Huge mega-menus dilute equity and add boilerplate.

## Core Web Vitals

- [ ] **[H] LCP is 2.5s or less at the 75th percentile**  
  _Why it matters:_ Largest Contentful Paint measures perceived load speed and is a page experience signal.
- [ ] **[H] INP is 200ms or less at the 75th percentile**  
  _Why it matters:_ Interaction to Next Paint measures responsiveness to user input.
- [ ] **[H] CLS is 0.1 or less at the 75th percentile**  
  _Why it matters:_ Layout shifts frustrate users and cause mis-clicks.
- [ ] **[M] LCP image is not lazy-loaded and is prioritised**  
  _Why it matters:_ Lazy-loading the hero image delays LCP.
- [ ] **[M] Images are compressed, sized and served in modern formats**  
  _Why it matters:_ Images are usually the largest bytes on a page.
- [ ] **[M] Width and height (or aspect-ratio) set on images, ads and embeds**  
  _Why it matters:_ Reserving space prevents layout shift.
- [ ] **[M] Render-blocking CSS/JS minimised; third-party scripts audited**  
  _Why it matters:_ Blocking resources and heavy tags delay paint and interaction.
- [ ] **[M] Server response time (TTFB) is under ~800ms**  
  _Why it matters:_ Slow TTFB delays every other metric.

## Mobile

- [ ] **[H] Site is responsive and uses a correct viewport meta tag**  
  _Why it matters:_ Google uses mobile-first indexing.
- [ ] **[H] Mobile and desktop serve the same primary content**  
  _Why it matters:_ Content hidden or removed on mobile is what Google indexes.
- [ ] **[H] Structured data, meta tags and links match on mobile**  
  _Why it matters:_ Missing elements on mobile are lost in mobile-first indexing.
- [ ] **[M] Tap targets and font sizes are usable**  
  _Why it matters:_ Poor usability hurts engagement and conversions.
- [ ] **[M] No intrusive interstitials on landing**  
  _Why it matters:_ Full-screen pop-ups on mobile can hurt rankings and UX.
- [ ] **[M] RTL layouts render correctly for Arabic pages**  
  _Why it matters:_ Broken RTL on ar-ae / ar-sa pages hurts usability for the target audience.

## Structured Data

- [ ] **[H] JSON-LD is valid and parses without errors**  
  _Why it matters:_ Invalid markup is ignored.
- [ ] **[M] Organization and WebSite schema on the homepage**  
  _Why it matters:_ Helps Google and AI systems understand the entity behind the site.
- [ ] **[M] Template-appropriate types used (Product, Article, LocalBusiness, FAQPage, BreadcrumbList)**  
  _Why it matters:_ Correct types make pages eligible for rich results.
- [ ] **[H] Markup matches visible on-page content**  
  _Why it matters:_ Marking up content users cannot see violates guidelines.
- [ ] **[M] Required and recommended properties are filled**  
  _Why it matters:_ Missing required properties block rich results eligibility.
- [ ] **[M] No errors in Search Console enhancement reports**  
  _Why it matters:_ Errors are reported per template and can affect many URLs.

## International SEO

- [ ] **[H] hreflang annotations present for every language/region version**  
  _Why it matters:_ hreflang helps Google serve en-ae vs ar-ae vs ar-sa versions to the right users.
- [ ] **[H] All hreflang annotations have return links**  
  _Why it matters:_ Without reciprocal links Google ignores the annotation.
- [ ] **[H] Each page includes a self-referencing hreflang**  
  _Why it matters:_ Self-reference is required for the cluster to be valid.
- [ ] **[H] Language and region codes are valid (ISO 639-1 + ISO 3166-1 Alpha-2)**  
  _Why it matters:_ Codes like en-uk or ar-ksa are invalid and ignored.
- [ ] **[M] x-default defined for language selector or global fallback**  
  _Why it matters:_ x-default tells Google which page to show users who match no listed locale.
- [ ] **[H] hreflang URLs are canonical, indexable and return 200**  
  _Why it matters:_ Pointing hreflang at redirects or non-canonicals breaks the cluster.
- [ ] **[M] Content is actually localised (language, currency, phone, address)**  
  _Why it matters:_ Near-identical en-ae and en-sa pages may be folded together.
- [ ] **[H] No automatic IP-based redirects that block crawlers**  
  _Why it matters:_ Googlebot mostly crawls from the US and may never see other versions.
- [ ] **[L] html lang and dir attributes are set correctly**  
  _Why it matters:_ Supports accessibility and language detection; dir='rtl' for Arabic.

## Redirects & Status Codes

- [ ] **[H] Permanent moves use 301 or 308**  
  _Why it matters:_ Permanent redirects consolidate signals to the new URL.
- [ ] **[H] No redirect chains longer than one hop**  
  _Why it matters:_ Chains slow users, waste crawl budget and can lose signals.
- [ ] **[H] No redirect loops**  
  _Why it matters:_ Loops make URLs unreachable.
- [ ] **[M] Removed pages return 404 or 410 (not 200 or homepage redirect)**  
  _Why it matters:_ Redirecting everything to the homepage is treated as a soft 404.
- [ ] **[M] Custom 404 page is helpful and returns a real 404 status**  
  _Why it matters:_ Helps users recover without creating soft 404s.
- [ ] **[H] Migrations have a complete redirect map**  
  _Why it matters:_ Missing redirects after a migration lose rankings and backlinks.
- [ ] **[H] 5xx errors are monitored and rare**  
  _Why it matters:_ Persistent 5xx errors lead to deindexing.

## Log File Analysis

- [ ] **[M] Server logs available and include user agent, status, URL and timestamp**  
  _Why it matters:_ Logs show what search engines actually crawl, not what you hope they crawl.
- [ ] **[M] Googlebot hits verified via reverse DNS**  
  _Why it matters:_ Many bots spoof the Googlebot user agent.
- [ ] **[M] Crawl budget is spent on important sections**  
  _Why it matters:_ Excess crawling of parameters or low-value pages delays important updates.
- [ ] **[M] Important pages are crawled regularly**  
  _Why it matters:_ Pages never crawled cannot be refreshed in the index.
- [ ] **[M] Crawled 3xx/4xx/5xx URLs are identified and fixed**  
  _Why it matters:_ Wasted hits on errors and redirects reduce useful crawling.
- [ ] **[L] AI and other crawlers are identified (GPTBot, ClaudeBot, PerplexityBot, etc.)**  
  _Why it matters:_ Understanding AI crawler access informs your AI search visibility strategy.

## Security (HTTPS)

- [ ] **[H] Entire site served over HTTPS with a valid certificate**  
  _Why it matters:_ HTTPS is a lightweight ranking signal and essential for user trust.
- [ ] **[H] HTTP redirects to HTTPS with a single 301**  
  _Why it matters:_ Prevents duplicate http/https versions.
- [ ] **[M] No mixed content**  
  _Why it matters:_ Insecure resources on HTTPS pages trigger browser warnings or are blocked.
- [ ] **[L] HSTS header enabled**  
  _Why it matters:_ Forces browsers to use HTTPS and removes a redirect hop for returning users.
- [ ] **[M] Canonicals, hreflang, sitemaps and internal links use HTTPS URLs**  
  _Why it matters:_ http references cause unnecessary redirects and mixed signals.
- [ ] **[H] No hacked content, spam pages or security issues flagged**  
  _Why it matters:_ Security issues can cause warnings in search results and deindexing.

---

Tip: copy this file into an issue or project board and tick items off as you audit a site.
