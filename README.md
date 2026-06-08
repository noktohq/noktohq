<div align="center">
<img src="https://raw.githubusercontent.com/noktohq/noktohq/chaos-main/mark.png" width="80" height="80" alt="Nokto" />
</div>

# Nokto

Edin Nokto · [nokto.no](https://nokto.no) · [edin@nokto.no](mailto:edin@nokto.no)

**Operativ AI-infrastruktur for en person som leverer som et helt selskap.**

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
