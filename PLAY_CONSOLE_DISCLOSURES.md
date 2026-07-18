# Google Play disclosure preparation

This checklist reflects the current v1 implementation. Recheck it against the final release artifact and Google Play forms immediately before submission.

## Required public information

- [ ] Publish `PRIVACY_POLICY.md` as an active, public, non-geofenced HTML webpage rather than a PDF.
- [ ] Add the final privacy-policy URL to Play Console.
- [ ] Add Privacy & Security and Terms & Disclaimer entries inside Settings.
- [ ] Replace all bracketed placeholders with the actual developer identity, contact method, effective date, and jurisdiction.

## Data Safety form — current implementation

- User-entered financial and work information is processed and stored solely on the device.
- The app uses internet access for internal map tiles and address lookup. It does not transmit financial, payroll, receipt, or work records to the developer.
- No advertising, analytics, remote logging, or third-party crash reporting is included.
- Local records are encrypted using AES-256-GCM with a device-bound Android Keystore key.
- Android application backup is disabled.
- Users can authenticate and delete all local data in Settings.

Google Play states that data accessed solely on-device and never transmitted off-device generally does not need to be declared as collected. The Data Safety form is still mandatory and must match every SDK and the final release artifact.

## Permissions and visible device surfaces

- Notification permission is requested on Android 13 and later.
- The active-shift notification and home-screen widget may display work status, elapsed time, lunch status, and punch controls.
- The current version does not request location permission.
- Users may enter job addresses for an internal map or explicitly open them in an installed maps app.
- Camera/document access is user initiated for on-device receipt or inventory-document recognition; confirmed records remain local.
- Future geofencing must not be enabled without updating the Privacy Policy, Data Safety form, permission disclosures, and Play background-location review materials.

## Financial Features declaration

- [ ] Complete the mandatory Financial Features declaration in Play Console.
- [ ] Describe the app as a personal budgeting/money-management and work-income estimation tool.
- [ ] Confirm that the app does not originate loans, broker investments, transfer money, sell financial products, or provide regulated lending services.
- [ ] Ensure store text does not claim guaranteed savings, tax accuracy, debt outcomes, or professional advice.

## Store and in-app disclosures

- [ ] State that tax, net-pay, overtime, interest, payoff, and budget outputs are estimates.
- [ ] State that local/city income taxes and state-specific credits may not be included.
- [ ] State that Work Tracker is not an employer-approved timecard or payroll record.
- [ ] State that Business Suite wage, contractor-payment, owner-pay, payroll-tax, and profitability outputs are user-maintained planning records rather than payroll processing or professional accounting services.
- [ ] State that users must verify important information with official records and qualified professionals.

## Final review triggers

Repeat the privacy and disclosure review if the app adds:

- Internet access, accounts, cloud sync, or remote storage
- Encrypted export or device transfer
- Location or geofencing
- Advertising, analytics, logging, or crash reporting
- New SDKs
- Payment processing, bank connections, lending, investing, or credit services
- A change to target audience or supported countries
