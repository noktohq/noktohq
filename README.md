<div align="center">
<img src="https://raw.githubusercontent.com/noktohq/noktohq/chaos-main/mark.png" width="80" height="80" alt="Nokto" />
</div>

# Nokto

Edin Nokto · [nokto.no](https://nokto.no) · [edin@nokto.no](mailto:edin@nokto.no)

**Operativ AI-infrastruktur for en person som leverer som et helt selskap.**

Internt operativsystem for levering. Bygget for fart, presisjon, kontroll og repeterbar output. Ikke promptkaos. Ikke tilfeldige maler. Ikke manuell hukommelse. Router velger riktig motor. Domeneregler styrer output. Validator stopper mangler. Quality gate blokkerer svak leveranse. CI stopper feil før merge. Input inn. Ferdig leveranse ut.

```ts
const response = await nokto.run({
  operator: "Edin Nokto",
  mode: "production",
  system: "Operativ AI-infrastruktur for levering.",
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

```
En jobb per motor.
Strukturert input.
Ferdig output.
Dry-run for mutasjon.
Menneskelig review der risiko krever det.
CI stopper feil før merge.
```
