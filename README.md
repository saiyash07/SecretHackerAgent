# The Secret Agent Hacker Terminal & Mini-Game

| | |
|---|---|
| **Name** | Saiyash Poojari |
| **Student Number** | 150096725136 |
| **Project** | The Secret Agent Hacker Terminal & Mini-Game |
| **Live Website** | https://saiyash07.github.io/SecretHackerAgent/ *(expected URL – not yet verified; test it after enabling Pages)* |
| **GitHub Repository** | https://github.com/saiyash07/SecretHackerAgent |

**Course Unit:** Unit 3 — AI Applications  **Course Outcome:** CO3-P

## Project overview
A light-theme, cyberpunk-style hacker terminal built with one `index.html` file (HTML + CSS + vanilla JavaScript). It has a Matrix-style rain background, a command terminal with fake "hacking" animations, a simulated system-status panel, a Web Audio sound system and a Secret Cipher decoding game.

## Project objectives
- Build a complete interactive app with no libraries, backend or build tools.
- Practise DOM events, timers, canvas animation and the Web Audio API.
- Practise AI-assisted debugging, code comments and `console.assert()` tests.
- Publish the result with GitHub Pages.

## Technologies used
HTML5, CSS3 (grid, transitions, keyframes), vanilla JavaScript, Canvas 2D, `requestAnimationFrame`, Web Audio API.

## Main features
- Matrix rain canvas (throttled to ~20 fps, pauses when the tab is hidden, handles resize)
- Terminal with prompt, blinking cursor, command history (↑/↓), quick-command buttons
- Animated progress bars and status messages for `scan`, `decrypt`, `hack`
- Live simulated system-status meters
- Secret Cipher game with scoring, hints and 6 messages
- Sound toggle with generated beeps (no audio before the first click)
- Reset button, accessible labels, keyboard-friendly, responsive layout
- User text is shown with `textContent` (no unsafe HTML insertion)

## Run locally
1. Download the project folder.
2. Double-click `index.html` (Chrome or Edge recommended).
3. Click **ENTER TERMINAL**. No server or install is needed.

## Terminal commands
| Command | What it does |
|---|---|
| `help` | List commands |
| `scan` | Fictional system scan with progress bar |
| `status` | Show simulated CPU / memory / network / shield |
| `decrypt` | Fictional decryption sequence |
| `hack` | Simulated hacking animation (0–100 %) |
| `clear` | Clear the terminal |
| `date` | Current date and time |
| `secret` | Hidden message (a clue) |
| `game` | Jump to the cipher game |
| `about` | Project information |
| `sound`, `reset` | Toggle audio / reset everything |

Only one animation can run at a time; other animated commands are politely refused until it ends (or you press Reset).

## Secret Cipher mini-game
1. Read the scrambled message (Caesar shift, reversed text, or A1Z26 numbers).
2. Type the decoded message and press **Submit** or Enter. Spaces and letter case are ignored.
3. Correct = **+10** points (**+5** if you used **Hint**). Empty answers are rejected.
4. Use **Next challenge** to continue, **Restart game** to reshuffle and reset the score.

## Secret Features
Two hidden Easter eggs unlock a full-screen animation, recoloured rain and **+50 bonus points** (once per session):
1. Type the name of "the chosen one" from *The Matrix* (the `secret` command gives a hint). It is **not** listed in `help`.
2. Press the classic Konami code on the keyboard: ↑ ↑ ↓ ↓ ← → ← → B A.

*(Spoiler for the marker: the hidden command is `neo`.)*

## AI-assisted debugging process
I will intentionally break one line, run the page, open DevTools (right-click → **Inspect** → **Console**), read the real red error, ask an AI assistant to explain and fix it, then verify the fix. A clean copy is saved as `index.backup-working.html`.

## The intentional bug and its actual fix
- **Original line:** `function updateScore(points) {`
- **Broken line:** `function updateScor(points) {`
- **Feature affected:** the score no longer updates when a cipher answer is correct (and the Easter-egg bonus).
- **Actual error observed:** `PLACEHOLDER – paste the real Console error here after you test it`
- **Actual fix:** `PLACEHOLDER – describe the fix after you apply it` (expected: rename the function back to `updateScore`)

## Matrix animation analogy
The comment above `drawMatrixRain()` in `index.html` compares the effect to raindrops sliding down a window: every column is a drop, the browser "wipes the glass" ~20 times per second with a see-through layer so old letters fade, each drop moves one row down and writes a new random character, and drops that fall off the bottom randomly restart at the top. `requestAnimationFrame` keeps asking for the next frame.

## Automated unit tests
Function under test: `clampProgress(value)` – returns a number from 0 to 100; empty, invalid and negative values become 0.
1. `clampProgress(50) === 50` – normal input
2. `clampProgress(0) === 0` – zero input
3. `clampProgress(-10) === 0` – negative input

They run at page load. Open DevTools → Console: **no assertion message means all three passed**; a failure prints "Assertion failed: Unit test N failed…". (During development, the function was also run in Node.js: it returned 0 for `""`, `NaN`, text and `undefined`, and 100 for 150.)

## Deploy with GitHub Pages
1. Sign in at github.com.
2. Click **+ → New repository**; name it `SecretHackerAgent`; choose **Public**; Create.
3. Click **uploading an existing file**; drag in `index.html`, `README.md`, `debugging-note.txt`; **Commit changes**.
4. Open **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select branch **main** and folder **/ (root)**; **Save**.
7. Wait 1–3 minutes and refresh; the site URL appears at the top of the Pages screen.
8. Open the URL and test it. Confirm the README links match the URL shown.
9. To update later: open the repo, **Add file → Upload files**, replace `index.html`, commit, wait for redeploy.

## Simulation notice
All "scanning", "decrypting" and "hacking" is **fictional**. The app makes no network requests and never touches real systems.

## Conclusion
This project combines animation, interactivity, audio, a game, tests and documentation in a single file that runs anywhere a browser does.
