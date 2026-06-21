# epccs — GitHub profile repo

This repo's name matches the GitHub username `epccs`, which makes `README.md`
the special "profile README" shown on https://github.com/epccs. It is Ron's
public-facing "about me" page, not a software project. There is no build,
test, or lint step — the only output is the rendered Markdown.

## Files

- `README.md` — the profile landing page (intro + "question of the year" musings).
- `experience.md` — reverse-chronological work history, oldest entries are the most polished.
- `embedded_systems.md` — Ron's view of what embedded engineering is and his skill summary.
- `crystal.md` — technical note on crystal oscillator PCB layout.
- `emi.md` — technical notes on automotive EMI compliance and load dump.
- `past_projects.md` — 1099/freelance project writeups.
- `328pb_xtl_setup.png` — layout image referenced by `crystal.md`.

These pages aren't cross-linked from `README.md` except `embedded_systems.md`
linking to `crystal.md`. If adding a new page, consider whether it should be
linked from somewhere a visitor would actually find it.

## Voice and content

- First person, conversational, sometimes stream-of-consciousness. Ron thinks
  out loud (e.g., logging AI chats he had about EE questions as a kind of
  personal study log). Preserve that voice — don't flatten it into generic
  corporate-bio language.
- Technical sections (crystal.md, emi.md) are written to demonstrate hands-on
  EE expertise to potential clients/employers. Keep technical accuracy intact
  when editing for grammar.
- Entries get added in bursts tied to whatever Ron is currently focused on,
  not as part of a planned content strategy. Expect the repo to look uneven
  in places — that's normal, not a defect to "fix" by restructuring.

## Known recurring writing issues to watch for

Ron has flagged that this content needs spelling/grammar cleanup and that he
doesn't always keep it up to date. Common patterns seen in the existing text:

- Typos on common words: "switching" → "swithing", "front" → "frount",
  "microcontroller" → "microcontroler", "believe" → "beleive",
  "authentication" → "athuntication", "increase" → "increas",
  "privilege" → "privlage", "functional" → "functinal", "perfect" → "perfict",
  "provided" → "provid", "Catalyst" → "Catalist", "Control" → "Contorl",
  "Experience" → "Experance", "April" → "Aprl".
- Missing/wrong punctuation and run-on sentences, especially in README.md's
  paragraph-style intro.
- Inconsistent capitalization of proper nouns/acronyms.
- When fixing typos, do a pass per file rather than guessing — don't assume
  a typo list is exhaustive.

## Editing guidance

- Fix spelling and grammar without rewriting Ron's voice or restructuring
  content unless asked. Small, surgical edits over wholesale rewrites.
- `experience.md` entries follow a consistent block format (`### Title`,
  fenced `Dates Employed / Location` block, bullet list). Match it for new entries.
- Dates: "now" is used for current/ongoing roles in `experience.md` — don't
  replace with a hardcoded date.
