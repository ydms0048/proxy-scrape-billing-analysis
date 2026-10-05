# proxyscrape review: what the "unlimited" clause hides, what the free list really is, and when $1/GB pay-as-you-go wins

Most people searching for a ProxyScrape review are stuck on one question: is this the cheap option, or is the cheap option somewhere else? Both things are true, depending on which of ProxyScrape's five products you're looking at. That's the part most reviews skip, so let's start there.

## ProxyScrape in one paragraph

A Belgian proxy provider that's been running since 2018. Its reputation comes from two very different things: a public free proxy list that anyone can scrape off the site, and a paid service that looks nothing like it. The free list is noisy, slow, and frequently dead. The paid side is a proper network with rotating residential, unlimited residential, shared and dedicated datacenter, and rotating mobile products, aimed mostly at scraping, automation and QA testing.

Worth knowing up front: the company's own comparison pages quote different residential pool sizes depending on the page you land on, ranging from around 48 million up to 120 million addresses, with a separate figure of roughly 40,000 datacenter IPs. Third-party reviewers repeat whichever number they saw first. Treat the big number as marketing and the datacenter figure as roughly accurate.

## Signing up: what you get before paying

Register and you get a trial of 100 shared datacenter proxies for seven days, with a 10 GB traffic cap. Two caveats that catch people out:

- The trial is HTTP only. SOCKS5 unlocks after purchase.
- You have to whitelist your IP address in the dashboard under IP Authentication, or nothing responds. This trips up a surprising number of first-time users who assume the proxies are broken.

An important distinction: that trial is not the same thing as the public free proxy list on the site. The list is a permanently open feed of IPs from all over, and it's where a lot of ProxyScrape's review complaints come from. The trial is a controlled slice of their own datacenter network. If you're evaluating the company, evaluate the trial.

## Five products, four different billing models

This is where the review needs to slow down, because "ProxyScrape pricing" is not one price. It's four separate billing logics stacked in the same dashboard, and picking the wrong one is how people end up paying 5x more than they expected.

| Product | How you pay | Entry point |
| --- | --- | --- |
| Rotating residential | Per GB | Small bundles, roughly $3–5/GB; falls to about $1.50–2.00/GB at the 1 TB tier |
| Unlimited residential | Flat monthly | From around $2,630/month |
| Shared datacenter | Per IP, per month | Minimum 1,000 proxies, from about $25/month |
| Dedicated datacenter | Per IP, per month | Minimum 5 IPs, US locations only, roughly $1.10–1.90 per IP |
| Rotating mobile | Per GB | US, UK and Austria only |

A note on the residential numbers, because they don't agree across sources. Third-party pricing trackers list the small-bundle rate at $4.25–4.85/GB. ProxyScrape's own pricing page currently runs a 25% residential discount that puts 5 GB at $14.25, which works out to $2.85/GB. Promotions move this figure constantly. What does hold steady is the shape of the curve: you pay somewhere in the $3–5/GB band at small volume, and the rate only drops to $1.50–2.00/GB once you're buying around a terabyte. That's the standard volume curve in this industry, and it's the single most important thing to understand before you compare ProxyScrape to a pay-as-you-go provider.

Also worth flagging: the shared datacenter minimum is 1,000 proxies. If you need ten datacenter IPs to run a small automation job, ProxyScrape's shared product isn't sold in a size that fits you. The dedicated product starts at 5 IPs, but it's US-only, which kills it for anyone targeting European or Asian sites.

## The "unlimited" datacenter clause almost nobody reads

Here's the detail that most ProxyScrape reviews miss entirely. Their terms and conditions include a Fair Use Policy that applies specifically to datacenter plans marketed as "unlimited."

The formula, in their own words: you get 1 TB of bandwidth for every $5 you pay for the subscription, with a minimum allowance of 10 TB regardless of the calculation. So a $20/month subscription calculates to 4 TB, but the 10 TB floor applies anyway. A $100/month subscription calculates to 20 TB.

Cross that line and ProxyScrape reserves the right to do any of four things, at its own discretion and without asking you first:

1. Bill you $5 per TB of excess bandwidth
2. Require you to upgrade to a higher tier or sign a custom agreement
3. Throttle your bandwidth, temporarily or progressively
4. Take "any other reasonable measures"

The word "unlimited" is doing a lot of work there. In practice the 10 TB floor is generous for most scraping operations, so this rarely bites. But if your workload is genuinely heavy, the difference between "unmetered" and "unlimited" is exactly this clause — and the provider is allowed to change the calculation method, the allowance ratio, or the minimum at any time.

Now run the unlimited residential math. From around $2,630/month, flat. Against ProxyScrape's own 1 TB residential rate of roughly $2.00/GB, that flat fee only starts paying off once you're burning past about 1.3 TB a month. Below that, per-GB billing is cheaper. Way below that, it's not even close.

## Where ProxyScrape genuinely holds up

Fairness matters here, so let's not pretend the whole product is a trap.

The trial is real value. Seven days and 100 proxies with no payment details is more than most providers offer, and it's the correct way to test whether their pool survives your specific targets.

Per-IP datacenter pricing is competitive. $25/month for 1,000 shared datacenter IPs with unmetered transfer is a sensible rate for unprotected targets — price monitoring on simple sites, parsing your own infrastructure, bulk QA checks. Residential IPs are wasted on that kind of work.

City-level targeting on residential, coverage across 195 countries, sticky sessions from three minutes up to twelve hours depending on type, a working API, and free checker and list-filter tools. Nothing exotic, but it's all there.

At the top of the curve, $1.50/GB at 5,000 GB is a legitimate rate. If you buy in the terabyte range and your targets are ones datacenter IPs can't touch, ProxyScrape is a normal, defensible choice.

## What the reviews actually say

Trustpilot carries a few hundred reviews for ProxyScrape, averaging around 4.2 out of 5 in the most recent tallies. Positive reviews cluster around convenience, rotation, unlimited connections per IP, and value for money. Complaints cluster in a few predictable places: IPs from the free list frequently don't work, the dashboard looks dated, getting a refund on large traffic bundles is difficult, and support isn't always fast.

One caution: aggregator scores for this provider vary a lot depending on which directory you read — you'll see 4.2 and 4.8 quoted for the same company. Directory scores are compiled at different times from different sample sizes, so a single number from a single site isn't worth much on its own. Read the negative reviews instead; they're the ones that tell you what breaks.

## The real cost driver: paying for failures

Every per-GB provider bills you the same way for a successful request and a blocked one. A Cloudflare challenge page is 30–80 KB you paid for, followed by a retry you also pay for. At $3/GB with a 20% failure rate and one retry each, your effective cost is closer to $3.60/GB. At $1/GB with the same failure rate, it's $1.20/GB.

This is why per-GB rate comparison is only half the story, and why the honest advice is to test against your actual targets before committing to a big bundle. It's also why the entry price matters so much more than the headline rate. A $5 test that tells you your failure rate is worth more than a terabyte bought at a discount.

## The pay-as-you-go option worth comparing against

If your usage is lumpy — heavy one month, quiet the next — subscription bundles are structurally the wrong shape. You buy 100 GB, use 30, and the rest either expires or sits there.

DataImpulse prices residential traffic at a flat **$1/GB** with a $5 minimum and no subscription. Datacenter runs **$0.50/GB**, mobile **$2/GB**, and premium residential **$5/GB**. Purchased traffic never expires, so leftovers carry over instead of evaporating at renewal. The network covers 195 countries on a first-party pool the company says it doesn't resell from other providers — which matters more than it sounds, because resold traffic is where a lot of dirty IPs come from.

👉 [Check DataImpulse's current per-GB pricing and $5 intro offer](https://bit.ly/dataimPulse)

Country-level targeting is included in the base rate. City, state, ZIP and ASN targeting is billed at double the standard rate on standard residential, which is worth knowing before you design a campaign around ZIP-level precision. Premium residential includes all targeting filters at no surcharge.

On support and track record: 24/7 human support rather than a bot queue, a 4.8/5 rating on G2, and a published success rate of 99.51%. Intro plans come with a 7-day money-back window for card payments, provided you've used less than 80% of the traffic — crypto purchases are non-refundable, which is standard across this industry and worth reading before you pay in BTC.

Where DataImpulse is the wrong tool: there's no static ISP product, no fully managed scraping API with JavaScript rendering and CAPTCHA solving, and it explicitly isn't built for banking or government targets. If those are your requirements, neither DataImpulse nor ProxyScrape's basic residential product is the answer.

## Every DataImpulse plan, side by side

The billing model is a dashboard top-up rather than fixed monthly packages, so the "plans" are tiers of the same balance. Here's the full picture.

| Plan | Best for | Entry price | Standard rate | Volume tier | Purchase |
| --- | --- | --- | --- | --- | --- |
| Residential | Defended targets: e-commerce, SERPs, social | $5 for 5 GB | $1.00/GB | $0.80/GB at 1 TB | [Start with the residential intro](https://bit.ly/dataimPulse) |
| Datacenter | Unprotected pages, speed-first testing | $5 for 10 GB | $0.50/GB | $0.45/GB at 1 TB ($450) | [Open a datacenter plan](https://bit.ly/dataimPulse) |
| Mobile | Hard targets, app and mobile-web data, 4G/5G/LTE | $5 for 2.5 GB | $2.00/GB | $1.60/GB at 1 TB ($1,600) | [Add mobile traffic](https://bit.ly/dataimPulse) |
| Premium Residential | High-stakes scraping, dedicated account manager | $5 for 1 GB (paid trial) | $5.00/GB to 1 TB | Custom from $20,000 at 5 TB+ | [See the premium residential pool](https://dataimpulse.com/premium-residential-proxies/?aff=86938) |

Coverage differs by product too: residential lists 214 locations, premium residential 210, mobile 191, datacenter 123. All four support HTTP(S) and SOCKS5, rotating and sticky sessions.

For most people reading a ProxyScrape review, the relevant comparison is residential at $1/GB against ProxyScrape's $3–5/GB at small volume. At 5 GB/month that's $5 versus roughly $15–25. The gap closes only if you buy ProxyScrape in the terabyte range — and it only closes *at all* if you actually consume what you bought.

## Which one should you actually pick

Straight answers, no hedging:

- **You scrape under ~50 GB a month, or your usage swings.** DataImpulse at $1/GB with non-expiring traffic. Subscriptions charge you for a bundle you won't finish.
- **You need datacenter IPs by the thousand with unmetered transfer.** ProxyScrape's shared plan at $25 for 1,000 proxies is hard to beat, since DataImpulse's datacenter product is billed per GB rather than per IP.
- **You need ten datacenter IPs for a small job.** DataImpulse, because ProxyScrape won't sell you a thousand-proxy minimum piecemeal.
- **You're scraping heavily protected sites and volume is high.** Test both on your actual targets before buying anything. Failure rate, not sticker price, decides this one.
- **You want a static ISP product.** Neither. Look at a provider that sells static residential IPs per month.

One practical note: both providers let you start tiny. A $5 test on your own target list beats any review, including this one, because IP pool quality is site-specific. Run the trial, count your 403s, and do the arithmetic on cost per successful request rather than cost per GB.

## FAQ

**Is ProxyScrape free?**
Partly. There's a public free proxy list you can download without an account, and a 7-day trial of 100 shared datacenter proxies capped at 10 GB. The paid products are a separate thing, and the free list is not a sample of them.

**Does ProxyScrape throttle "unlimited" plans?**
Yes, it can. Datacenter plans marketed as unlimited carry a guaranteed allowance of 1 TB per $5 paid, with a 10 TB minimum. Exceed it and the company can charge $5/TB, demand an upgrade, or throttle your bandwidth without prior approval.

**Do DataImpulse credits expire?**
No. Traffic you buy stays in your account until you use it, and there's no subscription requirement.

**Is $1/GB residential too cheap to be reliable?**
That's the right instinct, and the answer is that per-GB price and block rate are independent variables. A cheaper pool that fails 40% of the time costs more per usable page than a pricier one that fails 5%. Which is why the $5 entry point matters more than the rate: it lets you measure the failure rate on your own targets before you commit.

**Can I use the same account for residential and datacenter?**
On both providers, yes. DataImpulse separates them as top-up products inside one dashboard; ProxyScrape's residential and datacenter products sit in the same account, though mobile has to be added from the services menu rather than the dashboard's Add Service button.

## Bottom line

ProxyScrape is a legitimate provider with a genuinely useful free trial, a competitive per-IP datacenter product, and a residential line that's priced for volume buyers — with a fair-use clause on "unlimited" plans that's worth reading before you plan around it. If you're buying a terabyte of residential traffic at a time, it's a reasonable pick.

If you're not, the per-GB math doesn't work in your favour, and the free proxy list everyone associates with the brand isn't the product you'd be paying for anyway. For anything under roughly 50 GB a month or any workload that swings, a pay-as-you-go provider at $1/GB with non-expiring traffic simply costs less for the same job.

👉 [Start with a $5 DataImpulse balance and test it against your own targets](https://bit.ly/dataimPulse)
