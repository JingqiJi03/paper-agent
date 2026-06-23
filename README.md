# paperboy

English | [中文](README.zh-CN.md)

> A Claude Code plugin that reads papers for you every day and generates daily/weekly digests. `/paper-daily <topic> <keywords>` produces a structured report in one shot.

## What it does

- Searches arXiv / the web for your **topic + keywords** (WebSearch by default; falls back to `curl` / arXiv API / GitHub raw when unavailable).
- **Deduplicates** against already-read papers (via `papers/seen_papers.md`).
- Ranks papers by **relevance to your topic** — High / Medium / Low.
- Summarizes every important paper in a **six-section structure**: Challenge / Motivation / Insight / Main method / Effect / Results / Research Value.
- Generates a **daily report** (Chinese by default) + an **English related-work** section; can be switched to fully English.
- `/paper-weekly` synthesizes the last 7 days of daily reports into a **weekly report**.
- All files are written to your **current working directory** — the plugin itself carries no personal data, so it works anywhere you copy it.

## Prerequisites

- [Claude Code](https://claude.com/claude-code) installed and logged in.
- (Optional) `ANTHROPIC_API_KEY` set.
- WebSearch / WebFetch available; falls back to `curl` + arXiv API when not.

## Install

**Option A — marketplace (recommended)**

```
/plugin marketplace add https://github.com/JingqiJi03/paperboy
/plugin install paperboy
```

**Option B — manual clone**

```bash
git clone https://github.com/JingqiJi03/paperboy ~/.claude/plugins/paperboy
```

Restart or reload Claude Code, then `/paper-daily` and `/paper-weekly` are available.

## Usage

```
/paper-daily robot manipulation VLA pi0 flow matching
```

- The first phrase = topic, the rest = keywords.
- No args: `/paper-daily` → reads `memory.md` in the current directory to reuse the last config.
- English report: add `lang=en` to the args, or set `language: en` in `memory.md`.

```
/paper-weekly
```

- Synthesizes the last 7 days of daily reports + paper records into a weekly report. Best run after several days of `/paper-daily`.

## Files it creates in your current directory

| File | Purpose |
|---|---|
| `papers/seen_papers.md` | list of already-read papers (dedup baseline) |
| `papers/<date>/papers.md` | six-section summaries of all papers that day |
| `reports/<date>_morning.md` | daily report |
| `reports/<date>_weekly.md` | weekly report |
| `memory.md` | auto-generated on first run; stores topic/keywords/language/watch-list |

## Customization (`memory.md`)

The first `/paper-daily` auto-generates `memory.md`. You can edit it manually:

```markdown
topic: <one-line research topic>
keywords:
  - <keyword>
  - <keyword>
language: zh          # zh (default, Chinese report) or en (English report)
watch-repos:          # optional: GitHub awesome-lists / repos to monitor
  - <repo url>
```

Rule: **command-line args override `memory.md`**. So to change the topic temporarily, just pass args to `/paper-daily` — no need to edit the file.

## Self-check (after install)

1. Create an empty directory and `cd` into it.
2. Run: `/paper-daily retrieval-augmented generation RAG benchmark`
3. Verify:
   - `papers/seen_papers.md`, `papers/<today>/papers.md`, `reports/<today>_morning.md`, `memory.md` were created.
   - The daily report contains **Top 3** and an **English related-work** section.
   - The report title is `# 今日 retrieval-augmented generation Paper 晨报` (dynamically built from your topic — proving no domain is hardcoded).
   - `papers/seen_papers.md` recorded today's papers.

If no new papers are found that day, the daily report is still generated and clearly states "no new papers today" — never an empty report, never fabricated content.

## License

MIT
