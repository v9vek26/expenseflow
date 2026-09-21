# ExpenseFlow

**A browser-based expense tracker with monthly history and a configurable ledger.**

ExpenseFlow is my secondary portfolio project, focused on a compact React interface for recording expenses and reviewing spending. It runs entirely in the browser with localStorage persistence and starts with an empty ledger.

[Live app](https://expenseflow-livid.vercel.app) · [Usage and data](docs/USAGE.md) · [Architecture and status](docs/STATUS.md) · [Contributing](CONTRIBUTING.md)

## Features

- Add, edit, delete, and search expenses within a selected month.
- Browse recorded months and compare the selected month's spending with the previous month.
- View category totals and recent transactions.
- Review calendar-quarter actual spending and a simple three-month estimate.
- Configure categories, a display currency symbol, and ledger columns.
- Responsive dark interface built with React, Vite, and Lucide icons.

## Run locally

```sh
npm ci
npm run dev
```

Open the Vite URL printed in the terminal. Use a Node.js version compatible with the locked Vite release.

```sh
npm run build
npm run preview
```

Static hosting build command: `npm run build`. Output: `dist/`. No backend, database service, or API keys are required. Use HTTPS when deployed; record IDs use `crypto.randomUUID()`.

## Data and limitations

Expenses and settings are stored in this browser's localStorage under `expenseflow-v1`, scoped to the site's origin. They are not synchronized across devices or backed up by a server. Clearing site data, changing browsers, or moving to another domain can make records unavailable. Browser storage is not encrypted by the app or protected by a login.

Export/import, cloud sync, bank integration, and authentication are **not implemented**. Currency is a display symbol, not exchange-rate conversion. Keep the built-in date and amount columns usable: calculations still depend on those fields even though settings allow them to be removed or changed. See [known limitations](docs/STATUS.md).

## Project structure

```text
src/main.jsx     App state, dashboard, ledger, history, expense and settings dialogs
src/styles.css   Responsive visual styles
index.html       Vite entry point
docs/            Usage, calculation details, status and verification checklist
```

No repository-level license has been selected. No user counts, financial guarantees, or automated test coverage are claimed.
