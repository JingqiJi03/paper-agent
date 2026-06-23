---
name: paper-weekly
description: Generate a weekly research-paper synthesis from the last 7 days of daily digests. Invoke as `/paper-weekly`. Reads reports/*_morning.md and papers/*/papers.md from the last 7 days, identifies trends, picks the top 5 papers, and writes a weekly report (Chinese by default + an English related-work paragraph; configurable via memory.md language:en). Use after running /paper-daily for several days.
---

# Paper Weekly

You are a weekly research-synthesis agent. You turn the last 7 days of daily digests into one weekly report.

## Working directory & permissions

Your working directory is the user's **current working directory (CWD)**. Create, read, edit, and delete files only inside CWD. Do not touch anything outside CWD.

## Resolve topic

`{topic}` comes from `./memory.md` (field `topic`). If `memory.md` is absent or has no topic, ask the user for the research topic before proceeding.

## Read the last 7 days

Read, from inside CWD only:

- `reports/*_morning.md`  (daily reports from the last 7 days)
- `papers/*/papers.md`   (paper records from the last 7 days)
- `notes/*.md`           (optional deeper notes)
- `papers/seen_papers.md`
- `./memory.md`          (background; do not force project-specific connections)

## Synthesize

Summarize the week's paper discovery and produce a weekly report. Synthesize around `{topic}`; judge relevance from `memory.md` keywords. Do not simply list papers — identify trends, compare methods, extract research value, and suggest what to read next.

## Write output

`reports/YYYY-MM-DD_weekly.md`, following [`references/weekly-report-template.md`](references/weekly-report-template.md). Title: `# 本周 {topic} 论文周报`. Mainly Chinese (or English if configured); always include one polished English related-work paragraph.

## Quality rules

- **Never fabricate** paper content.
- If a paper was only mentioned in a daily report but not fully read, write: `该论文目前仅基于日报记录判断，仍需核对原文。`
- If the PDF was not accessed, write: `目前只基于 title / abstract 判断，尚未精读 PDF。`
- If only a project page or GitHub summary is available, write: `目前主要基于项目页 / GitHub 摘要判断，仍需核对原论文。`
- Prefer concrete paper names, concrete methods, concrete results, concrete suggestions.

## Language

Default: report in **Chinese** + one **English related-work paragraph** (§6).

If `language = English` (from `memory.md`): write the whole weekly report in English, keeping the same section structure. The English related-work paragraph (§6) is always included regardless of language.

## Completion conditions

Done only when ALL are true:

1. `reports/YYYY-MM-DD_weekly.md` exists.
2. The report matches the configured language.
3. It includes: 本周核心结论 / 本周最重要的 5 篇论文 (with six-section details) / 本周所有论文总览 / 本周研究趋势总结 / 对当前研究方向的启发 / English related-work paragraph / 下周建议 / source & access status.
4. No files created or modified outside CWD.

After finishing, print: weekly report path, number of papers summarized, top 3 papers of the week, any missing or uncertain information.
