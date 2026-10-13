---
type: claude-summary
session_id: local_725ad44a-f51d-4cde-8edb-e3007c46f3b4
session_title: Cash Load interactive demo app
last_synced: 2026-10-12
status: active
tags: [claude-summary, cash-load, sales-demo, white-label-theming]
---
# Cash Load Interactive Demo App

## Context
Karl wanted a standalone, offline, serverless browser demo of Green Dot's Cash Load solution that can be zipped and sent to customers or colleagues. It must be easily rebrandable per partner, with Chirp (GD's in-house mock brand) as the baseline. It complements the Cash Loads Solution Guide used in early-stage sales.

## Artifacts
- Demo zip (~20 KB) and `index.html`, presented in that session's outputs folder; theming via `brand/brand.js` (name, 5 color slots, logo path, default ZIP, retailer list) plus `brand/logo.png`; README included
- Inputs: Figma WL Chirp Theming Guide (file UBVNrAYs610XXFd1jHblci), WL Chirp Design Subsystem (eHygkWApWMyFraCp3NrrjV, logo), White-Label SDK v2 (JY6OZaRE77QvqfnUELLNcR, "Deposit with App" barcode flow)
- Uploaded: "GDN Use Case Flows - Simple Version.pptx" (slides 11-14, 62, 64 useful), "CSC Serviceworks - Cash Loads Solution Overview - August 2026.docx" (example solution guide)

## Key findings
- Chirp tokens: Primary #1A335D (navy), Secondary #3BB54A (green), Tertiary #FD7B27 (orange), Primary Dark #0E1C33, Primary Light #2B5399, Positive #00B24B, Warning #F2793D, Negative #EB0000; grey scale #F7F7F7 to #000000; Poppins type scale 10pt to 48pt. Logo: green line-art hummingbird (SVG not retrievable via sandbox).
- Customer flow: discover cash load in app, enter location/permit device location, list retailers with fees, select retailer, display transaction- and retailer-specific barcode.
- In-store: retailer scans, validates with GD, GD sends auth request to partner, partner approves/declines, GD tells retailer to proceed, cash collected, POS closes and prints receipt, GD sends auth commit, partner credits account.
- Void: within 15-30 minute window retailer voids, GD forwards void to partner, partner reverses credit.
- Demo sections built: hero (stats: 90K+ locations, <4s auth SLA, $20-$500, real-time credit), 4-screen phone simulator, "At the Register" 4 steps, integration diagram (Store Locator/Barcode APIs, AuthRequest/Response, AuthCommit/Void), capabilities and GD vs partner roles.

## Decisions
- Pure HTML/CSS/JS with relative paths, CSS custom properties set from brand.js at runtime.
- System font stack instead of bundled Poppins (revisit later).
- Text logo fallback until the Chirp SVG is supplied.
- Karl pushed back on building flows before research; flows were rebuilt from his documented sequence.

## Open questions
- Supply Chirp logo SVG/PNG for embedding.
- Validate the stat values against the solution guide before external use.

## Next steps
- Embed real Chirp logo; optionally bundle Poppins.
- Upgrade retailer text badges to logos.
- Possibly add an interactive cashier/POS flow and a void scenario.

## Key sources
- https://www.figma.com/design/UBVNrAYs610XXFd1jHblci/WL-Chirp-Theming-Guide
- https://www.figma.com/design/eHygkWApWMyFraCp3NrrjV/WL-Chirp-Design-Subsystem
- https://www.figma.com/design/JY6OZaRE77QvqfnUELLNcR/White-Label-SDK-v2

## Resume prompt
> I'm building an offline, serverless HTML/CSS/JS Cash Load demo app for Green Dot sales, branded with our mock brand Chirp (navy #1A335D, green #3BB54A, orange #FD7B27; Poppins, currently system font) and rebrandable via `brand/brand.js` plus `brand/logo.png`. A v1 zip exists with hero, a 4-screen customer phone flow (location, retailers with fees, barcode), an at-the-register summary, an integration diagram (Store Locator/Barcode, AuthRequest/Response, AuthCommit/Void), and capability cards. Open items: real Chirp logo, retailer logos, a cashier/POS interactive flow, and possibly a void scenario. Please help me with: [next task].
