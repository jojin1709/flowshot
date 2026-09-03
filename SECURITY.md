# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in FlowShot, please report it responsibly.

**Do not open a public GitHub issue for security vulnerabilities.**

Instead, please email security concerns to: security@westpoint.io

Include:
- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

## What We'll Do

- Acknowledge receipt within 48 hours
- Provide an initial assessment within 5 business days
- Work with you to understand and resolve the issue
- Credit you in the release notes (unless you prefer anonymity)

## Security Considerations

FlowShot is a browser extension that:

- **Stores data locally only** — guides, screenshots, and settings never leave your browser
- **Requires no backend** — all processing happens client-side
- **Handles API keys optionally** — if you configure AI features, keys are stored in browser storage and used only for direct API calls
- **Requires microphone access optionally** — only if voice narration is enabled
- **Captures screenshots** — only while recording is active, stored in IndexedDB

### Data Flow

1. Screenshots are captured via `chrome.tabs.captureVisibleTab()` and stored in IndexedDB
2. API keys (if configured) are stored in `chrome.storage.local` and sent only to the configured AI provider
3. Microphone audio (if enabled) is processed locally or sent to the configured transcription provider
4. No telemetry, analytics, or tracking of any kind

### Permissions

FlowShot requests these permissions:

| Permission | Purpose |
|------------|---------|
| `storage` | Store guides, settings, and API keys locally |
| `activeTab` | Access the current tab for screenshot capture |
| `tabs` | Query and manage tabs for recording |
| `scripting` | Inject content scripts when needed |
| `unlimitedStorage` | Store unlimited screenshots and guides |
| `webNavigation` | Track page navigations during recording |
| `sidePanel` | Open the side panel (Chrome/Edge) |
| `offscreen` | Process voice narration (Chrome/Edge) |
| `<all_urls>` | Content script injection on all pages (optional on Firefox) |

## Supported Versions

| Version | Supported |
|---------|-----------|
| 1.x     | Yes       |

## Best Practices

- Keep FlowShot updated to the latest version
- Review your API key configuration periodically
- Disable voice narration if microphone access is not needed
- Export and backup important guides regularly
