<div align="center">
<img src="nokto-logo.svg" alt="Nokto" width="360"/>
</div>

**Limits enforced in code, not in prompts.**

Open infrastructure for production AI that cannot exceed its mandate. Two rules run through every repository here: the model never holds the authority, and ambiguity is a rejection, not an assumption.

---

## Open source

| Repository | What it enforces | Tests | CI |
|---|---|---|---|
| [nokto-agent-orchestrator](https://github.com/noktohq/nokto-agent-orchestrator) | Coding tasks reach the repo only as a pull request a human merges: Claude plans → plan paths checked against scope → Codex or Claude implements in an isolated git worktree → model review (plus a second model when Claude implements or a major finding is raised, if that model is available) → the task's own test commands → secret-scanned push. The orchestrator runs its own processes as argv arrays with a hard timeout, never through a shell. Its own git commands cannot force-push, push to `main`, `reset`/`clean`, or mutate the repo root. Codex `danger-full-access` is rejected at config load. Audit log is redacted. Known gaps, documented in SECURITY.md: the implementer's diff is not checked against scope, and the implementing agent's own git use in the worktree is not filtered by the allowlist. | 95 (+1 live, skipped) | lint · format · typecheck · test · build · `pnpm audit` · gitleaks |
| [nokto-adk-pr-agent](https://github.com/noktohq/nokto-adk-pr-agent) | Gemini/ADK agent that inspects a GitHub repo read-only and emits a strictly validated task contract for the orchestrator. Tools outside a 6-tool read-only allowlist are denied in a `before_tool_callback`. Test commands with shell metacharacters are rejected. `mustPass` and `human_approval_required` are always true. Hackathon build; live deploy not verified. | 26 | ruff · codespell · ty · pytest |
| [haggle](https://github.com/noktohq/haggle) | A shopper's browser agent negotiates a price over WebMCP, at most 6 rounds. The floor is computed server-side and never serialized to the client. An LLM reply that does not quote the engine's number is discarded. The deal becomes a single-use, single-product discount code that expires in 48 h. Hackathon demonstrator. | 10 + smoke + 4 e2e | test · typecheck · HTTP smoke · Playwright |
| [nokto-ai-output-validator](https://github.com/noktohq/nokto-ai-output-validator) | Rejects LLM output before use: invalid or non-finite JSON, non-object roots, missing fields, wrong types (`bool` is not an `int`), type-aware enums, list item types, unfilled `{{PLACEHOLDER}}` tokens. The enrichment wrapper returns `None` instead of raising. Checks structure, not truth. | 106 | pytest |
| [nokto-shopify-sync-core](https://github.com/noktohq/nokto-shopify-sync-core) | SKU-based Shopify inventory and price sync. An unknown quantity is never written as 0. Duplicate SKUs are skipped as conflicts. Reads are retried a bounded number of times; writes are retried only on 429, and an unknown outcome is flagged. Dry-run blocks every non-GET at the HTTP layer. | 62 | pytest |
| [nokto-data-validator](https://github.com/noktohq/nokto-data-validator) | Schema validation of structured Markdown libraries. A file that matches no manifest rule is an error. Zero matched files exits 1. No runtime dependencies. | 17 | pytest |
| [nokto-integration-kit](https://github.com/noktohq/nokto-integration-kit) | MCP stdio proxy for the Shopify Catalog API. Size limits on every input and response, request timeouts, token refresh shared across callers, batches rejected, forwarded calls never retried. Errors never carry tokens, headers or upstream bodies. | 50 | `node --check` · `node --test` |

Test counts are test cases defined in each repo, with parametrized and looped cases expanded. The default CI run calls no paid model. Licences are in each repository.

## Private systems, same rules

| System | Status |
|---|---|
| EHF/Peppol invoicing for Shopify | Deployed. One invoice per order via a unique constraint. Invoice numbers come from a per-shop sequence written in the same transaction as the invoice, so a failed create leaves no gap. If the total does not reconcile with the Shopify order, no EHF is generated and the invoice stays a draft. Peppol sends and webhooks are idempotent. 142 unit tests; integration and end-to-end tests also run in CI. |
| Voice and chat agents | Agents and web chat deployed. The tool/webhook engine and outbound calling are built and tested, not yet in production. Agents, tools and evals are managed as code. Webhooks are HMAC-verified with a timestamp window, and rate limits apply per IP and per tenant. Outbound calling is blocked unless explicitly enabled and approved, outside legal calling hours and on public holidays, and, for consumers and sole proprietors, without a reservation-register check in the last 30 days. Recently contacted, reserved or blocked numbers are never called. Mutating control tools require an exact confirmation phrase. 123 tests. |
| Real-time sales-call coach | Prototype. The AI joins the customer's call through server-issued tokens that do not allow it to publish, so its audio cannot reach the customer. Sensitive fields are encrypted with AES-256-GCM, and retention is enforced per profile. |
| Bookkeeping and reconciliation | Tested, not in production. Journal entries must balance, and posted entries and audit events are immutable at the database level. Money is integer minor units, and mixing currencies throws. A user cannot approve their own correction. Audit logs are hash-chained. Postgres row-level security is forced. Unknown is reported as unknown, never as zero or as a discrepancy. |
| Order and payment verification | Tested, not deployed. Adapters are read-only by interface. A shop's own "paid" status never counts as proof of payment. Without an independent payment source the result is `UNKNOWN`. |
| EU cross-border compliance engine | Tested, not deployed. Only rule versions valid on the evaluation date apply. An unknown customs duty rate blocks the route instead of counting as 0. The audit trail is append-only and hash-chained. |
| Commerce operations | Partly deployed. Inventory sync aborts before writing if a plan would zero too many in-stock variants, and it treats stale source data as unknown. Each mutation carries its own idempotency key. Media publishing is gated on automated QC and uploads only the exact file QC approved, matched by SHA-256. |
| Mobile | Release build for Google Play. Plan quotas and rate limits are enforced server-side in Postgres, and deleting history does not reset them. |
| Ops tooling | Tested. Its stop command refuses to push from the default branch, and generated status snapshots reach main only through a pull request. Its prompt library and service registry are validated in CI. The desktop work-documentation app binds its API to loopback only, reads GitHub with GET only and makes nothing billable without an approval. |

## Rules

```
Secrets belong in environment variables.
Claims in each repo's README cite a test or are marked unverified.
Branch and pull request. Never directly to main.
No automatic merge.
```

[nokto.no](https://nokto.no) · [edin@nokto.no](mailto:edin@nokto.no) · [Sponsor](https://github.com/sponsors/noktohq)