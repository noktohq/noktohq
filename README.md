<div align="center">
  <img src="nokto-logo.svg" alt="NOKTO" width="300" />
</div>

# NOKTO

**BUILD THE SYSTEM. VERIFY THE RESULT.**

Full-stack engineering for commerce, financial workflows and AI agents. Shopify and B2B, EHF/Peppol invoicing, inventory synchronization, payment verification, developer tooling and controlled agent delivery.

From storefront to ledger. From agent task to reviewed pull request. From reported success to evidence.

## Code you can inspect

| Project | What the code actually does |
|---|---|
| [Agent Orchestrator](https://github.com/noktohq/nokto-agent-orchestrator) | Plans, implements, reviews and tests code in isolated worktrees. Humans merge the PRs. [Known limits are documented](https://github.com/noktohq/nokto-agent-orchestrator/blob/main/SECURITY.md). |
| [ADK PR Agent](https://github.com/noktohq/nokto-adk-pr-agent) | Uses read-only GitHub inspection to produce validated task contracts. |
| [Shopify Sync Core](https://github.com/noktohq/nokto-shopify-sync-core) | Syncs inventory and prices; unknown stock is never silently written as zero. |
| [AI Output Validator](https://github.com/noktohq/nokto-ai-output-validator) | Validates LLM output structure before use. Does not claim to verify truth or safety. |
| [Integration Kit](https://github.com/noktohq/nokto-integration-kit) | Bounded Shopify Catalog MCP proxy with controlled token refresh and timeouts. |
| [Haggle](https://github.com/noktohq/haggle) | WebMCP price negotiation with server-enforced limits and single-use discounts. |
| [Spoke](https://github.com/noktohq/spoke) | Bike-care prototype with a tested, tier-limited subscription negotiation engine. |
| [Data Validator](https://github.com/noktohq/nokto-data-validator) | Schema validation for structured Markdown libraries. |

## Beyond public source code

**Deployed or operated, according to project documentation:** Shopify commerce systems, EHF/Peppol invoicing, business websites, and voice/chat agents.

**Public Windows release:** [DEVPROOF](https://github.com/noktohq/nokto-devproof-download/releases/latest) turns local development activity and GitHub delivery evidence into traceable project documentation. Its source repository is private.

**Tested, not presented as production:** NOKTO ZERO, MONEYGUARD, DONE, ONE, an EU commerce compliance engine, and the TIDEL beta. Integration and live-readiness gaps are documented in their projects.

## The engineering standard

**Unknown is not zero. A store's “paid” flag is not independent payment proof. Valid JSON is not verified truth. A generated patch is not a delivered change.**

Permissions, test gates, audit trails and failure states belong in code. Limitations belong in the documentation.

[NOKTO](https://nokto.no) · [DEVPROOF releases](https://github.com/noktohq/nokto-devproof-download/releases/latest) · [Contact](mailto:edin@nokto.no)
