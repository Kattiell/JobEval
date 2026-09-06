# JobEval

AI persona prompt that turns a capable LLM into **Frau Schmidt**, a senior German HR director for the DACH market.

Version **1.1** (2026-09-06) · [MIT License](LICENSE)

She takes a candidate from raw CV + job ads to a complete *Bewerbungsmappe*: fit analysis, an ATS-safe Lebenslauf, and a DIN 5008 Form B Anschreiben — both as complete, compilable [Typst](https://typst.app) source.

This release supersedes v1.0 (phase-rush, chat-paste collision, Typst escaping, fold-mark clip).

## Contents

- [`german_recruiter_persona_prompt.txt`](german_recruiter_persona_prompt.txt) — operating manual / system prompt (source of truth)
- [`LICENSE`](LICENSE) — MIT

## How to use

1. Copy the entire prompt file.
2. Paste it as the **system prompt**. If the chat UI has no system field, send it as the first message.
3. Provide your CV (plain text or clearly structured) and one or more job descriptions. You can paste prompt + CV + ads in one shot.
4. Follow the stops. Frau Schmidt will not skip phases.

| Phase | What you get | You do next |
| --- | --- | --- |
| 1 Assessment | Compatibility report (0–100) per job | Pick **one** posting |
| 2 Lebenslauf | One Typst CV | Compile + answer intake questions |
| 3 Intake | Start date, salary, Anlagen, motivation | Answer in one message |
| 4 Anschreiben | One Typst letter (DIN 5008 Form B) | Compile |

Compile in the browser at [typst.app](https://typst.app) or locally:

```bash
typst compile lebenslauf.typ
typst compile anschreiben.typ
```

Every assistant turn ends with:

```
[STOP — waiting for: …]
```

## What v1.1 changes

- Silent **Turn Router** (branches A–F) so greeting, assessment, CV, and letter never collide
- Hard stop after Phase 1: zero Typst until you name a job
- Lebenslauf and Anschreiben never in the same turn
- Candidate text goes into `#let` strings so emails, URLs, `$`, `_`, and `#` compile
- No Falzmarken / no negative `#place` (clips in Typst 0.11+)
- AGG default: no photo, age, birth date, marital status, religion, or nationality unless you ask
- Font lock: Libertinus Serif only; no packages, no uploaded fonts

## Document contract

- Output is Typst only (never Markdown or LaTeX application files)
- Must compile as-is on typst.app and with `typst compile`
- Real data only; unknown facts are omitted, never invented
- Chat follows the candidate's language; documents follow the job ad
- CV: 1 page for junior / internship / Werkstudent, 2 pages max otherwise
- Letter: one page, bold Betreff without the word “Betreff”, no comma after “Mit freundlichen Grüßen”

## Requirements

- A capable long-context LLM (the prompt is about 17k characters)
- Typst in the browser or via CLI
- Your CV and target job postings

## Releases

| Tag | Date | Notes |
| --- | --- | --- |
| v1.1 | 2026-09-06 | Turn Router, Typst string discipline, DIN 5008 Form B without fold marks |
| [v1.0](https://github.com/MaloneFreak/JobEval/releases/tag/v1.0) | 2026-09-05 | First public release |

## License

MIT.
