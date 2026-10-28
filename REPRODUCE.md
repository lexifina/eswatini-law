# How this repository was made (Eswatini)

This file is written by the build on 2026-10-28, the day the source data was retrieved. Everything below is enough to rebuild this repository hash for hash.

## Sources

| Source | Address | Retrieved | Requests | Licence |
| --- | --- | --- | ---: | --- |
| EswatiniLII (the Judiciary of Eswatini, on the Laws.Africa Peachjam platform) | <https://eswatinilii.org> | 2026-10-28 | 67 | CC BY-NC 4.0, crediting EswatiniLII as the source (https://eswatinilii.org/terms-of-use/) |
| Internet Archive Wayback Machine | <https://web.archive.org> | 2026-10-28 | None | Archived copies of EswatiniLII pages; the content licence is EswatiniLII's |
| Common Crawl | <https://commoncrawl.org> | 2026-10-28 | None | Common Crawl terms of use (https://commoncrawl.org/terms-of-use); the content's licence is EswatiniLII's |

Every response is cached by the sha256 of its URL, and the table above lists every source with its retrieval date. Lexifina keeps its fetch scripts privately; `tools/parse.py` reads only the cache and writes `corpus.json`, so the same cache always gives the same corpus.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `constitution` | Constitution of the Kingdom of Swaziland, 2005 | 1 | 2006-02-08 to 2006-02-08 |
| `suppression-of-terrorism` | Suppression of Terrorism Act, 2008 | 2 | 2008-05-11 to 2017-08-25 |
| `money-laundering` | Money Laundering and Financing of Terrorism (Prevention) Act, 2011 | 2 | 2012-03-23 to 2016-09-28 |

The build made 5 commits:

| Commits | Kind |
| ---: | --- |
| 3 | first version of an act |
| 2 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-28.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 5 laws in the record.
- 10 tags.

## Dates

Each commit is dated at noon (Africa/Mbabane) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Not applied: every version is dated by EswatiniLII's own expression date, or by the commencement date EswatiniLII states for the act as published. No date is computed from a default rule. https://eswatinilii.org/legislation/

## Commands, in order

```sh
# fill the cache from the sources listed above (network; Lexifina's fetch scripts are kept privately)
python -X utf8 tools/parse.py                  # cache -> corpus.json (no network)
python -X utf8 tools/build.py <folder> --repo <empty folder> --docs-date 2026-10-28
python -X utf8 tools/check_repo.py <repo> --corpus <folder>/corpus.json --write
python -X utf8 tools/build.py <folder> --repo <another empty folder> --docs-date 2026-10-28 --compare <repo>
```

In the main Lexifina repository these files live as follows:
- `fetch.py`, `parse.py` and `repo/`: in `scripts/eswatini-law/`.
- `build.py`, `check_repo.py` (`check.py` there) and `on.py`: in `scripts/gitlaw_common/`, with the corpus format in `SCHEMA.md`.

## Exact inputs

- `corpus.json` sha256 `45fea3c55711745c45d884f087380142d088d6b2e2dedfd893a374c6118e2def` (649070 bytes)
- Script blob hashes (`git hash-object`):

| Script | Blob |
| --- | --- |
| build.py | `2bfc4ac9df193a7be844556d7f69cdb9d93ec3f2` |
| check.py | `cd346c7ff9996d450240e3bab52bcae03b2bc865` |
| on.py | `644a6c0857fbcc72562032b58d57aa113fee0641` |
| fetch.py | `8af7ec7278570a7768c0ec20b68696e8217d154a` |
| parse.py | `9f14a1c2ca9040f940ceb7b89fee41c80de269fc` |

- Tools:
  - Python 3.14.0
  - git version 2.52.0.windows.1
  - curl 8.21.0 (Windows) libcurl/8.21.0 Schannel zlib/1.3.2 WinIDN WinLDAP

## Checks

5 versions of 3 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

Not yet run for this build.

These results are from the check run on the build before this one, from the same corpus.

## Decisions made by hand

- Acts were chosen by what the archived source supports. Of the 361 EswatiniLII works with archived expression pages (one Internet Archive CDX query, 2026-10-28) and the 105 in Common Crawl (crawls 2022 to 2026), only a few have more than one dated expression with text. Phase 1 takes the Constitution (one expression) and the two acts whose every expression is archived with text and whose amending Act is named: the Suppression of Terrorism Act 2008 (amended by Act 11 of 2017) and the Money Laundering and Financing of Terrorism (Prevention) Act 2011 (amended by Act 5 of 2016).
- The Employment Act 1980 and the Companies Act 2009 were not taken: EswatiniLII's only archived expression with text is dated 1 December 1998 and marked "Consolidation" for both, a date before the Companies Act 2009 was even made, so it is a placeholder, not the date the text was in force. Their other archived expressions (Employment Act 1981-01-01, Companies Act 2010-04-01; 2023 captures) carry no text. Most other EswatiniLII acts share this 1998-12-01 date or have one expression only.
- EswatiniLII marks the Constitution and the Money Laundering and Financing of Terrorism (Prevention) Act 2011 with "[Note: The original publication document is not available and this content could not be verified.]" The text is EswatiniLII's; it was not compared with the Gazette, because the Gazette copies are scans and no OCR is used.
- Money Laundering and Financing of Terrorism (Prevention) Act 2011: EswatiniLII states "Commenced on 23 March 2012 by Money Laundering and Financing of Terrorism (Prevention) (Amendment) Act, 2016", and the 2016 Act's page lists it as commencing the 2011 Act. The first version is dated 2012-03-23 as stated; this commencement was fixed by an Act of 2016.
- In the Suppression of Terrorism Act, section 28's editorial note reads "[paragraph (e) substituted by section 5 of Act 11 of 2017]" but links to /akn/sz/act/2011/11; the credit follows the note's words and the History tab, which names only Act 11 of 2017 for that version.
- Licence and terms: EswatiniLII (the Judiciary of Eswatini) licenses its primary and secondary law content CC BY-NC 4.0, crediting EswatiniLII as the source, and its terms say "Scraping and bulk downloading from this website is strictly prohibited"; its robots.txt sends Content-Signal search=yes, ai-train=no, use=reference and Crawl-delay 5. No EswatiniLII document page was fetched: every page is read from the Internet Archive's copy (the Common Crawl copies were checked and added nothing), for the configured acts only. Seven of EswatiniLII's open listing pages (/legislation/?years=Y, robots-allowed) were read directly at 5 s spacing. The user decided on 2026-10-28 that reading archived copies is acceptable (relayed by the coordinator: "scraping wayback is fair game, dont overdo it"). The repository stays private; CC BY-NC allows only non-commercial use. No legal text was given to a model.
- Version dates are EswatiniLII's expression dates. Laws.Africa's terminology guide (https://docs.laws.africa/getting-started/terminology-guide) says "Amendments to Principal works come into force on the Commencement date of the Amending work" and that the first point in time is "the work as originally published"; so an amendment's expression is dated by its commencement (in force), and an act's original expression by its publication, which is replaced by the commencement date the page states.
- Credits: a version whose History names exactly one amending law (and no consolidation) between it and the previous version is credited to that law for every provision that changed. Otherwise a provision is credited only to laws that EswatiniLII's editorial note inside that provision links to; the rest are unexplained (publisher).
- Editorial notes (akn-remark) are left out of the text and used only as credit evidence, except where a provision has no other text (repealed or spent), where the note is the provision's whole printed content.
- Part, Chapter and Division headings are left out; each provision file starts with its own number and heading. Every other text of each version is in a provision file: parse.py checks this per version (verification.json, fidelity).
- Constitution: the first version is dated 2006-02-08, the commencement date EswatiniLII states ("Commenced on 8 February 2006 by Constitution of the Kingdom of Swaziland (Date of Commencement) Proclamation, 2006"), not 2005-07-26, the date of its expression (Gazette publication).
- Suppression of Terrorism Act: the first version is dated 2008-05-11, the commencement date EswatiniLII states ("Commenced on 11 May 2008"), not 2008-04-11, the date of its expression (Gazette publication).
- Money Laundering Act: the first version is dated 2012-03-23, the commencement date EswatiniLII states ("Commenced on 23 March 2012 by Money Laundering and Financing of Terrorism (Prevention) (Amendment) Act, 2016"), not 2011-08-23, the date of its expression (Gazette publication).
- Act 5 of 2016 (Money Laundering and Financing of Terrorism (Prevention) (Amendment) Act, 2016): its EswatiniLII page has no text (PDF only), so its dates come from the page's History tab (https://web.archive.org/web/20260420221703id_/https://eswatinilii.org/akn/sz/act/2016/5/eng@2016-09-28): assented to 2016-09-16, "Published in Swaziland Gvernment Gazette extraordinary 118" on 2016-09-28, commenced 2016-09-28; its changes are dated 2016-09-28, the same day.
- Act 11 of 2017 (Suppression of Terrorism (Amendment) Act, 2017): its EswatiniLII page has no text (PDF only), so its dates come from the page's History tab (https://web.archive.org/web/20260418004949id_/https://eswatinilii.org/akn/sz/act/2017/11/eng@2017-08-25): assented to 2017-08-08, "Published in Swaziland Gvernment Gazette supplement 99" on 2017-08-25, commenced 2017-08-25; its changes are dated 2017-08-25, the same day.

## What AI did and did not do

The fetch, parse and check scripts were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above, through code that anyone can rerun.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (Claude Opus 5.5, claude-opus-5-5) wrote the adapter and configuration and chose the acts. No model wrote, summarised or transformed legal text: parse.py is deterministic code.
