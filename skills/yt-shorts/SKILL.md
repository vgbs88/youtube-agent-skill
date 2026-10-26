---
name: yt-shorts
description: >-
  Find the Shorts hiding inside a long video and write them, using the
  transcript to pick self-contained moments. Use for "cut this into shorts",
  "clip this", "repurpose this video", "what should I clip".
---

# yt-shorts

A Short cut out of a long video is not a clip of the best moment. It is a moment that **survives
without the video around it**, which is a much smaller set.

## Before you write

1. Find the channel profile. There is one Markdown file per channel in
   `~/.claude/youtube/channels/` (files starting with `_` are not channels). Read `_shared.md`
   there first if it exists: it applies to every channel, and the channel file wins where they
   differ. Use the channel the user named, or the one the task makes obvious - a pasted URL or
   handle, a topic only one channel covers. If there is more than one profile and it is not
   obvious, ask which channel before writing anything. The profile is that channel's voice: how
   it sounds, the words it never uses, who it is talking to, what it will not claim, its language
   and units. If the folder has no profiles, read `~/.claude/youtube/voice.md` instead. If neither
   exists, ask for **three of their own videos**, read or transcribe them, infer the voice, and
   write `~/.claude/youtube/channels/<channel-handle>.md` from `_template.md` in that folder. A
   script in the wrong voice is worse than no script, because they have to read it out loud.
2. Never invent a number, a result or a source. If a figure would strengthen it and you do not have
   one, ask for it or write the line without it.

## Picking

Read the transcript and find spans of 20-55 seconds where all three are true:

1. It opens on a complete thought. If the first sentence needs the previous minute, it is not a Short.
2. There is a turn in it - a claim, then something that complicates or proves it.
3. It ends on a line, not a trail-off.

Rank the candidates and show the user the top five with their timecodes and first line, so they can
reject one without reading the whole transcript.

## Writing each one

- **A NEW first line.** The long video's line assumes context this viewer does not have. Write the
  replacement and run it through `../yt-script/hookscore.py`.
- **On-screen text for the first two seconds**, different words from the spoken line.
- **A loop point**: what the last line sets up so the first line answers it.
- Vertical framing note - what gets cropped out of a 16:9 frame and whether that matters.

## The gate

Nothing here publishes. This skill writes and you publish. Every output ends in a block the user
copies, and the last line of every run is the question: **ship it, or change it?**
