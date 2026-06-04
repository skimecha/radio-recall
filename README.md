Radio Recall
A browser-based trainer for the listen → retain → read-back skill at the core of aviation radio communications. It builds that ability from the ground up: starting with single spoken words and digits, working through sentences and mental math, and finishing with full ATC clearance read-backs. You answer out loud — the app listens, transcribes, and scores your response.
Live: https://<your-username>.github.io/radio-recall/
Why
Effective radio work is really four sub-skills stacked together: hearing accurately, holding information in working memory, processing it, and reading it back in the correct order. Jumping straight to full clearances overloads all four at once. This tool isolates them and ramps difficulty only after you've demonstrated mastery, so each layer is solid before the next is added.
How it works

Press Transmit (or Start session in continuous mode).
A transmission plays via text-to-speech. The on-screen text stays blurred so you're training your ears, not your eyes.
The microphone opens automatically and listens until you stop speaking.
Your spoken answer is transcribed and graded; the answer is then revealed so you can compare.
Advance to the next item or retry.

You must answer 10 in a row correctly to advance a level — a deliberate mastery bar, not a participation threshold.
Features

Voice-first grading. Speak your answer; the app captures and scores it. A typed fallback is always available.
Aviation-aware scoring. Digit strings and ATC items are read as digit-by-digit values (e.g. "two seven zero" → 270, "six thousand" → 6000), while math and word-problem answers are parsed as true cardinals ("fifty nine" → 59). You can speak naturally in either context.
Step mode. One press runs the full play → listen → score cycle, then waits for you to choose Next or Retry.
Continuous mode. Loops hands-free: correct answers advance to a new item, misses auto-replay the same item so you can nail it before moving on. Stop anytime.
Adjustable pause between rounds in continuous mode (1.5 / 3 / 5 seconds).
Playback speed control (0.6×–1.2×) to simulate a fast-talking controller as you improve.

The progression
#LevelWhat it trains1–3Single → two → three wordsRaw auditory memory4–7Digit strings, 1 to 7 digitsNumber retention (frequencies, squawks, altitudes)8Word + numberMixing two information streams9–10One → two sentencesHolding meaning, not just sounds11–12Math, then word problemsExtracting a value from speech under load13–15ATC one item → two items → full clearanceThe real read-back skill
Running it
Online (recommended): Use the GitHub Pages link above. A real https:// origin lets the browser remember your microphone permission, so you grant it once.
Locally: Download index.html and open it in your browser. Note that opening via file:// causes most browsers to re-request microphone permission on each attempt — this is a browser security behavior, not a bug. Hosting on any static host (GitHub Pages, Netlify, Cloudflare Pages) over HTTPS resolves it.
Hosting on GitHub Pages

Create a public repository and add index.html to the root.
Go to Settings → Pages, set the source to Deploy from a branch, select main / / (root), and save.
After a minute, your site is live at https://<your-username>.github.io/<repo>/.
On first use, choose Allow while visiting the site when prompted for the microphone.

Browser support
Speech recognition works best in Chrome and Edge, which provide the Web Speech API. Firefox and Safari have limited or no support; in those, use the Type-instead fallback. Recognition routes audio through the browser's speech service, so an active internet connection improves responsiveness.
Privacy
Everything runs in your browser. There is no backend and no account. The only outbound traffic is the browser's own speech-recognition service (in Chrome/Edge) and the web font loaded from Google Fonts on first visit.
Customizing
The content lives in plain arrays near the top of the <script> block in index.html — WORDS, SENTENCES, MATH, WORDPROBLEMS, ATC1, ATC2, and ATCFULL. Edit or extend these to add your own vocabulary, local airport names, or region-specific phraseology. The LEVELS array defines the progression order and can be reordered or expanded.
Known limitations

Recognition accuracy varies by accent, microphone, and background noise; the revealed transcript ("heard: …") lets you see exactly what was captured and retry if it misheard.
This is a recall and phraseology drill, not a certified training aid. It complements, but does not replace, instruction from a CFI or formal study of the AIM.

License
MIT — free to use, modify, and share.
