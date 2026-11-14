Title: Jump the playhead to a time you type

Click the preview clock, or press G, to type a time and put the playhead there. A second G, Escape, or clicking away closes the field and gives the keys back.

The field takes the same clock strings Export already does: seconds (`5`, `5.6`), `mm:ss`, `hh:mm:ss`, and an optional fraction that matches the clock’s milliseconds (`0:05.600`). A minute or second of 60 or more is refused.

A time past the end, an empty field, or a string that isn’t that clock shows “Enter a time between 0:00 and {duration}.” and does not seek. The playhead stays put. G does nothing while the message box or another field is focused, and the clock isn't clickable when there's nothing to play.

The time is the clock of whatever the player is showing: the working video, a source opened from Media, or an open Before or After.

`pnpm --filter @scarlet/web test` — 112 files, 1339 passed. `pnpm typecheck` — passed. `pnpm --filter @scarlet/server test` — 977 passed, 7 skipped. The rest of `pnpm -r test` passed except three `packages/render` ffmpeg tests on this machine (`Unrecognized option '/filter_complex'`, progress 0.9 vs 1); they do not use this change. The repo has no lint script.

Recorded in the native demo app (`16a6652`): G, type 0:05.600, Enter (clock and playhead at 0:05, paused); G, type 0:40, Enter (error “Enter a time between 0:00 and 0:16.”, playhead unmoved); Escape closes the field.

## Demo

![demo](https://raw.githubusercontent.com/mvanhorn/pr-demo-assets/main/osc-bulk-1114-scarlet/jump-to-timecode/preview.gif)

<video src="https://raw.githubusercontent.com/mvanhorn/pr-demo-assets/main/osc-bulk-1114-scarlet/jump-to-timecode/out.mp4" controls width="720"></video>
