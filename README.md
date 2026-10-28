# Content skills

The Claude Code skills we use every week to make, write and plan content. Each one lives in its own repo. This page lists them all so you can pick the ones you want and install them in one go.

## Install the ones you want

Paste this into Claude Code:

```text
Read https://github.com/ctskool/content-skills/blob/main/CLAUDE.md and follow it to install the content skills I pick.
```

Or clone this repo, open it in Claude Code, and say **"set me up"**.

Claude shows you the list, asks which ones you want, checks what they need, installs each one from its own repo, and tells you which keys to add. It never asks you to paste a key into the chat.

## Make

| Skill | Repo | What it does |
|---|---|---|
| Carousel engine (`/carousel`) | [ctskool/carousel-engine](https://github.com/ctskool/carousel-engine) | A video or repo in, 7 to 10 finished slides out. You approve twice. |
| `/animate` | [cth9191/animate](https://github.com/cth9191/animate) | Motion graphics videos written in JavaScript: 7 styles, or your own. |
| `/motion-design` | [cth9191/motion-design](https://github.com/cth9191/motion-design) | Turns motion design examples into full films through Higgsfield. |

## Write

| Skill | Repo | What it does |
|---|---|---|
| `/humanizer` | [ctskool/humanizer](https://github.com/ctskool/humanizer) | Strips the AI tells and rewrites in your saved voice. Includes `/humanizer-linkedin`, `/humanizer-x` and `/humanizer-email`. |
| `/content-cascade` | [ctskool/chase-ai-automations](https://github.com/ctskool/chase-ai-automations) | One YouTube video into a blog post, an X post and a LinkedIn post. |
| `/yt-package` | [ctskool/youtube-packaging](https://github.com/ctskool/youtube-packaging) | Thumbnail ideas and about 20 titles, scored on your channel's numbers. |
| `/yt-hooks` | [ctskool/youtube-packaging](https://github.com/ctskool/youtube-packaging) | Opening hooks: what viewers see, hear and read in the first seconds. |

## Plan

| Skill | Repo | What it does |
|---|---|---|
| `/morning-intel` | [cth9191/morning-intel](https://github.com/cth9191/morning-intel) | AI news, trending repos and your inbox, ending with today's content ideas. |
| `/outlier-radar` | [ctskool/chase-ai-automations](https://github.com/ctskool/chase-ai-automations) | Small channels' videos that beat their average, checked every 6 hours. |
| `/last30days` | [mvanhorn/last30days-skill](https://github.com/mvanhorn/last30days-skill) | What people said about a topic this month on Reddit, X, YouTube and more. |
| `/metrics-pull` | [ctskool/chase-ai-automations](https://github.com/ctskool/chase-ai-automations) | YouTube, Instagram and Claude usage numbers in one place. |

## What you'll need

- **Claude Code.** Every skill runs in it.
- **Keys**, only for the skills that use them. A free YouTube Data API key covers most of them. Keys go in `~/.claude/.env`, and each repo's `.env.example` lists its own.
- **The carousel engine** also needs the Codex CLI (signed in), Node and Python. It runs from its own folder, not from `~/.claude/skills`.
- **`/motion-design`** needs a Higgsfield account to generate video. Browsing and prompt drafting work without one.

## Updating

Run the install prompt again and pick the skills to update. Claude backs up your current copy before replacing it. Plugin skills (`/humanizer`, `/animate`, `/last30days`) update through Claude Code's plugin marketplace.

## License

This list is MIT. Each skill keeps the license in its own repo.
