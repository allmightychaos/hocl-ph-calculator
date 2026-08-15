## HOCl pH-calc

> [!IMPORTANT]
> This has been created with Claude Opus 5. 

Interactive single-file visualization of the pH dependence of chlorine disinfection
in swimming pool water. A pH controller (6.5–8.0) controls three graphs:

- **Species** – Proportion of HOCl (active form) vs. OCl⁻ (inactive form)
- **Disinfection Efficiency** - relative disinfection efficiency and contact time factor
- **Redox Potential** - model curve with uncertainty band and standard thresholds

Additional parameters: water temperature, free chlorine, HOCl:OCl⁻ activity ratio.

## Usage

Open `index.html` in a browser. No dependencies, no build, no server.
The only external resource is Google Fonts (optional; falls back to system fonts).

## Model

| Parameter | Basis |
|---|---|
| pKa(T) | Morris (1966), 3000/T − 10.0686 + 0.0253·T |
| HOCl fraction | Henderson-Hasselbalch |
| Active Power | W = f + (1−f)/k, normalized to pH 7.0 |
| Redox Potential | Nernst slope, level calibrated to 750 mV at pH 7.2 / 1.0 mg/L |

Standards: DIN 19643-1 and EN 16713.

## Limitations

The redox curve is **calibrated, not calculated absolutely** - actual Pt probes
show significantly lower values than thermodynamics
predicts due to the mixing potential. The change is meaningful, not the absolute value.

Not modeled: cyanuric acid (usually the dominant interfering factor in outdoor pools),
bound chlorine, chlorine consumption, UV degradation, and mixing.

For guidance only; not a substitute for measurement and maintenance.
