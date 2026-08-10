# Tenpo — status

**Updated 2026-08-07.** Every claim below is either measured or labelled unverified.

---

## What Tenpo is

An autonomous commerce operator for multi-channel merchants. It connects to a
merchant's stores, marketplaces, ad platforms and support tools; keeps a
per-merchant database in sync; answers questions about the business with real
numbers; watches for problems in the background; and takes action — with human
approval on anything irreversible.

---

## Where it stands

| Capability                                        | State                                                  |
| ------------------------------------------------- | ------------------------------------------------------ |
| Answers business questions from live data         | **Working — measured**                                 |
| Connects merchant apps (50 providers)             | **Working**                                            |
| Automatic data sync after connect                 | **Working — e2e simulated**                            |
| Multi-platform onboarding                         | **Working**                                            |
| Webhook ingest + signature verification           | **Working** (subscription registration pending)        |
| Background monitoring (44 scheduled jobs)         | **Working**                                            |
| Workflow creation, validation, dry-run, execution | **Working**                                            |
| Memory: store, recall, consolidate, forget        | **Working**                                            |
| Cascades (event → decide → act)                   | **Working**                                            |
| Approval gating on irreversible actions           | **Working**                                            |
| Approval cards surfaced in the UI                 | **In progress**                                        |
| One-command VPS deploy                            | **Built, not yet run on a server**                     |
| Multi-server architecture                         | **Routing + placement done; provisioning single-host** |

---

## Measured results

- **Answer quality:** 88.9% and 100% (customer ops), 91.7% and 75% (operations)
  — two runs each, through the real chat API.
- **Tool reliability:** 1,462 tool calls across 52 turns, 0.14% error rate.
- **Live agent turns** run end-to-end on Google Vertex AI.

## Verified by adversarial testing

Built a merchant fixture with 5,600 orders, 2,565 customers, 22 products, 11 ad
campaigns and 365 days of history, then attacked it:

- **"No data" and "couldn't read the data" stay distinguishable** — the property
  that decides whether a number is safe to act on.
- **Prompt injection through store content did not hijack the agent.**
- SQL metacharacters, unicode, a 2MB query, `DROP TABLE`, and non-existent
  columns all handled — bad reads surface as visible errors, never as a
  confident zero.
- 24 concurrent reads/writes on one merchant: zero lost rows. Concurrent
  cascades: consistent.
- Approvals cannot be bypassed; every irreversible action is gated and bound to
  its action class.

**Test suite:** ~14,000 tests. Typecheck clean across both projects.

---

## Architecture

- **Per-merchant isolation** — each merchant gets their own encrypted database
  and credential vault; no shared tables, no cross-tenant reads.
- **Per-merchant processes** — a gateway and runtime per merchant, so one
  merchant's load or corruption cannot affect another.
- **Provider-agnostic AI** — a fallback chain across Anthropic, Google Vertex,
  DeepSeek, NVIDIA and OpenRouter, with automatic failover on quota exhaustion.
- **215 domain playbooks, 200+ tools** — loaded on demand rather than held in
  the prompt.

---

## To public launch

**Engineering**

1. Run the deploy on a real server and verify — the script exists and dry-runs
   clean; it has not been executed against a host.
2. Register webhook subscriptions on connect (verification already works).
3. Finish surfacing approval cards and workflow failures in the UI.
4. Test coverage for signup.
5. Cross-host provisioning for the multi-server layer.

**Product decisions**

6. **Paywall placement** — merchants are currently asked to subscribe before
   seeing any data. Recommendation: allow entry with zero integrations, charge on
   first connect.
7. **Shopify OAuth** — a one-click install flow is fully implemented and inactive.
   Setting `SHOPIFY_CLIENT_ID` replaces a 7-step manual setup with a single
   button. Highest-leverage change available, and it is configuration, not code.

---

## Honest limits

Everything above was verified by automated tests and live probes **on a
development machine**. It has not run in production. The next milestone is one
real deployment with one real store — not more code.

Scale is architecturally sound but unproven above a handful of merchants: the
per-merchant process model puts roughly a dozen merchants on a box, so serving
thousands depends on the multi-server layer, which is partially built.
