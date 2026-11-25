# ScraperAPI free plan: 1,000 credits a month, what that actually scrapes, what happens when the 7-day trial ends, and when paying makes sense (with plan and credit-cost tables)

The ScraperAPI free plan costs **$0**, gives you **1,000 API credits per month** and up to **5 concurrent connections**, and doesn't ask for a credit card. Your first 7 days after signing up come with **5,000 credits** instead, so you can test at a larger scale; when the trial ends you either move to a paid plan or stay on the 1,000-credit monthly allowance.

Those 1,000 credits are worth very different amounts depending on what you point them at. Plain HTML pages, 1,000 a month (about 33 a day). Amazon, 200. Google or Bing, 40. That spread decides whether the free plan is enough for your project, so the tables below work it out per request type, along with the limits the free tier puts on you and the point where $49 a month beats rationing credits.

> **Quick verdict:** sign up, spend the 5,000 trial credits on your real target URLs, and stay free if you need less than roughly 1,000 plain pages a month. Once you've confirmed the API handles your sites and you need volume, Hobby is the next step at **$49/month**, or **$44.10/month billed annually** ($529.20 a year). 👉 [Create a free account and use the 5,000 trial credits](https://www.scraperapi.com/signup/?fp_ref=coupons)

## The full lineup, free through Enterprise

These are the eight tiers the pricing page currently shows. Every self-serve plan takes 10% off for annual billing; Enterprise is quoted per contract.

| Plan | Monthly | Annual (per month) | Credits per month | Concurrent threads |  |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | — | 1,000 | 5 | [Start free](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Hobby | $49 | $44.10 | 100,000 | 20 | [Hobby at $49](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 | [Startup at $149](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 | [Business at $299](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | $475 | $427.50 | 5,000,000 | 200 | [Scaling at $475](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 (limited offer: +250K bonus) | 300 | [Professional at $975](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 (limited offer: +500K bonus) | 500 | [Advanced at $1,975](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | [Ask about Enterprise pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

Three things shift with the tier besides the credit count. Geotargeting is US and EU on Hobby and Startup, country-level from Business up. Analytics history is the last 30 days on Hobby and Startup, unlimited from Business up. Priority support starts at Professional ($975), and a dedicated support team with Slack access only comes with Enterprise.

## What 1,000 credits actually buys

A standard page is 1 credit. Amazon, Walmart and eBay are 5, because ScraperAPI maintains custom logic for those sites. Google and Bing, subdomains included, are 25. LinkedIn is 30. Bypassing bot protection (Cloudflare, Cloudflare Turnstile, DataDome, PerimeterX/HUMAN, Akamai) adds 10 credits on top of the base cost, and so do JS rendering, premium proxies and screenshots. Premium proxies plus rendering together run 25 credits. Ultra Premium is 30 credits, or 75 with rendering, and both are paid-plan only.

| Request type | Credits per request | Requests from 1,000 credits |
| --- | --- | --- |
| Standard HTML page | 1 | 1,000 |
| Amazon, Walmart, eBay | 5 | 200 |
| Google or Bing (incl. subdomains) | 25 | 40 |
| LinkedIn | 30 | 33 |
| Page behind bot protection (bypass) | 11 | ~90 |
| `render=true` | 11 | ~90 |
| `premium=true` | 11 | ~90 |
| `premium=true` + `render=true` | 25 | 40 |
| `screenshot=true` | 11 | ~90 |
| `ultra_premium=true` | 30 | Paid plans only |
| `ultra_premium=true` + `render=true` | 75 | Paid plans only |
| Geotargeting, sessions, device type, output format, autoparse | 0 | No extra cost |

The per-request rates are ScraperAPI's published prices; the last column is my arithmetic from them. It's the number worth staring at before you plan a project around the free tier: a scraper that pulls product pages from Amazon gets 200 requests a month, which is under 7 a day. The same 1,000 credits aimed at unprotected blogs gets you 1,000.

The 5,000-credit trial multiplies all of this by five: 5,000 plain pages, 1,000 Amazon pages, 200 Google searches, or about 450 pages on a Cloudflare-protected site.

## The 7-day trial and the free plan are two separate allowances

Signing up gives you 5,000 credits for 7 days. That's the trial. The 1,000-credits-a-month free plan is what you drop to afterwards, and it's also what you're on if you never upgrade. Neither asks for a card, so day 8 doesn't trigger a charge. Your allowance just gets smaller.

That's the part people get wrong when they search for a ScraperAPI free trial and expect a countdown to a bill. There is no card on file to bill. The practical risk isn't an unexpected charge, it's building a pipeline during the trial that needs 5,000 credits a month and then discovering it needs a $49 plan to keep running.

Use the trial for what it's actually good for: run your real URLs, see which ones come back clean and which need rendering or premium proxies, and check the cost per request in the dashboard before you commit. If 5,000 credits won't cover the test, support can add more test credits on request.

## Where the free plan runs out of room

The allowance is the visible limit. Four others are documented and less obvious.

**No pay-as-you-go below Scaling.** Overage billing is available on Scaling ($475), Professional, Advanced and Enterprise. It is explicitly not available on Free, Hobby, Startup or Business. On the free plan there's no way to buy a few thousand extra requests in a busy month.

**No auto-upgrade either.** Hobby, Startup, Business, Scaling and Professional can opt in to move up a tier automatically when credits run out. Free can't, and neither can Advanced, which is the highest self-serve plan.

**Credits reset, they don't roll over.** Unused credits expire at renewal on every plan, Enterprise included. A quiet month doesn't bank capacity for a heavy one.

**Five concurrent connections.** The sixth simultaneous request gets a 429 and is turned away rather than queued, and you aren't charged for it. Five threads is fine for a script that walks one site politely; it's tight for anything parallel.

Ultra Premium parameters are also off the table until you're on a paid plan.

## How to keep 1,000 credits from disappearing

Billing rules work in your favour if you know them. You're charged for successful responses (200 and 404) and for requests you cancel after 70 seconds. Failed requests cost nothing, and a 429 costs nothing. A scraper that hammers a broken endpoint all month can burn zero credits.

Three tools in the dashboard make the rest predictable. The Domain Cost Estimator tells you what a specific URL will cost before you scrape it. Every response carries its cost in the `sa-credit-cost` header, so you can log spend per URL. And `max_cost` caps a single request, which stops one expensive page from quietly eating a chunk of the month.

Two habits stretch the allowance further. Send `render=true` and `premium=true` only to the pages that actually need them, since each one doubles or triples the cost of a request. And lean on the parameters that are free: geotargeting, session numbers, device type, output format and autoparse add nothing to the bill.

## When to upgrade, and which tier

Match the tier to your monthly credit burn at the rates above, not to the label on the plan.

- **Under 1,000 plain pages a month:** stay on the free plan. Nothing below Hobby is cheaper, and nothing at Hobby is worth $49 if you're at 800 pages.
- **Around 100,000 credits:** Hobby, $49/month. That's 100,000 plain pages, 20,000 Amazon pages or 4,000 Google searches, with 20 threads.
- **Around 1,000,000 credits:** Startup, $149/month, 50 threads, still US and EU geotargeting.
- **3,000,000 credits or country-level targeting:** Business, $299/month, 100 threads, unlimited analytics history.
- **You need overage billing or 300 threads:** Professional at $975/month and up. Scaling at $475 is where pay-as-you-go starts, with a monthly cap you set yourself.

Annual billing takes 10% off every self-serve tier. Over 12 months the gap is real money, and it's worth knowing before you pick monthly to "stay flexible":

| Plan | 12 months at the monthly rate | Annual total | Difference |
| --- | --- | --- | --- |
| Hobby | $588 | $529.20 | $58.80 |
| Startup | $1,788 | $1,609.20 | $178.80 |
| Business | $3,588 | $3,229.20 | $358.80 |
| Scaling | $5,700 | $5,130 | $570 |
| Professional | $11,700 | $10,530 | $1,170 |
| Advanced | $23,700 | $21,330 | $2,370 |

Annual plans hand you the whole year's credits upfront, usable on any timeline. Burn through them early and you can renew the same annual plan ahead of schedule for a fresh allocation. That suits a project with a heavy first quarter and a quiet summer better than a monthly plan does.

If you're close to a tier boundary, check before you buy. A workflow that needs 1.1 million rendered pages misses Startup's 1 million by 10% and, with no overage below Scaling, jumps to Business at $299 instead of $149. Trimming rendering to the pages that need it is usually cheaper than the next tier up.

👉 [Compare Hobby, Startup and Business on the pricing page](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Refunds, cancellation, and changing your mind

Paid plans come with a 7-day no-questions-asked refund policy. You can cancel at any time from the dashboard or through support, and there's no cancellation fee. Card details can be changed on the Billing page whenever you need to. Plan changes go both ways, so dropping from Business to Startup after a project wraps is a billing-page action, not a support ticket.

That combination makes the upgrade decision cheap to reverse: a month on Hobby to see whether your success rates hold up, with a refund window if the answer is no.

👉 [Start on the free plan and upgrade only when the credits justify it](https://www.scraperapi.com/signup/?fp_ref=coupons)

## FAQ

**Does the free plan need a credit card?**
No. Neither the 7-day trial nor the 1,000-credit monthly plan requires one.

**Will I be charged when the trial ends?**
No card is collected, so nothing is billed. The 5,000-credit trial simply ends and your account continues on 1,000 credits a month.

**Do unused credits carry over?**
No, on any plan. Your balance resets at renewal.

**Am I charged for failed requests?**
Only 200 and 404 responses are billed, plus requests you cancel after 70 seconds. Errors, timeouts and 429s cost nothing.

**Can I use JS rendering on the free plan?**
Yes, at 10 extra credits per request, so about 90 rendered pages from 1,000 credits. Premium proxies cost the same, and using both together is 25 credits per request.

**Can I use Ultra Premium?**
No. `ultra_premium=true` is limited to paid plans.

**What happens if I go over 5 concurrent connections?**
The extra request returns a 429 and is rejected rather than queued. There's no surcharge.

**Can I get more trial credits?**
Support can add test credits if 5,000 isn't enough to evaluate the API on your targets.

## The short version

Under 1,000 plain pages a month, the free plan covers you and costs nothing. Between there and Hobby's 100,000 credits, the free tier stops being a plan and becomes a bottleneck, especially on Amazon (200 pages) or Google (40 searches). Pick the tier by your credit burn, take the 10% annual discount if you'll be running for a year, and remember refunds are available for 7 days if the success rate on your targets doesn't hold.

Two things to do before you pay for anything: run a handful of your real URLs through the Domain Cost Estimator so the credit math is based on your sites rather than an average, and decide monthly versus annual knowing that year-upfront credits don't roll over.

👉 [Open a free ScraperAPI account and check your own URLs against the 5,000 trial credits](https://www.scraperapi.com/signup/?fp_ref=coupons)
