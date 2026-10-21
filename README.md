<div align="center">
  <img src="PassGenPro_Logo.png" alt="PassGen Pro Logo" width="300"/>
  <h1>PassGen Pro</h1>
  <p><b>Advanced, client-side password generator</b> — vanilla HTML, CSS &amp; JavaScript, zero dependencies.</p>
  <p>
    <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License: MIT"/></a>
    <img src="https://img.shields.io/badge/dependencies-0-brightgreen.svg" alt="Dependencies: 0"/>
    <img src="https://img.shields.io/badge/build-none-lightgrey.svg" alt="Build step: none"/>
  </p>
</div>

---

## Overview

PassGen Pro generates strong passwords entirely in your browser. Nothing is ever sent over the network — the whole app is a single self-contained `index.html` file you can open, audit, and even save offline.

Randomness comes from the browser's **`crypto.getRandomValues`** API (with rejection sampling to avoid modulo bias and a secure Fisher–Yates shuffle), so generated passwords are cryptographically strong and unpredictable.

## Features

- **Configurable length** (6 – 40 characters) with a live slider.
- **Character-set selection**: lowercase, uppercase, digits, symbols, and custom characters.
- **Pronounceable passwords** for easier memorisation.
- **Enforce inclusion** of at least one character from each selected set.
- **Separator insertion** (custom separator and interval) for grouped output.
- **Bulk generation** — produce multiple passwords at once.
- **Password history** with pinning, export, and clear actions.
- **Auto-copy** on generation, plus manual copy buttons.
- **Entropy & strength meter** visual feedback.
- **Responsive dark UI** with an animated gradient background and theme toggle.
- **Keyboard shortcuts** — `Ctrl+Enter` to generate, `Ctrl+C` to copy.

## Quick Start

No installation or build step required:

```bash
# Option 1 — just open the file
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows

# Option 2 — serve it locally (optional)
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Usage

1. Open `index.html` in a modern browser.
2. Configure the options in the **Options Panel**:
   - Move the **Length** slider.
   - Check/uncheck the character sets you want.
   - Optionally add custom characters.
   - Toggle **Pronounceable**, **Exclude similar**, **Enforce all sets**, etc.
   - Set a **Separator** and interval for grouped output.
   - Choose how many passwords to **generate** at once.
3. Click **Generate** (or press `Ctrl+Enter`).
4. Copy the result with the copy button (or `Ctrl+C`). Previous passwords appear in **History**, where you can pin, export, or clear them.

## Security Notes

- All randomness uses `crypto.getRandomValues` — never `Math.random()`.
- Generation is 100% client-side; no passwords leave your machine.
- For maximum safety, open the file from disk (or an `offline:`/localhost origin) rather than a hosted URL, and consider exporting passwords directly into a password manager rather than leaving them in History.

## Project Structure

```
password-generator-pro/
├── index.html            # Complete application (HTML + CSS + JS)
├── PassGenPro_Logo.png   # Branding
├── LICENSE               # MIT
└── README.md
```

## Development

The entire application lives in a single `index.html` for easy distribution. To modify it:

- Edit the JavaScript inside the `<script>` tag.
- Adjust styles in the `<style>` block.
- The code is plain ES6 with no framework. Cryptographic randomness is provided by the `secureRandomIndex` and `secureShuffle` helpers built on `crypto.getRandomValues`.

## Contributing

Contributions are welcome! Please open an issue or pull request. For behavioural changes, keep the "no dependencies, single file" constraint in mind.

## License

Distributed under the [MIT License](LICENSE).

Made with ❤️ by Chie
