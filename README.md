<div align="center">
<img src="nokto-logo.svg" alt="Nokto" width="360"/>
</div>


Edin Nokto

**Operativ AI-infrastruktur. En person. Komplett leveransemotor.**

Internt operativsystem for levering. Bygget for fart, presisjon, kontroll og repeterbar output — ikke promptkaos, ikke tilfeldige maler, ikke manuell hukommelse. Router velger riktig motor. Domeneregler styrer output. Validator stopper mangler. Quality gate blokkerer svak leveranse. CI stopper feil før merge. Input inn. Ferdig leveranse ut.

```ts
const response = await nokto.run({
  mode: "production",
  input: "Hva skal leveres?",
  route: {
    project: "auto",
    task: "auto",
    engine: "required",
  },
  gates: ["validator", "quality-gate", "ci"],
});

// En person.
// Mange motorer.
// Ingen output uten kontroll.
```

## Hva kjører

| Pipeline | Leveranse |
|---|---|
| Salg | Scoring, åpningsmeldinger, intakeskjema, tilbud og kontrakt |
| Regnskap | Bilag, MVA, årsoppgjør og kontroll |
| Brand | BrandVoice, brandbook, partner-kit og pressekit |
| Design | Designtokens, designsystem, WCAG og microcopy |
| Markedsføring | Landingssider, OG/SEO, e-post og annonser |
| Shopify | Produktflyt, katalog, lansering og Vipps-betaling |
| Datasynk | Leverandørdata, lager, priser, produkter og drift inn i ett system |
| System | Router, validator, quality gate og CI |

## Regler

```
En jobb per motor.
Strukturert input.
Ferdig output.
Dry-run før mutasjon.
Menneskelig kontroll der risiko krever det.
CI stopper feil før merge.
```

[nokto.no](https://nokto.no) · [edin@nokto.no](mailto:edin@nokto.no)
