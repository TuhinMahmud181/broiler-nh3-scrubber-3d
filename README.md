# Broiler NH₃ acid scrubber: 3D simulation

An interactive 3D simulation of ammonia (NH₃) capture from broiler-house exhaust with a sulphuric-acid spray scrubber, run as a continuous process over a 49-day flock.

**Live page:** https://tuhinmahmud181.github.io/broiler-nh3-scrubber-3d/

## What it shows

- A tunnel-ventilated broiler house (25,000 birds) with evaporative inlet pads, 8 exhaust fans, feeder and drinker lines, and birds that grow from chick to market weight.
- The exhaust plenum, the untreated bypass that opens when airflow exceeds scrubber capacity, and a bank of spray scrubber modules with mist eliminators.
- The liquid loop: sump, recirculation tank and pump at pH 3, sulphuric-acid dosing, make-up water, and draw-off of ammonium sulphate solution to a product tank.
- Live readouts, flock charts, the reaction and mass-transfer steps, and a stream table of the 8 process streams.

Controls: season (cold, mild, hot), number of spray modules, spray stages, nozzle pressure, and bird age (play or drag).

## Model

The calculations port the spray-scrubber part of `nh3_model.m` (version 9) from the companion repository [nh3-broiler-scrubber](https://github.com/TuhinMahmud181/nh3-broiler-scrubber):

- **Emission:** 0.031 g NH₃ per bird per day per day of age, on built-up litter (Wheeler et al., 2006; Gates et al., 2008).
- **Ventilation:** flock-average airflow by season, with the daily shape digitised from Moore et al. (2011), Fig. 2A.
- **Scrubber:** module geometry (0.356 m column, 1.65 m contact height, 4 m/s maximum velocity), PJ40 nozzle data and the Kya correlation of Hadlocon et al. (2015c), with removal efficiency η = 1 − exp(−Kya·z/G).
- **Mass balance:** 2 NH₃ + H₂SO₄ → (NH₄)₂SO₄, with product drawn off at 3 mol N/L (about 200 g/L ammonium sulphate).

With the base design (30 modules × 3 stages at 0.62 MPa), the page reproduces the flock-weighted capture reported in the paper: US 68.2%, Gulf 44.3%, developing country 45.9%.

The 3D drawing shows the plant schematically. The house is drawn shorter than a real 155 m house, one bird stands for about 23, and bird size follows an approximate broiler growth curve (about 40 g at hatch to 2.5 kg at day 49).

## Running it

Open `index.html` in any modern browser, or use the live page. It needs an internet connection to load three.js 0.128 and the Barlow fonts from public CDNs; there is no build step.

## Citation

Mahmud, T., & Sarker, S. (2026). *Recovering ammonia from broiler-house exhaust as ammonium sulphate: a model-based design, cost and uncertainty analysis for three climates.* Manuscript submitted for publication.

## Licence

MIT
