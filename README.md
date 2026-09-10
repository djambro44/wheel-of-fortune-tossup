# Wheel of Fortune: Toss-Up Showdown

A single-page, single-HTML-file recreation of Wheel of Fortune's "Toss-Up" round, built for in-person team building events. Run it on a laptop, mirror it to a TV or projector, and use it to host a 4-round buzz-in game between two on-stage players per round.

No backend, no build step, no dependencies — everything runs in the browser in memory.

## Features

- 4 rounds, one puzzle (category + answer) per round
- Two buzz-in controls per round — Player 1 / Player 2 — for whichever two reps are on stage that round
- Letters reveal one at a time, in random order, on a customizable timer
- Either player can buzz in at any point after reveal starts
- Host manually judges each buzz-in as Correct/Incorrect
  - Correct: reveals the full answer, confetti + flash + sound
  - Incorrect: locks that player out for the rest of the puzzle; the other player can keep buzzing
- Scoring is not tracked by the app — the game master keeps score manually across all teams
- "Reveal Answer" button for when nobody solves it
- Restart game or jump back into setup at any time
- Classic dark blue / gold Wheel of Fortune board styling with flip-in letter tiles
- Simple buzz/correct/incorrect sound effects (generated with the Web Audio API, no audio files)

## Running it locally

1. Download `index.html` (or clone this repo).
2. Open the file directly in any modern browser (double-click it, or drag it into a browser window). No server required.
3. On the setup screen:
   - **Puzzles** tab: enter a category and answer for all 4 rounds (or click "Load Sample Puzzles" to try it out).
   - **Settings** tab: set the letter-reveal speed.
4. Click **Start Game**, then **Start Round** to begin revealing letters.
5. When a player buzzes in (in person — shout it out, raise a hand, physical buzzer, whatever you use), click that side's "BUZZ" button on screen, then mark their guess **Correct** or **Incorrect**. Record the point value manually — the app doesn't track scores.
6. Repeat through all 4 rounds.

To project it: mirror or extend your laptop display to the TV/projector — the layout scales up automatically for large screens.

## Tech

Just one HTML file (`index.html`) with inline CSS and vanilla JavaScript. No build tooling, no npm install, no server.
