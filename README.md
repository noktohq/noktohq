<div align="center">
<img src="https://raw.githubusercontent.com/noktohq/noktohq/chaos-main/mark.png" width="80" height="80" alt="Nokto" />
</div>

# Nokto

Edin Nokto

**Operativ AI-infrastruktur for en person som leverer som et helt selskap.**

Internt operativsystem for levering. Bygget for fart, presisjon, kontroll og repeterbar output — ikke promptkaos, ikke tilfeldige maler, ikke manuell hukommelse. Router velger riktig motor. Domeneregler styrer output. Validator stopper mangler. Quality gate blokkerer svak leveranse. CI stopper feil før merge. Input inn. Ferdig leveranse ut.

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

## Regler

```
En jobb per motor.
Strukturert input.
Ferdig output.
Dry-run for mutasjon.
Menneskelig review der risiko krever det.
CI stopper feil før merge.
```
