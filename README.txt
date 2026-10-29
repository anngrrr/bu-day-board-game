GAME TIMELINE

Files:
- index.html - game page
- teams.csv - team list
- wsp-logo.jpg - WSP logo extracted from the supplied background.pdf

CSV format:
number,name
1,Team Red
2,Team Black
3,Team Yellow
4,Team Pink
5,Team Blue

Use between 1 and 10 teams. Every team starts with 0 hours.
The default five teams match the physical bands, in order: red, black,
yellow, pink (magenta), and blue (cyan). Board colors are assigned by CSV row.

HOW TO START

Open a terminal in this folder and run:

uv run python -m http.server 8001

Then open:

http://localhost:8001

NOTES

- The design uses the supplied PDF's white background and small red WSP logo.
- The board fills the first screen; scroll down to enter hours.
- The board uses the available browser width with side padding, without a desktop width cap.
- Desktop side padding grows with the viewport (7%, from 64 to 160 pixels).
- Team labels on the board use compact light-gray panels without color strips.
  Final results retain their full-height team-color indicators.
  Pieces appear on the timeline, without duplicates in the team labels.
- Hour entry uses compact fields in a responsive grid below the board.
- The top-right indicator shows the current and completed rounds.
- The game has two rounds. Enter nonnegative whole hours for every team,
  then use Round 1 or Round 2 to add them to the running totals.
- Zero is allowed. Blank, negative, fractional, and exponential values are not.
  Values and cumulative totals must be safe JavaScript integers.
- Draft values are not applied until the round is recorded.
- Recorded hours and the final-results view survive page refresh in the same
  tab using sessionStorage. Unrecorded input values are not saved.
- Reset game clears both rounds and returns every team to 0 hours.
- The timeline ends at 55 hours; overtime starts after the 40-hour deadline.
  Larger totals are allowed and displayed in full; their pieces stop at 55.
- Show final results becomes available after both rounds are recorded.
  The page scrolls to the results, then nine staggered firework bursts of
  different sizes play over them, with dense glowing sparks and falling trails.
  Reduced-motion
  preferences skip the animation; refreshing saved results does not replay it.
  Results show total hours sorted from lowest to highest, without place numbers.
  Teams with equal hours retain their CSV order. The board remains in CSV order.
- Progress from the previous game format is not loaded. Changing the team
  list resets incompatible saved progress with a visible notification.
