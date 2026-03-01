---
name: edge-tts-dialog-audio
description: Use when generating MP3 audio for German learning dialogs from markdown materials. Covers speaker voice mapping, filename conventions, and reliable edge-tts command usage.
---

# Edge TTS Dialog Audio

Use this skill when the user asks to generate audio files for dialog lines in this repo.

## When to use

- Converting dialog lines from `04-materials/` into `.mp3` files
- Creating A/B speaker audio for practice dialogs
- Regenerating audio after text corrections

## Defaults

- Lukas voice: `de-DE-ConradNeural`
- Carolina voice: `de-DE-KatjaNeural`
- Output format: `.mp3`
- Output root: `05-audio/`

## Core commands

Single line synthesis:

```bash
edge-tts --text "Hallo! Ich heiße Lukas. Wie heißt du?" --voice de-DE-ConradNeural --write-media 01-lukas.mp3
```

Alternative speaker:

```bash
edge-tts --text "Ich heiße Carolina." --voice de-DE-KatjaNeural --write-media 02-carolina.mp3
```

From text file:

```bash
edge-tts --file line.txt --voice de-DE-ConradNeural --write-media line.mp3
```

## Voice discovery

List voices when connectivity allows:

```bash
edge-tts --list-voices
```

If listing fails/timeouts, keep using the confirmed defaults above.

## Recommended naming convention

For day-based materials, use numbered turn files so `mplayer *.mp3` plays in order:

- `05-audio/week-01/day-01/01-lukas.mp3`
- `05-audio/week-01/day-01/02-carolina.mp3`
- `05-audio/week-01/day-01/03-lukas.mp3`
- `05-audio/week-01/day-01/04-carolina.mp3`

## Workflow

1. Read the target material file (for example `04-materials/week-01/day-01.md`).
2. Extract only dialog lines (ignore instructions and answer key).
3. Assign speakers consistently as `Lukas` / `Carolina`.
4. Generate mp3 files with sequential numeric prefixes (`01-`, `02-`, ...).
5. Verify all expected files exist.
6. Report generated file paths.

## Reliability rules

- Keep one sentence per `edge-tts --text` call for easier debugging.
- Escape quotes in text safely.
- Do not overwrite silently if user requested preservation; otherwise overwrite is allowed.
- If a command fails, retry once with a shorter line split.

## Optional tuning

- Slower speech for beginners: `--rate=-15%`
- Slightly clearer volume: `--volume=+5%`

Example:

```bash
edge-tts --text "Ich komme aus Kolumbien." --voice de-DE-KatjaNeural --rate=-15% --volume=+5% --write-media 04-carolina.mp3
```
