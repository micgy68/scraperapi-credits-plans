# ScraperAPI sign up: 5,000 free credits, no card required — what they buy, what happens when they run out, and which plan to pick (full plan and credit-cost tables)

ScraperAPI's signup gives you **5,000 API credits over 7 days with no credit card**. When the trial ends you don't have to pay: the free plan keeps **1,000 credits a month and 5 concurrent connections**. Paid plans start at **$49/month** for Hobby, which carries 100,000 credits and 20 threads, and annual billing takes exactly 10% off every tier.

What the signup page doesn't spell out is how fast 5,000 credits disappear once the requests go to Google or Amazon, what the account does at the credit limit, and what to run in the first five minutes to prove the key works. Those three things decide whether you need a $49 plan or a $475 one, so they get most of the space below.

> **Short version:** start the trial, point it at the URLs you actually need for a day or two, then choose a plan from the measured credit cost instead of a guess about page counts. Most first accounts land on Hobby or Startup. Heavy Amazon or SERP work belongs on Scaling, which is also the first tier with pay-as-you-go.
>
> 👉 [Start the 7-day trial with 5,000 credits](https://www.scraperapi.com/signup?fp_ref=coupons)

## Every plan on the pricing page

All seven paid tiers carry the same core stack: JS rendering, premium residential and mobile IPs, anti-bot bypass, Autoparse JSON, rotating proxy pools, custom headers, CAPTCHA handling, desktop and mobile user agents, automatic retries, unlimited bandwidth, a 99.9% uptime guarantee and full crawler access. What changes between tiers is volume, concurrency, where you can geotarget, and the level of support.

| Plan | Monthly | Annual (per month) | Credits/mo | Concurrent threads | Sign up |
| --- | --- | --- | --- | --- | --- |
| Hobby | $49 | $44.10 | 100,000 | 20 | [ See Hobby pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 | [ See Startup pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 | [ See Business pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | $475 | $427.50 | 5,000,000 | 200 | [ See Scaling pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 | 300 | [ See Professional pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 | 500 | [ See Advanced pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | [ Request an Enterprise quote](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

Annual prices are the effective monthly rate when the full year is billed up front. Every link in the table opens the pricing page, where you pick the plan; ScraperAPI doesn't publish separate per-plan checkout URLs, so there's nothing more direct to send you to. Figures here follow the pricing page as confirmed in October 2026, and the live page is always the authority.

Three restrictions matter more than the feature list, and they're easy to miss:

| Plan | Geotargeting | Pay as you go | Support |
| --- | --- | --- | --- |
| Hobby | US and EU only | No | Standard |
| Startup | US and EU only | No | Standard |
| Business | Global, country-level | No | Standard |
| Scaling | Global, country-level | Yes | Standard |
| Professional | Global, country-level | Yes | Priority support |
| Advanced | Global, country-level | Yes | Priority routing |
| Enterprise | Global, country-level | Yes | Dedicated team and Slack |

Geotargeting is country-level, not city-level. If your project needs traffic from Brazil, Japan or Germany, Business at $299 is the cheapest route in.

**Trial and free plan are separate things.** The 5,000 credits are a one-off allowance that runs for 7 days. The 1,000 credits are a permanent monthly allowance on the free plan, capped at 5 concurrent connections. That free plan is a test bench, not a production tier: 1,000 credits is 1,000 standard pages, or 200 Google results.

## What 5,000 credits actually buy

Credits don't map one-to-one onto pages. The charge per request depends on the domain you target, the parameters you send, and whether ScraperAPI has to switch on anti-bot bypass. The published rates:

| Target | Credits per request | 5,000 trial credits | Hobby (100k) | Startup (1M) | Scaling (5M) |
| --- | --- | --- | --- | --- | --- |
| Standard page | 1 | 5,000 | 100,000 | 1,000,000 | 5,000,000 |
| Amazon (all domains) | 5 | 1,000 | 20,000 | 200,000 | 1,000,000 |
| Google or Bing (incl. subdomains) | 25 | 200 | 4,000 | 40,000 | 200,000 |
| LinkedIn | 30 | 166 | 3,333 | 33,333 | 166,666 |
| Cloudflare-protected page | 11 (1 + 10 bypass) | 454 | 9,090 | 90,909 | 454,545 |

The trial column is the reality check. Five thousand credits sounds generous until the target is Google: that's 200 queries, which is enough to validate a parser and nowhere near enough to build a dataset. Spend the trial on the hardest domains in your list, not the easiest. If 200 SERP requests confirm your pipeline works, the trial did its job.

The same arithmetic sets your monthly budget. Hobby's $49 buys 100,000 standard pages, which works out to **$0.49 per 1,000 pages**; Startup drops that to $0.149 and Scaling to $0.095. On Amazon data the gap is starker: 20,000 product pages on Hobby costs $2.45 per 1,000, against $0.745 on Startup.

Two tools keep this from being guesswork. The Domain Cost Estimator in the dashboard prices any URL before you commit to a run, and every response reports what the request cost in a `sa-credit-cost` header. The `max_cost` parameter caps what a single call is allowed to spend, which is worth setting on any job that mixes cheap pages with expensive ones.

👉 [Compare all seven plans and their current prices](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Day eight: what happens at the trial end and at the credit limit

**Credits do not roll over.** The balance resets on every renewal date and the unused remainder is gone. There's no banking a quiet month to cover a busy one, so size the plan to your peak rather than your average.

**On Hobby, Startup and Business, running out means stopping.** None of those three has pay-as-you-go. Once the allowance is exhausted, scraping pauses and further requests come back as **429 with no charge**. You will not be billed for an accidental overage on a $49 plan. The options are upgrading a tier or asking support about a custom plan.

**Pay-as-you-go starts at Scaling.** From $475 up, you can keep scraping past the allowance at a fixed per-credit rate on top of the subscription, with a monthly spending cap you set yourself. If your workload swings hard between months, that cap is the reason to start at Scaling instead of Business.

**Auto-upgrade is a setting you have to switch on.** On Hobby through Professional, the account can be configured to move to the next tier automatically when credits run dry. Left off, you get the 429 behaviour described above. Advanced and Enterprise don't offer it.

**Hitting the thread limit is also a 429.** Send more simultaneous requests than your plan allows (20 on Hobby, 50 on Startup, 200 on Scaling, 300 on Professional, 500 on Advanced) and the excess requests are rejected rather than queued, again at no charge. The fix is on your side: lower the concurrency and retry, or move batch work to the Async API.

**Enterprise is priced on volume, with one exception.** Custom discounts apply across your usage, but Ultra Premium requests carry their own minimum rate that the discount doesn't cover.

## From sign up to a working request

The API key lives in the dashboard at `dashboard.scraperapi.com`. Copy it into an environment variable such as `SCRAPERAPI_API_KEY` rather than into your source files, then run one real request before writing any integration code:


curl "https://api.scraperapi.com/?api_key=$SCRAPERAPI_API_KEY&url=https://httpbin.org/ip"


A JSON body containing an `origin` address means the key is live. If you get a **401**, the key is wrong or inactive, and retrying with the same key only wastes time.

Four other status codes cover most failures you'll meet. **403** means the target site blocked the request; retry with `premium=true`, `ultra_premium=true`, or a different `country_code`. **429** is your own concurrency ceiling. **500** or **503** is transient, so retry with exponential backoff three to five times.

Two limits sit in the documentation rather than the pricing page: a **50MB cap per request**, and an official recommendation to set a **70-second timeout** in your application, which noticeably improves success rates on difficult domains.

From there, pick the entry point that matches the job. The Python SDK (`pip install scraperapi-sdk`) and the Node package wrap the standard API in a few lines; PHP, Ruby and Java SDKs exist as well. For LLM agents, the remote MCP server exposes up to 22 tools over a single connection, while the local variant (`pip install scraperapi-mcp-server`, Python 3.11+) offers only `scrape`. For Amazon, Walmart, eBay, Redfin and Google, the Structured Data Endpoints return clean JSON and usually cost fewer credits than a raw fetch with `render=true`, so they're the better default wherever they're supported.

👉 [Create the account and copy your API key](https://www.scraperapi.com/signup?fp_ref=coupons)

## Refunds, cancellation, and the only discount that's real

ScraperAPI runs a **7-day no-questions-asked refund policy**: contact support@scraperapi.com within that window and the charge is reversed. Subscriptions can be cancelled at any time from the dashboard, and cancelling costs nothing. For a first paid month, that pairing removes most of the risk from testing a tier above what you think you need.

Annual billing is the one documented saving: exactly 10% off, applied across every tier, billed as a single yearly charge. No other discount appears on ScraperAPI's own pricing or documentation pages. Coupon aggregator sites list 10% and even 70% codes for the brand, but none of that is verifiable against an official page, so don't build a purchasing decision around one. The `fp_ref` tag on the links in this article is a tracking parameter, not a coupon code you can enter at checkout.

## Which plan to pick

The decision comes down to two measured numbers: monthly credit consumption on your real targets, and whether you need geotargeting outside the US and EU.

- **Evaluating only, or a few thousand standard pages a month** — stay on the free plan after the trial. 1,000 credits and 5 threads will cover it.
- **Roughly 100,000 standard pages, or 20,000 Amazon pages a month** — Hobby at $49. This is where most first paid accounts land.
- **A million standard pages, or 200,000 Amazon pages** — Startup at $149, which is 10x the volume of Hobby for 3x the price.
- **Any country outside the US and EU** — Business at $299, since geotargeting is the feature that forces the jump.
- **Pay-as-you-go, or a workload that swings** — Scaling at $475, the entry point for overage billing at a fixed per-credit rate.
- **A million Amazon pages, or 200,000 Google queries a month** — Scaling again, because 200,000 SERP requests at 25 credits each is 5 million credits.
- **Multi-source pipelines above 10 million credits** — Professional and Advanced add concurrency and priority routing; Enterprise is for volume commitments above 22 million credits.

Two things to confirm before you enter card details. First, monthly or annual: the 10% is real, but the year is billed in one payment, so it only pays off if you're confident the workload continues. Second, whether you need PAYG or non-US geotargeting, since either one moves the floor from $49 to $299 or $475 regardless of how many credits you use. Everything else in the plan grid scales linearly with volume.

👉 [Sign up free and price your own targets before choosing a plan](https://www.scraperapi.com/signup?fp_ref=coupons)
