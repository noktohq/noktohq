<div align="center">
<img src="https://raw.githubusercontent.com/noktohq/noktohq/chaos-main/mark.png" width="80" height="80" alt="Nokto" />
</div>

# Edin Nokto

**Operativ AI-infrastruktur. Én person. Fullt selskap.**

[![nokto.no](https://img.shields.io/badge/nokto.no-000?style=flat-square&logo=safari&logoColor=95BF47)](https://nokto.no) [![Email](https://img.shields.io/badge/edin@nokto.no-000?style=flat-square&logo=gmail&logoColor=95BF47)](mailto:edin@nokto.no)

---

```ts
const response = await nokto.run({
  model: "nokto-production",
  system: "Internt operativsystem for levering. Én jobb per motor. Ingen unntak.",
  messages: [{ role: "user", content: "Hva kjører nå?" }],
  // → Salg: scoring → åpningsmelding → intakeskjema → tilbud → kontrakt.
  // → Regnskap: bilag, MVA-melding og årsoppgjør mot NS4102. Alltid til menneskelig review.
  // → Brand, design, markedsføring og print — leveransemotorer, ikke maler.
  // → Shopify: catalog storefront, Vipps ePayment, launch checklist.
  //
  // Input inn. Ferdig dokument ut. CI blokkerer merge ved feil.
})
```

---

### Hva kjører

| Pipeline | Hva den leverer |
|----------|-----------------|
| Salg | Scoring, åpningsmelding, tilbud, kontrakt |
| Regnskap | Bilag, MVA-melding, årsoppgjør — NS4102, alltid til review |
| Brand | BrandVoice, Brandbook, CDN, Partner-kit, Pressekit |
| Markedsføring | Landingsside, e-postmal, OG/SEO, annonse-kreativ |
| Shopify | Catalog storefront, Vipps ePayment, launch checklist |

---

### Stack

- **Primær IDE:** Claude Code — eksekvering og leveranse
- **Validering:** Python 3.14 — CI validerer alle motorer ved push
- **MCP:** Node.js — servere per integrasjon
- **E-handel:** Shopify Admin REST API 2026-01
- **CI:** GitHub Actions — blokkerer merge ved feil

---

**→ edin@nokto.no**
