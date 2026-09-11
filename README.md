<div align="center">
<img src="nokto-logo.svg" alt="Nokto" width="360"/>
</div>

**Limits enforced in code, not in prompts.**

Open infrastructure for production AI that cannot exceed its mandate. Two rules run through every repository here: the model never holds the authority, and ambiguity is a rejection, not an assumption.

---

## Open source

| Repository | What it enforces | Tests | CI |
|---|---|---|---|
| [nokto-agent-orchestrator](https://github.com/noktohq/nokto-agent-orchestrator) | Claude Code, Codex and Gemini deliver code only through a pull request: plan → static scope check → isolated git worktree → review by a second model → allowlisted test commands → secret-scanned push. Never merges. Processes are spawned as argv arrays, never through a shell. Append-only JSONL audit log with secret redaction. | 95 | lint · format · typecheck · test · build · `pnpm audit` · gitleaks |
| [nokto-adk-pr-agent](https://github.com/noktohq/nokto-adk-pr-agent) | Gemini/ADK control plane that turns a request into a validated task contract for the orchestrator. Tools outside a read-only allowlist are blocked in a `before_tool_callback`. Human approval is always required and auto-merge is always false, in code. Hackathon build, 2026-08. | 26 | ruff · codespell · ty · pytest |
| [haggle](https://github.com/noktohq/haggle) | An LLM negotiates a price over WebMCP on a Shopify development store. The floor is computed and clamped in a deterministic engine and never serialized to the client. A phrased reply that does not quote the authoritative number is discarded. Hackathon demonstrator. | 10 + smoke + 4 e2e | test · typecheck · HTTP smoke · Playwright |
| [nokto-ai-output-validator](https://github.com/noktohq/nokto-ai-output-validator) | Rejects LLM output before use: invalid JSON, missing fields, wrong types, enum violations, unfilled `{{PLACEHOLDER}}` tokens. Checks structure, not truth. | 11 | pytest |
| [nokto-shopify-sync-core](https://github.com/noktohq/nokto-shopify-sync-core) | Shopify Admin client for SKU-based inventory and price sync. Honours `Retry-After` on 429, cursor pagination, OAuth client-credentials tokens. | 8 | pytest |
| [nokto-data-validator](https://github.com/noktohq/nokto-data-validator) | Schema validation of structured Markdown libraries. No runtime dependencies. | 6 | pytest |
| [nokto-integration-kit](https://github.com/noktohq/nokto-integration-kit) | MCP stdio proxy for the Shopify Catalog API with OAuth token refresh and request timeouts. | none yet | `node --check` |

All MIT. Test counts are from the suites as they run offline in CI; none of them call a paid model.

## Private systems, same rules

| System | Status |
|---|---|
| EHF/Peppol invoicing for Shopify | Deployed. Audit table, idempotent HMAC-verified webhooks, AES-256-GCM field encryption, mock Peppol provider refused in production. 51 unit and 8 end-to-end tests. |
| Multi-agent orchestrator | Tested, PR-based, never auto-merged. Public: see above. |
| B2B supplier sync → Shopify | Automated. Rate-limited shared Shopify client. |
| AI workflows for sales, accounting, design, marketing | Active. Prompt library validated in CI. |

## Rules

```
Secrets only in environment variables.
No claim without a test behind it.
Branch and pull request. Never directly to main.
No automatic merge.
```

[nokto.no](https://nokto.no) · [edin@nokto.no](mailto:edin@nokto.no) · [Sponsor](https://github.com/sponsors/noktohq)
