# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A structured German language course for a beginner (A0) learner. It is content-driven, not a software project. The primary deliverable is learner-ready material files in `04-materials/`.

For the full teaching mission, constraints, and pedagogical rules, read `AGENTS.md`.

## Directory structure

```
00-assessment/    # Placement test, answer key, level rubric
01-syllabus/      # Week-by-week syllabi (week-01.md through week-06.md)
02-sessions/      # Templates for guided sessions and pronunciation checklists
03-tracking/      # Learning log, CEFR checklist, fossil error log, weekly review
04-materials/     # Daily self-study packs (week-01/day-01.md, etc.)
05-audio/         # Generated MP3 files — gitignored, produced with edge-tts
skills/           # Skill definitions (edge-tts-dialog-audio/SKILL.md)
```

## Material format

Each file in `04-materials/week-XX/day-XX.md` must follow this structure:

1. **Input (~25 min)** — dialogue or text + key vocabulary
2. **Práctica controlada (~35 min)** — fill-in, matching, writing exercises
3. **Producción (~20 min)** — free production task (written + spoken)
4. **Review (~10 min)** — review of prior day's errors or vocabulary
5. **Clave de respuestas** — answer key at the bottom

The syllabus file for the corresponding week (`01-syllabus/week-XX.md`) must link to each day file. Keep them in sync.

## Audio generation

Audio lives in `05-audio/week-XX/day-XX/NN-speaker.mp3`. Use the `edge-tts` CLI:

```bash
# Lukas voice
edge-tts --text "Hallo! Ich heiße Lukas." --voice de-DE-ConradNeural --write-media 01-lukas.mp3

# Carolina voice
edge-tts --text "Ich heiße Carolina." --voice de-DE-KatjaNeural --write-media 02-carolina.mp3

# Slower speech for beginners
edge-tts --text "..." --voice de-DE-KatjaNeural --rate=-15% --volume=+5% --write-media 04-carolina.mp3
```

Files are numbered sequentially so `mplayer *.mp3` plays turns in order. See `skills/edge-tts-dialog-audio/SKILL.md` for the full workflow.

## Tracking files to update

After any session or material change, encourage updating:
- `03-tracking/learning-log.md` — daily log
- `03-tracking/issue-log-fossil-errors.md` — recurring errors
- `03-tracking/cefr-can-do-checklist-a0-a1.md` — milestone tracking
