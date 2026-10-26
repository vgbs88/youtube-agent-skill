---
name: yt-seo
description: >-
  Write the description, tags and search-facing text for a YouTube video,
  aimed at the query a real person types. Use for "write my description",
  "tags", "SEO", "help this video get found", "nobody is finding this".
---

# yt-seo

Search is a smaller lever than packaging and a bigger one than people think for evergreen videos.
For a video aimed at the subscriber feed, say so and spend the effort on `/yt-package` instead.

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

## The description

- **The first two lines are the only ones anyone reads.** They show above "...more" and they are
  the search snippet. Say what the video gives them, in the words they would have typed.
- Then the link or the resource, if there is one, so it is above the fold.
- Then chapters (`/yt-chapters` writes them).
- Then the long version: what is covered, who it is for, what it assumes.

## Tags, honestly

Tags are a weak signal and YouTube has said so. Use them for disambiguation - spellings, the tool
names, the abbreviations people actually type - and stop. Fifteen is plenty. A wall of tags is not
a strategy and stuffing unrelated ones is against the terms.

## The query test

Before handing anything over, write the three search queries this video should win, and check the
title and first two description lines contain the words in those queries. If they do not, the
problem is the title, not the description.

## The gate

Nothing here publishes. This skill writes and you publish. Every output ends in a block the user
copies, and the last line of every run is the question: **ship it, or change it?**
