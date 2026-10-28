# Security policy

أرسل بلاغات الثغرات بشكل خاص. لا تنشر كلمات المرور أو ملفات الجلسات أو سجل التصفح في Issues العامة.

## System and supported versions

These are the default reporting guidelines for SanadBrowser repositories. A repository's own security policy takes precedence. The desktop application is currently maintained at [muradaljohani/Sanad-Browser](https://github.com/muradaljohani/Sanad-Browser), with its [specific security policy](https://github.com/muradaljohani/Sanad-Browser/blob/main/SECURITY.md).

Security maintenance targets current application source and the latest production Microsoft Store release. Historical unsigned previews are not recommended for new installations. Download production builds from [the official download page](https://ip-murad.com/browser/download/). Source commits and CI packages do not establish Store availability.

## Report a vulnerability privately

Use the affected repository's **Security → Report a vulnerability** when that feature is enabled. Otherwise email **IM_MURAD7@hotmail.com**, subject `Sanad Browser security report`. If you are unsure which repository is affected, use the same private contact rather than publishing a working exploit.

Include versions, operating system, affected path or feature, expected trust boundary, observed impact and minimal reproduction steps. Prefer a local fixture. Redact credentials and third-party personal data. Do not attack third-party services or access another person's data while preparing a report.

The maintainer will assess the report, discuss reproduction privately, and coordinate a fix and appropriate disclosure. A public advisory may follow a validated issue and available remediation. There is no paid bounty, staffed security team or guaranteed response time. No legal safe-harbor promise is made by this technical policy.

## Threat model and security boundaries

The desktop application displays untrusted websites and handles user-directed navigation and downloads. Remote content, imported files, filter updates and external metadata are untrusted inputs. Protected assets include the local profile, cookies, permission decisions, downloaded files and release credentials.

- Remote pages remain sandboxed and context-isolated, without Node integration, privileged preloads or access to the shell's `sanadBrowser` API.
- Privileged commands require the exact trusted shell main frame. The shell uses a restricted custom protocol and CSP.
- Production navigation requires HTTPS; invalid certificates and executable/local protocols are not bypassed. Loopback HTTP is limited to unpackaged tests.
- Sensitive website permissions require active-tab consent. Unsupported permissions and device access are denied.
- Downloads require eligible active tabs and allowed sources. Executable downloads require confirmation; downloaded files are not automatically launched.
- Private session storage is separate from regular tabs and retired when that private session ends. This is not network anonymity or forensic erasure of the operating system.
- File parsing must enforce actual byte bounds. Page content must not become unsanitized privileged-shell HTML or executable application code.
- Fixed YouTube helpers may not expose Node/IPC, open a debugging port, execute downloaded scriptlets or bypass TLS/CSP.
- Production distribution and updates retain their signature and origin checks. Store submission archives and CI test certificates are not end-user releases.

## Review and reportability

Report realistic violations of isolation, origin checks, permissions, safe parsing, update integrity or confidentiality, including a plausible reproduction and impact. Version or scanner output alone is a lead for investigation, not proof of exploitability. This policy does not introduce blanket vulnerability exclusions or accepted-risk waivers.

Never commit secrets or expose production credentials to untrusted pull requests. Changes to these boundaries require focused review, relevant regression evidence and retained dependency/license notices. CodeQL, audits, history-secret scanning and tests inform review; passing them or Store certification does not prove absence of unknown vulnerabilities.

## Known limitations

Ad blocking is best effort and changes with third-party sites; server-inserted media ads and some response paths may remain. A service/login wall prevents a live playback conclusion. Private mode does not hide the IP address or activity from visited services and the network operator. Chromium, Electron and filter-list behavior also depend on their upstream maintainers. These limitations do not excuse a new security boundary bypass.
