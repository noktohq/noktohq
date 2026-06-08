<div align="center">
<img src="https://raw.githubusercontent.com/noktohq/noktohq/chaos-main/mark.png" width="80" height="80" alt="Nokto" />
</div>

# Nokto

Edin Nokto

**Operativ AI-infrastruktur. 1 person. Full leveransemotor.**

Internt operativsystem for levering.<br>
Bygget for fart, presisjon, kontroll og repeterbar output.

Ikke promptkaos.<br>
Ikke tilfeldige maler.<br>
Ikke manuell hukommelse.

Router velger riktig motor.<br>
Domeneregler styrer output.<br>
Validator stopper mangler.<br>
Quality gate blokkerer svak leveranse.<br>
CI stopper feil før merge.

Input inn.<br>
Ferdig leveranse ut.

[nokto.no](https://nokto.no) · [edin@nokto.no](mailto:edin@nokto.no)

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
| Salg | Scoring, åpningsmeldinger, intake, tilbud og kontrakt |
| Regnskap | Bilag, MVA, årsoppgjør og review |
| Brand | BrandVoice, brandbook, partner-kit og pressekit |
| Design | Tokens, designsystem, WCAG og microcopy |
| Markedsføring | Landingssider, OG/SEO, e-post og annonser |
| Shopify | Produktflyt, katalog, launch og Vipps ePayment |
| B2B-synk | Merida, Ecoride og CSN til Shopify |
| System | Router, validator, quality gate og CI |

## Regler

```
En jobb per motor.
Strukturert input.
Ferdig output.
Dry-run før mutasjon.
Menneskelig review der risiko krever det.
CI stopper feil før merge.
```
