# Rocket Mass Heater Simulator

A single-page 3D tool for sketching a rocket mass heater and seeing how it performs.
Open `rocket-mass-heater-simulator.html` in a browser; there is nothing to build or install.

## What you can do

- Paint thermal mass (cob, brick, granite, concrete, sand) and insulation blocks on a 25 cm grid,
  as whole columns or stacked 15 cm blocks, up to 1.8 m tall. Shift-click deletes.
- Route the flue from the drum through the bench; the last cell is where the chimney rises.
- Place the core, choose a 6″ or 8″ system, riser height and riser insulation.
- Swap the steel drum for a firebrick bell, and wrap either in mass or insulation.
- Fit a counterflow heat exchanger that preheats combustion air from the exhaust.
- Set fires per day, wood per fire, building heat loss, outdoor temperature and floor insulation.

## What it reports

- A 72-hour simulation with day 3 results: heat kept indoors, room range, comfortable hours,
  bench-top and flue-exit peaks, draft margin, and where each day's wood energy goes.
- A cool-down test: one 6-hour fire from 0 °C, then hours until the room is back to 1 °C.
- Temperature-coloured 3D view and timeline you can scrub or play, plus a pinned baseline for comparisons.

## The model

A lumped thermal model: one node per 25 × 25 × 15 cm block, the riser liner, the drum or bell,
and the room. Combustion gets cleaner as the riser liner heats; flue gas gives heat to each block it
passes; blocks conduct to neighbours, the bench surface and the floor. Draft is judged against
rule-of-thumb flue lengths. The constants are tuned to be plausible, so use it to compare designs,
not to size a real build.
