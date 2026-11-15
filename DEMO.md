# Export captions as SubRip and WebVTT files

Recorded in the native Scarlet window (`pnpm desktop:demo`) on a private Linux Xvfb display at 1920×1080. The GIF is cropped to the app window (~960 px wide). Saves went to `~/Videos/Exports` with no replace prompts. The GTK sidebar has Home, Videos, Exports and Other Locations — no `src-tauri` bookmark.

The sample interview’s Export format menu lists **Captions (.srt)** and **Captions (.vtt)**. Saving each writes `Weekly interview — AI agents.srt` / `.vtt` with the two caption cues: Welcome back at 00:00:00,200–00:00:02,400, and Three things today at 00:00:05,600–00:00:08,000. SubRip uses comma milliseconds and cue numbers; WebVTT starts with `WEBVTT` and uses dots. The file cards in the recording are those saved files.

A custom range From **0:01.000** to **0:06.000** clips both cues and shifts them so 0 is the start of the range: Welcome back at 00:00:00,000–00:00:01,400, and Three things today at 00:00:04,600–00:00:05,000, saved as `Weekly interview — range.srt`.

On Tech brief — GPU shortage, which has no caption track, Export stays off and says: There’s no caption track to export. Ask Scarlet to add captions, then export again.
