# Security and diagnostics

Paycheck First stores financial and work data locally using AES-256-GCM encryption with a device-bound Android Keystore key.

## Logs and crash reports

- Production code does not log income, tips, bills, debts, balances, work history, names, notes, or authentication data.
- The app includes no analytics, advertising, remote logging, or third-party crash-reporting SDK.
- Crash reports are not collected or transmitted by the app.
- Cleartext network traffic and Android application backup are disabled.
- A build-time verification task rejects common logging and crash-reporting calls in production source code.

## Components and intents

- The launcher activity is the only exported application component and has no browsable deep links.
- The home-screen widget receiver is explicitly non-exported.
- Widget and notification actions use explicit, immutable `PendingIntent` instances.
- The app declares no internet permission, service, or content provider.
- A build-time component-security check protects these invariants and requires review before adding network access or deep links.

## Planned v2 export and transfer

Encrypted export and device transfer are intentionally disabled in v1. The future workflow must require user authentication, encrypt the export independently of the device-bound storage key, avoid cloud sync by default, and disclose exactly what records are included before creating a file.

Android itself may retain limited operating-system diagnostics according to the device owner's Android and manufacturer settings. The app does not add financial values to exception messages or intentionally transmit system diagnostics.
