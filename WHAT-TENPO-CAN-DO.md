# What Tenpo Can Do

Tenpo is an **AI operator for e-commerce stores**. Not a chatbot bolted onto a dashboard — it runs *alongside* the store with its own copy of the merchant's data, 284 tools it can actually call, 239 expert playbooks it can load on demand, and 46 background loops that keep working when nobody is logged in.

This document is the full inventory. Everything listed here exists in the codebase.

---

## The 60-second version

| | |
|---|---|
| **Tools it can call** | 284 |
| **Expert skills / playbooks** | 239 |
| **Pre-built workflows (one-click)** | 22 |
| **Scheduled routines** | 20 |
| **Always-on background loops** | 46 |
| **Integrations supported** | 56 |
| **Psychology models applied** | 33 named, always-on |

---

## How to read the levels

Every capability is rated by how much *judgement and machinery* sits behind it:

| Level | Meaning | Example |
|---|---|---|
| 🟢 **Basic** | A lookup. One question, one answer, read-only. | "What's low on stock?" |
| 🟡 **Mid** | Multi-step analysis, or a write to one system. | "Draft a win-back campaign for lapsed VIPs" |
| 🔴 **High** | Reasoning, forecasting, money movement, or autonomous action across systems. | "Why did margin drop and what do I do about it?" |

Tool counts by level: **45 Basic · 201 Mid · 38 High**

---

## What a merchant actually gets

Plain-English version, before the tables.

| Area | Level | What Tenpo does for you |
|---|---|---|
| **Know your numbers** | 🟢🟡 | Revenue, orders, AOV, margin, top products, top customers — asked in plain English, answered from your real data, not an estimate. |
| **Catch problems early** | 🟡🔴 | Stockouts hours away, oversells across channels, margin going negative, refund spikes, late shipments, fraud-shaped orders — surfaced before they cost you. |
| **Diagnose, not just report** | 🔴 | "Sales are down" gets a *cause*: fewer orders or smaller baskets? which SKUs? new buyers or repeat? discount-driven or price-driven? |
| **Buy the right stock** | 🔴 | Reorder points from real velocity × supplier lead time, EOQ sizing, MOQ floors, supplier scorecards, drafted POs emailed for your approval. |
| **Sell more to who you have** | 🟡 | Win-back for lapsed VIPs, abandoned-cart recovery, post-purchase flows, review requests, upsell and bundle discovery. |
| **Run ads without burning cash** | 🟡🔴 | ROAS by campaign, creative fatigue detection, budget-cut proposals, ad image/video generation, competitor ad-library intel. |
| **Handle customers** | 🟡 | WISMO auto-deflection, ticket triage and drafted replies, negative-review make-goods, delivery-delay apologies, returns processing. |
| **Keep the money straight** | 🟡🔴 | Contribution margin per SKU, P&L, payout reconciliation, cash-flow forecast, LTV/CAC payback, tax nexus checks. |
| **Watch competitors** | 🟡 | Tracked brands: price moves, new SKUs, promos, sold-out signals, historical snapshots, their ad library. |
| **Write like a human** | 🟡 | Every customer-facing word passes an anti-AI-slop filter and 33 behavioural psychology models. |
| **Work while you sleep** | 🔴 | 46 background loops + 22 workflows + 20 routines running on schedules and on events. |

---

## 1. Embedded Workflows — the 22 one-click automations

These ship pre-built and validated. A merchant turns one on; it then runs on a schedule or fires on an event, does the analysis, and either alerts, drafts, or (with permission) acts. **Every customer-facing action and every money action waits for a tap.**

| Workflow | What it does |
|---|---|
| **Low stock alert** | Alert me when a product is genuinely about to run out — measured in DAYS OF COVER (units on hand ÷ real 30-day sales velocity), not in units, so a SKU with 10 units and three months of cover stays silent while one with 10 units and two days of cover pages me.  It splits by severity: already at zero, under 3 days of… |
| **Low stock reorder** | When a product drops to its reorder point, size the reorder properly and hand me a finished reorder request: quantity from real 30-day velocity × supplier lead time + 30 days of cover, floored at the minimum order quantity on file, priced from cost-per-item.  SKUs with units already inbound on an open purchase… |
| **VIP churn rescue** | Find the customers worth real money who have gone quiet, then act by value tier instead of blasting everyone: whales get a personal outreach email drafted for your approval, mid-tier gets an approval-gated win-back, and anyone below your mid-tier bar is counted in the alert and never contacted.  If someone went… |
| **Negative review alert** | Sweeps the last day's 1–3★ reviews once a day and separates a product problem from an unhappy buyer: a product with 3+ negative reviews in 30 days is escalated as a defect (with what is still on the shelf), while a one-off 1★ gets a make-good coupon drafted for your approval plus the apology text to send.  Reviews… |
| **Weekly P&L summary** | ) with the SKUs that fell and why, while an up week gets the momentum read plus a warning on any growth driver about to run out.  Reads and reports only — nothing is written, sent to a customer, or changed in the store. |
| **Dead stock capital review** | Once a week, work out how much cash is actually sitting in stock that has stopped selling — every active SKU with units on hand and no real sale in 60+ days, valued at your cost where a cost is on file and at retail where it isn't (both totals reported separately at every level, never blended silently).  The size… |
| **Campaign fatigue guard** | 5 get split by whether click-through collapsed (creative fatigue) or held (price / stock / landing page).  It reports; it does not move budget — unless you have switched this store to full autonomy with live effects on, in which case it asks Meta to halve the daily budget on the burning ones and tells you to… |
| **Negative margin guard** | Every morning, work out what each SKU actually LOST over the last 30 days — units sold × the gap between what you kept per unit (line revenue minus that order's discount, shared across its lines) and what the unit cost you — then split the bleeders by cause: a list price sitting under cost gets an approval-gated… |
| **High-value order triage** | When an unusually large order lands, triage it against the buyer's own history and your store's normal order size before it ships: an order that isn't marked paid stops at a hold notice, a proven top-decile repeat buyer gets an approval-gated white-glove note, and an unknown or brand-new buyer above your… |
| **Oversell guard** | Catch the moment you have promised more units than the channel holding the stock says you have — units owed on open orders from your OTHER channels measured against your storefront's own sellable count, plus any SKU your platform already reports as negative — then act by blast radius.  Big exposure ($1,000+ at risk… |
| **Stockout imminent** | Catch SKUs that are HOURS from zero, not just low — then split them by the money at stake: a top-10 revenue driver inside 24 hours gets a loud two-channel alert and an approval-gated expedite purchase order drafted for review; everything else is flagged for the daily reorder routine.  Nothing is sent to a supplier,… |
| **Slow-mover markdown** | Spot products that have gone quiet for 45–90 days and propose a clearance discount to get them moving before they become dead stock. |
| **Win back lapsed customers** | Find proven repeat buyers who've gone quiet for 90 days and launch a win-back campaign to pull them back before they churn for good. |
| **Abandoned cart recovery** | Catch carts abandoned over an hour ago and still unrecovered, then fire a recovery email to win back the checkout. |
| **Post-purchase follow-up** | Send a friendly check-in SMS a few days after an order ships to build loyalty and pre-empt support tickets. |
| **Review request** | About a week after delivery, ask happy buyers for a review to compound social proof and lift conversion on the product page. |
| **Refund & chargeback spike triage** | Every morning, compare this week's refunds and open chargebacks against your own 4-week baseline — then work out WHY.  If the refunded money piles onto one product it's a quality problem: I show you the recorded reasons, how often it comes back, the stock still waiting to create the next refund, and — where that… |
| **WISMO / late shipment** | Every morning, find the paid orders that are past your 3-day ship SLA and work out WHICH failure it is: the ones that never left the warehouse (a picking problem — ship or refund it) versus the ones the carrier collected and then stalled (a carrier problem — open a trace).  Then it tiers by how late and how big:… |
| **Support escalation** | Twice a day, sweep the open tickets older than 24 hours and sort them by the failure they actually are.  You get a roll-up covering the WHOLE backlog: how many were never answered, how many are past 72 hours, how many are repeat contacts, and which issue dominates. |
| **Auto-deflect WISMO** | ' tickets with a grounded shipping-status update built from the customer's real order and tracking — clearing the most common ticket without a human touch. |
| **Proactive delivery update** | ' ticket: spot shipments running past their promised delivery date and proactively apologise to the customer with a grounded delay update.  No per-shipment notified-log exists, so the cooldown + approve-first gate are the dedup backstop. |
| **Negative-review make-good** | Recover an unhappy reviewer: detect 1–2★ reviews, draft a make-good coupon for approval, and alert the operator with a grounded apology + the review text to send.  Reviews carry no reviewer email, so the apology is the operator's to deliver — we never auto-email the reviewer. |

**Level:** 🔴 High — these are multi-step plans with conditions, forks, cost sizing, dedup, cooldowns, and approval gates.

---

## 2. Scheduled Routines — 20 recurring jobs

Lighter than workflows: they run on a clock, look at one thing, and report.


| Skill | What it gives the agent |
|---|---|
| `40rty-routines-abandoned-cart-patrol` | Every 4 hours — scans for abandoned checkouts, segments by value, surfaces high-priority recoveries to Slack. |
| `40rty-routines-catalog-health-weekly` | Wednesdays — comprehensive product data quality scan. |
| `40rty-routines-customer-churn-watch` | Weekly — identifies at-risk and churning customers with win-back recommendations. |
| `40rty-routines-dead-stock-weekly` | Sundays — identify dead stock and generate markdown candidates report. |
| `40rty-routines-discount-roi-weekly` | Tuesdays — review discount code performance and flag underperforming campaigns. |
| `40rty-routines-fraud-sentinel` | Every 2 hours — scans recent orders for fraud indicators and flags high-risk orders. |
| `40rty-routines-fulfillment-sla-watchdog` | Twice daily on weekdays — checks for overdue fulfillments and stalled shipments. |
| `40rty-routines-inventory-aging-monthly` | 15th of each month — inventory aging buckets with carrying cost analysis. |
| `40rty-routines-low-stock-watchdog` | Daily inventory scan — alerts when products drop below reorder point based on sales velocity. |
| `40rty-routines-monthly-financial-close` | First of every month — comprehensive financial close report with P&L, payouts, taxes, and refunds. |
| `40rty-routines-morning-store-briefing` | Daily morning digest — orders, revenue, fulfillment status, and issues from the last 24 hours. |
| `40rty-routines-new-product-launch-tracker` | Daily — tracks first-week performance of recently published products. |
| `40rty-routines-payout-recon-daily` | Daily — reconciles Shopify Payments payouts against orders, flags discrepancies. |
| `40rty-routines-price-anomaly-scanner` | Daily early morning — scans for pricing errors, zero-price products, and compare-at-price inconsistencies. |
| `40rty-routines-quarterly-business-review` | First day of each quarter — comprehensive QBR with trends, cohorts, top movers, and strategic insights. |
| `40rty-routines-return-fraud-watch` | Mondays — scans for suspicious return patterns and serial returners. |
| `40rty-routines-seo-coverage-weekly` | Thursdays — SEO metadata gap report across catalog. |
| `40rty-routines-staff-activity-monthly` | First of each month — staff account audit and permission review for the connected Shopify store. |
| `40rty-routines-vip-customer-watcher` | Daily — alerts on VIP customer orders, issues, or churn risk for white-glove handling. |
| `40rty-routines-weekly-business-review` | Monday morning — comprehensive weekly performance report across all store dimensions. |

**Level:** 🟡 Mid

---

## 3. Always-On Background Loops — 46

These are not user-configurable. They are Tenpo's own nervous system, running continuously per merchant.

| Loop | Job |
|---|---|
| `adapter-sync` / `incremental-sync` / `full sync` / `entity-sync` | Keep the merchant's local data mirror current with every connected platform. |
| `evaluate-workflows` | Re-ask every enabled workflow's condition each tick and fire the ones that are true. |
| `scheduled-routines` / `scheduled-campaigns` / `scheduled-reports` | Run anything the merchant put on a clock. |
| `approval-sweeper` | Chase, expire, and clean up approvals nobody answered. |
| `autonomous-scout` | Look for problems and opportunities nobody asked about. |
| `autonomous-incident-responder` | React to breakages (sync failures, integration outages, data gaps). |
| `autonomy-ladder-scan` / `skill-graduation` | Promote the agent's permissions on actions it has proven it gets right. |
| `replenishment-scan` | Continuously check every SKU against its reorder point. |
| `horizon-forecaster-scan` | Forward-looking demand and risk projection. |
| `fraud-scorer` | Score incoming orders for fraud signals. |
| `competitor-scrape` | Pull tracked competitors' catalogs, prices, promos, emails. |
| `revenue-attribution` | Tie revenue back to the action that caused it. |
| `delayed-outcome` / `rejects-to-battery` | Measure what happened *after* an action — the learning loop. |
| `cascade` | Turn one event into its downstream consequences across systems. |
| `dreaming` / `memory-decay` / `agent-event-distill` | Consolidate memory, forget noise, keep what matters. |
| `morning-briefing` / `morning-standup` | The daily "here's your store" message. |
| `automation-abandoned-cart` / `automation-win-back` / `automation-daily-flows` | Lifecycle marketing on autopilot. |
| `review-alerts` | Watch for new negative reviews. |
| `process-send-queue` | Actually deliver queued emails/SMS/notifications. |
| `derived-product-metrics` | Recompute per-product economics. |
| `workflow-tuner` / `workflow-reconciler` / `chain-health` | Self-tune thresholds, repair broken workflow state, detect dead chains. |
| `webhook-register` / `webhook-canary` / `telegram-webhook-reconciler` | Keep inbound webhooks alive and prove they still fire. |
| `daily-backup` / `duckdb-checkpoint` / `duckdb-fallback` / `boot-integrity-recovery` | Durability and self-healing of the merchant's data. |
| `retrieval-provability` | Prove every claim traces back to real rows. |
| `coupon-cleanup`, `bulk-worker`, `fast-lane`, `next-heartbeat`, `cron-jobs` | Housekeeping and dispatch. |

**Level:** 🔴 High

---

## 4. The 284 Tools

Grouped by what they're for. `Level` is per-tool.

### Core Brain & Store Reporting  
*23 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_can_help_with` | Basic | MERCHANT-FACING capability map: 9 categories grouped Core (cross-system intel, operator math, diagnostics, execution) / Data (inventory god-mode, customer intelligence god-mode, creative… |
| `tenpo_capabilities` | Basic | Returns what Tenpo can do for this merchant. |
| `tenpo_classify_intent` | Basic | INTENT CLASSIFIER — classifies a merchant query into one of Tenpo's intents (connect / investigate / create / launch / pause / discover / memory / onboard / strategy / global_signal /… |
| `tenpo_deeper_insights` | Mid | Get ADDITIONAL insights beyond what tenpo_run_intelligence already showed. |
| `tenpo_diagnose` | High | Run diagnostics on the merchant's database. |
| `tenpo_get_prompt` | Basic | Read any of the 200+ skills as a prompt template. |
| `tenpo_get_resource` | Basic | Read any tenpo:// resource. |
| `tenpo_get_skill` | Basic | Load an expert playbook on demand. Your prompt carries a DIGEST of the playbooks that matched this question — the opening lens plus a list of the sections it did not show. |
| `tenpo_google_analytics` | Mid | Fetch a metrics report from Google Analytics 4 (sessions, users, revenue, conversions) for a date range. |
| `tenpo_list_prompts` | Basic | List all available skills. |
| `tenpo_merchant_status` | Basic | Get the merchant's Tenpo status: sync state, data counts, last sync time. |
| `tenpo_ops_briefing` | Mid | Generate the ops briefing: what you DID (executed actions, last 24h), what you DETECTED (active alerts + recent insights), and what NEEDS the merchant's sign-off (pending approvals… |
| `tenpo_org_summary` | Mid | Combine metrics ACROSS MULTIPLE STORES the merchant operates (eg Shopify US + Shopify India, or a Shopify + a WooCommerce store). Returns combined revenue / order count / AOV over a… |
| `tenpo_pattern_detect` | High | Runs the same 4 deterministic SQL checks the heartbeat runs: revenue cliff, stock crash, refund spike, ROAS death. No LLM — pure SQL, so it is safe to run often. |
| `tenpo_query` | Mid | Run SQL against the merchant database with guardrails: - SELECT: read data - INSERT / UPDATE / DELETE: allowed only with an approved approvalId from tenpo_approve - CREATE TABLE: allowed… |
| `tenpo_route` | Basic | Preflight: top tools/skills + path + minimal soul. Use once per query. |
| `tenpo_run_intelligence` | High | Run the Tenpo intelligence engine on-demand. Analyzes revenue trends, inventory, customers, campaigns, profit margins, and cross-system correlations. |
| `tenpo_run_tool` | Mid | Execute any tool by name + args (proxies to gateway registry). |
| `tenpo_store_summary` | Basic | Get store performance snapshot: revenue (7d, 30d, and ALL-TIME), order count, AOV, active customers (90d), and last order date. |
| `tenpo_think` | High | GOD-MODE ENTRY POINT — Call this FIRST for ANY non-trivial commerce question. Returns a. |
| `tenpo_three_priorities` | Mid | The 3 highest-leverage things this merchant should fix THIS WEEK, ranked by $ impact. Pure SQL over revenue trend, CAC, inventory days-of-inventory, refund rate, ad efficiency and dead… |
| `tenpo_top_products` | Basic | Products over a rolling window, returned with BOTH ranking bases so you can pick the right one: product name, sku, units_sold (gross), units_sold_net, revenue (net of… |
| `tenpo_web_search` | Mid | Search the web for real-time information (Tavily/Brave + funded synthesis). |

### Inventory & Demand  
*11 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_export_barcodes` | Basic | Export barcode data from the products table as a downloadable CSV file. Validates each barcode format (EAN-13, UPC-A, Code-128) and flags invalid ones. |
| `tenpo_forecast_demand` | High | Demand forecasting and reorder alerts based on sales velocity. Identifies products that are at risk of stocking out before the next replenishment, calculates reorder quantities to cover… |
| `tenpo_import_inventory` | Mid | Bulk-set on-hand stock from a CSV/TSV/XLSX with a SKU column and a quantity column (quantity / qty / stock / on_hand / available / units). |
| `tenpo_inventory` | Basic | DEV-oriented inventory of the full technical surface — every tool, skill, integration, auto-routine, and workflow (live counts from the capability manifest). For. |
| `tenpo_inventory_adjust` | High | Per-location inventory: READ available-to-promise (on_hand − committed + incoming), the store-wide roll-up, and a reorder decision; or ADJUST a location's stock by a delta (+N/−N).… |
| `tenpo_inventory_intelligence` | Mid | GOD-MODE inventory analysis — multi-dimensional scorecard. |
| `tenpo_low_stock` | Basic | Products with low or zero stock, sorted by urgency — product names, current quantity, daily velocity, days of stock remaining. |
| `tenpo_oversell_ledger` | Mid | READ-ONLY audit trail of cross-channel oversell exceptions and how Tenpo resolved them. Lists recent detections — which SKU was oversold, on which channel an order was CANCELLED vs… |
| `tenpo_receive_inventory` | Mid | Mark a Purchase Order as received — fully or partially. Records received quantities, damaged items, updates PO status and stock levels. |
| `tenpo_replenishment_engine` | High | Identify products with natural repurchase cycles and generate proactive replenishment reminder campaigns. Analyzes average days between repeat purchases per product, classifies… |
| `tenpo_seasonal_twin` | High | Reads the merchant's own order ledger to compare the current calendar window against the SAME window one year ago, per product: units sold last year, units so far this year, the… |

### Suppliers & Purchasing  
*21 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_alibaba_rfq` | High | Submit a Request-For-Quote on Alibaba.com. Alibaba broadcasts the RFQ to matching suppliers who can then send quotes back. Requires approvalId — RFQs cost reputation (spam-rate-limited)… |
| `tenpo_alibaba_search` | Mid | Search Alibaba.com for suppliers and manufacturers for a given product. Returns supplier listings with price ranges, MOQs, locations, verification status, and a ready-to-send negotiation… |
| `tenpo_alibaba_search_native` | Mid | Search Alibaba.com supplier catalog via the merchant's connected Alibaba Open Platform app. Filters: product_query (required), min_moq, max_unit_price, country. Falls back to… |
| `tenpo_alibaba_suppliers` | Mid | List the merchant's saved/contacted Alibaba suppliers (from the synced cache), or fetch a specific supplier's detail via the API. Read-only — safe to call from background automation. |
| `tenpo_capture_po_confirmation` | Mid | Record that a supplier has confirmed a purchase order. Updates PO status to. |
| `tenpo_check_po_prerequisites` | Basic | MANDATORY: You MUST call this tool when a merchant asks to create a purchase order, order from a supplier, or restock. NEVER call tenpo_query before calling this tool for PO creation. |
| `tenpo_compare_quotes` | Mid | Compare all received quotes for a product or purchase order. |
| `tenpo_customize_po_template` | Mid | Customize the appearance of Purchase Order PDFs for this merchant. Supports changing the header/accent color, footer text, signature line visibility, and custom payment instructions or… |
| `tenpo_draft_supplier_email` | Mid | Draft OR send a professional email to a supplier via Gmail (requires Google Workspace). Supports: quote_request (request pricing), po_send (send a PO), chase_confirmation (follow up on… |
| `tenpo_email_purchase_order` | High | Send a Purchase Order email to a supplier. DESTRUCTIVE — sends real email to a real vendor. |
| `tenpo_extract_quote` | Mid | Extract a structured supplier quote from an email body and store it in the database. Parses unit price, quantity, total, delivery days, payment terms, validity period. |
| `tenpo_generate_po` | High | Generate a professional Purchase Order PDF, save it to the database, and return a clickable download link. |
| `tenpo_get_supplier_quotes` | Basic | Retrieve stored supplier quotes from the database. Filter by PO, supplier name, or product name. |
| `tenpo_import_suppliers` | Mid | Bulk-add or update suppliers from a CSV/TSV/XLSX with a supplier-name column (plus optional email, phone, lead_time_days, moq, reliability_score, notes). |
| `tenpo_manage_po_bundles` | Mid | Save, list, or delete Purchase Order bundles — reusable named groups of line items (eg 'Winter Pack = Ski Wax ×10, Goggles ×5'). Use action=. |
| `tenpo_po_status` | Basic | Purchase orders with delivery status, payment status, amounts, supplier name, and expected/created dates. |
| `tenpo_read_supplier_emails` | Mid | Read emails from suppliers via Gmail (requires Google Workspace connected with gmail.readonly scope). supplierEmail is OPTIONAL — if omitted, automatically looks up all known supplier… |
| `tenpo_save_supplier` | Mid | Save or update a supplier in the merchant's database. Call this after the merchant provides supplier details (email, address, payment terms, lead time) during a conversation. |
| `tenpo_supplier_scorecard` | Mid | GOD-MODE supplier scoring — multi-dimensional grade per supplier. Per supplier returns: PO count, on-time rate, avg lead days, lead-time variance, lifetime spend, price drift… |
| `tenpo_supplier_summary` | Basic | All vendors/suppliers with total PO count, amount paid, amount owed, and open PO count. |
| `tenpo_update_supplier_reliability` | Mid | Recalculate supplier reliability from purchase orders with both promised and actual receipt dates. Stores a 0-1 on-time delivery rate; stores unknown when no deliveries are measurable. |

### Finance, Pricing & Money  
*19 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_billing_status` | Basic | Returns current tier, daily call usage, calls remaining, upgrade URL, billing portal URL, available plans. Surface to merchant when they hit limits or ask about plans. |
| `tenpo_contribution_margin` | High | Get TRUE contribution margin broken down PER SALES CHANNEL (shopify/amazon/tiktok_shop/…) and PER PRODUCT/SKU — the per-dimension profitability a single 'store finance' number can't… |
| `tenpo_create_budget_rule` | Mid | Create an automated budget rule for ad campaigns. Templates. |
| `tenpo_finance_brain` | High | THE finance brain — one call that knows EVERYTHING about the store's money and tells the merchant exactly what to do about it. |
| `tenpo_generate_invoice` | Mid | Generate a branded invoice from a SAVED invoice template and a REAL order, then return a download link. |
| `tenpo_import_product_costs` | Mid | Bulk-set product COGS from a CSV/TSV that has a SKU column and a cost column (cost / unit_cost / cogs / cost_price). |
| `tenpo_ltv_cac` | Mid | Core DTC unit economics: 12-month customer LTV, blended CAC (last 30d), LTV:CAC ratio (target >3:1), payback period in months, and revenue per cohort. |
| `tenpo_mark_paid` | Basic | Record a payment against a Purchase Order — full or partial amount. Updates payment status, logs the transaction. |
| `tenpo_nexus_check` | Mid | Groups orders by ship-to state/country and flags every jurisdiction where the merchant has crossed an economic-nexus threshold (US states + EU). Surfaces where they may already owe… |
| `tenpo_payout_monitor` | Mid | Detects delayed or held Shopify Payments payouts (transfers running >7d behind expected). Payment holds are an existential cash-flow event for a small merchant, so this checks the… |
| `tenpo_pricing_optimizer` | High | Analyze product pricing against velocity and margin to find opportunities: underpriced fast-movers (raise price), dead stock (discount), and stable products. |
| `tenpo_quickbooks_invoice` | Mid | Create an invoice in QuickBooks Online. |
| `tenpo_quickbooks_payment` | High | Record a payment against an existing QuickBooks invoice. |
| `tenpo_receipts` | Basic | The merchant's SETTLED-OUTCOMES RECEIPTS: every approved/fired action whose effect has been MEASURED — what the action was, when it was approved, the measured $ effect, the causal… |
| `tenpo_save_invoice_template` | Mid | Save a REUSABLE invoice template reproduced from an invoice the merchant uploaded as a PDF. Workflow: after an invoice PDF is uploaded, its text/OCR is injected under a. |
| `tenpo_set_product_cost` | Mid | Set the unit COST (COGS / cost-per-item) for a product so margin + profit math becomes real. Shopify does NOT sync cost into Tenpo, so when the merchant tells you what a product costs to… |
| `tenpo_store_finance` | Mid | Get the store's REAL finance numbers in one call: contribution P&L (revenue, COGS, payment fees, shipping, contribution profit + margin %), unit economics (AOV, orders, customers, repeat… |
| `tenpo_stripe_action` | High | Perform Stripe actions: issue refunds, create payment links, check account balance, list open disputes, or respond to a dispute with evidence. |
| `tenpo_xero_push` | High | Push data to Xero: create sales invoices, supplier bills, list existing invoices, sync a Tenpo purchase order as a Xero bill, or retrieve Xero contacts. |

### Marketing & Campaigns  
*16 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_abandoned_cart_analysis` | Mid | Analyze abandoned carts: count, total value at risk, breakdown by customer type (new vs returning), and draft a 3-step recovery sequence. |
| `tenpo_attentive_send` | Mid | Send an SMS or MMS message to a subscriber via Attentive. |
| `tenpo_campaign_report` | Mid | Get open rate, click rate, conversion rate, and attributed revenue for email campaigns. Optionally refreshes revenue attribution from recent orders within 72h of send. |
| `tenpo_create_campaign` | Mid | CREATE a marketing email campaign as a DRAFT. This does NOT send — it builds the campaign object, computes recipient count from the segment, and returns the draft for merchant review. |
| `tenpo_create_coupon` | Mid | Create a discount coupon on the merchant's platform (WooCommerce, Shopify, or BigCommerce). REQUIRES an approval ID from a prior tenpo_approve call. |
| `tenpo_draft_campaign` | Mid | INTERNAL HELPER. Returns a structured campaign-plan template (audience, subject scaffold, body scaffold, coupon, timeline). |
| `tenpo_esp_send` | High | PREFER this over tenpo_send_email for ALL marketing emails. Auto-routes to the merchant's connected ESP (Klaviyo → Mailchimp → Omnisend) before falling back to Resend. |
| `tenpo_execute_campaign` | High | Execute (send) a campaign that was previously drafted via `tenpo_draft_campaign` or `tenpo_create_campaign`. DESTRUCTIVE — creates REAL Shopify discount codes, builds branded emails with… |
| `tenpo_klaviyo_action` | Mid | Create campaigns, send campaigns, create segments, and track events in Klaviyo. |
| `tenpo_klaviyo_profile` | Mid | Add or update a customer profile in Klaviyo, manage list memberships, or retrieve available lists. Use after a purchase, win-back trigger, or customer data update to keep Klaviyo in sync… |
| `tenpo_lead_capture` | Mid | Email list building strategy — identifies underserved customer segments, generates lead magnet ideas, drafts pop-up copy sequences, and builds Klaviyo-compatible segment definitions.… |
| `tenpo_mailchimp_action` | Mid | Create campaigns, send campaigns, add/update subscribers, and list audiences in Mailchimp. |
| `tenpo_meta_campaign_create` | High | Create / pause / resume Meta (Facebook + Instagram) ad campaigns. The campaign is created in PAUSED state — the merchant must explicitly approve via Tenpo inbox or the Meta Ads Manager… |
| `tenpo_omnisend_action` | Mid | Create campaigns, add/update contacts, and list campaigns in Omnisend. |
| `tenpo_postscript_send` | Mid | Send a transactional or custom SMS message to a subscriber via Postscript. |
| `tenpo_upsell_recommendations` | Mid | Generate smart upsell and cross-sell recommendations. For a specific product, finds what customers buy alongside or after it. |

### Advertising & Creative  
*12 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_creative_dna` | High | GOD-MODE creative drafting — pattern library + past-winner DNA + multi-variant generation. Modes: (1) {mode. |
| `tenpo_creative_studio` | Mid | Generate ad copy, email content, and social media captions. |
| `tenpo_execute_ad_launch` | High | STAGE 2 of ad launch — creates the actual campaign, ad set/group, and ad on the platform. )` (typically the one returned by `tenpo_launch_ad`'s draft step). |
| `tenpo_generate_ad_image` | Mid | Generate an AI ad image for Meta, TikTok, or Google ad campaigns. STRICT BYOK — the merchant must have connected at least one image provider via `tenpo_connect_integration`. |
| `tenpo_generate_ad_video` | Mid | Generate an AI VIDEO ad clip (Kling via fal.ai) for TikTok/Reels/Meta/YouTube. STRICT BYOK — reuses the merchant's connected fal.ai key (the same one used for fal images). Compose the… |
| `tenpo_google_ads` | Mid | Manage Google Ads campaigns. |
| `tenpo_launch_ad` | High | PREPARE an ad campaign for Meta or TikTok — generates the ad copy + image and returns a complete `adLaunchPayload` with status `pending_approval`. SPENDS NOTHING AND CREATES NOTHING:… |
| `tenpo_linkedin_ads` | Mid | Pause or resume a LinkedIn Ads campaign. |
| `tenpo_meta_ads` | Mid | Manage Meta (Facebook/Instagram) ad campaigns and ad sets. |
| `tenpo_pinterest_ads` | Mid | Pause or enable a Pinterest Ads campaign. |
| `tenpo_snapchat_ads` | Mid | Pause or enable a Snapchat Ads campaign. |
| `tenpo_tiktok_ads` | Mid | Pause or resume a TikTok Ads campaign or ad group. |

### Customers, CRM & Outreach  
*9 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_customer_intelligence` | Mid | GOD-MODE customer analysis — predictive + concentration + cross-sell in one call. |
| `tenpo_customer_segments` | Mid | Customers grouped by loyalty tier — champions, loyal, new, at_risk, lost, occasional — with counts and total spend per segment. |
| `tenpo_hubspot_crm` | Mid | Create or update HubSpot CRM records (contacts, deals). |
| `tenpo_influencer_tracker` | Mid | Track influencer/UGC campaign ROI via coupon codes and generate outreach sequences or creative briefs. AUTO-DISCOVERS top products and coupon data from the database — call immediately… |
| `tenpo_partnership_finder` | Mid | Find non-competing brands sharing customer profile for cross-promo. Maps adjacent categories via Particl. |
| `tenpo_pipedrive_crm` | Mid | Create or update Pipedrive CRM records (persons, deals, activities). |
| `tenpo_pr_outreach` | Mid | PR and media outreach tool. Uses real store data (top SKUs, repeat-order patterns, customer counts, category trends, optionally Tenpo's competitor intel) to build credible pitches that… |
| `tenpo_salesforce_record` | Mid | Create or update a Salesforce CRM record (Contact, Lead, Opportunity, Account). |
| `tenpo_top_customers` | Basic | Top customers ranked by total spend — customer names (auto-resolved and decrypted server-side), order count, total spent. |

### Customer Support & Post-Purchase  
*19 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_aftership_track` | Mid | AfterShip shipment tracking. action=track (default) looks up real-time status + ETA for an existing tracking number. action=create_tracking REGISTERS a new tracking number with AfterShip… |
| `tenpo_build_faq` | Mid | Generate FAQ content for products to reduce pre-sale questions and returns. AUTO-DISCOVERS the best products from the database — call immediately without asking the merchant for product… |
| `tenpo_create_shipment` | Mid | Create shipping labels, get rates, void labels, or track packages via ShipStation or Shippo. PREFER this over manual tracking when either ShipStation or Shippo integration is connected. |
| `tenpo_delivery_watch` | Mid | Catch shipping problems BEFORE the customer files a WISMO ticket. mode=delayed/shipped/out_for_delivery/delivered/exception/all (default all — all proactive states + exceptions). |
| `tenpo_freshdesk_reply` | Mid | Reply to, add notes to, close, reopen, or list open Freshdesk support tickets. |
| `tenpo_gorgias_action` | Mid | Update ticket status, add internal notes, create tags, or assign tickets in Gorgias. |
| `tenpo_gorgias_reply` | Mid | Reply to or add a note on a Gorgias support ticket. |
| `tenpo_handle_ticket` | Mid | Run the deep post-sales CX flow on a support ticket: classify intent (wismo / return / refund / cancel_order / address_change / subscription / wrong_item / product_question / complaint),… |
| `tenpo_intercom_message` | Mid | Send a reply or note in an Intercom conversation. |
| `tenpo_okendo_review_reply` | Mid | Post a reply to an Okendo product review. Requires Okendo integration to be connected and an approvalId. |
| `tenpo_order_triage` | Mid | Triage a customer order issue end-to-end: look up the order (by customer email or order number), pull its real fulfillment status, carrier tracking (ShipStation/Shippo), and any refunds… |
| `tenpo_post_review_response` | Mid | Post a public merchant response to a customer review on Judge.me or Yotpo. Use to respond to negative reviews, thank positive reviewers, or address product concerns publicly. Platform… |
| `tenpo_process_returns` | High | Analyze return rates at the store and product level, break down return reasons, and provide actionable recommendations to reduce returns. Replaces Loop Returns analytics. |
| `tenpo_review_makegood` | Mid | Detect negative product reviews (rating <= threshold) in the merchant's synced review feed and draft a grounded make-good for each: a deterministic apology referencing the real product +… |
| `tenpo_review_monitor` | Mid | Replaces Judge.me / Yotpo analytics. Provides review sentiment analysis, negative review alerts with AI-suggested responses, and per-product rating trends over time. |
| `tenpo_ship_queue` | Mid | The cross-channel fulfillment queue: paid orders that still need to ship, across Shopify, WooCommerce and every connected channel, oldest first, each flagged on-track / due-soon /… |
| `tenpo_support_reply` | Mid | Reply to a Gorgias support ticket, add internal notes, or update ticket status. action. |
| `tenpo_trustpilot_reply` | Mid | Post a public reply to a Trustpilot review on behalf of the business. |
| `tenpo_zendesk_ticket` | Mid | Reply to an existing Zendesk ticket or create a new one. |

### Content, SEO & Merchandising  
*13 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_apply_enrichment_drafts` | Mid | Mark enrichment drafts as approved-for-write. Pass either draftIds (list of specific drafts) OR minConfidence (auto-approve all pending drafts above this threshold). |
| `tenpo_bundle_discovery` | Mid | Discovers frequently co-purchased products and generates bundle recommendations with suggested pricing. Results can be used to manually create Shopify bundles. |
| `tenpo_content_strategy` | Mid | Founder content and storytelling strategy + content calendar grounded in real store data. Generates brand story frameworks, 30-day content calendars with seasonal hooks, content… |
| `tenpo_cro_audit` | Mid | Run a Conversion Rate Optimization audit on the merchant's store. Analyzes conversion funnel, cart abandonment, product page performance, and checkout flow. |
| `tenpo_enrich_catalog` | Mid | Start a catalog enrichment batch — fills in missing metadata, standardises descriptions, and proposes competitive prices for products with gaps. NEVER writes to Shopify directly; all… |
| `tenpo_list_enrichment_drafts` | Basic | List enrichment drafts for merchant review. Each draft contains the current → proposed diff per field with confidence score (0-1) and source citation. |
| `tenpo_listing_health_audit` | Mid | READ-ONLY audit of catalog listing hygiene across every connected channel. Flags listings that are inactive while holding sellable stock (hidden inventory), stranded inbound stock,… |
| `tenpo_packaging_copy` | Mid | Generate personalized packaging insert copy, ritual card text, thank-you notes, gift messages, and shipping label taglines for unboxing experiences. Auto-detects brand category and tone… |
| `tenpo_product_photography_brief` | Mid | Generate detailed AI image prompts and photography briefs for product imagery. Covers hero shots, lifestyle, detail/macro, and social-format variants with platform-specific ratios. |
| `tenpo_publish_blog` | Mid | Publish a blog article to Shopify or WordPress/WooCommerce. Accepts HTML or Markdown (auto-detected). |
| `tenpo_seo_content` | Mid | SEO content generation and optimization. |
| `tenpo_seo_update` | Mid | Audit products for SEO issues and write optimized SEO fields back to Shopify. READ-ONLY. |
| `tenpo_social_content` | Mid | Generate platform-optimized social media content (TikTok, Instagram, Facebook) using real store data including bestsellers, seasonal performance, and product details. AUTO-DISCOVERS hero… |

### Store & Marketplace Control  
*10 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_amazon_listings_write` | High | Set an Amazon MFN (seller-fulfilled) listing's available quantity via SP-API Listings Items. IRREVERSIBLE (a live marketplace listing) → always requires a tenpo_approve approvalId. |
| `tenpo_amazon_orders` | Mid | Fetch recent Amazon Marketplace orders or get order details via the SP-API. |
| `tenpo_bigcommerce_admin` | Mid | Direct BigCommerce Catalog / Orders API write actions. Supports: update_product (PUT /catalog/products/{id}), create_product (POST /catalog/products), set_inventory (PUT… |
| `tenpo_bigcommerce_graphql` | Mid | Run a GraphQL query against the BigCommerce Admin GraphQL API. Pass `query` (the GQL string) and optional `variables` (JSON). |
| `tenpo_cross_channel` | Mid | Reason ACROSS sales channels at once. Returns (1) CHANNEL MIX — revenue/order share per channel (shopify/amazon/woocommerce/…) and which channel is rising/collapsing/new/gone vs the… |
| `tenpo_etsy_listings_write` | High | Set an Etsy listing's available quantity via the Etsy v3 inventory API. IRREVERSIBLE (a live marketplace listing) → always requires a tenpo_approve approvalId. |
| `tenpo_etsy_shop` | Mid | Fetch Etsy shop listings, orders, or shop stats via the Etsy API v3. |
| `tenpo_shopify_admin` | Mid | Direct Shopify Admin API actions for store management. DESTRUCTIVE actions (. |
| `tenpo_shopify_graphql` | High | Execute Shopify Admin GraphQL query or mutation against the merchant's store. READ-ONLY queries (start with `query` keyword or no keyword) — Safe; no approval needed. |
| `tenpo_tiktok_shop_stock_write` | High | Set a TikTok-SHOP SKU's available stock via the Shop Update-Inventory API (NOT TikTok Ads). IRREVERSIBLE (a live marketplace listing) → always requires a tenpo_approve approvalId. |

### Competitive & Market Intelligence  
*20 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_competitor_intel` | Mid | Read latest scraped intel for a tracked brand — catalog, pricing, recent emails, 30-day snapshots. |
| `tenpo_competitor_list` | Mid | List all competitors this merchant is tracking (with last-scraped timestamps + scrape status). |
| `tenpo_competitor_new_skus` | Mid | Products first seen in last N days. |
| `tenpo_competitor_price_changes` | Mid | Competitor SKUs whose price moved in the last N days, derived from stored snapshots (no new external calls). |
| `tenpo_competitor_promo_scan` | Mid | Every tracked SKU currently on sale (compare_price > price). |
| `tenpo_competitor_track` | Mid | Register a brand to monitor (Tenpo scrapes their site). |
| `tenpo_competitor_velocity_signals` | Mid | SKUs that disappeared from competitor catalog (sold-out / delisted proxy). |
| `tenpo_competitor_wayback` | Mid | Wayback Machine CDX historical snapshots. |
| `tenpo_global_signals` | Mid | GOD MODE — anonymized approval patterns aggregated across the Tenpo merchant network. |
| `tenpo_market_pulse` | Mid | Weekly category digest — what's hot, what's trending, what to do. Particl + own data. |
| `tenpo_market_research` | Mid | Full market research pipeline for a product or niche — demand signals, trend stage, competition analysis, margin estimates → GO / CAUTIOUS / NO-GO verdict. |
| `tenpo_meta_ad_library` | Mid | Meta Ad Library search — free with FB Graph token. |
| `tenpo_network_intelligence` | High | PRODUCTION-GRADE network telemetry — k-anonymous (k≥3) signals from across the network. overview = headline numbers; intents = top intents merchants asked + sample queries… |
| `tenpo_particl_analyze_marketing` | Mid | Optional Particl integration] Analyze a competitor brand or category. |
| `tenpo_particl_browse_products` | Mid | Optional Particl integration] Browse competitor product catalogs. |
| `tenpo_particl_search_assets` | Mid | Optional Particl integration] Find competitor creative assets. |
| `tenpo_particl_search_emails` | Mid | Optional Particl integration] Search 1M+ competitor marketing emails. Free fallback: tenpo_competitor_intel. |
| `tenpo_revenue_trend` | Basic | Day-by-day revenue and order count for a given period — useful for charts and trend analysis. |
| `tenpo_winning_ads_generator` | High | Generates ad concepts for a product grounded in competitor ad-library activity plus the merchant's own past winners. |
| `tenpo_winning_patterns` | Mid | Cross-references competitor wins against the merchant's OWN historical winners, then synthesises a 'do X because Y' recommendation set for a given surface. |

### Automation & Workflows  
*14 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_create_task` | Mid | Create a new task card on the merchant's kanban board (tenpo_tasks). Use for a merchant-requested to-do or an agent-planned work item. |
| `tenpo_create_workflow` | Mid | Create a persistent automated workflow from a merchant's natural language description. The agent parses the merchant's intent into trigger + actions + approval mode and saves it. |
| `tenpo_disable_graduated_routine` | Mid | Disable (or re-enable) an auto-routine. |
| `tenpo_enable_automation` | Mid | Pause / discard |
| `tenpo_enable_workflow_template` | Mid | Turn on a pre-configured workflow by its template id (from tenpo_list_workflow_templates). Validates the curated plan against the merchant's data, then creates it as an active workflow. |
| `tenpo_list_graduated_routines` | Basic | List the merchant's auto-graduated routines + their success/failure counts. |
| `tenpo_list_workflow_templates` | Basic | Browse the pre-configured workflow catalog — curated, ready-to-enable automations (low-stock alerts, VIP churn, weekly P&L, dead-stock, oversell guard, …). Returns… |
| `tenpo_list_workflows` | Basic | List all automated workflows for a merchant, with trigger info and execution stats. |
| `tenpo_manage_tasks` | Mid | CRUD interface for the AI-powered kanban task board. Create tasks from insights, update status (todo/in_progress/done), list by priority, or get the board URL. |
| `tenpo_manage_workflow` | Mid | Pause, resume, delete, or approve a pending workflow execution. Use. |
| `tenpo_pause_automation` | Mid | Pause a running automation or workflow without deleting it. |
| `tenpo_run_routine` | Mid | Returns a routine spec (prompt body + cron + skills used) so host AI runs it with own LLM. Spec only — no Tenpo LLM fired. |
| `tenpo_schedule_report` | Mid | Schedule recurring store performance email reports. Replaces expensive analytics tools. |
| `tenpo_set_task_status` | Mid | Update a tenpo_tasks row status from trusted UI flows (board drag/drop). This is a constrained mutation path for task lifecycle changes only. |

### Approvals, Safety & Audit  
*17 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_action_ledger` | Mid | Review the AGENT ACTION LEDGER: every action the operator took (today: simulated writes against a would-land receptor), threaded end to end — action → the would-land record → the… |
| `tenpo_approve` | Mid | Request merchant approval for a SPECIFIC, IRREVERSIBLE write action they have asked you to perform. Returns an approval ID. |
| `tenpo_autonomous_status` | Basic | Returns Tenpo's autonomous-system state for THIS merchant: list of detectors that watch for incidents (revenue cliff, stock crash, refund spike, ROAS death, dead stock with ads, payment… |
| `tenpo_autonomy_policy` | High | Get or set the merchant's autonomous-execution policy. action='get' returns the current policy; action='set' updates the provided fields. Fields: level… |
| `tenpo_dashboard` | Mid | Multi-chart pack for a domain (revenue/ads/inventory/customers). Returns KPIs + Mermaid charts ready to render. |
| `tenpo_delete_board_card` | Mid | Soft-delete a board card (sets deleted_at) so it no longer shows on the kanban board. kind='action' targets tenpo_actions (match id or action_id); kind='task' targets tenpo_tasks. Scoped… |
| `tenpo_get_board` | Basic | Read the current kanban board — returns recent agent actions and their statuses. |
| `tenpo_hq_dashboard` | Mid | Generate a unified HQ dashboard snapshot across all connected integrations. period. |
| `tenpo_log_action` | Basic | Log actions AND findings to the merchant's kanban board. |
| `tenpo_log_board_comment` | Basic | Append a merchant comment to a board card's activity timeline (agent_events, kind='comment'). Used by the card drawer so the merchant's instruction is recorded against the card. |
| `tenpo_onboarding` | Mid | State-aware new-merchant flow with persistence (Supabase) + auto-detection from broker vault. |
| `tenpo_read_agent_events` | Basic | Read the append-only glass-box activity spine (agent_events) for the live board feed. Returns events with seq > since (ascending), optionally filtered to one taskId, plus the next cursor. |
| `tenpo_resolve_alert` | Basic | Mark an active alert as resolved after the merchant has addressed it. Use whenever the merchant confirms an action was taken — eg. |
| `tenpo_resolve_approval` | Mid | Resolve a pending approval as approved or denied. Call after the merchant has explicitly confirmed or rejected the proposed action. |
| `tenpo_set_action_status` | Mid | Update a tenpo_actions row status from trusted UI flows (board/inbox). This tool only mutates action status fields and optional result metadata. |
| `tenpo_shadow_report` | Mid | Builds the 'promote to live' card for a merchant's shadow-mode workflow runs: how many times it fired in shadow (write_receptors), how many of those writes were verified by re-read, how… |
| `tenpo_undo_last_fire` | Mid | Undo the merchant's MOST RECENT completed workflow fire. Reconstructs the writes that ACTUALLY ran (resolved args, not the template), builds the honest inverse for each reversible write… |

### Memory & Learning  
*13 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_episode_recall` | Basic | Looks up a past consolidated CASE (episode) from the memory graph that resembles the given situation — eg 'supplier delay', 'CPM spike', 'stockout wave' — and quotes it back VERBATIM:… |
| `tenpo_graph_ingest` | Mid | Feed a document/CSV into the knowledge graph. THE headline: a merchant drops a supplier CSV (sku, supplier, unit_cost, lead_time, moq) and this creates variant-level `supplies` edges… |
| `tenpo_graph_traverse` | High | Walk the merchant's knowledge graph from a start node (a SKU, product, supplier, location, or channel) and return the connected sub-graph — the edges + nodes within N hops. |
| `tenpo_graph_upsert` | Mid | Add or update knowledge-graph edges (and non-canonical nodes) — the agent's way to RECORD a relationship it learned: 'supplier Acme supplies SKU X at $4.20', 'this product belongs to the… |
| `tenpo_log_interaction` | Basic | Log a CRM interaction for a customer (note, call, meeting, deal, etc.). |
| `tenpo_memory_forget` | Mid | Retire one fact from what Tenpo knows about this merchant's store so it stops being used in answers. A soft, reversible retire (lifecycle_status=. |
| `tenpo_memory_pin` | Mid | Pin (or unpin) one fact so dreaming holds it at full strength and never lets it decay or be forgotten. Pinning also lifts an expiring/forgotten fact back to active immediately, so the… |
| `tenpo_memory_recall` | Basic | Search semantic memory for past facts / preferences / decisions. |
| `tenpo_memory_teach` | Mid | Add a fact the MERCHANT states about their store to long-term memory, marked source='user_said' — the highest-trust source. Deduped and embedded like any distilled fact. |
| `tenpo_record_merchant_activity` | Basic | Record an authenticated merchant touch used to learn when daily briefings are useful. |
| `tenpo_remember` | Mid | Persist a fact, insight, or piece of information about the merchant's business to long-term memory. Use whenever the merchant shares something important that should be recalled in future… |
| `tenpo_update_memory` | Mid | Update the merchant's MEMORY.md business narrative. Call this silently when you learn context worth preserving: supplier details (with WHY they use them), product backstory, decisions… |
| `tenpo_write_daily_memory` | Mid | Write a session summary to today's daily memory file. Call at the END of a conversation or whenever a significant event or decision has been completed. |

### Visualization & Reporting  
*5 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_chart` | Mid | Generate a beautiful rendered chart image from a SQL query. ALWAYS use this tool instead of the canvas tool when the merchant asks for a chart, pie chart, bar chart, line chart, radar… |
| `tenpo_compare_table` | Mid | Me vs N competitors comparison via Particl. Returns next_steps for parallel tool calls + output template. |
| `tenpo_generate_pdf` | Mid | DEPRECATED FOR PURCHASE ORDERS — use tenpo_generate_po instead for ALL purchase order creation. Do NOT use this tool when the inventory-ops skill is active or when generating a PO. |
| `tenpo_mermaid` | Mid | SQL → Mermaid diagram (pie/bar/flowchart/timeline). Coding agents render Mermaid inline. |
| `tenpo_visualize` | Mid | Turn the merchant's data (or a supplied data bag) into a PORTABLE render package the host draws itself: the best-fit viz (a board when the data is entities-with-state/actions, a KPI grid… |

### Integrations, Channels & Messaging  
*44 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_add_custom_connector` | Mid | Connect Tenpo to any REST API or create inbound webhook endpoints. Test connectivity first, then register for scheduled pulls. |
| `tenpo_airtable_record` | Mid | Create or update a record in an Airtable base. |
| `tenpo_asana_action` | Mid | Create tasks, mark tasks complete, add comments, or list tasks in Asana. |
| `tenpo_asana_task` | Mid | Create a task in an Asana project. |
| `tenpo_call_integration` | Mid | Call a live API endpoint for any connected integration (47 supported). Most writes do NOT need approval — Notion / Slack / Discord / Trello / Asana / Monday / ClickUp / Airtable / GitHub… |
| `tenpo_check_oauth_app_credentials` | Basic | Check whether merchant OAuth app credentials exist in the vault for a given provider. |
| `tenpo_clickup_task` | Mid | Create a task in a ClickUp list. |
| `tenpo_connect_google_sheet` | Mid | Register a Google Sheets document as a live-sync integration source. Does a dry-run preview to validate the URL and infer column schema. |
| `tenpo_connect_integration` | Mid | Connect a merchant's store to Tenpo (Shopify or WooCommerce) and store credentials securely. ). |
| `tenpo_create_gmail_draft` | Mid | Create a Gmail draft in the merchant's connected Google Workspace inbox. |
| `tenpo_create_monday_task` | Mid | Create an item (task) on a merchant's Monday.com board. ONLY use this if the merchant explicitly has Monday.com connected AND specifically asks to create a Monday task. Use cases:… |
| `tenpo_create_webhook_endpoint` | Mid | Create a named inbound webhook endpoint that receives pushed data from any external system. Returns a unique URL that external systems POST JSON to. |
| `tenpo_cross_integration_insight` | Mid | CORE GOD-MODE TOOL: Find hidden patterns by cross-referencing data from ALL connected integrations simultaneously. Use this tool FIRST for complex multi-platform questions. |
| `tenpo_disconnect_integration` | Mid | Disconnect a third-party integration. Deletes credentials from vault and marks the integration inactive. |
| `tenpo_get_integration_capabilities` | Basic | Return the authoritative capability record for an integration: name, category, OAuth scopes or credential fields, agent tools, DB tables, and explicit canDo/cannotDo lists. |
| `tenpo_github_action` | Mid | Create issues, close issues, add comments, or list open issues in a GitHub repository. |
| `tenpo_github_issue` | Mid | Create an issue in a GitHub repository. |
| `tenpo_google_sheets_write` | Mid | Append rows, write ranges, clear ranges, create new sheets, create charts, or export JSON data to a Google Sheet. |
| `tenpo_http_call` | High | Make an HTTP request to ANY API on the internet. This is the. |
| `tenpo_integration_query` | Basic | Run a read-only SQL query against integration tables (klaviyo_profiles, klaviyo_campaigns, gorgias_tickets, monday_items, ga4_daily_metrics, ga4_traffic_sources, stripe_charges,… |
| `tenpo_integration_request` | Mid | Call ANY connected integration's API with auth handled automatically (via Nango). Use method. |
| `tenpo_list_custom_integrations` | Basic | List custom HTTP integrations the merchant has registered. Use to answer. |
| `tenpo_list_integrations` | Basic | List all third-party integrations connected for a merchant, with sync HEALTH: status is 'connected' (last successful sync within its cadence window), 'degraded' (credentials present but… |
| `tenpo_monday_item` | Mid | Create an item on a Monday.com board. |
| `tenpo_notify_discord` | Mid | Send a notification to the merchant's Discord server via webhook. |
| `tenpo_notify_slack` | Mid | Send a Slack notification to the merchant's team channel via webhook or bot token. PREFER this proactively when Slack is connected for: critical stock alerts, large orders, dispute… |
| `tenpo_notify_telegram` | Mid | Send a Telegram message to the merchant via their connected Telegram bot. Use proactively for: critical stock alerts, large orders, dispute notifications, fulfillment delays, daily… |
| `tenpo_notify_user` | Mid | Push a message into the merchant's Tenpo chat inbox so they see it the next time they open the chat — even if they're not actively in a conversation right now. |
| `tenpo_notion_page` | Mid | Create a new page in a Notion database or workspace. |
| `tenpo_notion_update` | Mid | Update a Notion page's properties or query a Notion database. |
| `tenpo_purge_integration_data` | Mid | Delete all rows from this merchant's synced tables for a given integration. Called by the Disconnect flow in Settings → Integrations when the merchant ticks. |
| `tenpo_register_custom_integration` | Mid | Register a new custom HTTP integration (any API on the internet) for THIS merchant. After registration, call tenpo_http_call with integrationId to invoke endpoints — auth + base URL are… |
| `tenpo_remove_custom_integration` | Mid | Remove a previously-registered custom HTTP integration. Use only when merchant explicitly asks to disconnect a custom integration. |
| `tenpo_request_custom_integration` | Mid | Handle unsupported tools gracefully. Call this when a merchant mentions a tool Tenpo doesn't have a native adapter for. |
| `tenpo_send_email` | High | Send a transactional or marketing email via Resend. TRANSACTIONAL TYPES (order_confirmation, shipping_update, delivery_confirmation, refund_confirmation, password_reset,… |
| `tenpo_send_sms` | High | Send an SMS or WhatsApp message to a customer via Twilio. Always requires an approvalId. |
| `tenpo_send_whatsapp` | High | Send a WhatsApp message to the merchant's configured WhatsApp number via Meta WhatsApp Business Cloud API. |
| `tenpo_setup_channel_chat` | Mid | Save credentials to enable two-way inbound chat on Telegram, WhatsApp (Meta Cloud API), or Slack. After saving, customers/merchants can DM the bot and get AI responses. |
| `tenpo_sms_send` | Mid | Send an SMS using Postscript, Attentive, or Twilio (whichever is connected). |
| `tenpo_store_oauth_app_credentials` | Mid | Store a merchant's own OAuth app credentials (Client ID + Client Secret) in the vault, then immediately return the authorization URL. Called directly via /tools/invoke — NOT LLM-mediated. |
| `tenpo_sync_monday` | Mid | Bidirectional sync with Monday.com. ONLY use if the merchant has Monday.com connected and explicitly requests a sync. push: creates/updates a Monday item from a Tenpo task. pull: imports… |
| `tenpo_trello_action` | Mid | Create, move, close, or comment on Trello cards. |
| `tenpo_trello_card` | Mid | Create a card on a Trello board list. |
| `tenpo_webhook_token` | Mid | Issue or rotate the signed token for an inbound webhook endpoint. |

### Data Import, Export & Sync  
*9 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_analyze_custom_schema` | Mid | Analyze webhook payloads from a custom (unsupported) integration and propose a structured DuckDB schema. |
| `tenpo_export_data` | Mid | Export store data as a downloadable CSV spreadsheet. DESTRUCTIVE FOR PRIVACY: this tool decrypts and emits PII (customer emails, addresses, phone numbers in `customers` table) into a… |
| `tenpo_full_sync` | Mid | Trigger a full data sync for a merchant. Use during onboarding to import all products, orders, customers, and coupons. |
| `tenpo_import_data` | Mid | Import CSV, TSV, JSON, NDJSON file content or a Google Sheets URL into a Tenpo custom table. Auto-detects format, cleans dates/currencies/emails/phones. |
| `tenpo_import_from_saas` | Mid | Pull data from Notion, HubSpot, Airtable, Google Drive, Monday.com, Salesforce, ClickUp, Asana, Zendesk, or Pipedrive into a Tenpo custom table. Auto-paginates all records. Auth… |
| `tenpo_import_from_url` | Mid | Server-side fetch + ingest CSV/TSV/JSON/XLSX from any URL into a custom_* DuckDB table. Handles binary files. |
| `tenpo_incremental_sync` | Mid | Manually trigger an incremental sync for a merchant to get the latest data. Only fetches records modified since the last sync. |
| `tenpo_list_uploaded_datasets` | Basic | List uploaded files (CSV/TSV/JSON/NDJSON) that were imported into a per-merchant queryable table. Returns the table name (data_table), row/column counts, original filename and detected… |
| `tenpo_register_uploaded_file` | Mid | Internal: register an uploaded file (CSV/TSV/JSON/NDJSON/PDF/XLSX) in tenpo_files so the agent can see it and reference it. Auto-detects type and builds a plain-English summary. |

### Setup & Account  
*9 tools*

| Tool | Level | What it does |
|---|---|---|
| `tenpo_bulk_cancel` | High | Cancel a queued or running bulk operation job. A cancelled job stops processing as soon as the current item finishes. |
| `tenpo_bulk_create` | Mid | Create and queue a bulk operation job for the merchant's Shopify store. |
| `tenpo_bulk_list` | Mid | List recent bulk operation jobs for the merchant. Returns up to 10 most recent jobs with their status and progress. |
| `tenpo_bulk_status` | Mid | Check the status and progress of a bulk operation job. Returns status (queued/running/completed/failed/cancelled), counts, and result summary. |
| `tenpo_cancel_subscription` | High | Cancel Pro subscription. Default: returns Dodo customer-portal URL. |
| `tenpo_set_language` | Basic | Set the merchant's preferred language for all Tenpo responses. Supports 20+ languages including English, Spanish, Portuguese, German, French, Japanese, Korean, Hindi, Indonesian, Polish,… |
| `tenpo_set_preference` | Basic | Persist a merchant preference that should apply in all future interactions. |
| `tenpo_update_merchant_settings` | Mid | Update merchant settings from trusted UI flows (store name, timezone, language, display currency, quiet hours). This is a constrained settings mutation path and does not allow arbitrary SQL. |
| `tenpo_update_user_profile` | Mid | Update the merchant's USER.md profile file. Call this silently when you learn new details about the store owner, their operating style, preferences, timezone, corrections, or any… |

---

## 5. The Psychology Layer

Tenpo doesn't just do the work — it does it the way a good operator would, because behavioural science is loaded into every recommendation.

Two skills carry this, and **both are always on**:

- **`tenpo-psychology-core`** — the always-on lens. Applied silently to every recommendation. It never says "according to loss aversion" — it just writes better copy, better prices, better layouts.
- **`tenpo-human-voice`** — strips the tells that make writing feel machine-made (significance padding, AI vocabulary, rule-of-three cadence, bolded inline-header lists) and replaces them with the merchant's own specifics.
- **`tenpo-conversion-psychology`** — the full 60+ model library, loaded on demand.

### Which model gets applied when

| Merchant problem | Models Tenpo reaches for |
|---|---|
| Low product-page conversion | Loss Aversion, Social Proof, Scarcity, Decoy Effect |
| Email not opened or clicked | Curiosity Gap, Zeigarnik, FOMO, Personalisation |
| Cart abandonment | Loss Aversion, Sunk Cost, Urgency, Friction reduction |
| Pricing resistance | Anchoring, Rule of 100, Charm Pricing, Decoy Effect |
| Low repeat purchase | Commitment & Consistency, Endowment Effect, Reciprocity |
| Weak upsell / cross-sell | Foot-in-the-Door, Bundling, Contrast Effect |
| New customer acquisition | Social Proof, Authority, Mere Exposure, Story |
| Win-back campaigns | Endowment Effect, Peak-End Rule, Loss Framing |

### The named models in the library

**Behavioural foundations** — Loss Aversion (Kahneman & Tversky) · Anchoring · Decoy Effect (Asymmetric Dominance) · Social Proof · Scarcity (real only) · Reciprocity (Cialdini) · Commitment & Consistency (Cialdini) · Authority (Cialdini) · Foot-in-the-Door · Door-in-the-Face · Mere Exposure Effect · Availability Heuristic · Confirmation Bias

**Buyer psychology** — Endowment Effect · IKEA Effect · Hyperbolic Discounting · Paradox of Choice (Schwartz) · Goal-Gradient Effect · Peak-End Rule (Kahneman) · Zeigarnik Effect · Mental Accounting (Thaler) · Pratfall Effect

**Pricing psychology** — Rule of 100 · Charm vs. Round Pricing · Good-Better-Best Tier Design · Anchoring in Pricing Pages

**Behaviour change** — BJ Fogg B = MAP · EAST Framework (Behavioural Insights Team) · Activation Energy · Nudge Theory (Thaler & Sunstein)

**Growth & retention** — Positive Feedback Loops · Switching Costs · Network Effects

**The rule Tenpo follows:** scarcity must be real, social proof must be true, and the business problem leads — psychology is the engine, never the conversation.

**Level:** 🔴 High

---

## 6. The Skill Library — 239 playbooks

Skills are expert knowledge the agent loads *on demand*, so it doesn't carry 239 playbooks in its head at once. Two are always resident (psychology, human voice); the rest are pulled when the question calls for them.

### Routines (scheduled, always-on)
*20 skills*

| Skill | What it gives the agent |
|---|---|
| `40rty-routines-abandoned-cart-patrol` | Every 4 hours — scans for abandoned checkouts, segments by value, surfaces high-priority recoveries to Slack. |
| `40rty-routines-catalog-health-weekly` | Wednesdays — comprehensive product data quality scan. |
| `40rty-routines-customer-churn-watch` | Weekly — identifies at-risk and churning customers with win-back recommendations. |
| `40rty-routines-dead-stock-weekly` | Sundays — identify dead stock and generate markdown candidates report. |
| `40rty-routines-discount-roi-weekly` | Tuesdays — review discount code performance and flag underperforming campaigns. |
| `40rty-routines-fraud-sentinel` | Every 2 hours — scans recent orders for fraud indicators and flags high-risk orders. |
| `40rty-routines-fulfillment-sla-watchdog` | Twice daily on weekdays — checks for overdue fulfillments and stalled shipments. |
| `40rty-routines-inventory-aging-monthly` | 15th of each month — inventory aging buckets with carrying cost analysis. |
| `40rty-routines-low-stock-watchdog` | Daily inventory scan — alerts when products drop below reorder point based on sales velocity. |
| `40rty-routines-monthly-financial-close` | First of every month — comprehensive financial close report with P&L, payouts, taxes, and refunds. |
| `40rty-routines-morning-store-briefing` | Daily morning digest — orders, revenue, fulfillment status, and issues from the last 24 hours. |
| `40rty-routines-new-product-launch-tracker` | Daily — tracks first-week performance of recently published products. |
| `40rty-routines-payout-recon-daily` | Daily — reconciles Shopify Payments payouts against orders, flags discrepancies. |
| `40rty-routines-price-anomaly-scanner` | Daily early morning — scans for pricing errors, zero-price products, and compare-at-price inconsistencies. |
| `40rty-routines-quarterly-business-review` | First day of each quarter — comprehensive QBR with trends, cohorts, top movers, and strategic insights. |
| `40rty-routines-return-fraud-watch` | Mondays — scans for suspicious return patterns and serial returners. |
| `40rty-routines-seo-coverage-weekly` | Thursdays — SEO metadata gap report across catalog. |
| `40rty-routines-staff-activity-monthly` | First of each month — staff account audit and permission review for the connected Shopify store. |
| `40rty-routines-vip-customer-watcher` | Daily — alerts on VIP customer orders, issues, or churn risk for white-glove handling. |
| `40rty-routines-weekly-business-review` | Monday morning — comprehensive weekly performance report across all store dimensions. |

### Charts & Visual Output
*11 skills*

| Skill | What it gives the agent |
|---|---|
| `tenpo-viz-board` | Render a live operator board — a KPI strip plus columns of entities-with-state (pending approvals, low-stock reorders, at-risk orders), each row carrying one-tap action… |
| `tenpo-viz-cascade-graph` | Render a cause-effect impact graph (nodes = entities/events, edges = ripple relationships, severity-weighted) as a force-directed SVG the host shows as an interactive… |
| `tenpo-viz-cohort-heatmap` | Render a cohort-retention or repeat-purchase matrix (rows = signup cohort, cols = months-since, cells = retained %) as a beautiful CSS-grid heatmap with hover tooltips and… |
| `tenpo-viz-experiment-lift` | Render measured action lift with confidence intervals (difference-in-differences results) as a beautiful dot-and-CI plot the host shows as an interactive artifact.  Use to… |
| `tenpo-viz-funnel` | Render a conversion funnel (ordered steps with counts) as a beautiful trapezoid SVG funnel with per-step drop-off percentages the host shows as an interactive artifact.… |
| `tenpo-viz-gauge` | ' metric with a good-enough threshold.  The bar-vs-target read answers the health question instantly where a number in prose does not. |
| `tenpo-viz-inventory-risk-dashboard` | Render an inventory-risk command view — headline KPIs, a stockout-risk list (days-of-cover, RAG-coded), and a reorder queue — as a responsive bento HTML dashboard the host… |
| `tenpo-viz-ranked-bar` | Render a ranked/Pareto bar chart the host shows as an interactive artifact — top products by units sold, customer revenue concentration (80/20), or any 'what/who drives… |
| `tenpo-viz-revenue-waterfall` | Turn a sequence of revenue/margin/cash movements (base to increases to decreases to total) into a beautiful animated SVG waterfall the host renders as an interactive… |
| `tenpo-viz-series` | Render a time-series (revenue/orders trend) as a beautiful, self-contained interactive artifact instead of a static PNG. spec ({labels, series, unit}). |
| `tenpo-viz-tokens` | The Tenpo viz DESIGN SYSTEM — one shared palette, type scale, spacing rhythm, depth and motion tokens as copy-paste CSS custom properties.  Every tenpo-viz-* skill inlines… |

### Core Operator Brain
*26 skills*

| Skill | What it gives the agent |
|---|---|
| `tenpo-anything-api` | Connect to ANY external service via API — when the merchant says 'connect to X' / 'set up X' / 'I use X' / 'send to my X' / 'pull from my X' / 'sync with X' / 'can you… |
| `tenpo-ask-anything` | Answer ad-hoc natural language questions about the merchant's store data.  Translates questions to DuckDB SQL, executes against the merchant's database, and returns… |
| `tenpo-automations` | Full automation creation guide — tenpo_create_workflow, llm_agent config, send_notification templates, 5 task patterns (simple report, conditional, approval gate,… |
| `tenpo-connectors` | Connect Tenpo to any REST API on a recurring schedule, or receive pushed data via inbound webhooks.  Use when a merchant wants to auto-sync data from a custom or… |
| `tenpo-custom` | Custom integration support for tools without native Tenpo adapters.  Handles CSV imports, webhook ingestion, and custom API connections. |
| `tenpo-customer-winback` | Customer win-back intelligence.  Identifies at-risk and churning customers, diagnoses WHY they left, and executes personalized recovery campaigns with root-cause-aware… |
| `tenpo-daily-briefing` | Daily morning briefing — your $200/hr fractional CMO condensed into a 2-minute read.  Executive-quality KPIs, anomaly detection, cross-system intelligence, and one… |
| `tenpo-data-privacy` | Global data-privacy compliance for ecommerce — GDPR (EU), CCPA/CPRA (California), PIPEDA (Canada), LGPD (Brazil), DPDP (India), Privacy Act 1988 (Australia), PIPL (China),… |
| `tenpo-data-query-playbook` | How to write valid tenpo_query SQL against the merchant's DuckDB — schema-aware joins, BigInt/Decimal handling, common patterns, performance tips. |
| `tenpo-db` | Tenpo's complete database reference — every table, column, relationship, and query pattern.  The model's single source of truth for all SQL queries. |
| `tenpo-db-core` | Critical database rules for every query: forbidden SQL, column names, PII rules, table inventory.  For full per-table schema + SQL examples, call get_skill('tenpo-db') or… |
| `tenpo-db-recipes` | Copy-ready SQL for the questions that otherwise burn a turn on exploration: cross-channel oversell, the four metrics whose SOURCE decides the answer (revenue… |
| `tenpo-discovery` | Progressive feature discovery.  Tenpo reveals capabilities naturally during conversations, not all at once. |
| `tenpo-exploration` | Self-directed data exploration. ". |
| `tenpo-hq-dashboard` | Centralized real-time dashboard providing unified KPI view across all connected integrations.  Surfaces key metrics, alerts, and action items in a single snapshot. |
| `tenpo-human-voice` | Makes everything Tenpo writes for a merchant read like a person wrote it, not a language model.  Apply to email campaigns, subject lines, product descriptions, SEO copy,… |
| `tenpo-import` | Import data from files (CSV, TSV, JSON, NDJSON, Google Sheets) or any of 10 SaaS platforms directly into Tenpo custom tables.  Use when a merchant wants to bring external… |
| `tenpo-insights` | Proactive business intelligence — finds patterns and opportunities the merchant would miss.  Runs on daily-insights cron. |
| `tenpo-intelligence` | Tenpo intelligence — the Harvard MBA brain.  Activates when running intelligence analysis, presenting insights, or when merchant asks about their store. |
| `tenpo-memory` | Tenpo remembers merchant priorities, preferences, past experiments, and goals.  Captures context during conversations. |
| `tenpo-onboarding` | Guides a new merchant through connecting their store to Tenpo, OR gives an existing connected merchant a personalised "here's what I can do for YOUR store" walkthrough.… |
| `tenpo-operator-core` | Always-on DTC operator lens — leaky bucket revenue diagnosis, cmROAS, LTV:CAC, RFM segments, churn windows, DOI, email benchmarks, pricing decision trees.  Apply these… |
| `tenpo-operator-intelligence` | 80+ named frameworks, decision trees, and mental models spanning revenue diagnosis, pricing, retention, inventory, email/CRM, paid ads, brand strategy, customer… |
| `tenpo-psychology-core` | Always-on behavioral psychology lens — Loss Aversion, Anchoring, Social Proof, Scarcity, Decoy Effect, Reciprocity, Commitment, Paradox of Choice, Rule of 100, BJ Fogg… |
| `tenpo-soul` | Tenpo's core intelligence.  Identity, thinking protocols, autonomy rules, memory, and integration awareness. |
| `tenpo-workflows` | Handles workflow creation, management, and explanation.  Activates when merchant wants to automate something, set up alerts, or use 'whenever', 'alert me when',… |

### Money, Pricing & Finance
*18 skills*

| Skill | What it gives the agent |
|---|---|
| `tenpo-cac-ltv-payback` | CAC:LTV and payback period framework — channel-level and cohort-aware.  Computes blended + per-channel CAC, 3/6/12-month observed LTV cohort curves, payback period, and… |
| `tenpo-cash-flow-forecast` | 13-week rolling cash-flow forecasting for ecommerce — runway math, inventory-financed growth (Settle/Drivepoint/Wayflyer), AR/AP scheduling, payout timing, working capital… |
| `tenpo-cash-growth-tradeoff` | Cash-vs-growth capital allocation framework — when to reinvest, buffer, or pay down supplier debt.  Computes operating runway, cash conversion cycle, inventory capital… |
| `tenpo-cogs-import` | Import product costs (COGS) from Google Sheets or CSV to enable profit analysis, margin-aware discounts, and true dead-stock valuation. |
| `tenpo-finance-playbook` | How to think about a merchant's financial health — revenue quality, gross margin, payouts, cash flow, tax exposure, and the 5 questions every financial decision must answer. |
| `tenpo-finance-pnl` | " skill.  Computes contribution margin by pulling revenue, COGS, fees, shipping, ad spend, and custom expenses. |
| `tenpo-finance-tracker` | Cash flow monitoring, financial health alerts, and revenue trend tracking.  Ongoing financial pulse — complements the P&L skill's deep analysis with continuous monitoring,… |
| `tenpo-payments-regional` | Regional payment processor selection — Stripe (US/EU/UK), Adyen (global enterprise), Mollie (EU), Razorpay (India), Square (US/AU/UK/CA/JP), Worldpay (UK/EU enterprise),… |
| `tenpo-pricing-advisor` | Pricing strategy for Shopify stores.  Applies Van Westendorp, Decoy Effect, Good-Better-Best tiering, and psychology-backed frameworks to help merchants find optimal price… |
| `tenpo-pricing-elasticity-strategy` | Pricing elasticity strategy — when and how to change prices, how to proxy elasticity without a controlled experiment, psychological price-point theory for DTC, and the… |
| `tenpo-pricing-optimizer` | Pricing intelligence for Shopify stores.  Analyzes product margin, velocity, and stock levels to surface underpriced fast-movers and overpriced dead stock. |
| `tenpo-pricing-playbook` | How to think about price changes for a Shopify merchant — elasticity proxies, hero-SKU protection, anchor pricing, discount stacking risk, and the 4 questions every price… |
| `tenpo-quickbooks` | QuickBooks accounting intelligence for ecommerce.  Manages invoices, tracks payments, and reconciles revenue. |
| `tenpo-stripe` | Stripe payment intelligence.  Analyzes charges, fees, net revenue, disputes, and payout schedules. |
| `tenpo-subscription-ops` | Subscription / recurring-revenue operations for ecommerce — Recharge, Skio, Stay Ai, Loop, Awtomic.  MRR cohorts, churn analysis, billing-failure dunning, swap rates,… |
| `tenpo-tax-nexus` | Sales tax / VAT / nexus management for ecommerce — US economic-nexus thresholds, EU OSS/IOSS, UK VAT, 1099-K, marketplace facilitator law, Avalara/TaxJar/Stripe Tax… |
| `tenpo-unit-economics` | Unit economics drill-down — the full contribution margin ladder (CM1→CM3) per order, per SKU, per customer segment.  Goes beyond gross margin to true per-unit profit after… |
| `tenpo-xero` | Xero accounting intelligence.  Bridges Shopify sales with proper bookkeeping. |

### Inventory, Supply & Fulfilment
*11 skills*

| Skill | What it gives the agent |
|---|---|
| `tenpo-aftership` | AfterShip tracking intelligence for ecommerce.  Monitors shipment status, delivery performance, and carrier reliability. |
| `tenpo-inventory-analyst` | Ad-hoc inventory intelligence: stockout prediction, dead stock analysis, reorder recommendations, demand forecasting.  Answers inventory questions in real-time. |
| `tenpo-inventory-deep` | Deep inventory operator playbook — replenishment math, dead stock thresholds, cash-trapped inventory analysis, hero SKU coverage discipline. |
| `tenpo-inventory-intelligence` | Daily inventory analysis and real-time critical alerts.  Dead stock detection, stockout prediction, reorder recommendations, and supplier PO drafts. |
| `tenpo-inventory-ops` | Purchase order generation, supplier management, stock transfers, stocktakes, demand forecasting, and the complete inventory operations lifecycle.  The Stocky replacement. |
| `tenpo-purchase-orders` | Purchase order creation, PDF generation, and supplier communication |
| `tenpo-returns-intelligence` | Analyzes refund patterns to detect fraudulent returns, identify systemic product quality issues, compute true margins, and generate actionable return rate reduction… |
| `tenpo-shipping-regional` | Regional shipping carriers + cross-border duties + 3PL selection — US (USPS/UPS/FedEx/DHL), UK (Royal Mail/DPD/Hermes/Parcelforce), EU (DPD/DHL/GLS/Hermes/PostNL/Bpost),… |
| `tenpo-shippo` | Shippo fulfillment intelligence.  Analyzes shipment tracking, carrier rates, delivery ETAs, and shipping costs. |
| `tenpo-shipstation` | ShipStation fulfillment intelligence.  Analyzes shipment performance, carrier costs, delivery times, and tracking status. |
| `tenpo-wholesale-outreach` | Wholesale and B2B outreach automation.  Finds retail buyers and boutiques in the merchant's niche, writes personalized outreach, and runs multi-touch email sequences to… |

### Marketing, Email & Campaigns
*23 skills*

| Skill | What it gives the agent |
|---|---|
| `tenpo-abandoned-cart` | Abandoned cart recovery intelligence.  Detects abandoned carts, tailors recovery messaging by customer type and cart context, and executes multi-step recovery sequences. |
| `tenpo-attentive` | Attentive SMS & email marketing intelligence.  Analyzes subscriber engagement, campaign performance, and conversational commerce ROI. |
| `tenpo-campaign-engine` | Core campaign execution engine.  Handles email (Resend), SMS (Twilio), and WhatsApp sending. |
| `tenpo-campaigns` | Build and send email campaigns, set up automation flows (abandoned cart, win-back, post-purchase, welcome series), and schedule recurring store performance reports.… |
| `tenpo-crm` | Customer intelligence and relationship management.  RFM segmentation, lifetime value analysis, customer profiling, cohort retention, and actionable segment strategies. |
| `tenpo-deliverability` | Email deliverability optimization — SPF/DKIM/DMARC setup, Google + Yahoo Feb 2024 bulk-sender rules, IP warming, sender reputation (Postmaster Tools, Sender Score), domain… |
| `tenpo-email-compliance` | Email marketing compliance per region — CAN-SPAM (US), GDPR (EU), PECR (UK), CASL (Canada), Australian Spam Act, Brazilian LGPD, Indian DPDP, Spam Act 2003 (AU).  Sender… |
| `tenpo-growth-agent` | The goal-driven SELLING agent: the merchant gives ONE marketing goal ("grow my email list", "win back lapsed VIPs", "drive repeat purchases", "sell more of X", "get me 50… |
| `tenpo-hubspot` | HubSpot CRM intelligence for ecommerce.  Manages contacts, companies, deals, and activities. |
| `tenpo-influencer-affiliate` | Influencer + affiliate marketing operations — partnership types (paid post / gifting / affiliate / ambassador / whitelisting), platforms (Aspire, GRIN, Refersion,… |
| `tenpo-klaviyo` | Klaviyo email/SMS marketing intelligence.  Analyzes campaign performance, flow effectiveness, segment health, and profile engagement. |
| `tenpo-mailchimp` | Mailchimp email marketing intelligence.  Analyzes campaign performance, audience health, automation effectiveness, and subscriber engagement. |
| `tenpo-market-research` | Outbound market research for ecommerce — TAM sizing, competitor pricing intelligence, positioning gaps, white-space identification.  Loads when merchant asks "what's the… |
| `tenpo-marketing-mix-incrementality` | Marketing mix and incrementality framework — cuts through platform-reported ROAS to true incremental contribution.  Allocates budget by marginal ROAS, detects diminishing… |
| `tenpo-omnisend` | Omnisend email/SMS marketing intelligence.  Analyzes campaign and workflow performance, contact engagement, and multi-channel (email + SMS) effectiveness. |
| `tenpo-pipedrive` | Pipedrive CRM intelligence for ecommerce sales teams.  Manages deals, contacts, organizations, and activities. |
| `tenpo-post-purchase` | Post-purchase experience optimization.  Manages the critical window after a purchase with timed sequences: thank-you, shipping updates, review requests, cross-sell, and… |
| `tenpo-postscript` | Postscript SMS marketing intelligence for Shopify.  Analyzes campaign performance, subscriber growth, and SMS revenue attribution. |
| `tenpo-pr-outreach` | PR and media outreach automation.  Researches journalists and publications relevant to the merchant's niche, drafts personalized pitches, manages outreach sequences, and… |
| `tenpo-resend` | Resend transactional email intelligence for ecommerce.  Sends order confirmations, shipping notifications, password resets, and custom transactional emails via Resend API. |
| `tenpo-salesforce` | Salesforce CRM intelligence for ecommerce.  Manages leads, opportunities, accounts, and contacts. |
| `tenpo-seo-writer` | SEO content creation and optimization.  Performs keyword research from store data, writes optimized product descriptions, blog posts, and collection page copy. |
| `tenpo-social-scheduler` | Social media content scheduling and management across TikTok, Instagram, and LinkedIn.  Writes posts tailored to each platform's voice, suggests optimal posting times,… |

### Advertising & Creative
*13 skills*

| Skill | What it gives the agent |
|---|---|
| `tenpo-ad-library-intel` | Competitor ad creative research using public ad libraries — Meta Ad Library, TikTok Creative Center, Google Ads Transparency Center, Pinterest Trends, LinkedIn Ad Library.… |
| `tenpo-conversion-psychology` | Behavioral science and persuasion psychology for ecommerce.  Applies 60+ named psychological models to campaigns, pricing, product pages, and checkout flows. |
| `tenpo-creative-studio` | Ad creative and marketing asset generation.  Creates ad copy variations, email designs, social media captions, product photography briefs, and banner concepts. |
| `tenpo-cro-optimizer` | Conversion Rate Optimization for Shopify stores.  Audits landing pages, product pages, checkout flow, and site speed. |
| `tenpo-cross-intel` | Cross-system intelligence.  Combines data from multiple integrations to surface insights no single tool can provide. |
| `tenpo-google-ads` | Google Ads intelligence for Shopping, Search, Performance Max, and Demand Gen.  Analyzes campaign performance, ROAS, keyword efficiency, and budget allocation. |
| `tenpo-linkedin-ads` | LinkedIn Ads intelligence for B2B ecommerce.  Analyzes campaign performance, audience targeting, and lead generation ROI. |
| `tenpo-meta-ads` | Meta (Facebook/Instagram) Ads intelligence.  Analyzes campaign performance, ROAS, audience reach, and creative effectiveness. |
| `tenpo-pinterest-ads` | Pinterest Ads intelligence for visual commerce.  Analyzes pin performance, shopping campaigns, and visual discovery ROI. |
| `tenpo-snapchat-ads` | Snapchat Ads intelligence for Gen Z commerce.  Analyzes campaign performance, AR lens engagement, and story ad conversions. |
| `tenpo-tiktok-ads` | TikTok Ads intelligence.  Analyzes campaign performance, ROAS, conversion data, and creative effectiveness. |
| `tenpo-video-ad-prompts` | Composes model-ready AI VIDEO GENERATION prompts for ecommerce ads — UGC/testimonial, unboxing, problem-solution, product hero/360, and cinematic b-roll — grounded in the… |
| `tenpo-video-creative` | Video creative production for ecommerce — UGC ad scripts, hook libraries, format guidance per platform (TikTok, Reels, YouTube Shorts, in-feed), creator brief generation,… |

### Customer Experience & Reviews
*10 skills*

| Skill | What it gives the agent |
|---|---|
| `tenpo-fraud-response` | Fraud investigation playbook — how to triage suspicious orders, evaluate chargeback risk, and respond without false-flagging legitimate customers. |
| `tenpo-freshdesk` | Freshdesk customer support intelligence.  Analyzes ticket volume, priority distribution, response quality, and contact matching. |
| `tenpo-gorgias` | Gorgias customer support intelligence.  Analyzes ticket volume, response times, channel distribution, satisfaction scores, and automation rules. |
| `tenpo-intercom` | Intercom messaging intelligence for ecommerce.  Analyzes customer conversations, support patterns, and engagement signals. |
| `tenpo-judge-me` | me product-review integration.  The most popular Shopify review app. |
| `tenpo-okendo` | Okendo product-review integration.  Mid-market Shopify review platform popular with beauty + apparel brands. |
| `tenpo-reviews` | me and Yotpo.  Analyzes review sentiment, rating distributions, product quality signals, and verified purchase patterns. |
| `tenpo-trustpilot` | Trustpilot business-review integration. me/Okendo). |
| `tenpo-yotpo` | Yotpo reviews + loyalty integration.  Enterprise-tier review platform with built-in loyalty/rewards module. |
| `tenpo-zendesk` | Zendesk support intelligence for ecommerce.  Analyzes ticket patterns, response times, customer satisfaction, and resolution rates. |

### Channels & Messaging
*15 skills*

| Skill | What it gives the agent |
|---|---|
| `tenpo-airtable` | Airtable workspace intelligence for ecommerce ops.  Manages product catalogs, inventory tracking, and supplier databases in Airtable. |
| `tenpo-asana` | Asana project management for ecommerce teams.  Creates and tracks tasks for product launches, marketing campaigns, and operational workflows. |
| `tenpo-clickup` | ClickUp project management for ecommerce teams.  Creates and manages tasks, lists, and spaces for product launches, campaigns, and operations. |
| `tenpo-discord` | Discord notifications via Tenpo.  Post via webhooks (no auth, low-friction) or bot token (richer features). |
| `tenpo-ga4` | Google Analytics 4 intelligence.  Analyzes website traffic, user behavior, conversion funnels, traffic sources, and page performance. |
| `tenpo-github` | GitHub operations via Tenpo — file issues, comment on PRs, manage release notes, read commit history.  Used by merchants whose storefront / theme / custom apps live on GitHub. |
| `tenpo-google-analytics` | Google Analytics 4 data via Tenpo.  Cross-references storefront traffic + conversion with Tenpo's order/customer data to answer "what's the revenue per channel", "which… |
| `tenpo-google-suite` | Google Workspace integration for Gmail, Calendar, and Drive.  Enables sending emails (outreach, PR pitches), scheduling events, and accessing documents. |
| `tenpo-monday` | com workspace intelligence.  Analyzes boards, items, updates, and automations. |
| `tenpo-notion` | Notion workspace integration.  Tenpo writes daily briefings, alert summaries, and incident postmortems into a merchant-configured Notion database; reads task status back… |
| `tenpo-slack` | Slack messaging through Tenpo.  Send team notifications, low-stock alerts, refund-spike pings, abandoned-cart reports, weekly performance digests, and incident-responder… |
| `tenpo-telegram` | Telegram notification and bot intelligence for ecommerce.  Sends order alerts, inventory warnings, and daily summaries to Telegram channels. |
| `tenpo-trello` | Trello board operations via Tenpo — create cards, move them across lists, label, set due dates.  The default lightweight task system for solo / 2-person merchants who… |
| `tenpo-twilio` | Twilio SMS and voice intelligence for ecommerce.  Sends transactional SMS (order confirmations, shipping alerts), marketing campaigns, and supports voice/IVR for customer… |
| `tenpo-whatsapp` | WhatsApp Business messaging for ecommerce.  Sends order confirmations, shipping updates, and customer communications via WhatsApp Business API. |

### Storefronts & Marketplaces
*5 skills*

| Skill | What it gives the agent |
|---|---|
| `tenpo-amazon` | Amazon Seller Central via the Selling Partner API (SP-API).  For merchants on Amazon Marketplace (FBA, FBM, or both). |
| `tenpo-etsy` | Etsy shop operations via Tenpo.  For merchants selling on Etsy in addition to (or instead of) Shopify. |
| `tenpo-shopify` | Shopify is Tenpo's flagship integration.  Reads orders, products, customers, inventory, fulfillments, collections, payouts, discount codes, metafields, abandoned checkouts. |
| `tenpo-shopify-developer` | Shopify theme development and customization via the Shopify Admin API.  Builds custom sections, fixes theme bugs, optimizes page speed, and ships theme changes directly to… |
| `tenpo-woocommerce` | WooCommerce store intelligence.  Analyzes orders, products, customers, and inventory from WooCommerce stores. |

### Merchandising & Catalog Strategy
*3 skills*

| Skill | What it gives the agent |
|---|---|
| `tenpo-bundling-strategy` | Bundle strategy for ecommerce — Mix-and-match, BOGO, threshold/tiered, gift-with-purchase, subscription bundles, premium bundles, "good/better/best" tiering.  Bundle… |
| `tenpo-catalog-enrichment` | Catalog enrichment playbook — fill missing product metadata (ISBN, author, year, publisher, condition, specs), standardise product descriptions, propose competitive… |
| `tenpo-product-portfolio-triage` | Product portfolio triage — BCG-style scale/maintain/kill decision framework.  Classifies every SKU by 90-day revenue velocity (x-axis) and true contribution margin… |

### Shopify Developer Reference
*19 skills*

| Skill | What it gives the agent |
|---|---|
| `shopify-admin` | Write or explain **Admin GraphQL** queries and mutations for apps and integrations that extend the Shopify admin.  Use when the user wants to **understand, design, or… |
| `shopify-app-store-review` | Run a pre-submission compliance check against your Shopify app's codebase.  Reviews App Store requirements and surfaces likely issues before you submit for official review. |
| `shopify-custom-data` | MUST be used first when prompts mention Metafields or Metaobjects.  Use Metafields and Metaobjects to model and store custom data for your app. |
| `shopify-customer` | The Customer Account API allows customers to access their own data including orders, payment methods, and addresses. |
| `shopify-dev` | Search Shopify developer documentation across all APIs.  Use only when no API-specific skill applies. |
| `shopify-functions` | Shopify Functions allow developers to customize the backend logic that powers parts of Shopify. |
| `shopify-hydrogen` | Hydrogen storefront implementation cookbooks.  Some of the available recipes are: B2B Commerce, Bundles, Combined Listings, Custom Cart Method, Dynamic Content with… |
| `shopify-liquid` | Liquid is an open-source templating language created by Shopify.  It is the backbone of Shopify themes and is used to load dynamic content on storefronts. |
| `shopify-onboarding-dev` | Get started building on Shopify.  Use when a developer asks to build an app, build a theme, create a dev store, set up a partner account, scaffold a project, or get… |
| `shopify-onboarding-merchant` | Set up and connect a Shopify store from your AI assistant.  Use when the user wants to: set up my Shopify store, connect my store, install Shopify plugin, get started with… |
| `shopify-partner` | The Partner API lets you programmatically access data about your Partner Dashboard, including your apps, themes, and affiliate referrals. |
| `shopify-payments-apps` | The Payments Apps API enables payment providers to integrate their payment solutions with Shopify's checkout. |
| `shopify-polaris-admin-extensions` | Add custom actions and blocks from your app at contextually relevant spots throughout the Shopify Admin.  Admin UI Extensions also supports scaffolding new adminextensions… |
| `shopify-polaris-app-home` | Build your app's primary user interface embedded in the Shopify admin.  If the prompt just mentions `Polaris` and you can't tell based off of the context what API they… |
| `shopify-polaris-checkout-extensions` | Build custom functionality that merchants can install at defined points in the checkout flow, including product information, shipping, payment, order summary, and Shop… |
| `shopify-polaris-customer-account-extensions` | Build custom functionality that merchants can install at defined points on the Order index, Order status, and Profile pages in customer accounts.  Customer Account UI… |
| `shopify-pos-ui` | Build retail point-of-sale applications using Shopify's POS UI components.  These components provide a consistent and familiar interface for POS applications. |
| `shopify-storefront-graphql` | Use for custom storefronts requiring direct GraphQL queries/mutations for data fetching and cart operations.  Choose this when you need full control over data fetching and… |
| `shopify-use-shopify-cli` | toml`); run or troubleshoot store workflows (`shopify store auth`, `shopify store execute`); inventory or product changes by handle, SKU, or location name; or CLI setup,… |

### Product & Market Research
*11 skills*

| Skill | What it gives the agent |
|---|---|
| `amazon-listing-expert` | Creates and optimizes Amazon product listings following proven high-conversion templates: '4+2' bullet points, 'X+1' image layout, and '1+8+1+8+1' A+ content structure.… |
| `bestseller-pattern-decoder` | Deconstructs the success patterns of Amazon Best Sellers — pricing sweet spots, image composition, title keyword structures, and A+ content narrative logic.  Use when… |
| `customer-voice-analyzer` | Mines customer reviews into 6 actionable dimensions — personas, scenarios, pros, cons, unmet needs, and buying motives.  Use when analyzing Amazon product reviews to… |
| `etsy-seo-optimizer` | Optimizes Etsy listing SEO using eRank data and Etsy search algorithm best practices.  Covers keyword research, title/tag construction, and continuous performance monitoring. |
| `jungle-scout-deep-dive-analyzer` | Jungle Scout API-powered deep market analysis for Amazon product selection.  Uses real keyword data, competitor metrics, trend history, and brand share data to compute an… |
| `market-insight-product-selection` | Adaptive product-selection methodology built on multi-source signals and voice of customer (VoC): validate demand, momentum, competitive intensity, and user pain points… |
| `market-viability-logic-auditor` | Evaluates cross-platform product/market feasibility using a risk-first framework — screens for exclusion filters, validates market thresholds, and audits profitability. ). |
| `product-attribute-analyzer` | Profiles product attributes across top sellers using 3-D tagging (structural/fit, material/process, design elements), calculates sales-weighted market share from real… |
| `scenario-driven-product-scout` | Discovers product ideas using the 'Three Shopping Moments' framework (Calendar / Life / Everyday) combined with 20 differentiation strategies.  Generates beginner-friendly… |
| `tech-pack-generation` | Generate production-ready tech pack with technical annotations for an EXISTING product image.  Use ONLY when user explicitly requests tech pack / technical drawing / spec… |
| `trend-stage-timing-analyzer` | Determines whether a product is in early growth, peak momentum, or saturation by analyzing ad libraries (TikTok, Facebook), Google Trends, and marketplace traction.  Use… |

### Desktop, Media & Utility
*54 skills*

| Skill | What it gives the agent |
|---|---|
| `1password` | Set up and use 1Password CLI (op).  Use when installing the CLI, enabling desktop app integration, signing in (single or multi-account), or reading/injecting/running… |
| `ai-product-designer` | Product development workflow with design image generation.  Use when user explicitly requests design images, design proposals, or product visualization. |
| `apple-notes` | Manage Apple Notes via the `memo` CLI on macOS (create, view, edit, delete, search, move, and export notes).  Use when a user asks OpenClaw to add a note, list notes,… |
| `apple-reminders` | Manage Apple Reminders via the `remindctl` CLI on macOS (list, add, edit, complete, delete).  Supports lists, date filters, and JSON/plain output. |
| `bear-notes` | Create, search, and manage Bear notes via grizzly CLI. |
| `blogwatcher` | Monitor blogs and RSS/Atom feeds for updates using the blogwatcher CLI. |
| `blucli` | BluOS CLI (blu) for discovery, playback, grouping, and volume. |
| `bluebubbles` | Use when you need to send or manage iMessages via BlueBubbles (recommended iMessage integration).  Calls go through the generic message tool with channel="bluebubbles". |
| `camsnap` | Capture frames or clips from RTSP/ONVIF cameras. |
| `canvas` | Display HTML content on connected OpenClaw nodes (Mac app, iOS, Android). |
| `clawhub` | com.  Use when you need to fetch new skills on the fly, sync installed skills to latest or a specific version, or publish new/updated skill folders with the npm-installed… |
| `coding-agent` | Run Codex CLI, Claude Code, OpenCode, or Pi Coding Agent via background process for programmatic control. |
| `discord` | Discord ops via the message tool (channel=discord). |
| `eightctl` | Control Eight Sleep pods (status, temperature, alarms, schedules). |
| `food-order` | Reorder Foodora orders + track ETA/status with ordercli.  Never confirm without explicit user approval. |
| `gemini` | Gemini CLI for one-shot Q&A, summaries, and generation. |
| `gifgrep` | Search GIF providers with CLI/TUI, download results, and extract stills/sheets. |
| `github` | Interact with GitHub using the `gh` CLI.  Use `gh issue`, `gh pr`, `gh run`, and `gh api` for issues, PRs, CI runs, and advanced queries. |
| `gog` | Google Workspace CLI for Gmail, Calendar, Drive, Contacts, Sheets, and Docs. |
| `goplaces` | Query Google Places API (New) via the goplaces CLI for text search, place details, resolve, and reviews.  Use for human-friendly place lookup or JSON output for scripts. |
| `healthcheck` | Host security hardening and risk-tolerance configuration for OpenClaw deployments.  Use when a user asks for security audits, firewall/SSH/update hardening, risk posture,… |
| `himalaya` | CLI to manage emails via IMAP/SMTP.  Use `himalaya` to list, read, write, reply, forward, search, and organize emails from the terminal. |
| `imsg` | iMessage/SMS CLI for listing chats, history, watch, and sending. |
| `logo-design` | End-to-end logo design workflow: brand understanding → competitor analysis → logo generation → design assets.  Use when user requests logo or brand identity design ('Make… |
| `mcporter` | Use the mcporter CLI to list, configure, auth, and call MCP servers/tools directly (HTTP or stdio), including ad-hoc servers, config edits, and CLI/type generation. |
| `model-usage` | Use CodexBar CLI local cost usage to summarize per-model usage for Codex or Claude, including the current (most recent) model or a full model breakdown.  Trigger when… |
| `nano-banana-pro` | Generate or edit images via Gemini 3 Pro Image (Nano Banana Pro). |
| `nano-pdf` | Edit PDFs with natural-language instructions using the nano-pdf CLI. |
| `notion` | Notion API for creating and managing pages, databases, and blocks. |
| `obsidian` | Work with Obsidian vaults (plain Markdown notes) and automate via obsidian-cli. |
| `openai-image-gen` | Batch-generate images via OpenAI Images API. html` gallery. |
| `openai-whisper` | Local speech-to-text with the Whisper CLI (no API key). |
| `openai-whisper-api` | Transcribe audio via OpenAI Audio Transcriptions API (Whisper). |
| `openhue` | Control Philips Hue lights/scenes via the OpenHue CLI. |
| `oracle` | Best practices for using the oracle CLI (prompt + file bundling, engines, sessions, and file attachment patterns). |
| `ordercli` | Foodora-only CLI for checking past orders and active order status (Deliveroo WIP). |
| `peekaboo` | Capture and automate macOS UI with the Peekaboo CLI. |
| `remotion-best-practices` | Best practices for Remotion - Video creation in React |
| `sag` | ElevenLabs text-to-speech with mac-style say UX. |
| `session-logs` | Search and analyze your own session logs (older/parent conversations) using jq. |
| `sherpa-onnx-tts` | Local text-to-speech via sherpa-onnx (offline, no cloud) |
| `skill-creator` | Create or update AgentSkills.  Use when designing, structuring, or packaging skills with scripts, references, and assets. |
| `slack` | Use when you need to control Slack from OpenClaw via the slack tool, including reacting to messages or pinning/unpinning items in Slack channels or DMs. |
| `songsee` | Generate spectrograms and feature-panel visualizations from audio with the songsee CLI. |
| `sonoscli` | Control Sonos speakers (discover/status/play/volume/group). |
| `spotify-player` | Terminal Spotify playback/search via spogo (preferred) or spotify_player. |
| `summarize` | Summarize or extract text/transcripts from URLs, podcasts, and local files (great fallback for “transcribe this YouTube/video”). |
| `things-mac` | Manage Things 3 via the `things` CLI on macOS (add/update projects+todos via URL scheme; read/search/list from the local Things database).  Use when a user asks OpenClaw… |
| `tmux` | Remote-control tmux sessions for interactive CLIs by sending keystrokes and scraping pane output. |
| `trello` | Manage Trello boards, lists, and cards via the Trello REST API. |
| `video-frames` | Extract frames or short clips from videos using ffmpeg. |
| `voice-call` | Start voice calls via the OpenClaw voice-call plugin. |
| `wacli` | Send WhatsApp messages to other people or search/sync WhatsApp history via the wacli CLI (not for normal user chats). |
| `weather` | Get current weather and forecasts (no API key required). |

---

## 7. Integrations — 56 platforms

Tenpo reads from and (where permitted) writes to:

**Storefronts & marketplaces** — Shopify · WooCommerce · BigCommerce · Magento · Squarespace · Wix · Saleor · Medusa · Amazon · Etsy · eBay · TikTok Shop

**Ads** — Meta Ads · Google Ads · TikTok Ads · Pinterest Ads · Snapchat Ads · LinkedIn Ads

**Email / SMS** — Klaviyo · Mailchimp · Omnisend · Postscript · Attentive · Resend · Twilio · WhatsApp

**Support & reviews** — Zendesk · Gorgias · Intercom · Freshdesk · Judge.me · Okendo · Yotpo · Trustpilot

**Money** — Stripe · QuickBooks · Xero

**Shipping** — Shippo · ShipStation · AfterShip

**CRM & sales** — HubSpot · Salesforce · Pipedrive

**Work & comms** — Slack · Discord · Telegram · Notion · Monday · Asana · Trello · ClickUp · Airtable · GitHub · Google Suite · Google Analytics

**Sourcing** — Alibaba

Plus a **custom REST connector** — any API with a URL and a key, and inbound webhook endpoints Tenpo generates for you.

---

## 8. The Safety Model

This is what makes the autonomy usable rather than terrifying.

| Guarantee | How |
|---|---|
| **Nothing customer-facing sends itself** | Every email, SMS, review reply and support message is drafted and queued for a tap. |
| **Nothing irreversible fires alone** | Cancels, refunds, price changes and de-stocking are approval-gated regardless of autonomy level. |
| **Spend is capped** | Purchase orders over a threshold (default $2,500) always wait for the merchant. |
| **Actions are reversible where possible** | `tenpo_undo_last_fire` rolls back the last action; the oversell write is capped to what's actually sellable. |
| **Everything is on the record** | `tenpo_action_ledger` threads every action end to end — what fired, what it touched, what it was worth. |
| **Permissions are earned** | The autonomy ladder promotes the agent only on action types it has proven it gets right; `tenpo_autonomy_policy` is per-merchant and per-action. |
| **Claims are provable** | A grounding gate checks that every number traces back to real rows before it reaches the merchant. |
| **Data is isolated** | Each merchant gets their own database, their own memory, and their own credential vault. |

---

## What Tenpo is *not*

Worth saying plainly:

- It does **not** place supplier orders on its own — it prepares them and emails them to you.
- It does **not** email your customers or reviewers without approval.
- It does **not** move money.
- It does **not** invent numbers — if the data isn't there, it says the data isn't there.
- It can only see the channels you've actually connected.
