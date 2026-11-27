# Structure

| Folder | What it holds |
| --- | --- |
| `constitution/` | The Constitution of the Kingdom of Eswatini (Act No. 1 of 2005) |
| `acts/<year>/<NNN>-<slug>/` | An Act, by its year and number, e.g. `acts/2022/006-computer-crime-and-cybercrime/`; an Act whose number the source does not print has no number prefix, and an old consolidated Act is filed under the year it commenced |
| `subsidiary/<year>/<NNN>-<slug>/` | Subsidiary legislation (regulations, rules, orders, legal notices), by year and Legal Notice number when printed |

Each folder holds one file per section (`sec-023.md` is section 23; `sec-012-a.md` is section 12A), a `README.md`
with the source and the section headings, or `text.md` when the text has no numbered sections. No folder holds more
than 1,000 entries.

## Dates

Each version is one commit, dated 12:00 Africa/Mbabane on the day it took effect, which its `In-force:` trailer
repeats. `In-force-basis:` says where that day comes from:

- `commencement`: the text's own "Date of commencement" line;
- `gazette-publication`: the Government Gazette date, for a text that says it comes into force on publication;
- `deemed-commencement`: the text's own "deemed to have come into force on" provision;
- `stated-commencement`: the text's own "shall come into force on <day>" provision;
- `commencement-notice`: the day a (Commencement) Notice in the Gazette names for the Act;
- `faolex-entry-into-force` / `wipo-entry-into-force`: the entry-into-force date in the FAOLEX or WIPO Lex record;
- `publisher-revision`: for a consolidated text (one that cites later amending Acts), the date the publisher gave
  its PDF. The text was in force on that day at the latest; the day its last amendment took effect is not given.
  Such commits are credited to the publisher.

Before 1970 (which git cannot store) a commit is dated 1 January 1970, one second after the one before it; the real
day is in the subject and the `In-force:` trailer. A text with no reliable day is held back, not guessed. No date in
this repository is the day we downloaded anything.

## Sources and status

- Judiciary of Eswatini, <https://www.judiciary.org.sz/legislation> (official, live).
- Government of Eswatini, gov.sz and parliament.gov.sz: both hosts stopped answering (TCP timeouts) by November
  2026, so their PDFs are read from Internet Archive copies (raw `id_` form); the `Archived:` trailer gives the copy.
- FAOLEX (FAO) and WIPO Lex: secondary copies, marked `Source-status: secondary copy (...)`; `Text-source:
  publisher OCR` marks a text layer the publisher made from a scan. No OCR is run by Lexifina.
- EswatiniLII: the first versions in the repository, read from archived copies (see REPRODUCE.md).
