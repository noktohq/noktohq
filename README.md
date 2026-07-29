<div align="center">
<img src="nokto-logo.svg" alt="Nokto" width="360"/>
</div>

# Edin Nokto

Fullstack- og AI-utvikler. Bygger produksjonssystemer og AI-infrastruktur for e-handel, betaling og drift.

[nokto.no](https://nokto.no) · [edin@nokto.no](mailto:edin@nokto.no)

---

## Nokto

Nokto er selskapet — ett menneske, egen kodebase for hvert prosjekt. Ingen fellesplattform som "gjør alt"; hvert repo har ett avgrenset formål.

## Nokto OPS

Nokto OPS er den private operative infrastrukturen som driver Noktos egne leveranser og klientdrift: B2B-lagersynkronisering mot Shopify, et bibliotek av strukturerte AI-arbeidsflyter for salg/regnskap/design/markedsføring, og en multi-agent-orkestrator som kobler Claude Code og OpenAI Codex sammen for kodelevering — med git-worktree-isolasjon, testdekning og pull request-basert leveranse, aldri automatisk merge. Koden er privat; se de offentlige prosjektene under for konkrete eksempler på kvalitetsnivå og arbeidsmåte.

## Offentlige prosjekter

Små, avgrensede verktøy — ikke plattformer. Hver har egen README, egen CI og egen testsuite.

| Prosjekt | Hva det gjør | Stack |
|---|---|---|
| [nokto-ai-output-validator](https://github.com/noktohq/nokto-ai-output-validator) | Validerer strukturert JSON-output fra LLM-kall mot et deklarert skjema — påkrevde felt, typer, enum-verdier, uutfylte placeholders | Python |
| [nokto-data-validator](https://github.com/noktohq/nokto-data-validator) | Avhengighetsfri validator for strukturerte Markdown-biblioteker mot deklarerte skjemaer | Python |
| [nokto-shopify-sync-core](https://github.com/noktohq/nokto-shopify-sync-core) | Generisk Shopify Admin REST-klient for lager- og prissynkronisering fra eksterne kilder, matchet på SKU | Python |
| [nokto-integration-kit](https://github.com/noktohq/nokto-integration-kit) | MCP stdio-proxy mot Shopifys Catalog MCP-endepunkt, med OAuth-tokenhåndtering | Node.js |

## Kvalitet, sikkerhet og testing

- Alle prosjekter over har egen testsuite som kjøres i CI ved push og pull request — ingen påstand om testdekning uten faktiske tester bak.
- Hemmeligheter leses utelukkende fra miljøvariabler, aldri hardkodet i kildekode.
- Endringer går via branch og pull request — ingen direkte push til hovedbranch, ingen automatisk merge.
- Standard stack: TypeScript/Node.js (pnpm) og Python, med ESLint/Prettier/Vitest eller pytest og GitHub Actions CI, avhengig av prosjekt.

## Kontakt

[nokto.no](https://nokto.no) · [edin@nokto.no](mailto:edin@nokto.no)
