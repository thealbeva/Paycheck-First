# Changelog

## 2026-07-16

### Website

- Built a complete local, unpublished Paycheck First website with responsive Home, About the Developers, Privacy, Security, Terms, and Support/FAQ pages.
- Added an app-forward landing page explaining net-income planning, weekly obligations, effective net wage, work tracking, local privacy, and private Android field testing.
- Added working navigation, footer links, release messaging, mobile layouts, and a disabled public-download control.
- Added plain-language website versions of the privacy policy, security overview, financial disclaimer, and support FAQ without inventing unfinished legal/contact details.
- Added an About the Developers page describing the product mission, development principles, field-testing approach, and goblin development team.
- Added Alex Vang to the developer page with a polished identity-preserving portrait and clearly marked profile-copy placeholders for completion.

### Goblin team and support

- Added Mr. Goblin as a local guided-support helper available from every website page.
- Replaced unreliable free-text support with approved clickable questions covering plan optimization, weekly smoothing, privacy, punch corrections, tax estimates, widgets, and release timing.
- Gave Mr. Goblin a concise goblin-style support voice while keeping tax, security, deletion, and financial limitations clear.
- Added Sir Goblin as Chief Financial Goblin & Strategy Advisor with his portrait, responsibilities, and motto: “Protect the shiny. Plan before you spend.”
- Created an official companion portrait for Mr. Goblin and defined his role as Chief Builder Goblin & Product Engineer with the motto: “Build it. Test it. Protect the shiny.”
- Matched Sir Goblin and Mr. Goblin portrait sizing and presentation on the developer page.

### Visual polish and fixes

- Increased the navbar logo size and brightened the “Built for real-life paychecks” status dot.
- Replaced unclear privacy symbols with custom phone, padlock, account-off, and tracking-off line icons.
- Replaced the placeholder square feature icon with a correction/redo symbol.
- Fixed missing website logo and goblin assets by serving project images directly.
- Repaired Windows text-encoding corruption affecting punctuation, symbols, and quotation marks.
- Removed unintended section padding that created a large blank area above the support panel.
- Made the support panel responsive and hid the duplicate website trigger while the panel is open.

### Verification

- Website lint passes with no errors.
- Production website build passes for Home, About, Privacy, Security, Support, and Terms routes.
- All website routes and local logo/portrait assets return successfully from the local development server.
- The website remains local and unpublished during development.

## 2026-07-15

### Added

- Added exact next-payment due dates for bills and debts so current statements can override a recurring due day.
- Added manual statement-value entry for next due date, minimum payment, and current debt balance.
- Added a paused / not-currently-due debt state for inactive obligations such as deferred student loans.
- Added quick Punch in/out and Lunch out/in controls directly below the Home cash-flow summary.
- Added separate Hour, Minute, and AM/PM controls when correcting work shifts.
- Added the official Paycheck First logo and Android launcher icons, including adaptive and round variants.
- Implemented optional credit-limit, utilization, and available-credit calculations for credit cards; the UI remains disabled until rollout or a later update.
- Produced an installable private field-test APK.

### Fixed

- Prevented Income and Checklist navigation labels from wrapping on narrow phone screens.
- Kept app content and dialog actions above Android's three-button navigation area.
- Made the work-shift correction form scrollable on smaller screens.
- Fixed disabled shift correction saving caused by unclear military-time input requirements.
- Preserved paid/checklist history when editing existing bills and debts.
- Corrected retirement and savings percentage bases: retirement uses gross pay, while savings uses estimated take-home after taxes, retirement, benefits, payroll deductions, and extra withholding.
- Prevented paused debts from creating current obligations, checklist items, or urgency warnings while retaining their balances in total debt.

### Changed

- Renamed all user-facing product references from Goblin Accountant to Paycheck First while retaining the internal Android package for compatibility.
- Kept detailed work summaries, tips, overtime, history, corrections, and deletion under Income while moving only the quick shift controls to Home.
- Added clearer wording explaining that savings and retirement percentages use different calculation bases.
- Updated debt displays to show Paused / N/A when no payment is currently required.

### Field testing

- Began private physical-phone field testing with real financial and shift data.
- Rebuilt the field-test APK after each calculation and workflow correction.
- Unit tests, Android builds, sensitive-logging checks, and component-security checks pass.

## 2026-07-14

### Added

- Added local on-device persistence for income settings, bills, debts, payment status, and work shifts.
- Added AES-256-GCM encryption backed by the Android Keystore for saved app data.
- Added recovery handling when encrypted data cannot be opened after a device-security or Keystore change.
- Added Settings controls for deleting all local data and viewing the planned encrypted export/device-transfer feature.
- Added optional biometric or device-credential confirmation before editing or deleting bills and debts.
- Added a manual work tracker with punch in/out, lunch out/in, shift editing, shift deletion, cash tips, other income, and overtime.
- Added work summaries for average hours, gross income, estimated net income, and effective net hourly wage.
- Added a disabled “Automatic work tracking — Coming soon” card for the planned v2 geofence feature.
- Added an Android home-screen widget with worked time, punch in/out, and lunch out/in controls.
- Added an ongoing shift notification with worked time and quick punch/lunch actions.
- Added Home totals for amount past due and amount ahead.
- Added red past-due styling for overdue obligations.
- Added explicit tax rules for all 50 states, including the nine states without a broad wage income tax.
- Added Privacy Policy, Terms of Use, Play Console disclosures, Security notes, and a detailed tax-engine review.
- Added build checks for sensitive logging and exported Android components.

### Changed

- Changed budgeting and tracked-work projections to emphasize estimated net income and effective net wage.
- Corrected the finalized 2026 federal single-filer brackets while retaining the $16,100 single standard deduction.
- Audited all 50 state rate schedules and corrected stale 2026 entries for California, Delaware, Hawaii, Maine, Massachusetts, Minnesota, New Jersey, New Mexico, New York, Vermont, West Virginia, and Wisconsin.
- Added a clear “single-filer estimate only” disclaimer to the income estimate.
- Clarified that state deductions, exemptions, credits, local taxes, withholding methods, and special rules may not be included.
- Kept overtime earnings in income calculations because the temporary federal overtime deduction applies only to eligible overtime premium pay, not all overtime wages.
- Moved security and data-management actions into Settings to keep the main screens uncluttered.
- Kept shift editing available without biometric confirmation because shift time is not treated as protected financial data.

### Security and privacy

- Financial data remains local to the phone; no account or cloud sync is required.
- Release builds prevent cleartext network traffic and exclude app data from Android backup and device transfer.
- Widget and notification components use non-exported receivers/services where applicable and immutable pending intents.
- App-wide biometric locking, automatic geofence tracking, and encrypted export/device transfer remain deferred so daily punch actions stay quick.

### Verification

- Unit tests, sensitive-logging checks, and Android component-security checks pass after the tax updates.
- Full hands-on Android/device suite review is planned for 2026-07-15.

## 2026-07-13

### Added

- Built the Android-first Paycheck First starter app.
- Added Home, Income, Bills, Debts, and Weekly Checklist sections.
- Added a clean first-run state with no prefilled bills.
- Added paycheck planning from effective income to recommended bill/debt payments.
- Added bill creation, editing, deletion, due dates, categories, payment cadence, and payment overrides.
- Added weekly, biweekly, and monthly bill payment options.
- Added a warning dialog when changing bills away from weekly smoothing.
- Added subscription-friendly monthly default behavior.
- Added debt creation, editing, deletion, due dates, payoff estimates, interest estimates, and paycheck-sized payment views.
- Added debt types for mortgage, auto loan, credit card, personal loan, student loan, and other.
- Added APR, APY, and simple-interest calculation support.
- Added debt-derived bill/checklist entries so loans and cards do not need to be entered twice.
- Added income estimator for hourly/salary pay, overtime, pay frequency, state, deductions, retirement, savings, benefits, and extra withholding.
- Added a tax-year configuration layer for estimate rules.
- Added no-earned-income-tax states plus Minnesota and Wisconsin income tax estimates.
- Added actual take-home pay override so the user can use their real paycheck amount.
- Added collapsible Income breakdowns for income, taxes, benefits/insurance, retirement, and savings.
- Added privacy-gate code for Income masking, currently disabled during active development.
- Added Home cash-flow summary for inflow, outflow, Food/Gas, and discretionary money.
- Added bill progress status on Home with green, amber, and red states.
- Added color/status indicators across cash flow, checklist urgency, debt interest risk, and locked income states.
- Added comma-formatted money display.
- Added month-aware paid checkmarks keyed to the phone's current calendar month.
- Added tests for income estimates, state taxes, debt math, weekly checklist periods, and month-specific paid status.

### Changed

- Moved Add/Edit bill and Add/Edit debt into focused screens instead of permanent inline forms.
- Moved Income setup behind an Add/Edit button instead of permanently showing the form.
- Changed recommended payments on Home from counts to dollar amounts.
- Updated Compose dropdown anchors to remove app-code deprecation warnings.

### Notes

- Data is still in-memory during active screen-building.
- Privacy lock is intentionally disabled while development is active.
- Remaining Gradle warning is from build tooling/dependencies, not current app UI code.
