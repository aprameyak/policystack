# Policy Stack

A side-by-side list of insurance quotes. Enter quotes you have received for auto, home, or health coverage and see the average, lowest, and highest premium for each type.

## Features

- Add a quote with type (auto, home, health), insurer, annual premium, coverage description, and deductible
- Filter the list by insurance type
- See the average premium and the premium range for the current filter
- Entries are saved to a local JSON file

## Getting started

Requires Node.js.

```bash
npm install
npm start
```

Then open http://localhost:3006. `npm run dev` runs the same command.

## How it works

- `index.html` contains the quote form, a type filter, summary stats, and the quote list. It calls the API at `http://localhost:3006`.
- `server.js` is an Express app that serves the page and exposes:
  - `POST /api/quotes` to save a quote.
  - `GET /api/quotes` to return quotes plus `avgPremium`, `minPremium`, and `maxPremium`. Add `?type=auto` (or `home`, `health`) to filter.
- Data is written to `data.json`, created on first run and ignored by git.
- `utils.js` holds validation and file helpers that are not yet wired into `server.js`.

## Status

Prototype. Quotes are entered by hand and coverage is free text, so the app compares premiums but does not normalize coverage between policies.

## License

MIT, see [LICENSE](LICENSE).
