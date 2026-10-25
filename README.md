# Problem Set 6 kit: two agents that work while you sleep

MGMT 6110 Human-AI Collaboration, due Wednesday 28 October 2026, 9:00 AM
Prof. Sungjong Roh, PhD, Lee Kong Chian School of Business, Singapore Management University

Dear Team,

This folder holds the one task of Problem Set 6, the US market earnings watcher and assessor. It is a pair of Claude
routines in one GitHub repository: a watcher that writes a morning brief at 6:07 AM, and an assessor that checks the
watcher's work at 6:37 AM. Please copy the folder into a public repository of your own, and follow the step-by-step
guide. You write no code: a small Python tool in the folder fetches the data and keeps the files, and your routines do
the judging.

Claude's cloud is not allowed to reach the SEC's websites. So the folder also holds a small GitHub Action, **SEC
fetch**, which runs on GitHub's own computers at 5:10 AM and 5:40 AM, asks the SEC for what the two routines need, and
keeps the answers in `sec_cache/` in your repository. Your routines read them from there, so you set up no special
network in Claude.

## The timeline

Problem Set 6 opens on Sunday 25 October at 9:30 PM. Please set the task up that evening or on Monday 26 October, at any time of day. Your first Run now reads last week's results: the
radar lists every company that reported in the previous week, and the watcher reads two of them, picked at random, in
full. Then the scheduled 6:07 AM run on Tuesday 27 October reads the companies that reported on Monday in the US, and
the 6:37 AM assessor checks them. Please rate S5 after Tuesday's 6:37 AM run. Wednesday's runs are the last before
the deadline.

## What each item is for

| Item | What it is |
|---|---|
| `earnings-extractor-assessor/` | The task. The watcher lists every US company that filed its results with the SEC since its last run. For the companies on its watchlist and two companies picked at random from those that reported, it pulls out the main figures, each with a quote, the guidance, two to four things management says and the tone of the release. The assessor checks each quote against the release and each figure against the company's quarterly filing, builds a table of the company's fundamentals, judges what management says against those numbers, and rates the watcher's work. |
| `REFLECTION_TEMPLATE.md` | Groups 5 and 6 only: your reflection on R1 to R5. |

## The pages that go with this kit

| Page | What it is for |
|---|---|
| `MGMT6110_Problem_Set_6.html` | The problem set: what you hand in, the steps, the questions, and section B for Groups 5 and 6. |
| `MGMT6110_PS6_Step_by_Step_Guide.html` | Every click for your repository, the SEC fetch, your dashboard and your two routines, with what you should see. |
| `MGMT6110_PS6_Self_Assessment_Form.html` | The form that makes your JSON file, for example `PS6_Oppenheimer_Robert.json`. |

## Inside the task folder

| File | What it is for |
|---|---|
| `PROMPT_WATCH.md` | The watcher's job, step by step. Every run reads it again. |
| `PROMPT_ASSESS.md` | The assessor's job, step by step. |
| `CLAUDE.md` | The house rules both agents follow, including what they must never do. |
| `config.json` | Your GitHub username and a contact email, because the SEC asks every program that reads its filings for one. |
| `.github/workflows/sec-fetch.yml` | The SEC fetch on GitHub. Your Mac hides this folder: press Command-Shift-. (full stop) in Finder to see it before you upload. |
| `index.html` | Your dashboard on GitHub Pages. |
| `data/`, `briefs/`, `sources/` and `sec_cache/` | What the agents and the SEC fetch keep from one run to the next. Only the tool writes in `data/`, `sources/` and `sec_cache/`. |
| `tools/` | The Python tool the routines and the SEC fetch run, and saved copies of the data for testing. |
| `_dev/` | Sample runs for previewing the dashboard. The routines never use it. |
| `.nojekyll` | An empty, hidden file that lets GitHub Pages show every file. Please keep it. |

## Real data, read with care

The task reads real, public data: the SEC's filings. The agents only read. They never post, send or change anything
outside your repository. The briefs report company results and check them, and never recommend buying or selling.

## When to pause your routines

Please pause the Week 8 routines you no longer need, and pause your two PS6 routines after our class on Wednesday
28 October, so that their runs do not keep using your plan.

Enjoy,
Prof. Roh
