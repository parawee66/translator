# Translator — Quick Ping‑Pong Phrase Translator for Travelers

[Live demo](https://parawee66.github.io/translator/) · Single‑page static HTML · Privacy‑first (no data collection)

Short description
A lightweight phrasebook‑style translator optimized for fast, back‑and‑forth conversational exchanges (ping‑pong style) for travelers — airports, restaurants, directions, and emergencies. Client‑side only; no server storage by default.

---

## Table of contents
- About
- Target audience
- Key features
- Privacy & data handling
- Quick examples
- Run locally
- Project structure
- Phrase pack format
- Contribution
- Deployment (GitHub Pages)
- Accessibility
- Troubleshooting
- Roadmap ideas
- License
- Contact
- Short Thai summary

## About
This repository hosts a single‑page web app (index.html) that simulates short conversational translation suitable for casual travelers. All logic runs in the browser (client‑side); there is no server backend or persistent storage unless you add one intentionally.

## Target audience
- Casual travelers who need short, actionable phrases rather than long-form translation.
- Mobile users who prefer tap‑to‑send phrases.
- Privacy‑conscious users — the app does not send or store conversations externally by default.
- Contributors who want to add curated phrase packs for languages, countries, or specific situations.

## Key features
- Ping‑pong style chat UI for quick send/receive flows.
- Single static HTML deployment — no backend required.
- Privacy‑first: no telemetry, analytics, or server‑side logging by default.
- Lightweight and responsive — optimized for mobile and low bandwidth.
- Easy to extend with curated phrase packs (JSON recommended).

## Privacy & data handling
- No conversation data is sent to the project’s servers by default.
- Conversation history exists only in the current page session (in memory). Refreshing or closing the page clears the history.
- If you integrate third‑party analytics, cloud storage, or remote APIs later, document them clearly, ask for consent, and provide opt‑out instructions.

## Quick examples
- Airport: "Where is the check‑in counter?"
- Restaurant: "Is this vegetarian?" / "Can I have the bill, please?"
- Directions: "How do I get to the train station?"
- Emergency: "I need a doctor" / "Please call the police"

## Run locally
1. Clone the repo:
   git clone https://github.com/parawee66/translator.git
   cd translator
2. Open `index.html` directly in a browser or run a static server:
   - Python 3: `python -m http.server 8000` → http://localhost:8000/
   - VS Code: use Live Server
3. The app is static — no build step required unless you introduce a bundler.

## Project structure (example)
- index.html — UI and client logic
- assets/ — icons, images, demo GIFs
- js/phrases.json — optional phrase packs (JSON)
- README.md — this file

Adjust based on your repo layout.

## Phrase pack format (recommended)
Store curated phrases in JSON for maintainability and community contributions.

Example:
[
  {
    "id": "airport_01",
    "source": "Where is the check-in counter?",
    "target": "เคาน์เตอร์เช็คอินอยู่ที่ไหน",
    "tags": ["airport", "travel", "practical"],
    "language": "th"
  },
  {
    "id": "restaurant_01",
    "source": "Can I have the bill, please?",
    "target": "ขอบิลทีครับ/ค่ะ",
    "tags": ["restaurant", "payment"],
    "language": "th"
  }
]
Guidelines:
- Keep phrases short and culturally appropriate.
- Use tags for categories (airport, restaurant, emergency, directions).
- Include a language code and optional tone/context notes.

## Contribution
Contributions welcome — phrase packs, UI improvements, accessibility fixes.

Suggested labels: `feature:phrasepack`, `i18n`, `bug`, `enhancement`.

Recommended workflow:
1. Fork the repo
2. Create a branch (e.g., `add-th-phrases`)
3. Add or update phrase JSON or UI changes
4. Open a Pull Request describing the use case and verification steps

If you want, I can add issue templates and label configuration to `.github/`.

## Deployment (GitHub Pages)
- To publish: place static files in the repository root or `docs/` and set Pages source to the `main` branch (root or `docs/`) under Settings → Pages.
- Demo: https://parawee66.github.io/translator/

## Accessibility & mobile tips
- Make buttons large enough for touch targets.
- Ensure sufficient color contrast.
- Provide ARIA labels for interactive elements and support keyboard navigation.

## Troubleshooting
- 404 on Pages: verify files are on the branch selected for Pages.
- Voice input/TTS requires HTTPS and microphone permissions.
- If translations feel off: prefer curated phrase packs over generic machine output.

## Roadmap ideas
- Optional voice input and TTS (user opt‑in).
- Downloadable offline phrase packs.
- Categories, favorites, and quick access shortcuts.
- Community‑contributed phrase packs via PRs.
- A small admin UI to preview and test phrase packs offline.

## License
Add a license file (e.g., MIT) if you want permissive reuse. This repo currently has no license file — add LICENSE to clarify permissions.

## Contact
Owner: parawee66 — https://github.com/parawee66

---

Short Thai summary
โปรเจคนี้เป็นเว็บแอพหน้าเดียวสำหรับนักท่องเที่ยวที่เน้นประโยคสั้น ๆ เพื่อสื่อสารอย่างรวดเร็วและเป็นส่วนตัว — ทำงานฝั่งไคลเอนต์เท่านั้นและโดยค่าเริ่มต้นไม่เก็บข้อมูลบนเซิร์ฟเวอร์
