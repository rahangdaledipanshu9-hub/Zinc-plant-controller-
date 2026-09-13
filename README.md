# ZnO Recovery — JAMP Industries

Interactive batch-control guides for zinc oxide recovery from zinc ash.

| File | What it is |
|---|---|
| `index.html` | Plant line, chloride route. Ten stages from ST-1 through to packing, with equipment tags, vessel utilisation checks and mass balance. |
| `lab-protocol.html` | Lab-scale sulfate route. Ten steps from hot-water dechlorination through to calcination. |

Both are single self-contained HTML files. No build step, no dependencies to install — open the file in a browser, or push the repo and serve it.

## Publishing on GitHub Pages

1. Push these files to the repository root.
2. Repository → **Settings** → **Pages**.
3. Under *Build and deployment*, set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save. The site appears at `https://<username>.github.io/<repo>/` within a minute or two.

`index.html` is served automatically at the root. The lab protocol is at `/lab-protocol.html`.

## Using it

Both pages open on a setup screen. Enter the batch charge and, if you have it, the XRF assay. Every downstream quantity — reagents, water, cake weights, expected yield — rescales from those two inputs. Then work through the stages; timed holds run a countdown, manual actions advance on a button.

The **demo speed** control in the header compresses the hold timers so a full batch can be walked through in a presentation.

## Calculation sheet

`index.html` carries the full ZnO process calculator in the **Calculation sheet** panel: process inputs, process analysis, reagents required, theoretical products, yield efficiency against a measured result, a session batch log and a printable report.

Every quantity is derived stoichiometrically from the moles of ZnO in the charge rather than scaled from a fixed recipe, so it stays correct at any batch size and any ash grade:

```
ZnO + 2HCl  → ZnCl₂ + H₂O
ZnCl₂ + 2NaOH → Zn(OH)₂ + 2NaCl
Zn(OH)₂ → ZnO + H₂O
```

Two plant ratios are carried over unchanged from the 866 kg reference batch:

| Ratio | Basis |
|---|---|
| Process water | 13,995.51 L / 866 kg = 16.1611 L per kg of ash |
| Hydrogen peroxide | 216.50 L / 866 kg = 0.2500 L per kg of ash |

HCl solution density is taken as 1.20 kg/L at every strength. The acid charge is shown both stoichiometrically and with the 10% working excess actually dosed; caustic carries 5%.

## Note on the numbers

Reagent demand, theoretical products and the water and peroxide ratios are calculated. Recovery is banded at 83.2–90% of theory — the lower bound reproduces the 500 kg of ZnO marked on the flowsheet for an 866 kg charge. Cycle times, the water split across the circuit and the sludge estimate are indicative. Confirm them against plant records before operational use.

Internet access is needed once on first load for the Google Fonts stylesheet; the pages fall back to system fonts without it.
