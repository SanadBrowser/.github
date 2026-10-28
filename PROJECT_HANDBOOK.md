# Sanad Browser project handbook

Updated 28 October 2026. These guidelines describe the current independent project and its intended contribution/release process. They do not claim a registered company, a staffed security department or affiliation with another browser vendor.

## Governance · إدارة المشروع

The project is maintained by [Murad Aljohani](https://github.com/muradaljohani), the current SanadBrowser organization owner. Contributors participate through issues, documentation, testing and pull requests. There is no elected board or multi-company foundation described by this policy.

The maintainer is responsible for repository access, merge decisions, moderation and release approval. Discuss substantial changes in an issue, explain the user benefit and security/privacy consequences, and record the decision in a reviewable issue or pull request. Urgent vulnerability details stay private until coordinated disclosure is appropriate.

Repository permissions should be limited to the task. Code ownership identifies reviewers; it does not automatically grant repository access. New maintainers or release access require an explicit owner decision. No contributor is promised a role, payment or merge date.

## Privacy · الخصوصية

### Scope

This section explains the public desktop application's current design and community reporting practices. The separate hosted website, search/account services, Microsoft Store and GitHub each have their own data handling. The [website's browser privacy notice](https://ip-murad.com/browser/privacy/) covers that hosted service; it should not be replaced by assumptions about the desktop code.

### Data on the device

Regular browsing uses a local Chromium profile with website cookies and storage. The application stores preferences, bookmarks and a bounded local history. Downloaded files, exports and user-created screenshots are written to locations chosen by the user. The current application does not implement a built-in account-sync service for those local records.

Private tabs use a separate temporary session whose cookies/storage are cleared when the private session retires. Files deliberately downloaded or exported can remain on disk. Private mode does not make a user anonymous, conceal the IP address or guarantee erasure of operating-system traces. Local bookmarks/history should not be assumed to have the same encryption properties as Chromium cookies.

### Network activity and permissions

Websites and search services necessarily receive requests made while browsing. They may receive the IP address, user agent, search queries, cookies and submitted content according to site settings. The hosted Sanad home/search page is a network destination with its own notice. Filtering reduces some requests; it is not a promise that no tracking can occur.

Application filter snapshots ship with the build. A manual protection-list refresh contacts the listed maintainers at EasyList/EasyPrivacy. Source builds can query the configured release feed; Store distributions use Store-managed updates. Upstream Chromium/Electron and visited-site behavior must also be considered.

Website camera/microphone, location and notification permissions are prompted for eligible active tabs. Deny a request you do not intend to grant. Normal profile data and history can be managed through application controls; uninstall behavior and operating-system backups may leave data. No unsupported promise of universal or immediate deletion is made here.

### Community data

Public GitHub reports, pull requests and discussions are public. Post only minimal reproduction details and sanitized evidence. Private security or conduct reports go to the published maintainer contact. Use the same contact for a project-held report-data concern; GitHub/Microsoft account records remain subject to those services' processes. No identity documents are required by these contribution guidelines.

## Release and distribution policy · سياسة الإصدارات

Production Windows downloads are linked from [the official download page](https://ip-murad.com/browser/download/) to [Microsoft Store](https://apps.microsoft.com/detail/9NZB8PG7D7KP). Store application signing and delivery are managed by Microsoft. Store identity fields must match the reserved product exactly.

A source commit, successful build, checksum or Store submission draft is not a published production release. An `.msixupload` archive is a maintainer upload package, not an end-user installer. CI test identities/certificates must never be presented as trusted production publisher credentials.

Before a release, maintainers review relevant unit and actual Chromium interaction tests, dependency audits, CodeQL/secret-scan results, packaging and installation evidence. Security-sensitive changes need focused regression evidence. Keep dependency and Chromium/Electron versions visible, preserve notices and disclose material known limitations in release notes.

Direct EXE publication remains gated on valid, timestamped trusted publisher signatures. Downloaded updates are not executed automatically by the source application. Prefer Store-managed updates for Store installations. A certificate or successful scan is not a guarantee of zero vulnerabilities.

For live third-party tests, distinguish normal playback, observed advertisements, consent/login walls and inconclusive network results. Never report all campaigns blocked from a fixture or a service wall. A new immutable submission version is needed when an already-staged version's package contents change.

## Brand and licensing · الهوية والتراخيص

Use “سَنَد الحرمين” and “Sanad Browser” to refer accurately to this project. Preserve attribution, dependency notices and each repository's license. Current original application/community material is MIT licensed; third-party components, images and services retain their own rights. This handbook does not relicense those materials.

Do not present a modified build, unrelated download or commercial service as the project's official release or imply maintainer endorsement without permission. Descriptive references, criticism and compatible uses allowed by applicable licenses are not prohibited by this guideline. Ask the maintainer if an endorsement or branding arrangement is needed.

Brave, Google, Chromium, Electron and Microsoft names refer to their respective projects or products. Technical research, use of open-source dependencies and Store distribution do not imply affiliation, sponsorship or independent certification.

## Roadmap · أولويات التطوير

These are proposed priorities, not committed dates or completed features:

| Area | Next evidence to seek |
| --- | --- |
| Browser engine maintenance | Current supported Electron/Chromium versions and passing installation/security gates |
| YouTube and site compatibility | Reproducible live playback tests across more regions and account states, with explicit limitations |
| Arabic and accessibility | RTL review, keyboard checks and named assistive-technology reports |
| Performance | Reproducible startup, navigation and memory measurements; no invented speed multipliers |
| Release operations | Clear signed distribution, Store availability and versioned release notes |
| Community | Better reproductions, contributor documentation and reviewable ownership decisions |

Propose a feature through the issue form with the problem, expected benefit and testable acceptance criteria. Platform expansion, synchronization, paid rewards and Brave-level feature/security equivalence are not promised by this roadmap.
