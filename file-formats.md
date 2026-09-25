---
status: generated
version: "0.1"
---

# Supported file formats

Texterify imports and exports these formats (from the built-in format list):

| Format | Typical use |
| --- | --- |
| JSON (flattened) | Web apps with flat key files |
| JSON (plurals) | JSON with plural forms |
| JSON Format.js | FormatJS / react-intl |
| JSON POEditor | Files exchanged with POEditor |
| iOS .strings | iOS / macOS |
| iOS .stringsdict | iOS plurals |
| TOML | TOML-based configs |
| Java .properties | Java apps |
| PO | gettext |
| Flutter .arb | Flutter |
| XLIFF .xlf, .xliff | Exchange format for CAT tools |
| Ruby on Rails | Rails YAML locales |
| YAML | Generic YAML |
| TypeScript | TypeScript translation modules |
| Android | Android `strings.xml` |
| CSV | Spreadsheets |

Choose the format per [export configuration](concepts.md#export-configurations). One project can have several export configurations, for example Android and iOS from the same keys.
