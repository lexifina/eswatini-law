# How this repository was made (Eswatini)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| EswatiniLII (the Judiciary of Eswatini, on the Laws.Africa Peachjam platform) | <https://eswatinilii.org> | 2026-10-28 | CC BY-NC 4.0, crediting EswatiniLII as the source (https://eswatinilii.org/terms-of-use/) |
| Internet Archive Wayback Machine | <https://web.archive.org> | 2026-10-28 | Archived copies of EswatiniLII pages; the content licence is EswatiniLII's |
|  | <https://commoncrawl.org> | 2026-10-28 | the content's licence is EswatiniLII's |
| EswatiniLII (the Judiciary of Eswatini, on the Laws.Africa Peachjam platform) (Prevention of Corruption Act) | <https://eswatinilii.org> | 2026-10-30 | CC BY-NC 4.0, crediting EswatiniLII as the source (https://eswatinilii.org/terms-of-use/) |
| Internet Archive Wayback Machine (Prevention of Corruption Act) | <https://web.archive.org> | 2026-10-30 | Archived copies of EswatiniLII pages; the content licence is EswatiniLII's |
|  | <https://commoncrawl.org> | 2026-10-30 | the content's licence is EswatiniLII's |
| EswatiniLII (the Judiciary of Eswatini, on the Laws.Africa Peachjam platform) (Serious Offences (Confiscation of Proceeds) Act) | <https://eswatinilii.org> | 2026-10-30 | CC BY-NC 4.0, crediting EswatiniLII as the source (https://eswatinilii.org/terms-of-use/) |
| Internet Archive Wayback Machine (Serious Offences (Confiscation of Proceeds) Act) | <https://web.archive.org> | 2026-10-30 | Archived copies of EswatiniLII pages; the content licence is EswatiniLII's |
|  | <https://commoncrawl.org> | 2026-10-30 | the content's licence is EswatiniLII's |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `constitution` | Constitution of the Kingdom of Swaziland, 2005 | 1 | 2006-02-08 to 2006-02-08 |
| `suppression-of-terrorism` | Suppression of Terrorism Act, 2008 | 2 | 2008-05-11 to 2017-08-25 |
| `money-laundering` | Money Laundering and Financing of Terrorism (Prevention) Act, 2011 | 2 | 2012-03-23 to 2016-09-28 |
| `prevention-of-corruption-act` | Prevention of Corruption Act, 2006 | 1 | 2007-02-01 to 2007-02-01 |
| `serious-offences-confiscation-of-proceeds-act` | Serious Offences (Confiscation of Proceeds) Act, 2001 | 1 | 2001-10-18 to 2001-10-18 |

The build made 7 commits:

| Commits | Kind |
| ---: | --- |
| 5 | first version of an act |
| 2 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-30.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 7 laws in the record.
- 14 tags.

## Dates

Each commit is dated at noon (Africa/Mbabane) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Not applied: every version is dated by EswatiniLII's own expression date, or by the commencement date EswatiniLII states for the act as published. No date is computed from a default rule. https://eswatinilii.org/legislation/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `39835ab00a1618e158e9154d27b85e57f132411d482beabfacb1f19da78809ef` (771501 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3d00541d258745461ab52b1b0cb4e1716a27a95d`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

7 versions of 5 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

A second build from the same corpus into an empty folder gave identical hashes for all 7 history commits and 14 tags (history tip `05a2b59a025ad56ca0fc4374c950560dab712caa`).

## Decisions made by hand

- Acts were chosen by what the archived source supports: of the 361 EswatiniLII works with archived expression pages, only a few have more than one dated expression with text. Phase 1 takes the Constitution (one expression) and the two acts whose every expression is archived with text and whose amending Act is named: the Suppression of Terrorism Act 2008 (amended by Act 11 of 2017) and the Money Laundering and Financing of Terrorism (Prevention) Act 2011 (amended by Act 5 of 2016).
- The Employment Act 1980 and the Companies Act 2009 were not taken: EswatiniLII's only archived expression with text is dated 1 December 1998 and marked "Consolidation" for both, a date before the Companies Act 2009 was even made, so it is a placeholder, not the date the text was in force. Their other archived expressions (Employment Act 1981-01-01, Companies Act 2010-04-01; 2023 captures) carry no text. Most other EswatiniLII acts share this 1998-12-01 date or have one expression only.
- EswatiniLII marks the Constitution and the Money Laundering and Financing of Terrorism (Prevention) Act 2011 with "[Note: The original publication document is not available and this content could not be verified.]" The text is EswatiniLII's; it was not compared with the Gazette, because the Gazette copies are scans and no OCR is used.
- Money Laundering and Financing of Terrorism (Prevention) Act 2011: EswatiniLII states "Commenced on 23 March 2012 by Money Laundering and Financing of Terrorism (Prevention) (Amendment) Act, 2016", and the 2016 Act's page lists it as commencing the 2011 Act. The first version is dated 2012-03-23 as stated; this commencement was fixed by an Act of 2016.
- In the Suppression of Terrorism Act, section 28's editorial note reads "[paragraph (e) substituted by section 5 of Act 11 of 2017]" but links to /akn/sz/act/2011/11; the credit follows the note's words and the History tab, which names only Act 11 of 2017 for that version.
- Licence: EswatiniLII (the Judiciary of Eswatini) licenses its primary and secondary law content CC BY-NC 4.0, crediting EswatiniLII as the source; CC BY-NC allows only non-commercial use. Every expression page is read from the Internet Archive's copy, for the configured acts only. No legal text was given to a model.
- Version dates are EswatiniLII's expression dates. Laws.Africa's terminology guide (https://docs.laws.africa/getting-started/terminology-guide) says "Amendments to Principal works come into force on the Commencement date of the Amending work" and that the first point in time is "the work as originally published"; so an amendment's expression is dated by its commencement (in force), and an act's original expression by its publication, which is replaced by the commencement date the page states.
- Credits: a version whose History names exactly one amending law (and no consolidation) between it and the previous version is credited to that law for every provision that changed. Otherwise a provision is credited only to laws that EswatiniLII's editorial note inside that provision links to; the rest are unexplained (publisher).
- Editorial notes (akn-remark) are left out of the text and used only as credit evidence, except where a provision has no other text (repealed or spent), where the note is the provision's whole printed content.
- Part, Chapter and Division headings are left out; each provision file starts with its own number and heading. Every other text of each version is in a provision file: this is checked per version (verification.json, fidelity).
- Constitution: the first version is dated 2006-02-08, the commencement date EswatiniLII states ("Commenced on 8 February 2006 by Constitution of the Kingdom of Swaziland (Date of Commencement) Proclamation, 2006"), not 2005-07-26, the date of its expression (Gazette publication).
- Suppression of Terrorism Act: the first version is dated 2008-05-11, the commencement date EswatiniLII states ("Commenced on 11 May 2008"), not 2008-04-11, the date of its expression (Gazette publication).
- Money Laundering Act: the first version is dated 2012-03-23, the commencement date EswatiniLII states ("Commenced on 23 March 2012 by Money Laundering and Financing of Terrorism (Prevention) (Amendment) Act, 2016"), not 2011-08-23, the date of its expression (Gazette publication).
- Act 5 of 2016 (Money Laundering and Financing of Terrorism (Prevention) (Amendment) Act, 2016): its EswatiniLII page has no text (PDF only), so its dates come from the page's History tab (https://web.archive.org/web/20260420221703id_/https://eswatinilii.org/akn/sz/act/2016/5/eng@2016-09-28): assented to 2016-09-16, "Published in Swaziland Gvernment Gazette extraordinary 118" on 2016-09-28, commenced 2016-09-28; its changes are dated 2016-09-28, the same day.
- Act 11 of 2017 (Suppression of Terrorism (Amendment) Act, 2017): its EswatiniLII page has no text (PDF only), so its dates come from the page's History tab (https://web.archive.org/web/20260418004949id_/https://eswatinilii.org/akn/sz/act/2017/11/eng@2017-08-25): assented to 2017-08-08, "Published in Swaziland Gvernment Gazette supplement 99" on 2017-08-25, commenced 2017-08-25; its changes are dated 2017-08-25, the same day.
- Prevention of Corruption Act: the first version is dated 2007-02-01, the commencement date EswatiniLII states ("Commenced on 1 February 2007"), not 2006-07-14, the date of its expression (Gazette publication).
- Prevention of Corruption Act: EswatiniLII's History lists no amendment after commencement (archived copy of 2026); the one version is the Act as published, dated by its commencement.
- Prevention of Corruption Act: EswatiniLII notes on the page: "The original publication document is not available and this content could not be verified." The text is EswatiniLII's, copied as published.
- Serious Offences (Confiscation of Proceeds) Act: the first version is dated 2001-10-18, the commencement date EswatiniLII states ("Commenced on 18 October 2001"), not 2001-09-21, the date of its expression (Gazette publication).
- Serious Offences (Confiscation of Proceeds) Act: EswatiniLII's History lists no amendment after commencement; the one version is the Act as published (Gazette 752 of 2001-09-21), dated by its stated commencement.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (Claude Opus 5.5, claude-opus-5-5) wrote the adapter and configuration and chose the acts. No model wrote, summarised or transformed legal text: the text is parsed by deterministic code.
- Prevention of Corruption Act: none at data-build time; units are parsed by code from the published page.
- Serious Offences (Confiscation of Proceeds) Act: none at data-build time; units are parsed by code from the published page.
