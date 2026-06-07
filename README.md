<div align="center">
<img src="https://raw.githubusercontent.com/noktohq/noktohq/chaos-main/mark.png" width="80" height="80" alt="Nokto" />
</div>

# Edin Nokto

**Drifter ett selskap med AI. Én person. Ingen manuell formatering.**

[![nokto.no](https://img.shields.io/badge/nokto.no-000?style=flat-square&logo=safari&logoColor=95BF47)](https://nokto.no) [![Email](https://img.shields.io/badge/edin@nokto.no-000?style=flat-square&logo=gmail&logoColor=95BF47)](mailto:edin@nokto.no)

---

```ts
const response = await nokto.run({
  model: "nokto-production",
  system: "Du er Edin Nokto. Én person. Fullt operativt selskap.",
  messages: [{ role: "user", content: "Hva produserer systemet?" }],
  // → Salg: scoring → kald kontakt → inntaksskjema → tilbud → kontrakt.
  // → Regnskap: MVA-melding og årsoppgjer mot NS4102. Alltid til menneskelig review.
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
| Salg | Scoring, kald kontakt, tilbud, kontrakt |
| Regnskap | MVA-melding, årsoppgjer — NS4102, alltid til review |
| Brand | BrandVoice, Brandbook, CIM, Pressekit |
| Markedsføring | Landingsside, e-postmal, OG/SEO, annonse-kreativ |
| Shopify | Catalog storefront, Vipps ePayment, launch checklist |

---

### Stack

- **Primær IDE:** Claude Code
- **Validering:** Python — CI validerer alle motorer ved push
- **Integrasjoner:** Shopify Admin API 2026-01, Vipps ePayment, MCP-servere
- **CI:** GitHub Actions — blokkerer merge ved feil

---

**→ edin@nokto.no**
