# BOBM Tracker — iPhone app

A small iPhone app that opens the live BOBM Production Tracker (https://bobm-dryroom-tracker.vercel.app)
and adds Apple push notifications with the tracker's own alert sound (`ios/App/App/bobm_alert.caf`).

- Everything you see in the app comes from the live website, so web changes show up instantly — no new build needed.
- A new build is only needed for app-level changes (alert sound, icon, app name). Push to `main` or press
  **Actions → iPhone app → TestFlight → Run workflow**.
- The workflow also runs on the 1st of each month so the TestFlight build never expires (TestFlight builds last 90 days).

## Repository secrets (Settings → Secrets and variables → Actions)

| Name | What it is |
| --- | --- |
| `APPLE_TEAM_ID` | 10-character Team ID (developer.apple.com → Account → Membership details) |
| `ASC_ISSUER_ID` | Issuer ID shown at the top of App Store Connect → Users and Access → Integrations → App Store Connect API |
| `ASC_KEY_ID` | Key ID of the App Store Connect API key (Admin access) |
| `ASC_KEY_P8` | Full text of that key's `.p8` file, including the BEGIN/END lines |

The separate Apple **push** key (.p8) is not stored here — it's entered once in the tracker under
Supervisor → Alerts → "iPhone app alert sound — one-time setup".

Bundle ID: `com.nrodgers.bobmtracker`
