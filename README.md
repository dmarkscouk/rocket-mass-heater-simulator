# Rocket Mass Heater Simulator

A single-page 3D tool for sketching a rocket mass heater and seeing how it performs.
Try it at **https://dmarkscouk.github.io/rocket-mass-heater-simulator/**, or open
`rocket-mass-heater-simulator.html` in a browser; there is nothing to build or install.

Every push to `main` redeploys the site. The workflow in `.github/workflows/pages.yml` wraps the
simulator in the document shell from `.github/pages/head.html` to make `index.html`.

## What you can do

- Paint thermal mass (cob, brick, granite, concrete, sand) and insulation blocks on a 25 cm grid,
  as whole columns or stacked 15 cm blocks, up to 1.8 m tall. Shift-click deletes.
- Route the flue from the drum through the bench; the last cell is where the chimney rises.
- Place the core, choose a 6″ or 8″ system, riser height and riser insulation.
- Swap the steel drum for a firebrick bell, and wrap either in mass or insulation.
- Fit a counterflow heat exchanger that preheats combustion air from the exhaust.
- Rebuild the bench at 1× to 5× its flue length with the Bench length control.
- Set the fire length, building heat loss, outdoor temperature and floor insulation.

## What it reports

- One fire of a length you set, lit with everything at the outdoor temperature, followed for a week:
  heat kept indoors, wood burned, room peak, hours until the room is back to outdoor + 1 °C,
  comfortable hours, bench-top and flue-exit peaks, draft margin, and where the energy goes.
- Every result is compared with a regular RMH (classic 8″ cob bench, steel drum) under the same fire, or with a design you pin.
- Temperature-coloured 3D view and a one-week timeline you can scrub or play.

## The model

A lumped thermal model: one node per 25 × 25 × 15 cm block, the riser liner, the drum or bell,
and the room. Combustion gets cleaner as the riser liner heats; flue gas gives heat to each block it
passes; blocks conduct to neighbours, the bench surface and the floor. Draft is judged against
rule-of-thumb flue lengths. The constants are tuned to be plausible, so use it to compare designs,
not to size a real build.
