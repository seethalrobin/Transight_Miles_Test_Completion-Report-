# Transight_Miles_Test_Completion-Report-
## About the project

**Transight Miles** is a fleet-management platform with an Admin console, a Fleet Owner
portal and a Fleet Owner mobile app. I worked on it as QA Engineer at Fegno Technologies,
covering manual functional, negative/validation, UI, role-access, cross-browser, API and
performance testing on the staging environment.

This repository is the **automation suite I built alongside the manual test cycle**. It
covers the highest-traffic admin and fleet-owner flows end to end so they can be
re-checked quickly after every build.

### What the manual cycle covered (and this suite automates a slice of)

| Area | Modules |
|---|---|
| Login & session | Login, logout, session handling, role-based access |
| Admin console | Dashboard, Fleet Owners, Staff, Content, Insurance, Master Data, Vahan API / Fleet Sync, Settings |
| Fleet Owner portal | Dashboard, Vehicles, Drivers, FASTag / Fuel Cards, Documents, Reports |
| Mobile app | Fleet, Drivers, Reports (manual only) |

Third-party integrations (vehicle registry, IOCL fuel cards, FASTag, insurance) are
exercised only against provider sandbox / UAT environments.

### Highlights
- Page Object Model in TypeScript, one class per screen
- Single shared logged-in tab, built to work around the app's one-session-per-user
  rule and rate-limited token refresh
- Self-generating, clearly tagged test data (`pwauto_` prefix, `example.com` emails,
  non-routable phone numbers) so runs never contact real people
- Cross-browser login checks on Chromium, Firefox and WebKit
- CI on GitHub Actions with credentials held in repository secrets
