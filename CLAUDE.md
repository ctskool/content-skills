# Installer: content skills

You are installing Claude Code skills for content work. The user may have cloned this repo and said "set me up", or pasted a prompt pointing here. Follow these steps in order. Keep messages short and plain.

## 1. Show the list and ask

Show this numbered list and ask which ones they want. Accept numbers, names, a group ("all the write ones") or "all".

**Make**
1. Carousel engine (`/carousel`): a video or repo in, 7 to 10 finished slides out
2. `/animate`: motion graphics videos written in JavaScript
3. `/motion-design`: motion design examples into full films through Higgsfield

**Write**
4. `/humanizer`: strips the AI tells, rewrites in your voice (plus LinkedIn, X and email versions)
5. `/content-cascade`: one YouTube video into a blog post, an X post and a LinkedIn post
6. `/yt-package`: thumbnail ideas and scored titles from your channel's numbers
7. `/yt-hooks`: opening hooks for the first seconds of a video

**Plan**
8. `/morning-intel`: AI news, trending repos and your inbox, ending with content ideas
9. `/outlier-radar`: small channels' videos that beat their average
10. `/last30days`: what people said about a topic this month
11. `/metrics-pull`: YouTube, Instagram and Claude usage numbers in one place

## 2. Check the basics

Check only what their picks need, and report what's missing with the install command for their OS. Don't install system tools without a yes.

- `git`: all of them
- Python 3: 5, 6, 7, 8, 9, 11, and 1
- Node 18+ and Playwright Chromium: 1 and 2
- `ffmpeg`: 2 (and 1 for video sources)
- Codex CLI, signed in (`codex login`): 1
- `yt-dlp`: 5, and 1 for video sources

## 3. Install each pick

Clone source repos into `~/.content-skills-src/<repo>` (shallow clone, or `git pull` if it's already there). Before copying a skill into `~/.claude/skills/<name>`, check whether that folder exists. If it does, show what differs, back it up to `~/.claude/skills/<name>.bak-<date>`, and replace it only after a yes.

| # | Skill | How to install |
|---|---|---|
| 1 | Carousel engine | Ask where to keep it (default `~/carousel-engine`). Clone `https://github.com/ctskool/carousel-engine` there and follow the Install section of its README. It runs from that folder: the user opens Claude Code there and types `/carousel`. Don't copy it into `~/.claude/skills`. |
| 2 | animate | `claude plugin marketplace add cth9191/animate`, then `claude plugin install animate@animate` |
| 3 | motion-design | Copy `skills/motion-design` from `cth9191/motion-design` into `~/.claude/skills/motion-design`. Then point them to the repo's `docs/setup.md` to connect Higgsfield. |
| 4 | humanizer | `claude plugin marketplace add ctskool/humanizer`, then `claude plugin install humanizer@chase-ai-humanizer`. This brings the LinkedIn, X and email skills too. |
| 5 | content-cascade | Copy `skills/content-cascade` from `ctskool/chase-ai-automations`. Copy its `config.example.json` to `config.json` and fill it in with them. Follow that skill's README. |
| 6, 7 | yt-package, yt-hooks | Copy `skills/yt-package`, `skills/yt-hooks` and `skills/yt-search` from `ctskool/youtube-packaging`. Picking either one installs all three. |
| 8 | morning-intel | Copy `skills/morning-intel` and `skills/github-trending` from `cth9191/morning-intel`. Also copy its `skills/yt-search`, unless 6 or 7 is picked or a `yt-search` is already installed. Then walk through that repo's `CLAUDE.md` for the profile and the Gmail connector. |
| 9 | outlier-radar | Copy `skills/outlier-radar` from `ctskool/chase-ai-automations`. Set up `config.json` from `config.example.json`. Follow its README. |
| 10 | last30days | `claude plugin marketplace add mvanhorn/last30days-skill`, then `claude plugin install last30days@last30days-skill` |
| 11 | metrics-pull | Copy `skills/metrics-pull` from `ctskool/chase-ai-automations`. Set up `config.json` from `config.example.json`. Follow its README. |

If a `claude plugin` command fails, give the user the matching `/plugin marketplace add ...` and `/plugin install ...` lines to type in Claude Code themselves.

**yt-search:** youtube-packaging's copy uses the YouTube API and has the options yt-package needs. If 6 or 7 is picked, that copy wins. Never replace it with morning-intel's yt-dlp copy.

## 4. Keys

Make a list of the keys their picks use, from each repo's `.env.example`:

- `YOUTUBE_API_KEY`: 6, 7, 9, 11, and 8's YouTube section (free, from Google Cloud: enable "YouTube Data API v3", then create an API key)
- `YOUTUBE_CHANNEL_ID`: 6, 7 (their channel ID or @handle)
- Optional: `APIFY_API_TOKEN` (5), `INSTAGRAM_ACCESS_TOKEN` (11), `GITHUB_TOKEN` and `AGENTIC_OS_VAULT` (8)

Tell them to add these to `~/.claude/.env` themselves, one `NAME=value` per line, and say when they're done. Never ask them to paste a key into the chat, and never print a key's value. To check a key exists, test only whether the name is set.

## 5. Check and report

For each pick, run the lightest check its README gives (for example `python ~/.claude/skills/yt-package/scripts/channel_baseline.py`), or confirm the skill folder or plugin is in place. Finish with a table: skill, installed or not, what's left to do, and the first command to try. Plugin skills show up after a Claude Code restart.

Don't post, send or publish anything while testing. Don't schedule anything unless they ask. If they want a skill to run on a timer, point them to the Scheduling section of `ctskool/chase-ai-automations`.
