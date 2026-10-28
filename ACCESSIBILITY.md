# Accessibility · إمكانية الوصول

هدفنا أن يكون سَنَد واضحًا وسهل الاستخدام بالعربية والإنجليزية، مع دعم اتجاه RTL ولوحة المفاتيح وتقنيات المساعدة. هذا هدف تطوير، وليس شهادة مطابقة مكتملة.

## Goals

- Meaningful labels and reading order for the browser's own controls.
- Keyboard access, visible focus and predictable dialog behavior.
- Readable text, usable contrast and layouts that tolerate text enlargement.
- Correct Arabic shaping, RTL layout, mixed Arabic/Latin URLs and understandable permission prompts.
- Useful error messages and settings that do not rely on color alone.

The browser shell and hosted home page are separate interfaces. Third-party website accessibility is controlled by those websites, although browser regressions that affect assistive technology are relevant reports.

## Report a barrier

Use the accessibility/documentation form in [the community issue chooser](https://github.com/SanadBrowser/.github/issues/new/choose), or [application issues](https://github.com/muradaljohani/Sanad-Browser/issues) for a runtime defect. Include:

1. App/version and the affected screen or control.
2. Operating system, language and zoom/text scaling.
3. Assistive technology and its version, if relevant.
4. Steps, expected behavior and observed barrier.

You do not need to disclose a diagnosis, disability or medical history. A keyboard-only reproduction is useful. Redact personal information from recordings and screenshots.

Proposed fixes should describe how they were checked, for example keyboard navigation, accessible names, RTL layout or a named screen reader. Do not claim broad conformance from a single automated score. There is currently no published independent accessibility certification or guaranteed remediation date.
