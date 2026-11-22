# AI agent VPS: how much CPU and RAM you actually need, what AVA Hosting charges from €2 to €40, and the model bill that sits next to it (full plan table)

A coding agent that keeps working after you close the laptop needs around 4 vCPU and 8 GB of RAM. A personal assistant answering over Telegram or Slack runs on 2 GB. AVA Hosting prices the first at €20 a month and the second at €5, with a €2 entry plan for a test deployment.

Below is the full plan list from AVA Hosting's own catalogue, the half of the bill that never appears in a plan grid, and the handful of details worth confirming before you pay.

> **Quick pick:** running one agent against a hosted model, the €5 plan (1 vCPU / 2 GB) is the minimum AVA Hosting itself recommends. Running Claude Code or several subagents in parallel, take the €20 tier (4 vCPU / 8 GB / 90 GB or 100 GB depending on catalogue). Multiple agents or a small team, €30 to €40.
> 👉 [See AVA Hosting's current plan list and prices](https://my.ava.hosting/aff.php?aff=15562)

## The full AVA Hosting plan list, both catalogues

AVA Hosting runs two catalogues over the same price ladder. "Self-hosted Start" is the one that matters if you're deploying an agent application; the plain VPS/VDS catalogue is the same hardware with ECC memory, a guaranteed 1 Gbps port and an extra €15 tier wedged in the middle. Names differ between the two, storage differs slightly, and the €20 tier is the only row most readers need to compare.

**Self-hosted app plans (Self-hosted Start)**

| Plan | vCPU / RAM | NVMe | Transfer | Price | Order |
| --- | --- | --- | --- | --- | --- |
| Start | 1 / 1 GB | 15 GB | Unlimited | €2.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| Mini | 1 / 2 GB | 25 GB | Unlimited | €5.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| Basic | 2 / 4 GB | 50 GB | Unlimited | €10.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| Pro | 4 / 8 GB | 100 GB | Unlimited | €20.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| Business | 6 / 12 GB | 150 GB | Unlimited | €30.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| Power | 8 / 16 GB | 200 GB | Unlimited | €40.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |

**VPS/VDS catalogue**

| Plan | vCPU / RAM | NVMe | Port | Price | Order |
| --- | --- | --- | --- | --- | --- |
| VPS Nano | 1 / 512 MB ECC | 20 GB | 100 Mbps | €11.00/yr (showing 0 available) | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| VPS One* | not listed | not listed | not listed | €5.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| VPS Basic | 2 / 4 GB ECC | 50 GB | 1 Gbps | €10.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| VPS Lucky | 2 / 6 GB ECC | 70 GB | 1 Gbps | €15.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| VPS Power | 4 / 8 GB ECC | 90 GB | 1 Gbps | €20.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| VPS Extra | 6 / 12 GB ECC | 120 GB | 1 Gbps | €30.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |
| VPS Ultra | 8 / 16 GB ECC | 160 GB | 1 Gbps | €40.00/mo | [Order](https://my.ava.hosting/aff.php?aff=15562) |

\*VPS One's RAM and disk figures weren't readable on the catalogue page; the order form carries them. Treat it as the €5 entry point alongside Mini.

Every VPS/VDS row lists weekly backups, DDoS protection, full root access, a control panel, a 99.9% uptime SLA, 24/7 support and unlimited bandwidth. Prices are shown in euros as "starting from" figures, so the total at checkout may move with VAT and your billing country.

## Which tier actually fits your agent

The 4 vCPU / 8 GB line is where agent workloads stop queueing. QuantVPS, which sells into the same search traffic, recommends at least 4 vCPU and 8 GB for AI coding agents, and the same figure shows up in Contabo's plan ladder as its second tier. Below 2 GB of RAM you're running an agent that reloads context constantly and dies on a large repository.

At identical €20 prices, Pro gives 100 GB of disk and Power gives 90 GB. If your agent clones repositories, keeps a local vector store or writes logs, Pro is the better of the two, and it's the plan to click if you only read one row of the tables above.

The jump to €30 buys 6 vCPU and 12 GB, which is the point where parallel subagents stop competing for the same cores. €40 doubles the memory again for teams running several long-lived services on one box.

One thing the grid doesn't tell you: whether those vCores are shared or guaranteed. AVA Hosting's plan pages don't state it either way. Space-Node says openly that its vCores are shared and only RAM is dedicated; QuantVPS advertises dedicated CPU and RAM and no throttling. If you're planning four subagents doing concurrent work, that difference decides whether the €20 tier behaves like 4 cores or like 1.5. Ask support before you size up.

👉 [Check the €20 4 vCPU / 8 GB plan](https://my.ava.hosting/aff.php?aff=15562)

## The bill has two halves

The VPS fee pays for a machine sitting in a rack. It does not pay for the model. Claude, GPT and the rest run on the AI company's infrastructure and are billed to your own API key or subscription, and AVA Hosting's own hosted-app page says the same thing about its OpenClaw product: model-provider accounts and usage stay separate from the hosting fee.

So the real monthly number is the plan price plus whatever your token consumption costs. On the server side that's easy arithmetic: €5 is €60 a year, €20 is €240, €40 is €480. On the model side there is no fixed figure, because it depends on how much your agent reads, writes and retries. A background agent doing a nightly report costs far less than one refactoring a codebase all afternoon.

The trap is assuming a VPS removes the limits of a consumer AI plan. It doesn't. Claude Pro and Max carry a five-hour session cap and a weekly cap, and ChatGPT plans have their own; those follow your account, not your server. Moving the agent to a data centre fixes uptime and gives you a static IP for webhooks. It doesn't buy you more messages.

AVA Hosting's OpenClaw guide makes the point from the other direction, pitching "no per-message fees, flat VPS cost only" against assistants that charge per message. That holds for the server bill. Your provider still meters you.

👉 [Start on the €5 plan and upgrade if the agent needs more](https://my.ava.hosting/aff.php?aff=15562)

## Five things to confirm before you pay

1. **Backups.** The VPS/VDS catalogue includes weekly backups on every plan. Space-Node, by contrast, states plainly that backups are not included. Confirm the self-hosted group carries the same backup terms, and test a restore once rather than assuming.
2. **Downgrades.** AVA Hosting doesn't publish a downgrade policy. IONOS states outright that moving to a smaller plan isn't technically supported, so this isn't a hypothetical worry. If you might shrink later, ask first, and consider starting on €10 rather than €30.
3. **One-click installs.** AvaHost ships a one-click OpenClaw template on Ubuntu 22.04 that installs OpenClaw, Docker, a web gateway and firewall rules in 2 to 5 minutes, then walks you through pasting an Anthropic or OpenAI key. That's OpenClaw. Hermes and the other agents don't have a listed template, so budget an evening for the install.
4. **Where support stops.** Bluehost labels its Hermes VPS "infrastructure only support" and Contabo says the same in more words: the VPS is theirs, the open-source software on top is yours to maintain. AVA Hosting advertises 24/7 support without drawing that line. Assume it sits at the hypervisor.
5. **Small print that bites.** The Nano plan lists port 25 as closed, which matters if your agent sends mail. Nano is also showing zero availability. And confirm whether the euro figure includes VAT for your country.

## How the other AI agent VPS offers look on paper

| Provider | Entry price | Config at that price | What stands out |
| --- | --- | --- | --- |
| IONOS | "from $2/mo" headline | VPS S+ 1 vCore / 2 GB / 60 GB, up to XXL+ 12 vCores / 24 GB / 720 GB | 30-day money-back guarantee, 99.99% uptime, no downgrades |
| Contabo | €5.50/mo equivalent on a 12-month term, first 24 months | 4 vCPU / 8 GB / 100 GB | Cheapest 4/8 on paper, price changes after 24 months, support covers the VPS only |
| QuantVPS | $39.99/mo | Recommends 4 vCPU / 8 GB | Dedicated CPU and RAM claim, New York only, 99.999% SLA, no contract |
| Space-Node | €4.20/mo incl. VAT | 2 shared vCores / 2 GB / 20 GB | Shared vCores, dedicated RAM, no backups, no one-click install |
| Bluehost | $4.49/mo on a 24-month term, renews at $5.69 | 1 vCPU / 2 GB / 50 GB | Self-managed, infrastructure-only support, one-click Hermes install |

Contabo's €5.50 for 4 vCPU and 8 GB undercuts AVA Hosting's €20 by a wide margin for the first 24 months. That number is an effective monthly rate on a 12-month subscription including tax, and it isn't the rate you'll pay in year three. AVA Hosting's counter-arguments are the weekly backups, the shorter commitment and the euro pricing that doesn't reset after two years. On uptime, AVA's 99.9% SLA is the weakest figure in this table; IONOS quotes 99.99% and QuantVPS 99.999%.

## FAQ

**Do I need a GPU?**
No, unless you plan to run the model itself on the same box. With a hosted provider, the VPS handles the agent, the gateway, scheduled jobs and tool calls. AVA Hosting's plans are CPU machines on Intel Xeon E5 hardware with NVMe storage, which is the right shape for API-driven agents and the wrong one for local inference.

**How is the model billed?**
Through your own account with Anthropic, OpenAI or whoever you use, metered by usage. AVA Hosting's OpenClaw setup guide assumes exactly this: you bring an API key, the server doesn't include one.

**Can my laptop do this instead?**
Only while it's awake and online. A closed lid means a dead agent, no cron jobs and no webhook endpoint. The static IP a VPS gives you is also what keeps WhatsApp or Slack callbacks reachable.

**Is there a one-click install for every agent?**
No. OpenClaw has a template; Hermes and the coding agents are manual installs. AvaHost also sells OpenClaw 2 as a hosted application from €5, which adds a custom domain, automatic HTTPS, automatic updates and scheduled backups, with application email disabled.

**Anything to watch on Ubuntu 24.04?**
Claude Code's sandbox needs an AppArmor profile configured for bubblewrap on 24.04 and newer, documented separately by Anthropic. AvaHost's one-click template is 22.04, which skips that step but runs an older LTS.

## Picking by situation

One assistant on Telegram or WhatsApp, hosted model: Mini at €5. A coding agent working a real repository: Pro or VPS Power at €20. Several subagents running at once: Business or VPS Extra at €30. A team with separate services on one machine: Power or VPS Ultra at €40.

Two things to settle before you click: ask support whether you can move down a tier later, and check the VAT-inclusive total on the order form rather than the "starting from" figure.

👉 [Open AVA Hosting's VPS catalogue and pick a tier](https://my.ava.hosting/aff.php?aff=15562)
