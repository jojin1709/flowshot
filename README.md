<div align="center">

<img src="public/mascot.svg" width="140" height="140" alt="FlowShot" />

# FlowShot

**Auto-capture any browser workflow into a step-by-step guide.**

Click record, do the thing, get a polished guide with annotated screenshots. Narrate it as you go, edit it after, then replay or export. No account, no cloud, no tracking.

[![License][license-shield]][license-link]
[![Manifest V3][mv3-shield]][mv3-link]
[![100% Local][local-shield]][local-link]
[![No Account][no-account-shield]][no-account-link]

</div>

---

## Table of Contents

- [What is FlowShot?](#what-is-flowshot)
- [Features](#features)
  - [Smart Blur](#smart-blur)
  - [AI Descriptions](#ai-descriptions)
  - [Guide Me Replay](#guide-me-replay)
  - [Voice Narration](#voice-narration)
  - [Guide Editor](#guide-editor)
  - [Multi-Format Export](#multi-format-export)
- [Supported Browsers](#supported-browsers)
- [Quick Start](#quick-start)
- [Privacy & Storage](#privacy--storage)
- [Contributing](#contributing)
- [License](#license)

---

## What is FlowShot?

FlowShot is a browser extension that automatically captures your browser workflows and turns them into step-by-step guides with annotated screenshots. It runs entirely in your browser — no backend, no account, no telemetry, and nothing ever leaves your device.

Whether you're documenting internal tools, writing product tutorials, or onboarding a teammate, FlowShot captures every click, keystroke, and navigation automatically so you can focus on the work.

Every meaningful action becomes a step: clicks on buttons and links, form inputs, keyboard shortcuts, clipboard actions, drag events, and page navigations. Rapid clicks on nearby elements are merged so guides stay clean, and clicks are intercepted before the page navigates away, so nothing is lost on SPAs or full page loads.

Each step gets a screenshot with the clicked element highlighted and zoomed in. No manual cropping, no annotation tools to learn.

---

## Features

### Smart Blur

FlowShot automatically detects and blurs sensitive data in your screenshots: emails, phone numbers, SSNs, credit cards, IP addresses, MAC addresses. Toggle each category independently.

Need to blur something custom? The manual blur picker lets you select any DOM element and mask it across every screenshot where it appears.

### AI Descriptions

Bring your own API key (OpenAI or Anthropic) and FlowShot generates human-readable step descriptions like *"Click the **Submit** button to save changes"* instead of the rule-based `Click Submit`.

Descriptions are generated from a lightweight DOM context (~50-100 tokens), not screenshots. Roughly 15-30x cheaper than vision models. Choose the language you want descriptions in (English, Spanish, Portuguese, French, German).

### Guide Me Replay

Replay any guide live on a real page. FlowShot highlights the next element to click, tracks your progress step by step, and advances automatically as you interact. Perfect for onboarding teammates or walking through a process yourself.

### Voice Narration

Talk through the workflow out loud while you record and FlowShot turns what you said into the step descriptions. Audio is transcribed with your own key (OpenAI or Groq) and matched to the steps it belongs to, so you narrate once instead of writing every step by hand.

### Guide Editor

Fix a guide after the fact without re-recording. Crop, annotate and redact any screenshot, rewrite a step with AI inline, drop headings and notes between steps, reorder or bulk-delete, and roll back through version history.

### Multi-Format Export

Share guides in whatever format fits your workflow:

| Format | Details |
|--------|---------|
| **Video** | Narrated walkthrough, mp4/H.264, with cursor movement |
| **PDF** | Print-ready, A4 portrait with auto page breaks |
| **DOCX** | Open and keep editing in Word |
| **HTML** | Self-contained, base64-embedded images |
| **Markdown** | Paste into Notion, GitHub, internal docs, wikis |

All exports are generated client-side. Nothing touches a server.

---

## Supported Browsers

| Browser | Status |
|---------|--------|
| Google Chrome | Supported |
| Mozilla Firefox | Supported |
| Microsoft Edge | Supported |
| Brave | Supported |

Available in English, Spanish, Brazilian Portuguese, French, and German. The AI description language is set separately, so you can run FlowShot in English and generate guides in Spanish, or any combination.

---

## Quick Start

### Prerequisites

- Node.js 22+
- [pnpm](https://pnpm.io) 10+
- Chrome, Firefox, Edge, or Brave (for testing)

### Install

```bash
git clone <your-repo-url>
cd flowshot
pnpm install
```

### Run in Development

```bash
pnpm dev                   # Chrome (MV3) with HMR
pnpm dev:firefox           # Firefox (MV3) with HMR
```

WXT launches a fresh browser instance with the extension loaded.

### Build

```bash
pnpm build                 # Chrome
pnpm build:firefox         # Firefox
pnpm zip:all               # Package both browsers
```

### Test

```bash
pnpm test                  # Run all tests once
pnpm test:watch            # Watch mode
pnpm test:cov              # Coverage report
```

### Lint & Format

```bash
pnpm lint                  # Check
pnpm lint:fix              # Auto-fix
pnpm format                # Format only
```

---

## Privacy & Storage

Guides, steps, and screenshots live on your device. There's no backend, no account, no telemetry. Your API keys (if you bring one) never leave your browser — they're stored locally and used to call the provider you chose directly.

Two things do leave the browser: site icons are fetched from Google's favicon service, which sends that site's domain, and the optional AI and voice features send text or audio to the provider you configured.

---

## Contributing

Contributions of all kinds are welcome: bug reports, feature requests, PRs, and translations.

See [CONTRIBUTING.md](./CONTRIBUTING.md) for development setup, project layout, and contributor guidelines.

---

## License

MIT License

Copyright (c) 2026 Jojin John

Developed by Jojin John

See [LICENSE](./LICENSE) for details.

---

<div align="center">

**Built by [Jojin John](https://github.com/jojinjohn)**

</div>

<!-- LINK GROUP -->

[license-shield]: https://img.shields.io/badge/license-MIT-4F46E5?style=flat-square&labelColor=1E1B4B
[license-link]: ./LICENSE

[mv3-shield]: https://img.shields.io/badge/manifest-v3-3730A3?style=flat-square&labelColor=1E1B4B
[mv3-link]: https://developer.chrome.com/docs/extensions/mv3/intro/

[local-shield]: https://img.shields.io/badge/storage-100%25%20local-4F46E5?style=flat-square&labelColor=1E1B4B
[local-link]: #-privacy--storage

[no-account-shield]: https://img.shields.io/badge/account-not%20required-4F46E5?style=flat-square&labelColor=1E1B4B
[no-account-link]: #-privacy--storage
