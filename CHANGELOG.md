# V2 changes

Revised November 2, 2026, from the latest saved Moonlight game. The earlier releases are preserved separately.

- Purple and near-black replace the light Moonlight palette and original black/gold palette. Supporting text is larger; touch controls and color contrast are improved. Icons and home-screen metadata match.
- Classic Imposters see **YOU ARE THE IMPOSTER!** in a bold red announcement (32–44px), followed by a separate 22–26px hint. Normal words remain large. Question cards retain one identical interface with no role indicators.
- Starter selection uses a separate 32-bit draw and rejection sampling. It cannot depend on the content/role RNG, reveal order, or assignment history. Each player has exactly 1/N of the accepted secure-random outcomes. Repeated starters remain allowed.
- Reviewed **1,080 hints**: **461 changed, 619 retained** relative to the latest saved version. No words, categories, or question pairs were removed; the scale remains **45 categories and 200 question pairs**.
- Existing card locks, category balancing, used-content history, role weighting, category-name migration, player limits, navigation, confirmation, and replay remain intact.
- Release-specific asset URLs prompt browsers to load V2 files after an update.

## What the starter investigation found

Neither saved version hardcodes Player 3. The newer Moonlight engine already used secure rejection sampling during normal play. V2 retains that mathematically unbiased behavior, gives it a dedicated testable function, and separates its input from the content/role testing RNG. It also applies rejection to the legacy fallback path. A repeated starter in a short session can be a normal random outcome.

Modern supported browsers use `crypto.getRandomValues`. If that API is absent, the existing `Math.random` fallback keeps the game playable through the same rejection mapping; the exact uniform-source guarantee applies to the secure path, not to an unspecified legacy random generator.

## Included evidence

- `CLASSIC-AUDIT.md` — audit criteria, examples, and per-category totals.
- `HINT-AUDIT.csv` — all 1,080 entries, previous and V2 hints, decision, and review note.
- `RANDOMIZATION.md` — the 500,000-round simulation and mathematical explanation.
- `randomization-results.json` — exact counts and starter/role joint tables.
- `TESTING.md` — executed checks and verification limits.
- `README.md` — local play and update instructions.
