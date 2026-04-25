# Hormuz Dashboard

Interactive web widgets accompanying *Chokepoint: Global Oil Supply Vulnerability and the 2026 Strait of Hormuz Crisis* — a spatial analysis project examining the consequences of a hypothetical Strait of Hormuz closure on global oil supply chains.

## About the project

This repository hosts two interactive components embedded in an [ArcGIS StoryMap](https://arcg.is/195jHS1) that visualizes the geography of oil supply vulnerability during the 2026 Hormuz crisis scenario. The project was developed as the final deliverable for 90-434/834 Geospatial Health Analytics at Carnegie Mellon University Heinz College, Spring 2026.

## Widgets

### Brent Crude Price Tracker (`brent-price.html`)

Live time-series chart of Brent crude oil daily spot prices, with crisis-period annotations. The widget pulls data directly from the U.S. Energy Information Administration (EIA) API v2.

- Data source: [EIA Petroleum & Other Liquids — Series RBRTE](https://www.eia.gov/opendata/)
- Built with: Chart.js (category scale, no date adapter)
- Display: Latest price, pre-crisis baseline (Feb 27), crisis change, and peak price

### SPR Drawdown Model (`spr-drawdown.html`)

Interactive choropleth map modeling strategic petroleum reserve depletion across 39 countries over the duration of the crisis. Users adjust a date slider (Feb 28 – Dec 31, 2026) and a substitution scenario dropdown to observe how reserves deplete under different assumptions.

- Data sources: IEA Oil Market Report, national energy agencies, UN Comtrade (HS 2709)
- Built with: Leaflet, Esri Dark Gray Canvas basemap, Natural Earth 110m country geometry
- Model: Each country's SPR depletes at a rate proportional to its Middle East import share × (1 − substitution rate). The widget supports three scenarios — Limited (70% substituted from non-Hormuz sources), Moderate (50%), and Heavy (30%) — to illustrate the range of plausible depletion trajectories.

## Live versions

Both widgets are deployed via GitHub Pages and embedded in the StoryMap referenced above. They can also be accessed directly at the GitHub Pages URL for this repository.

## Methodology notes

The SPR drawdown model is illustrative, not predictive. It does not capture IEA coordinated release allocations, demand reduction measures, alternative supply route activation, or commercial stock dynamics. Baseline SPR figures are drawn from a heterogeneous mix of sources with varying methodologies (days of consumption vs. days of net imports; government-controlled stocks only vs. inclusion of legally-mandated industry stocks). These limitations are documented in the accompanying project report.

## File structure

```
hormuz-dashboard/
├── brent-price.html       # Brent crude price tracker
├── spr-drawdown.html      # SPR depletion choropleth
└── README.md
```

## Author

Kaitlin Moore — Carnegie Mellon University Heinz College
