# AstroVitals

AstroVitals is a NASA Space Apps hackathon prototype for recording astronaut crew health readings, checking input data, and reviewing trends and simple rule-based alerts. It is a demonstration and decision-support concept, not a medical diagnostic or treatment tool.

## Run the local demo

1. Install Node.js 18 or newer.
2. Open a terminal in the project folder.
3. Run `npm start`.
4. Open [http://localhost:3000](http://localhost:3000) in a browser on the same computer.

On Windows, you can double-click `start-astrovitals.bat` instead. Keep the server window open while using the app.

The local server uses Node.js built-in modules; there are no third-party Node packages to install. It saves readings in `data/state.json` when data is saved. This file is created at runtime and excluded from the repository.

## Public demo

[Open AstroVitals on GitHub Pages](https://shivam-kumar-dutta.github.io/AstroVital_space_app/)

The hosted version is a static demo. It stores visitor-entered demo data in that visitor's browser storage. The local Node.js server and its JSON-file persistence are not running on GitHub Pages.

## Features

- Add crew members and log daily readings for heart rate, blood oxygen, blood pressure, breathing rate, temperature, sleep, stress, exercise, fluids, and radiation.
- Validate JSON structure, supported fields, finite numbers, configured input ranges, mission-day uniqueness, and blood-pressure consistency.
- View status, simple alerts, personal-baseline comparisons, trends, and reading history.
- Export readings as CSV.
- View a separate panel with NASA ISS radiation telemetry.
- Draw trend graphs as SVG with the app's JavaScript; no charting library is used.

## Project files

- `index.html`, `style.css`, `script.js`: browser dashboard and interactions.
- `server.js`: local web server and JSON API.
- `dataValidator.js`: validates crew state and daily readings.
- `healthEngine.js`: calculates prototype status, trends, and reports.
- `data/nasa-iss-radiation.json`: NASA ISS environmental radiation sample.
- `.github/workflows/pages.yml`: publishes the static demo to GitHub Pages.
- `start-astrovitals.bat`: Windows launcher.

## NASA data and attribution

The included JSON file contains 12 ISS DosTel absorbed-dose-rate measurements accessed through NASA Open Science Data Repository (OSDR) RadLab. The sample covers 2022-04-01 23:00 UTC to 2022-04-02 01:05 UTC and uses microgray per hour (µGy/hour).

These are environmental radiation measurements, not individual astronaut vital signs. The dashboard presents them separately; they are not used in the crew health score. NASA describes RadLab data as preliminary.

Suggested attribution: “Data are courtesy of the NASA Open Science Data Repository. ISS radiation telemetry accessed through NASA OSDR RadLab.”

- [NASA OSDR RadLab data API](https://visualization.osdr.nasa.gov/radlab/gui/data-api/)
- [NASA OSDR repository](https://osdr.nasa.gov/bio/repo)
- [NASA OSDR citation guidance](https://science.nasa.gov/reference/osdr-faq/)

## AI and other credits

OpenAI Codex assisted with code organization and refactoring, implementation, debugging, NASA data integration, and documentation. The team is responsible for reviewing, understanding, and presenting the submitted project.

The interface fonts Inter, JetBrains Mono, and Space Grotesk are loaded from [Google Fonts](https://fonts.google.com/).

## Limitations and data safety

The crew examples are synthetic. Validation bounds, readiness scores, and alert thresholds are prototype settings, not clinical standards. AstroVitals does not diagnose or prescribe. The app has no sign-in, encryption, hosted database, or multi-user synchronization. Do not enter real or identifiable medical records.
