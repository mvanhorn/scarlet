# Jump to a time — native demo

Scarlet’s preview clock is a control. Click it, or press G, type a time, press Enter. The playhead goes there.

Recorded in the native demo app from `feat/jump-to-timecode` (`16a6652576071c0d579dce457108c4c218bfd8f5`). `out.mp4` and `preview.gif` are cropped to the player, clock and timeline so the field and error stay readable.

## What the recording shows

1. Clock at **0:00 / 0:16**.
2. Press G. Field opens, pre-filled with the current time.
3. Type **0:05.600**, Enter.
4. Clock **0:05 / 0:16**, picture overlay **0:00:05.600**, playhead on that moment, still paused.
5. Press G. Field opens on **0:05.600**.
6. Type **0:40**, Enter.
7. Error **Enter a time between 0:00 and 0:16.** Field stays open. Playhead and overlay stay at 0:05.600.
8. Press Escape. Field closes. Clock **0:05 / 0:16**, playhead unmoved.

`out.mp4` is 24s, 1040×820, 30 fps, 720 frames, H.264 yuv420p. `preview.gif` is the same 24s at 960×758, 12 fps (288 frames).

## Checks

- `pnpm --filter @scarlet/web test` — 113 files, 1345 passed
- `pnpm typecheck` — passed
- `pnpm --filter @scarlet/server test` — 75 files, 977 passed, 7 skipped
- Three `packages/render` ffmpeg tests failed on this machine and do not use this change
- No lint script in the repo
