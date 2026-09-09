# JobEval

JobEval turns a capable LLM into a market-specific recruitment-adviser persona.

Choose one operating prompt per country. The assistant then guides a candidate from a CV and job advertisements to an evidence-based fit assessment, a tailored CV, and an optional cover letter delivered as complete, self-contained [Typst](https://typst.app) source.

Documents use a text-first, single-column layout designed for straightforward text extraction. The German letter follows a DIN-5008-oriented digital business-letter layout; strict Form B conformity and rendered page counts require verification.

## Markets

| Market | Persona | Prompt | Version |
| --- | --- | --- | --- |
| Germany | Frau Schmidt | [Frau-Schmidt-Germany](Frau-Schmidt-Germany) | 1.2.0-rc1 |
| Spain | Elena Martínez | [Elena-Martinez-Spain](Elena-Martinez-Spain) | 1.0.0-rc1 |
| Brazil | Helena Duarte | [Helena-Duarte-Brasil](Helena-Duarte-Brasil) | 1.0.0-rc1 |

Spain means Spain, not all Spanish-speaking countries. Brazil means Brazil, not Portugal or other Portuguese-speaking countries. Germany is the primary DACH edition; Austria and Switzerland are not fully localized.

Each prompt file is self-contained. Copy one file into the LLM as system or custom instructions. Do not mix two personas in the same chat.

## How to use

1. Copy the prompt for the target country into a capable LLM as the operating instructions.
2. Send your CV or structured career history and one or more job advertisements.
3. Review the compatibility assessment and explicitly select one job (`J1`, `J2`, …).
4. Receive the CV as Typst source, answer remaining letter questions, then receive the letter.
5. Save and compile, for example:

```bash
typst compile lebenslauf.typ
typst compile anschreiben.typ
```

Browser compilation: [typst.app](https://typst.app).

Chat follows the candidate's language, including Portuguese. Document language follows the employer instruction or the advertisement.

The assistant does not submit applications, contact employers, or upload your data.

## What this release does not claim

- Not an ATS score, hiring decision, or interview probability.
- Not universal ATS compatibility.
- Not legal advice on AGG, GDPR, visas, or qualification recognition.
- Missing evidence is not treated as a confirmed unmet requirement.
- Cover letters are optional. Salary questions are conditional.
- Source generation is not PDF creation. Page counts are verified only after compilation.

## Changelog

### Unreleased

First Brazil edition (`Helena-Duarte-Brasil`, 1.0.0-rc1).

- Same architecture as v1.2.0: per-job state, turn router, evidence-based scoring, STOP contract, self-contained Typst output.
- Consultative recruiter read after the score (30-second read, tailoring levers, perception risks, screening questions, suggested decision).
- Triage mode for four or more advertisements with a comparison table and CV-reuse analysis.
- Contract regime (CLT, PJ, internship) and work mode (on-site, hybrid, remote) as a weighted operational dimension.
- Brazilian localization: seniority labels, degree types, diploma revalidation, professional council registration, language scale, salary expectation format, affirmative vacancies, LGPD privacy defaults, screening platforms.
- Phase 4 offers a cover letter, a short application message or form-field texts, depending on the channel.
- Output format switch: Typst (default), self-contained HTML or plain text.

### v1.2.0

Germany (`Frau-Schmidt-Germany.txt`, 1.2.0-rc1) and first Spain edition (`Elena-Martinez-Spain.txt`, 1.0.0-rc1).

- Explicit per-job state and deterministic phase routing.
- Transparent evidence-based compatibility scoring.
- Missing evidence distinguished from confirmed unmet requirements.
- Targeted intake; previously answered questions are not repeated.
- Safe handling of target changes, factual corrections and compile errors.
- Privacy defaults without overstating AGG requirements.
- No inferred CEFR levels, date precision or qualification equivalence.
- No nationality-based authorization assumptions or cultural stereotypes.
- Data-first Typst structure and safer list rendering.
- Removed missing-image placeholders.
- Optional cover letter and conditional salary questions.
- Honest compilation, page-count, ATS and DIN conformity claims.
- Separate self-contained prompt per country. `german_recruiter_persona_prompt.txt` is replaced by `Frau-Schmidt-Germany.txt`.

## License

MIT. See [LICENSE](LICENSE).
