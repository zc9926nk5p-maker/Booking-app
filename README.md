# Wolf Adventure Tours: Yukon River Explorer

A bilingual (German/English) web app for exploring Yukon canoe rivers, building a trip and sending an inquiry. It is one self-contained file (`index.html`) with no build step, designed to be embedded in the new Wolf Adventure Tours website.

## What it does
- 14 rivers (7 guided tours plus 7 rental-only rivers) shown as photo tiles, filterable by difficulty and type
- River pages with itineraries, rental package prices, shuttle notes and a route map
- Maps: an illustrated Yukon map (highways, communities, lakes, ranges, grid) and real Topo and Satellite maps (Esri tiles via Leaflet)
- "Rent and shuttle" tab with boat packages, gear, shuttle prices and a cost estimator
- Trip builder (one river per trip) with start date, group size, name, email and notes
- "Request a river or custom trip" card for rivers that are not listed
- German/English switch, light/dark mode, phone and desktop layouts

## Run it locally
Open `index.html` in Chrome or Edge with an internet connection. The real maps load Leaflet and map tiles from the internet.

## Put it on GitHub Pages
1. Create a repository and upload these files to the root of the `main` branch.
2. In the repository, go to Settings > Pages.
3. Under "Build and deployment", choose "Deploy from a branch", then branch `main` and folder `/ (root)`.
4. After a minute the app is live at `https://<your-user>.github.io/<repo-name>/`.

To embed it in another site, use an `<iframe>` pointing at that address.

## Where to edit things (all inside `index.html`)
- Rivers, itineraries, prices, trip options: the `R` array
- Photos: the `PH` object (base64 images keyed by river id)
- Shuttle prices, boats, gear: `SHUT`, `BOATS`, `GEAR`, `PRICES`
- Text in both languages: the `UI` object (each entry is `[English, German]`)
- Business location: `WOLF` (latitude/longitude order is `[lon, lat]`)
- Contact and demo links: `CONTACT` and `ABOUT`
- Colours: the CSS variables at the top of the `<style>` block

## Known to-dos
- River routes and start points are hand-plotted approximations. Replace them with real GPX/KML tracks.
- The inquiry "Send" button is a demo that opens the About us page. Connect it to a real email or form service.
- Photos are small placeholders from the existing site. Swap in originals from Wolf.
- Upper Wheaton is intentionally left out (the existing site says it is not offered). Its photo is stored in `PH` as `upperwheaton`.
- The Lower Liard River is a "Coming soon" placeholder.
- Prices come from the existing website, in CAD plus 5% GST. Confirm before launch.
- German text is a translation. Compare it with the wording on the German pages.

## Before launch
- **Map tiles:** the Esri tiles are fine for testing. Check their terms, or use a licensed provider, for a business site.
- **Privacy (EU visitors):** the app loads Google Fonts and Leaflet from CDNs and map tiles from Esri. Self-host the fonts and Leaflet, and consider asking for consent before loading the real maps.
- **Attribution:** keep the map attribution shown on the real maps.

## Credits
- Maps: Esri tiles; Leaflet (BSD-2-Clause)
- Fonts: Barlow and Barlow Condensed (SIL Open Font License)
- River details and prices: wolf-adventure-tours.de
