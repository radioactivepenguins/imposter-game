# IMPOSTER — V2

Two pass-the-phone party games, updated with a purple-and-black theme. No accounts, backend, build tools, subscriptions, or external content services. Everything runs in ordinary HTML, CSS, and JavaScript.

## Play locally

Unzip the download and double-click `index.html` inside the game folder. Keep the `data` and `icons` folders alongside it. Choose a mode, type 3–25 players, and start. A server or Node installation is not required.

Players select their numbered cards in any order. Each player reads their assignment privately, then uses the back arrow or **Hide My Card**. Viewed cards lock identically. Once everyone is ready, discuss and vote aloud, then confirm **Reveal Results**.

Classic gives regular players one shared word and Imposters a shared hint. The default Imposter count is 1 for 3–6 players, 2 for 7–11, 3 for 12–16, 4 for 17–21, and 5 for 22–25. Optional adjustments always retain two regular players. Question Mode always gives exactly one player an alternate question; no player is told their role.

**Play Again** retains mode, group size, Imposter setting, and selected categories. Fresh independent starter selection does not try to prevent repeats. Keep the same Person numbers across rounds to benefit from the separate role-fairness history.

## Update your existing GitHub Pages game

1. Back up your existing repository or keep its previous commit available.
2. Open your repository on GitHub. Choose **Add file → Upload files**.
3. Upload the **contents** of this game folder to the same publishing location as V1. Replace matching files and preserve the `data/` and `icons/` paths. Do not upload only the ZIP or nest the game inside an extra version folder.
4. Commit the update to the branch already used by Pages. If your setup is `main` with `/(root)`, put `index.html` at the repository root. If you use `/docs`, update that folder instead.
5. Leave your existing Pages configuration, repository name, and account unchanged. Wait for the Pages deployment to finish, then open the same website URL and reload.

The runtime files to replace are `index.html`, `style.css`, `script.js`, `engine.js`, `data/classicWords.js`, `manifest.webmanifest`, and all four files inside `icons/`. The complete package also includes the unchanged `data/questionPairs.js` and `.nojekyll`. The reports can remain alongside the game but are not required for gameplay.

V2 uses release-specific stylesheet/script URLs to avoid reusing V1 assets. Finish an active round before updating. If Safari's home-screen app still displays the old icon, remove only the shortcut and add it again after opening the updated site.

## First-time GitHub Pages deployment

Create a **public** repository, upload the game folder's contents, and commit to `main`. In **Settings → Pages**, choose **Deploy from a branch**, select **main** and **/(root)**, then save. Use the address shown by **Visit site**. GitHub Free supports Pages for public repositories. [Official GitHub Pages instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

The game has not been published or uploaded during this revision. No example username or site address is hardcoded. Your hosted game works while your Mac is off.

## iPhone home screen

Open your actual published address in Safari, choose **Share → Add to Home Screen**, and add it as **Imposter**. Use **Open as Web App** if offered. Installation is optional. There is no service worker; the hosted page needs a connection to load, then gameplay runs locally.

## Saved data and privacy

Content history uses the same V1 localStorage key so used words, questions, and role counts continue to work. All 1,080 word labels and 45 categories remain unchanged from the latest saved revision. Existing category/word alias migrations are preserved.

The session marker stores settings, never secret assignments. Reloading during a game offers a fresh-round restart when sessionStorage is available. If storage is blocked, gameplay still works in memory and reload returns home. Closing a reveal, switching away from the page, or navigating back hides the card and keeps it locked. Results require confirmation.

This prevents accidental spoilers in normal pass-the-phone play. A browser-only game is not designed to hide its runtime data from someone deliberately inspecting developer tools.

## Review the revision

- `CHANGELOG.md`: concise changes and preserved behavior.
- `CLASSIC-AUDIT.md`: audit summary and category totals.
- `HINT-AUDIT.csv`: all 1,080 reviewed entries and decisions.
- `RANDOMIZATION.md`: unbiased-selection explanation and 500,000-round results.
- `randomization-results.json`: full simulation counts.
- `TESTING.md`: executed checks and remaining real-device verification.

The databases remain editable plain JavaScript files. Preserve existing question IDs and word labels when only changing hints so stored history keeps its meaning.
