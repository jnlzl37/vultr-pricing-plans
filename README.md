# Buy VPS: How Much Does Vultr Cost, Which Plan Do You Need, and Is the $300 Credit Real? (Full Plan Table)

Vultr's realistic entry price is **$5–$6 a month for a 1 GB instance**, and every plan bills by the hour with the monthly rate as a cap, so a server you keep for three days costs three days' worth. New accounts can pick up **$300 in promotional credit** with the code `FLY300VULTR`, but that credit is documented as valid for 30 days from account creation, which makes it a month of free capacity rather than a year of cheap hosting. What follows is the price list I could confirm, what each tier is actually good for, and the terms that decide whether the credit is worth opening an account for.

> **Quick pick:** the 1 GB High Performance plan at **$6.00/mo** covers a small site, a Discord bot, a VPN node or a staging box, and it bills hourly. Step up to the **$12.00/mo 1 vCPU / 2 GB** plan once WordPress plugins or a real database are involved.
> 👉 [Open a Vultr account and attach the $300 credit](https://bit.ly/VuLtr)

## Buy VPS from Vultr: the full plan and price list

Vultr runs several product families at once (Regular Performance on older Intel hardware, High Performance on AMD EPYC or Intel Xeon with NVMe, plus General Purpose and other optimized tiers), and one independent tracker counts 88 separate configurations across them. The rows below are the price points that show up consistently in current listings and that matter for a first purchase.

| Plan | vCPU / RAM | Storage | Price (USD/mo) | Order |
| --- | --- | --- | --- | --- |
| Regular Performance (entry) | 1 vCPU / 1 GB | SSD | from $5.00 | [ Check the entry plan](https://bit.ly/VuLtr) |
| High Performance AMD | 1 vCPU / 1 GB | 25 GB NVMe | $6.00 | [ Start the $6 plan](https://bit.ly/VuLtr) |
| High Performance | 1 vCPU / 2 GB | NVMe | $12.00 | [ Start the $12 plan](https://bit.ly/VuLtr) |
| Largest tracked configuration | 12 vCPU / 24 GB | NVMe | $216.00 | [ Check the top tier](https://bit.ly/VuLtr) |

Two things about that table are worth spelling out, because they change how you budget.

First, **the floor price is disputed across sources**. One tracker lists a $2.50/mo plan; another puts the cheapest High Performance instance at $6.00/mo with a $5.00 basic tier below it. The gap is usually about which network setup and which hardware generation you land on, and it shifts. Treat $5–$6 as the number to plan around for a usable 1 GB box and confirm the current entry price on the pricing page before you promise anyone a budget.

Second, **every plan is billed hourly, capped at the monthly rate at 672 hours**. You are never locked into a month for a job that takes an afternoon. A $216/mo machine works out to a bit over $0.30 an hour, so a six-hour migration onto bigger hardware costs roughly $2. That is the single most useful property of the whole lineup for anyone doing one-off work: database moves, load tests, a build that needs 12 cores for two hours and 1 core for the other 718.

Bandwidth is metered, starting at 2 TB on the cheapest plan and scaling up with the tier. If your project is video, mirrors or anything that pushes terabytes out the door, price the overage before you commit.

## The $300 credit, priced out properly

The offer is real and it is listed on Vultr's own coupons page, next to a $200 version, a $250 version, and a deposit-match offer (`VULTRMATCH`, which doubles your first deposit up to $100). The $300 code is `FLY300VULTR`. You cannot stack them; the terms say promotional credit can't be combined with any other offer, and it's new customers only.

Here is the part most write-ups get wrong. Because the credit expires 30 days after the account is created, it is not "50 months of a cheap VPS." Divide $300 by 30 days and you get a budget of about **$10 a day, or roughly $0.42 an hour**, to spend on compute. Put differently:

- One 12 vCPU / 24 GB instance at $216/mo, running the entire 30 days, eats about $216 and leaves roughly $84.
- That leftover $84 will keep fourteen of the $6 plans, or seven of the $12 plans, running alongside it for the same 30 days.
- Or skip the big machine: twenty-five $12 instances running side by side for a month also adds up to $300.

So the credit is a one-month lab. It is genuinely useful for benchmarking three configurations against each other, running a load test on hardware you'd never rent at list price, or migrating a stack without paying twice. It is not a way to host a blog for free for two years, and any article that frames it that way has not read the expiry terms.

Practical details that decide whether the credit actually lands:

- **A card has to be on file.** The credit activates when you add a credit or debit card; write-ups of the offer agree that a PayPal-only setup won't clear verification. Check your Billing overview after signing up and confirm the balance appears before you deploy anything.
- **The clock starts at account creation, not at first deploy.** Don't register a week before you're ready to work.
- **It applies to select products only.** Cloud Compute instances are covered; don't assume every product in the catalogue is.

👉 [Claim the $300 credit on a new Vultr account](https://bit.ly/VuLtr)

## Hourly billing vs. monthly-only hosts

If you have only bought shared hosting before, the billing model is the biggest change. Hourly billing means the meter runs while the server exists and stops when you destroy it. A weekend experiment, a client demo, a CI runner that only wakes up during releases: all of these cost cents instead of a month.

The cap matters just as much. At 672 hours, a server left running all month never bills above its monthly rate, so there's no penalty for forgetting to shut something down, and no arithmetic to do at the end of the month. Set a calendar reminder to destroy anything you don't need, and the bill stays predictable.

One number nobody mentions in the sales copy: **the tracked range tops out at 24 GB RAM and 12 vCPU**. If you're shopping for 64 GB or a 32-core box, this isn't the catalogue for it, and you'll waste an afternoon looking. The $300 credit does cover a month on the $216 top-tier machine, which is a cheap way to find out whether 24 GB is enough before you sign a year with someone else.

## Which plan for which job

Independent hosting guidance puts most websites at 1–2 cores to start, WordPress and small applications at 2 GB of RAM minimum, and dynamic or database-heavy sites at 4 GB and up. Storage lands around 20–40 GB for a typical site. That maps onto Vultr's tiers cleanly:

**1 GB at $5–$6.** A static site behind a cache, a Telegram or Discord bot, a WireGuard node, an uptime monitor, a jump box. This is also the right size for learning: you get root, a real kernel and a public IPv4, and you can rebuild the whole thing from a snapshot in five minutes when you break it.

**2 GB at $12.** WordPress with a plugin stack, a small Node or Django app with Postgres on the same box, Gitea, a single Nextcloud instance for a few people. The extra gigabyte is what keeps MySQL from swapping during a plugin update, which is the most common way a cheap VPS turns into a support ticket.

**Above 2 GB.** WooCommerce with real order volume, self-hosted analytics, Elasticsearch, game servers with mods. You're past the point where a single number on a pricing table tells you enough, and the credit is the sane way to test 4 GB against 8 GB with your own workload rather than guessing.

**Short-lived jobs.** Anything measured in hours belongs on the biggest machine you can rent for that window, then gets destroyed. That's the case hourly billing was built for.

## How Vultr compares on price

Entry prices across the budget VPS market, all pulled from provider pages. Note that one column is in euros and the rest in dollars, so don't read them as a single ranked list.

| Provider | Entry price | What that buys | Billing | Worth knowing |
| --- | --- | --- | --- | --- |
| Vultr | $5.00–$6.00/mo | 1 vCPU / 1 GB, NVMe on High Performance | Hourly, capped at monthly | 32 locations; metered bandwidth from 2 TB |
| BuyVPS | $7.99/mo | 1 vCPU / 2 GB, NVMe RAID10 | Monthly, no setup fee | First month $1 once per customer; Amsterdam and New York only |
| LightNode | $7.71/mo | Entry configuration | Hourly | 40+ locations; first top-up bonus up to $15 |
| Infrawire | €8.30/mo | 4 GB RAM, NVMe | Monthly to yearly, no long contract | 7 locations; 7-day money-back on first payment; Alipay and crypto accepted |

Read that table by what you actually need. BuyVPS gives you 2 GB for $7.99 while Vultr charges $12 for the same RAM, so on pure RAM-per-dollar at the 2 GB size, BuyVPS wins. Vultr's advantage sits elsewhere: 32 regions including São Paulo, Seoul, Melbourne and Johannesburg, NVMe on every High Performance plan, and hourly billing that makes the $1-first-month, monthly-only model look rigid if your project has a short life. LightNode's hourly billing competes on the same axis with a wider location list and a smaller entry discount.

Two traps in comparing these numbers. **First-month pricing is not renewal pricing.** BuyVPS's $1 is a one-time acquisition price, and month two reverts to $7.99. Vultr's $6 is the rate, month after month; there's no promotional price that jumps at renewal, which is rare enough in this market to be worth saying out loud. And **euros are not dollars**: an €8.30 headline is not cheaper than a $7.71 headline just because 8.30 is a bigger-looking number in a different currency. Convert before you compare, and remember the figure you pay is the one in the provider's own currency.

If you need 64 GB of RAM, unmetered bandwidth, or a fully managed server where someone else patches the OS, none of these four is the right answer and you should keep looking.

## Before you place the order

- **Pick the region deliberately.** Most Vultr locations price the same, but São Paulo runs roughly 50% higher for an identical plan. Put the server near your users and check the regional price before checkout.
- **Estimate your bandwidth.** 2 TB on the cheapest plan is plenty for a website and nowhere near enough for a media server.
- **Confirm the credit landed.** Billing overview, before you deploy. If the balance isn't there, the code didn't attach and you'll be paying from the first hour.
- **Know the ceiling.** 24 GB RAM and 12 vCPU is the top of the range, so plan a migration path if your project is likely to outgrow it.

Choosing is then straightforward. A bot, a VPN, a small site or a box to learn on: the 1 GB plan at $5–$6. WordPress, a database, or anything with plugins: the 2 GB plan at $12. Multiple heavy containers or a game server: start at 4 vCPU, watch the bandwidth cap, and use the credit to test the size before you commit to it. And if the whole project has a two-week lifespan, hourly billing is the reason to be here at all.

👉 [Start with Vultr and apply the $300 new-account credit](https://bit.ly/VuLtr)
