# TripMind – AI Travel Planner

TripMind is a single-page travel planning website. Enter a destination, budget and number of days, and it builds a day-wise itinerary with attractions and a budget breakdown. You can then adjust the plan by typing in plain English.

## Features

- **Destination and budget input:** choose a place, a total budget in ₹ and 2–7 days.
- **Day-wise itineraries:** morning, afternoon and evening stops for every day, each with an estimated cost.
- **Attraction recommendations:** curated places for Goa, Jaipur, Manali, Kochi and London. Other destinations get general stops.
- **Budget suggestions:** the total is split into stay, food, transport, activities and buffer.
- **Natural-language customization:** type things like `more food`, `less walking`, `add beaches` or `keep it cheap`, then regenerate.
- **3D interactions:** a draggable globe with clickable destination pins, and day and destination cards that tilt toward the cursor or finger.
- **Responsive and accessible:** works on mobile, supports light and dark mode, keyboard focus styles, and respects reduced-motion settings.

## Tech stack

- HTML5, CSS3, vanilla JavaScript (no frameworks, no build step)
- Canvas 2D for the globe
- CSS 3D transforms for the tilt cards
- Google Fonts: Sora and Inter

## Run locally

1. Save `tripmind-pro.html` (or rename it to `index.html`).
2. Open it in any modern browser. No server needed.

## Project structure

```
tripmind/
├── index.html    # page, styles and script in one file
└── README.md
```

## How it works

- The `D` object in the script holds attractions per destination as `[name, tag, cost, description]`.
- Tags are `food`, `nature`, `culture`, `adventure` and `relax`.
- Words in the customization box are matched with regular expressions to score and re-rank attractions.
- The budget is split by fixed percentages: stay 40%, food 25%, transport 15%, buffer 5%. Activities use the real cost of the chosen stops.

## Limitations

- This version does not use a live AI model. Itineraries come from the built-in list.
- Prices are rough per-person estimates and not live data.

## Roadmap

- Connect a real LLM through a backend (Node/Express or a serverless function) that returns itineraries as JSON.
- Keep the API key on the server, never in browser code.
- Add more destinations, save and share trips, and export to PDF.
- Add real maps and a continent-accurate globe (for example with three.js).

## Deploy

Upload the file to GitHub Pages, Netlify or Vercel as a static site.

## Author

Rohit Kurup
