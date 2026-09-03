# ExpenseFlow

A polished, dark-mode personal expense tracker built with React + Vite. It is fully client-side and stores data in the browser's `localStorage`, so previous months remain available on the same device/browser.

## Features
- Add, edit and delete expenses
- Month-by-month navigation
- Persistent history for previous months
- 3-month actual spend and automatic 3-month estimate
- Category breakdown and recent transactions dashboard
- Searchable expense ledger
- Settings where expense columns are editable: rename, type, required/optional, add/remove
- Custom categories and currency symbol
- Responsive dark money-focused UI
- No backend, API keys or database required

## Run locally
```bash
npm install
npm run dev
```
Then open the local Vite URL shown in the terminal.

## Production build
```bash
npm run build
npm run preview
```

## Deploy
This is a static Vite app. Upload the project to GitHub and import the repository into Vercel or Netlify.

Build command: `npm run build`
Output directory: `dist`

## Important data note
Data is stored in browser localStorage. Clearing site data/browser storage will remove the saved expenses. This version intentionally has no server/database, so it is private to the browser/device where it is used.
