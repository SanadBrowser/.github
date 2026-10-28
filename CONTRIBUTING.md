# Contributing to Sanad Browser

نرحّب بالمساهمات بالعربية والإنجليزية: إصلاح الأعطال، تحسين الواجهة العربية وإمكانية الوصول، اختبار توافق المواقع، والتوثيق. أرسل الثغرات سرًا وفق [سياسة الأمان](SECURITY.md).

## Choose the right place

- Browser code and runtime defects: [application repository](https://github.com/muradaljohani/Sanad-Browser).
- Organization profile, policies and shared templates: [SanadBrowser/.github](https://github.com/SanadBrowser/.github).
- Read the target repository's own guide first; its build and security instructions take precedence.

Search existing issues before filing a duplicate. For a large feature, explain the user problem and proposed scope in an issue before investing in a large implementation. A small, focused fix can be submitted directly as a pull request.

## Application development

Use Node.js 24 and the checked-in npm lockfile. Fork the application repository, create a branch from `main`, then run:

```sh
cd desktop
npm ci
npm audit --audit-level=moderate
npm test
```

For changes to navigation, tabs, protection, permissions, privacy, preloads or application packaging, also run:

```sh
npm run prepare:filters
npm run test:desktop
# Linux without a display: xvfb-run -a npm run test:desktop
```

Windows packaging and installed-application checks run in Windows CI. Contributors do not need production certificates or Store publisher credentials. An opt-in `npm run test:youtube:live` probe contacts real YouTube using a fresh signed-out profile. Service/login/network walls must be recorded as inconclusive, not as ad-free playback.

## Keep changes reviewable

1. Describe the concrete problem and resulting behavior.
2. Keep each pull request focused; include a screenshot for a material UI change.
3. Report what you tested, the platform and any remaining limitation. Do not claim tests you did not run.
4. Add a meaningful regression fixture when changing a security boundary or fixing a reproducible defect. Documentation-only edits usually do not need runtime tests.
5. Update relevant documentation and notices when behavior or dependencies change.

Preserve renderer sandboxing, context isolation, HTTPS checks, exact shell IPC validation, permission consent and signature gates. Never weaken these controls to make an ad blocker or test pass. Dependency changes must retain notices, update the lockfile and be checked against the project's dependency audit.

## Protect private information

Do not commit API keys, tokens, cookies, certificates, user profiles, `.env` files or production secrets. Remove personal/account data from screenshots and logs. Share only a minimal public URL or local fixture; report sensitive reproduction details privately.

## Review and licensing

The maintainer may request revisions, split a large change or decline a proposal that conflicts with project scope. Approval is not a promise of a release date. Follow the [code of conduct](CODE_OF_CONDUCT.md).

Contributions must be yours to submit and compatible with the destination repository's license. The current application and original community material are MIT licensed; upstream dependencies and assets retain their licenses. These guidelines do not add a separate CLA or transfer copyright.
