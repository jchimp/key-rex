# Key-Rex

> Tiny Arms. Massive Entropy.

A browser-based password and cryptographic key generator. Runs entirely client-side — no backend, no data sent anywhere.

![Key-Rex screenshot](images/screenshot.png)

## Features

Seven generator modes, each accessible via a tab:

| Tab | What it generates |
|-----|-------------------|
| **Simple Phrase** | Memorable adjective+noun combos (Dinopass-style), with optional number/symbol/caps |
| **Random** | Cryptographically random characters; configurable charset and length (8–64) |
| **Diceware** | EFF Large Wordlist passphrases, 4–8 words (~44–88 bits entropy) |
| **Combination** | Modular builder — mix nouns, verbs, adjectives, numbers, and symbols with a custom separator |
| **Encryption Key** | AES/JWT-ready keys at 128/192/256/512-bit in hex or Base64 |
| **BIP39** | 12- or 24-word mnemonic phrases using the standard BIP39 wordlist |
| **Strength Checker** | Paste any password to get entropy, composition analysis, and crack-time estimates across 5 attack scenarios |

**Other highlights:**

- All randomness via `crypto.getRandomValues()` (CSPRNG)
- Copy-to-clipboard with visual feedback
- QR code display for each result
- Session history (last 10 items, persisted to localStorage)
- Dark/light theme toggle (remembers your preference)

## Usage

No build step. Open `index.html` in a browser.

Hosted via CDN (Bootstrap 5.3.3, Bootstrap Icons, qrcodejs) — requires an internet connection on first load for CDN assets.

## Browser Requirements

- Web Crypto API (`crypto.getRandomValues`)
- localStorage
- Modern browser: Chrome 26+, Firefox 21+, Safari 11+, Edge 79+

## Security Notes

- All generation happens in-browser. No passwords or keys are transmitted anywhere.
- The Strength Checker's crack-time estimates are illustrative; real-world cracking speed varies significantly by hardware and hash algorithm.
- The BIP39 tab generates word sequences from the standard wordlist but does **not** implement full BIP39 checksum validation — do not use the output as a real wallet seed without a compliant tool.

## License

MIT — see [LICENSE](LICENSE).
