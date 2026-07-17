# Paycheck First

Android-first starter for the paycheck-first budgeting app.

Project notes:

- [Changelog](CHANGELOG.md)
- [To Do](TODO.md)

## What is in this first version

- Blank first-run state so users enter their own income and bills.
- Home dashboard with quick access to each major area.
- Home dashboard shows paycheck inflow, recommended bill/debt outflow, Food/Gas survival cash, and discretionary money left.
- Home dashboard tracks bill payments due/expected this month and uses green, amber, or red to show on-track, warning, or behind status.
- Status colors are used across cash flow, checklist urgency, debt interest risk, and locked/private income states.
- Separate sections for Income, Bills, Debts, and Weekly Checklist.
- Income estimator for hourly or salary pay, overtime, pay frequency, state, deductions, pre-tax or post-tax retirement, post-tax savings, benefits, and extra withholding.
- Income setup stays hidden behind an Add/Edit income button so the page opens as a clean summary first.
- Income dashboard has collapsible breakdowns for income, taxes, benefits/insurance, retirement, and savings with paycheck, monthly, and annual amounts.
- Income dashboard has PIN privacy-gate code for masking money values, currently disabled during active development.
- Active tax-year configuration layer for federal brackets, standard deduction, FICA rates, and Social Security wage base.
- State tax layer currently handles no-earned-income-tax states exactly and uses configured progressive brackets for Minnesota and Wisconsin.
- Actual take-home pay override that always becomes the budget income when entered.
- Bill entry and editing with name, category, monthly minimum, due day, and payment schedule.
- Manual bills default to weekly payments to smooth cash flow, while subscriptions default to monthly payments.
- Switching a bill to biweekly or monthly shows a warning that some companies do not apply smaller weekly payments cleanly.
- Bills dashboard with total monthly bills and paycheck set-aside at the top once bills exist.
- Bills automatically includes monthly payments generated from Debts so loans and cards are not entered twice.
- Add/Edit bill form opens as its own focused screen instead of living inside the bill list.
- Paycheck-sized recommendations from monthly bills.
- Priority ordering that favors urgent due dates and essential bills.
- Manual payment overrides.
- Paid checklist for each recommendation.
- Delete control for bills that no longer belong in the plan.
- Remaining income and projected shortage summary.
- Debt tracking by type: mortgage, auto loan, credit card, personal loan, student loan, and other.
- Debts dashboard with total balance, payoff time, and interest estimate at the top once debts exist.
- Add/Edit debt form opens as its own focused screen instead of living inside the debt list.
- Mortgage and auto loans use scheduled APR-style payoff estimates.
- Credit card payoff uses a simple estimate and assumes no new spending unless the balance is updated.
- Other debts can use APR, APY, or simple-interest calculation modes.
- Debt payoff estimates with monthly interest, first-month principal, and paycheck-sized payment view.
- Weekly Checklist includes both manually entered bills and debt payments.
- Debt payments now have due days so debt-derived bill/checklist items can be prioritized.
- Weekly Checklist shows 4 or 5 weekly checkboxes for the current month and hides the current week's item after it is paid.
- Paid bill/debt checkmarks are keyed to the phone's current calendar month so the checklist and home progress reset cleanly each month.

## How to open it

Open this folder in Android Studio:

`C:\Users\AlexB\Documents\Goblin Accountant`

Android Studio will sync the Gradle project, download Android dependencies if needed, and let you run the app on an emulator or connected Android device.

## Next product steps

1. Persist data locally with Room or DataStore.
2. Add first-time setup screens.
3. Add notifications for Monday, Wednesday, and payday.
4. Add debt payoff details.
5. Add optional credit utilization recommendations.
