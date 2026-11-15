Title: Export captions as SubRip and WebVTT files

Export can save the video’s captions as a SubRip (`.srt`) or WebVTT (`.vtt`) file. Cue times are each clip’s timeline times, to the millisecond. SubRip uses `HH:MM:SS,mmm` and numbered cues; WebVTT starts with `WEBVTT` and uses `HH:MM:SS.mmm`. Hidden tracks, disabled clips, and empty text are left out. Overlapping cues are written as they are. A custom range keeps only cues that overlap it and shifts them so 0 is the start of the range, so the file stays in time with a range MP4. Word-level karaoke timing and the uppercase caption style are not written to the sidecar.

If more than one caption track is visible, Export offers a track picker; with one, it uses that track. On a project with no caption track, Export stays off and says: There’s no caption track to export. Ask Scarlet to add captions, then export again. If the chosen track has no cues, or a custom range leaves none, Export stays off and says: There are no captions in this range. Video options stay hidden for these formats, as they do for a Resolve timeline export. The save dialog opens on the project name with a SubRip or WebVTT filter.

Tested on Linux, after `pnpm --filter @scarlet/agent build`, `pnpm --filter @scarlet/mcp build`, and `node apps/server/scripts/gen-skills.mjs`:

- `pnpm --filter @scarlet/timeline typecheck` — passed
- `pnpm --filter @scarlet/shared typecheck` — passed
- `pnpm --filter @scarlet/mcp typecheck` — passed
- `pnpm --filter @scarlet/agent typecheck` — passed
- `pnpm --filter @scarlet/server typecheck` — passed
- `pnpm --filter @scarlet/web typecheck` — passed
- `pnpm --filter @scarlet/timeline test` — 13 files, 253 passed
- `pnpm --filter @scarlet/shared test` — 13 files, 123 passed
- `pnpm --filter @scarlet/server test` — 77 files, 1006 passed, 7 skipped
- `pnpm --filter @scarlet/web test` — 115 files, 1343 passed
- `pnpm --filter @scarlet/mcp test` — 20 files, 339 passed
- `pnpm --filter @scarlet/agent test` — 10 files, 155 passed
- `cargo test --locked --manifest-path apps/desktop/src-tauri/Cargo.toml` — 181 passed
- Caption writer, `export.srt` / `export.vtt` routes, Export sheet (including a stale track id while the sheet is open), `exportJobs`, mock client, and demo data-URL save tests included above
- This repo has no lint script

Native app: `pnpm desktop:demo` on Ubuntu, private Xvfb `:99` at 1920×1080. From the sample interview, Export saved both caption files into `~/Videos/Exports`. A custom range 0:01–0:06 clipped both cues and shifted their times. On a project with no caption track, Export stays off and says: There’s no caption track to export. Ask Scarlet to add captions, then export again. macOS and Windows save dialogs were not run.

## Demo

![demo](https://raw.githubusercontent.com/mvanhorn/pr-demo-assets/main/osc-bulk-1114-scarlet/export-caption-sidecars/preview.gif)

<video src="https://raw.githubusercontent.com/mvanhorn/pr-demo-assets/main/osc-bulk-1114-scarlet/export-caption-sidecars/out.mp4" controls width="720"></video>
