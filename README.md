<div align="center">
<img src="nokto-logo.svg" alt="Nokto" width="360"/>
</div>

**Edin Nokto** — Fullstack- og AI-utvikler.

Produksjonssystemer. AI-infrastruktur. E-handel, betaling og drift.

---

## Nokto OPS

Privat operativ infrastruktur. Driver Noktos leveranser og klientdrift.

| System | Status |
|---|---|
| B2B-lagersynk → Shopify | Daglig drift, automatisert |
| AI-arbeidsflyter — salg, regnskap, design, markedsføring | Aktiv |
| Multi-agent-orkestrator — Claude Code + Codex | Testet, PR-basert, aldri auto-merge — [åpen kildekode](https://github.com/noktohq/nokto-agent-orchestrator) |
| EHF/Peppol-fakturering for Shopify | Produksjon |

## Åpen kildekode

| Prosjekt | Gjør | Stack |
|---|---|---|
| [nokto-agent-orchestrator](https://github.com/noktohq/nokto-agent-orchestrator) | AI-agenter som leverer kode via PR — worktree-isolasjon, allowlist, hemmelighetsskann | TypeScript |
| [nokto-ai-output-validator](https://github.com/noktohq/nokto-ai-output-validator) | Validerer LLM-output mot skjema før bruk | Python |
| [nokto-data-validator](https://github.com/noktohq/nokto-data-validator) | Skjemavalidering av strukturerte Markdown-biblioteker | Python |
| [nokto-shopify-sync-core](https://github.com/noktohq/nokto-shopify-sync-core) | Lager- og prissynk mot Shopify Admin API, per SKU | Python |
| [nokto-integration-kit](https://github.com/noktohq/nokto-integration-kit) | MCP-proxy for Shopify Catalog med OAuth | Node.js |

Egen testsuite og CI i hvert prosjekt.

## Regler

```
Hemmeligheter kun i miljøvariabler.
Ingen påstand uten tester bak.
Branch og pull request. Aldri direkte til main.
Ingen automatisk merge.
```

[nokto.no](https://nokto.no) · [edin@nokto.no](mailto:edin@nokto.no)
