# Wheel of Fortune: Toss-Up Showdown

A single-page, single-HTML-file recreation of Wheel of Fortune's "Toss-Up" round, built for in-person team building events. Run it on a laptop, mirror it to a TV or projector, and use it to host a 4-round buzz-in trivia game between 2-10 teams.

No backend, no build step, no dependencies — everything runs in the browser in memory.

## Features

- 4 rounds, one puzzle (category + answer) per round
- 2-10 teams with editable names
- Letters reveal one at a time on a customizable timer
- Any team can buzz in at any point after reveal starts
- Host manually judges each buzz-in as Correct/Incorrect
  - Correct: awards that round's points, reveals the full answer, confetti + sound
  - Incorrect: locks that team out for the rest of the puzzle; others can keep buzzing
- Configurable point values per round
- Live running scoreboard
- "Reveal Answer" button for when nobody solves it
- Restart game or jump back into setup at any time
- Classic dark blue / gold Wheel of Fortune board styling with flip-in letter tiles
- Simple buzz/correct/incorrect sound effects (generated with the Web Audio API, no audio files)

## Running it locally

1. Download `index.html` (or clone this repo).
2. Open the file directly in any modern browser (double-click it, or drag it into a browser window). No server required.
3. On the setup screen:
   - **Puzzles** tab: enter a category and answer for all 4 rounds (or click "Load Sample Puzzles" to try it out).
   - **Teams** tab: set 2-6 team names.
   - **Settings** tab: set point values per round and the letter-reveal speed.
4. Click **Start Game**, then **Start Round** to begin revealing letters.
5. When a team buzzes in (in person — shout it out, raise a hand, physical buzzer, whatever you use), click that team's "BUZZ" button on screen, then mark their guess **Correct** or **Incorrect**.
6. Repeat through all 4 rounds. Final scores and the winner are shown at the end.

To project it: mirror or extend your laptop display to the TV/projector — the layout scales up automatically for large screens.

## Tech

Just one HTML file (`index.html`) with inline CSS and vanilla JavaScript. No build tooling, no npm install, no server.
