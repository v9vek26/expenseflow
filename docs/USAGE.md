# Usage and data

## Everyday workflow

1. Choose a month with the arrows or **This month**.
2. Select **Add expense**, fill required fields, and save. The record's date determines its month; the form defaults to today's UTC date, not the month currently selected.
3. Open **Expenses** to search the selected month, edit records, or delete them. Deletion is immediate; there is no undo.
4. Use **History** to select a recorded month, then return to Dashboard or Expenses for its details.
5. Settings change the currency symbol, categories, and columns. Changing a category name does not migrate older records.

## Calculation definitions

- Monthly spend: sum of amounts dated in the selected month.
- Comparison: percentage change versus the immediately preceding month when its total is nonzero.
- Three-month actual: total for the calendar quarter containing the selected month, not a rolling 90-day window.
- Estimate: quarter total divided by the number of quarter months containing at least one expense, multiplied by three. With no records, the displayed estimate is zero. This is simple extrapolation, not a predictive model.

For example, recorded totals of 100 and 200 in two months of one quarter produce an estimate of 450. The unrecorded third month is excluded from the averaging denominator.

## Storage

The localStorage object contains `settings` and `expenses`. The key is `expenseflow-v1`. Storage is specific to protocol, hostname and port; localhost data does not move into the hosted app. Private browsing and storage restrictions may prevent durable persistence.

There is no built-in export, import, recovery, or backup UI. Do not treat this app as the sole copy of important financial records. Clearing browser data removes records. Scripts running on the same origin can access localStorage.
