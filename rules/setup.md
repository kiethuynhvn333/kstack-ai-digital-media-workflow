# Setup — rules 1–8

**Load when:** `profile.md` or `workspace.md` is missing, the user says "set up" or "update my
setup", or a task needs an answer these files mark unknown.

## Rules
1. Read `profile.md` and `workspace.md` if they exist. Ask about missing information; do not repeat
   questions already answered. Write the full path of this folder in `workspace.md` (kstack folder).
2. **Your work.** "What is your job?" (e.g. performance marketer) · "Which company do you work
   for? If you are at an agency or freelance: which clients?" · "Which channels do you handle?"
   (e.g. Facebook ads, Google ads, SEO, email) · "Do you manage separate brands, countries, clients
   or products? List them, or say no." Each one becomes a `<segment>` folder; no = `cross-segment`.
3. **Goals.** "What do you want to grow right now, by how much, and by when?" (e.g. 2,000 new
   sellers a month by December) · "Any limit, like a budget or a max cost per result?" Each goal
   with its own target becomes a project.
4. **How we work.** "Short or detailed answers?" · "Should I explain the basics, or skip them?" ·
   "How do you want results: in chat, a document, slides or a spreadsheet?"
5. **What I may do.** "What can I do without asking you? (e.g. read reports, write drafts)" ·
   "What must I always ask first? (e.g. change a budget, send a message, publish)" · "Does anyone
   else have to approve spending or publishing? Who?"
6. **Tools and numbers.** "Which tools and data can I use? (e.g. Google Ads, Meta, BigQuery,
   Google Sheets)" · "When two numbers disagree, which one do you trust?" · "Who can double-check a
   number for you, and how fast? (e.g. the data team, about 1 hour)" · "Your timezone and
   currency?" · "How often should we review what we learned? (default: every Monday)"
7. Ask one topic (rules 2–6) per message, as a short numbered list in the words above, ending with
   "Say skip for anything you don't know yet." Plain words only: never say segment, objective,
   cadence or canonical to the user. Let the user start useful work early; keep unanswered business
   facts and permissions `unknown`. An unknown permission means "ask first".
8. When editing is allowed, show the proposed content in plain words (say "areas", "goals", "how
   often we review", not file headings like Segments or Objectives), then save confirmed working
   preferences in `profile.md` and business, tool, and permission settings in `workspace.md`. Keep actual company
   and client configuration private. Revisit setup when the user asks or an answer is outdated.

## What setup produces
| Answer from | Saved to |
|---|---|
| Rule 4 (working style) | `profile.md` |
| Rules 1, 2, 3, 5, 6 (kstack folder, business, goals, permissions, tools, timezone, currency, review) | `workspace.md` |
| Each objective (rule 3) | `projects/<objective>/` copied from `projects/_template/`, with its `README.md` brief filled in |
| Each objective × each segment (rule 2) | `projects/<objective>/<segment>/` copied from `projects/_template/_segment/` |

Start from `profile.example.md` and `workspace.example.md`. Unknown answers stay in the file as
`unknown`, never deleted, so the next session knows what is still missing.

## Done when
- Both files exist and the user has confirmed their content.
- Every project folder has a filled-in `README.md`, a `worklog.md`, a `deliverables/` folder, and each
  segment has its four files (`open-items.md`, `decisions.md`, `experiments.md`, `knowledge.md`).
- You ran `scripts/validate.sh` and fixed what it reported before telling the user setup is done.
  If you cannot run shell commands, say so and list the structure you could not check. A web chat
  (Gemini, ChatGPT or Claude in a browser) cannot save files to the user's computer: say so at the
  start, give the files to download, and never claim a file was saved.
- The first worklog entry records that setup ran, what was answered, and what is still unknown.
- Your last message ends with one bold line telling the user their files are saved on this computer
  only, and to type **commit and push** to back them up (just **commit** if there is no GitHub copy).
