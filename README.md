# windows vps: what a license-included plan really costs, and which RackNerd tier to pick

Most people searching for a windows vps want three things: a genuine Windows Server license, full RDP access, and a monthly price that doesn't double the moment you add that license. That's exactly the gap RackNerd's Windows line targets. It runs on AMD Ryzen 3900X hardware with NVMe storage out of Los Angeles, ships with the Windows Server license already included in the plan price, and starts at **$27.59/month** for a 2 GB configuration. Six tiers are available, from 2 GB up to 16 GB, all with a 1 Gbps port and full administrator access.

This article walks through the full plan list, where the actual value sits, and the fine-print limits that most comparison posts skip — because two of them (concurrent RDP sessions and backups) will affect your decision more than an extra gigabyte of RAM.

> **Quick pick**
> - Most users: **Windows VPS 4GB** at $30.59/month — one step up from the base plan, and the price jump is only $3.
> - Light RDP use or a single Windows app: the 2 GB plan at $27.59/month.
> - 3–5 concurrent RDP users or a small game server: the 8 GB plan at $44.59/month.
>
> 👉 [Check the 4GB Windows VPS at $30.59/month](https://my.racknerd.com/aff.php?aff=11397&pid=294)

## The full RackNerd Windows VPS plan list

RackNerd currently publishes six Windows VPS configurations, all hosted in Los Angeles on Ryzen cores with NVMe SSD storage. Every plan includes the Windows Server license, a dedicated IPv4 address, full administrator and RDP access, and a KVM/SolusVM control panel for reboot, reinstall, and rDNS management.

| Plan | CPU / RAM / Storage | Monthly bandwidth | Price | Order |
| --- | --- | --- | --- | --- |
| Windows VPS 2GB | 1 vCore / 2 GB / 35 GB NVMe | 2 TB | $27.59/mo | [ Get the 2GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=293) |
| Windows VPS 4GB | 2 vCores / 4 GB / 60 GB NVMe | 2 TB | $30.59/mo | [ Get the 4GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=294) |
| Windows VPS 6GB | 2 vCores / 6 GB / 85 GB NVMe | 3 TB | $35.59/mo | [ Get the 6GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=295) |
| Windows VPS 8GB | 3 vCores / 8 GB / 110 GB NVMe | 5 TB | $44.59/mo | [ Get the 8GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=296) |
| Windows VPS 12GB | 4 vCores / 12 GB / 160 GB NVMe | 6 TB | $64.59/mo | [ Get the 12GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=297) |
| Windows VPS 16GB | 6 vCores / 16 GB / 200 GB NVMe | 10 TB | $89.59/mo | [ Get the 16GB plan](https://my.racknerd.com/aff.php?aff=11397&pid=298) |

Two details worth noticing in that table. The 12 GB and 16 GB plans come with two dedicated IPv4 addresses instead of one. And bandwidth scales with tier rather than being flat: the entry plan gets 2 TB per month, the top plan gets 10 TB.

On billing, the order page prices these plans monthly, and RackNerd's own promotional listings have shown annual-billed figures for the same Windows configurations. Those annual numbers don't always line up cleanly with the monthly cart page, so the price that matters is the one the checkout actually shows for the billing cycle you select — check it before paying, whichever cycle you choose.

## Why the 4GB and 6GB tiers are where the value sits

The price ladder is unusually flat at the bottom. Going from the 2 GB plan to the 4 GB plan costs three dollars more per month, and for that you double both RAM and CPU cores. Storage nearly doubles too, from 35 GB to 60 GB of NVMe.

The same logic extends one step further: 6 GB adds another $5/month on top of 4 GB and buys you another 25 GB of storage plus a full extra terabyte of monthly transfer. Beyond that point the increments get steeper — 8 GB costs $9 more than 6 GB, and 16 GB costs $25 more than 12 GB.

A practical rule of thumb, based on how Windows Server behaves: a Server 2022 install idles at roughly 1.2–1.5 GB of RAM before you run anything. On the 2 GB plan, that leaves you very little headroom. It works for a single remote desktop session and one light application — a single MetaTrader bot, which typically eats 500 MB to 1 GB on its own and leans on one fast core, fits within a 2 GB box. But a trading platform plus a browser and multiple charts will start swapping. If you're running anything beyond a bare desktop or one bot, the 4 GB tier is the realistic floor, and 6 GB is the comfortable one.

👉 [Order the 6GB Windows VPS with 3TB monthly bandwidth](https://my.racknerd.com/aff.php?aff=11397&pid=295)

## What the license-included pricing actually means

The single biggest cost factor in a windows vps is usually the Windows Server license itself. Many providers charge $10–20 per month just for the license, on top of the server price. Here it's bundled: the $27.59–$89.59 monthly prices you see are what you pay, with Server licensing baked in.

That changes the comparison math considerably. A "$20/month VPS plus license" at a competitor can easily land above RackNerd's 4 GB plan once the license is added — and RackNerd's FAQ claims most competitors charge $15–30/month for similar specs overall. Whether or not every competitor matches that description, the structure of the deal is verifiable: one price, license included, no separate line item.

Beyond the license, every plan carries the same infrastructure: Ryzen 3900X cores (3.8 GHz base, 4.6 GHz boost — the single-thread speed that matters for RDP responsiveness and lightweight apps), NVMe storage in RAID-10, a 1 Gbps network port with no 100 Mbps throttle, and a dedicated IPv4. The control panel is SolusVM-based, so you can reboot, reinstall the OS from one Windows Server version to another, open a noVNC console, and set rDNS yourself. Los Angeles deployments can also request up to 100 free IPv6 addresses by opening a support ticket after ordering — relevant if you plan to run mail or anything else that benefits from v6 connectivity.

## The fine print that actually matters

This is the section most comparison posts leave out. Four limits are documented in RackNerd's terms and FAQ but don't appear in the headline pricing.

**Concurrent RDP sessions are capped at two by default.** If your use case involves multiple users connecting at once — a small team sharing a Windows workspace, for example — the standard license only allows two simultaneous remote desktop connections. Additional users require Remote Desktop Services (RDS) CALs, which you arrange through RackNerd support. Plan for this before ordering, not after.

**Backups are your problem.** The plan pages advertise reboot, reinstall, and console access, but no snapshots, no automated backups, no API, and no hourly billing. Whatever data lands on this server, you're responsible for copying it elsewhere. For a trading bot or a .NET app with a database, set up a backup routine on day one.

**Support covers infrastructure only.** The terms state the service is unmanaged by default: support handles "server hardware, power, network connectivity, and service availability," and explicitly excludes software issues, firewall configuration, malware cleanup, and script troubleshooting. Managed service may be available for an extra fee, but assume you're the sysadmin.

**No refunds by default.** The terms say refunds are case-by-case and that, by default, none are provided once payment is received. Cancellation requires written notice through the client area at least 7 days before renewal, and data is deleted when a service is cancelled. There's no free trial either.

One more location note: the official Windows VPS order page lists Los Angeles as the deployment location. That's fine for most North American and Asia-Pacific users — the LA site is described as "Asia optimized" — but if you need a Windows box physically located in Europe, confirm available locations at order time rather than assuming.

## Getting started: from order to RDP login

Setup is straightforward because the image comes pre-installed. The flow looks like this:

1. Pick your plan, choose the Windows Server version at order time — 2012, 2016, or 2022, switchable later via a panel reinstall — and select the datacenter. For a fresh install, 2022 is the sensible pick.
2. Activation is near-instant; the welcome email arrives within minutes and contains your dedicated IPv4, administrator username, and initial password.
3. Connect with the built-in Remote Desktop client on Windows (mstsc), Microsoft Remote Desktop on Mac, or Remmina on Linux.
4. **Change the password immediately** — the initial one is stored in plain text in your email.
5. Run Windows Update, deploy your applications, and if you need rDNS/PTR records or IPv6, open a support ticket; neither is enabled by default.

No ISO mounting, no manual installation. The main learning curve is the same as any unmanaged server: you own the patching and the hardening.

## Promo codes, renewal pricing, and the real long-term cost

RackNerd runs two pricing tracks. The list prices above are the everyday rates. On top of those, third-party deal trackers report a recurring promo code for the Windows line — **WIN-30OFF**, described as 30% off Windows VPS plans for life, which would bring the 2 GB plan to roughly $19/month. Two cautions: the code comes from community deal listings rather than an official page I could verify, so treat it as worth trying rather than guaranteed; and the discount is applied in the promo code field at checkout, which sits below the plan configuration and is easy to miss.

On renewal, the consistent report from long-term users and multiple deal trackers is that RackNerd renews at the price you signed up at — the codes are recurring rather than first-billing-cycle tricks that reset to full price. That's the part that separates budget hosts worth keeping from ones worth escaping, and it's also the part you should confirm for yourself: check the renewal amount shown in your client area after the first invoice, before you build anything permanent on the box.

For a mid-tier example: the 4 GB plan at $30.59/month works out to about $367 per year with the license included, or around $257 if the 30% code applies. Compare that against any competitor where the license is a separate $10–20/month line item and the difference explains why this line gets recommended for Windows workloads on a budget.

## Who should skip this line

Honesty about fit saves everyone time. RackNerd's Windows VPS is a poor match if you need any of the following: hourly billing or an API for auto-scaling (not offered), managed server administration (support is infrastructure-only), built-in snapshots and backups (bring your own), a refund guarantee (there isn't one by default), or a Windows datacenter outside Los Angeles (the order page lists LA for this line). Teams that need those features should look at premium cloud providers instead and accept the higher bill.

## FAQ

**Is the Windows Server license really included?**
Yes. Licensing for Windows Server is bundled into every plan's monthly price — you choose the version (2012, 2016, or 2022) at order time and pay no separate license fee.

**Is 2 GB of RAM enough for a Windows VPS?**
For a single trading bot or one light application, yes — MetaTrader typically uses 500 MB to 1 GB and leans on a single fast core. For anything more, Windows Server 2022 idles at 1.2–1.5 GB, so start at 4 GB.

**Can I upgrade later if I pick too small?**
Yes. Upgrades are arranged through support, with your remaining billing time credited proportionally, and the process takes roughly one restart — about a minute of downtime. You can also switch between Windows Server versions yourself via a panel reinstall.

**How many people can RDP in at once?**
Two concurrent sessions by default. More requires RDS CALs added through RackNerd support.

**Do I get a refund if I change my mind?**
Not by default. Refunds are handled case-by-case, and the terms state none are provided once payment is received. Cancel at least 7 days before renewal if you don't want the next cycle.

## Final decision, by use case

- Single trading bot (MetaTrader, cTrader) or one light remote desktop: **2 GB** at $27.59/month.
- Trading platform plus charts and browser, .NET hosting, a proper working desktop: **4 GB** — the extra $3 over the base plan is the easiest decision in this whole lineup.
- Multi-app servers, small game servers, or a shared workspace for a few users: **8 GB** at $44.59/month.
- Databases and heavier multi-service setups: **12 GB or 16 GB**, both of which include a second dedicated IPv4 on top of the standard one.

Before you check out, three things: try the promo code in the checkout field and verify the discount actually applied, confirm the renewal and billing-cycle price shown on the invoice matches what you expect to pay long-term, and set a reminder to sort out backups within the first week. Then grab the plan that fits:

👉 [Browse RackNerd's full Windows VPS lineup and order the tier you need](https://my.racknerd.com/index.php?rp=/store/windows-vps-with-nvme-ssd&aff=11397)
