# Wheel of Fortune: Toss-Up Showdown

A single-page, single-HTML-file recreation of Wheel of Fortune's "Toss-Up" round, built for in-person team building events. Run it on a laptop, mirror it to a TV or projector, and use it to host a 4-round buzz-in game between two on-stage players per round.

No backend, no build step, no dependencies — everything runs in the browser in memory.

## Features

- 4 rounds, one puzzle (category + answer) per round, plus a 5th "emergency" puzzle kept in reserve
  - After Round 4, the host can either **Finish Game** (normal ending) or **Play Round 5 (Emergency)** if something went wrong earlier and an extra question is needed
  - The emergency round works exactly like the other 4 — same reveal, buzz-in, and judging — it's just optional
- One shared "Buzz In" button — whoever calls it out first, the host clicks it; the app doesn't track which of the two on-stage players it was
- Letters reveal one at a time, in random order, on a customizable timer
- Buzzing in at any point after reveal starts pauses the reveal for the host to judge
- Host manually judges each buzz-in as Correct/Incorrect
  - Correct: reveals the full answer, confetti + flash + sound
  - Incorrect: reveal resumes and the Buzz In button is immediately available again — no limit on how many buzz-ins a puzzle can have
- Scoring is not tracked by the app — the game master keeps score manually across all teams
- "Reveal Answer" button for when nobody solves it
- Restart game or jump back into setup at any time
- Classic dark blue / gold Wheel of Fortune board styling with flip-in letter tiles
- Simple buzz/correct/incorrect sound effects (generated with the Web Audio API, no audio files)

## Running it locally

1. Download `index.html` (or clone this repo).
2. Open the file directly in any modern browser (double-click it, or drag it into a browser window). No server required.
3. On the setup screen:
   - **Puzzles** tab: enter a category and answer for all 4 rounds plus the emergency 5th, or pick a saved preset from the dropdown in the top-right and click **Load Preset** to fill them in automatically.
   - **Settings** tab: set the letter-reveal speed.
4. Click **Start Game**, then **Start Round** to begin revealing letters.
5. When either player buzzes in (in person — shout it out, raise a hand, physical buzzer, whatever you use), click the **BUZZ IN** button, then mark their guess **Correct** or **Incorrect**. Record the point value manually — the app doesn't track scores or which player buzzed.
6. After Round 4, choose **Finish Game** to end normally, or **Play Round 5 (Emergency)** if you need the backup question.

To project it: mirror or extend your laptop display to the TV/projector — the layout scales up automatically for large screens.

## Adding a new preset

Presets are hardcoded puzzle sets in `index.html`, in the `PRESETS` array near the top of the `<script>` block. To add one for a future game, add another entry:

```js
{
  name: 'Preset 2',
  puzzles: [
    { category: 'Category text', answer: 'ANSWER TEXT' },  // Round 1
    { category: 'Category text', answer: 'ANSWER TEXT' },  // Round 2
    { category: 'Category text', answer: 'ANSWER TEXT' },  // Round 3
    { category: 'Category text', answer: 'ANSWER TEXT' },  // Round 4
    { category: 'Category text', answer: 'ANSWER TEXT' }   // Round 5 (emergency)
  ]
}
```

then commit and push — it'll show up in the preset dropdown on the setup screen once deployed. Loading a preset only fills in the puzzle fields; those fields can still be freely edited afterward for a one-off change, but edits aren't saved anywhere unless they're added back into this list.

## Tech

Just one HTML file (`index.html`) with inline CSS and vanilla JavaScript. No build tooling, no npm install, no server.
