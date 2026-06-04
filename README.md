Radio Recall
A browser-based trainer for the listen → retain → read-back skill at the core of aviation radio communications. It builds that ability from the ground up — starting with single spoken words and digits, working through sentences and mental math, and finishing with full ATC clearance read-backs — and then layers on a concurrent "fly the plane" tracking task to train the divided attention real cockpit work demands. You answer out loud; the app listens, transcribes, and scores your response.
Live: https://<your-username>.github.io/radio-recall/
Version: v1.3.0
Why
Effective radio work is really four sub-skills stacked together: hearing accurately, holding information in working memory, processing it, and reading it back in the correct order. Jumping straight to full clearances overloads all four at once. This tool isolates them and ramps difficulty only after you've demonstrated mastery, so each layer is solid before the next is added. The optional dual-task mode then adds the final real-world wrinkle: doing all of that while flying.
How it works

Press Transmit (or Start session in continuous mode).
A transmission plays via text-to-speech. The on-screen text stays blurred so you train your ears, not your eyes.
The microphone opens automatically and listens until you stop speaking.
Your spoken answer is transcribed and graded. The transmission is revealed only once you get it right (or you tap Reveal answer) — seeing it earlier would defeat the recall drill.
Advance to the next item or retry.

Advancing a level requires a streak of correct answers in a row, with the requirement scaled to difficulty: 5 for single-item levels, 7 for two-item levels, and 10 for everything beyond.
Features

Voice-first grading. Speak your answer; the app captures and scores it. A typed fallback is always available.
Aviation-aware scoring. Digit strings and ATC items are read as digit-by-digit values ("two seven zero" → 270, "six thousand" → 6000), while math and word-problem answers are parsed as true cardinals ("fifty nine" → 59). Speak naturally in either context.
Step mode. One press runs the full play → listen → score cycle, then waits for Next or Retry.
Continuous mode. Loops hands-free: correct answers advance to a new item, misses auto-replay the same item so you can nail it before moving on. Stop anytime.
Aviate (dual-task) mode. A compensatory tracking instrument appears: a marker drifts under simulated turbulence and you hold it in the center ring using the arrow keys or WASD while the radio drill runs. A round only counts toward your streak if your read-back is correct and you stayed on target (≥65% of the time). Drift off with a perfect read-back and it won't count — the "aviate first" priority, enforced.
Answer stays hidden until you succeed or choose to reveal it; wrong answers never spoil the transmission.
Adjustable pause between rounds in continuous mode (1.5 / 3 / 5 seconds).
Playback speed control (0.6×–1.2×) to simulate a fast-talking controller.
Progress persistence. Level, streak, and settings are saved in your browser and restored on reload. A Reset link clears them.

The cognitive idea behind Aviate mode
The dual-task design is grounded in Wickens' Multiple Resource Theory: attention draws on several semi-independent pools, separated by modality (visual vs. auditory), processing code (verbal vs. spatial), and response type (vocal vs. manual). The radio task is almost entirely verbal-auditory-vocal. The tracking task is deliberately silent and visual-spatial-manual, so the two compete minimally — mirroring how a pilot flies (a motor/spatial loop) while communicating (a verbal loop). Once holding the ring steady becomes automatic, attention is freed for the radio, which is exactly the fluency the real task requires.
The progression
#LevelWhat it trainsStreak to advance1–3Single → two → three wordsRaw auditory memory5 / 7 / 104–7Digit strings, 1 to 7 digitsNumber retention (frequencies, squawks, altitudes)5 / 10 / 10 / 108Word + numberMixing two information streams79–10One → two sentencesHolding meaning, not just sounds1011–12Math, then word problemsExtracting a value from speech under load1013–15ATC one item → two items → full clearanceThe real read-back skill10
Enable Aviate mode on any level to add the concurrent flying task on top.
Running it
Online (recommended): Use the GitHub Pages link above. A real https:// origin lets the browser remember your microphone permission, so you grant it once, and it enables saved progress to persist reliably.
Locally: Download index.html and open it in your browser. Opening via file:// causes most browsers to re-request microphone permission on each attempt — a browser security behavior, not a bug. Hosting over HTTPS resolves it.
Hosting on GitHub Pages

Create a public repository and add index.html to the root.
Go to Settings → Pages, set the source to Deploy from a branch, select main / / (root), and save.
After a minute, your site is live at https://<your-username>.github.io/<repo>/.
On first use, choose Allow while visiting the site when prompted for the microphone.

Controls

Arrow keys / WASD — fly the marker (Aviate mode only); ignored while typing in the answer box.
Enter — submit a typed answer.
Tap the Listening badge — stop the mic early instead of waiting for silence.

Browser support
Speech recognition works best in Chrome and Edge. Firefox and Safari have limited or no support; use the Type-instead fallback there. Recognition routes audio through the browser's speech service, so an active internet connection improves responsiveness.
Privacy
Everything runs in your browser. There is no backend and no account. Saved progress lives only in your browser's local storage. The only outbound traffic is the browser's own speech-recognition service (in Chrome/Edge) and the web font loaded from Google Fonts on first visit.
Customizing
Content lives in plain arrays near the top of the <script> block in index.html — WORDS, SENTENCES, MATH, WORDPROBLEMS, ATC1, ATC2, and ATCFULL. Edit or extend these for your own vocabulary, local airport names, or regional phraseology. The LEVELS array defines the progression; the winFor() function sets the per-level streak requirement; and the tracking difficulty is governed by the TURB, CTRL, KD, RING_R, and CTRL_TH constants in the Aviate section.
Versioning
This project uses semantic versioning (MAJOR.MINOR.PATCH).

v1.3.0 — Added Aviate dual-task tracking mode and browser-saved progress; adopted three-part version numbers.
v1.2 — Single-press auto flow (play → listen → auto-grade), continuous mode with auto-replay on miss, configurable pause, playback speed.
v1.1 — Hide-until-correct behavior, difficulty-scaled streak requirements, pre-blur flash fix.
v1.0 — Standalone build: 15-level progression, voice grading, typed fallback.

Known limitations

Recognition accuracy varies by accent, microphone, and background noise; the revealed transcript ("heard: …") lets you see what was captured and retry if it misheard.
The tracking task's turbulence and control feel are tuned for a general case and can be adjusted in the constants noted above.
This is a recall, phraseology, and attention-management drill — not a certified training aid. It complements, but does not replace, instruction from a CFI and formal study of the AIM.

License
MIT — free to use, modify, and share.
