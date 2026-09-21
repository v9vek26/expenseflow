# Architecture and status

Source review: 2026-09-21. React state in `src/main.jsx` is initialized from localStorage; updates clone state and persist the whole data object. Derived monthly/quarterly views are computed in the browser. There is no server component.

| Area | Status |
| --- | --- |
| Expense CRUD, monthly views, search, settings | Implemented in source |
| Local persistence | Implemented; browser/origin-specific |
| Quarterly totals and estimate | Implemented as calendar-quarter aggregation and simple extrapolation |
| Export/import | Not implemented; unused icon imports are not functionality |
| Login, cloud sync, bank connections | Not implemented |
| Automated tests and lint scripts | Not configured in package.json |

## Known limitations / next work

- Protect required core column IDs/types; settings can currently remove date/amount even though aggregation requires them.
- Add storage-schema validation, migrations, and handling for storage-write failures.
- Review date-only parsing across time zones and the UTC default date near midnight.
- Define category rename/removal behavior: older expenses retain old category values and may be absent from configured-category charts.
- Add backup/export and restore validation before treating storage as durable.
- Add keyboard, dialog-focus, screen-reader, mobile, and core-flow verification.
- Replace `latest` manifest ranges through a deliberate dependency-maintenance change; the committed lockfile currently supplies repeatable installs.

## Manual regression checklist

Use synthetic data in an isolated browser profile. Add and edit an expense, verify monthly totals, reload to confirm persistence, search the ledger, navigate to a different month, verify quarter calculations, and delete only the test record. Check settings and narrow-screen layout. A successful production build alone does not establish these behaviors.

Feature descriptions must stay synchronized with implementation. Record verification separately from source review; do not label planned backup or sync features as shipped.

## Verification record — 2026-09-21

- Locked dependency install: `npm ci --ignore-scripts --no-audit --no-fund` passed.
- Production build: `npm run build` passed with Node.js 24.20.0 and locked Vite 8.2.2.
- Existing deployment opened successfully and displayed the empty dashboard.
- Expense CRUD, persistence, accessibility, and mobile interaction checks were not run during this documentation-only change.
