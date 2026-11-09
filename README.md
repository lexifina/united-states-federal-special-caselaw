# US case law: The special federal courts (Claims, Customs, Customs and Patent Appeals, Tax, International Trade, military and others)

Part of [lexifina/global-law](https://github.com/lexifina/global-law), one git history for every country's law: this is the case law of the special federal courts (Claims, Customs, Customs and Patent Appeals, Tax, International Trade, military and others), United States, which global-law reads at `united-states/federal-special/caselaw/`.

Every published opinion of the special federal courts (Claims, Customs, Customs and Patent Appeals, Tax, International Trade, military and others) in the Caselaw Access Project, as a git history: one file per decision, one commit
per decision, dated the day it was decided. 144,890 decisions from 1793-10-01 to the end of the source (Cust. Ct., Ct. Cl., M.J., T.C., B.T.A., F.2d, C.C.P.A., Fed. Cl., F. Supp., Ct. Int'l Trade, C.M.A., F. Supp. 2d and 25 more).

## Questions as git commands

| Question | Command |
|---|---|
| A decision by its citation | `grep -P '^<citation>\t' decision-index.tsv` then `cat <path>` |
| Decisions given in a window | `git log --format='%(trailers:key=In-force,valueonly,separator=) %an' \| awk '$1 >= "1973-01-01" && $1 <= "1973-01-31"'`: read the `In-force:` trailer, not the commit date (see Corrections), or use the global-law tools |
| Decisions citing 11 U.S.C. § 1182 | `cat judgments/united-states/federal/usc/title-11/1182.jsonl` |
| The section as the court applied it | each overlay row's `law_commit` is the section's own version in the US Code record on the day decided (or `law_record_from` when the decision is older than the record) |
| Who wrote a line? | `git blame decisions/...`: each line is credited to the decision (court and citation) |

## Dates and authors
The commit date is the day the decision was given, at noon US Eastern (`In-force:` and `Decided:`). Git cannot hold dates
before 1970, so earlier decisions are committed on 1970-01-01, a second apart, and `In-force:` holds the real day. The
author is the court and the official citation, at an address that cannot exist. These are court rulings, not laws: every
commit is `Kind: court`.

## Source
The Caselaw Access Project's bulk data (Harvard Law School Library), dedicated to the public domain under CC0; court
opinions are not copyrightable (17 U.S.C. § 105; Georgia v. Public.Resource.Org, 2020). Each file keeps its source URL.
Text is CAP's OCR, unchanged. The head matter CAP holds (syllabus, headnotes, counsel lists, the
reporter's summary) is left out: in these reporters it is written by the publisher, not the court. Each file's front matter
gives the reporter and `precedential_status: published` (every decision here was printed in a reporter; CAP records no
other status).

## What it does not show
Decisions after the end of CAP's coverage (its last volumes are of 2018-2020): CAP is a closed archive, so no nightly
runner appends here. Unpublished decisions not in the reporters, the head matter, and statute citations to US Code titles
the record does not hold.

## Corrections (2026-11-09)
An independent check of the CAP case-law repos found data defects; they are fixed here by new commits on top of the
history (nothing is rewritten). Now 145,159 decisions.

- 269 decisions added, each as its own commit dated the day decided, in date order: decisions with text the first build missed (volumes whose extract was lost, decisions merged with a different decision of the same day, docket and name, decisions CAP files under no court name or under another place's jurisdiction).
- 123 files had no text: CAP holds no opinion text for them, only head matter. Each now gives the head matter under `## CAP head matter` (`text_source` in the front matter), in a `Kind: correction` commit on the same file (`Corrected:`, `Corrects:` the commit that added it).
- decision-index.tsv: 6,339 rows added (the citations and CAP ids of decisions held here under another reporter, and of the new decisions), 232 rows that gave a citation to a different decision removed.
- `decision-dates.tsv` lists the 2,474 decisions whose CAP date gives only the month or the year (precision `month` or `year`); they are committed on the first day of it, and In-force says that day.

Dates in the commit history: git cannot hold dates before 1970, so a decision before 1970 is committed from 1970-01-01 noon UTC-5, a second apart.
Here 94,042 decisions are before 1970, so 50,843 of their commits are dated 1970-01-02 or later. The commit date is not the day decided: `git log --since/--until` over 1970 mixes them with the decisions of 1970. Read the `In-force:` trailer (as the window recipe above now does) or use the global-law tools.

## Decisions moved to their own repos (2026-11-09)
1,196 decisions were here by a routing mistake (CAP gives them a jurisdiction their court name contradicts, or a court name the router did not read). Each is now in its own repo, and its file here is removed; `decision-relations.tsv` gives each removed path as `moved-to <repo>/<path>`. 817 to united-states-ca9-caselaw, 167 to united-states-ca10-district-caselaw, 39 to united-states-pennsylvania-appellate-caselaw, 34 to united-states-ca8-district-caselaw, 33 to united-states-ca4-district-caselaw, 31 to united-states-cadc-district-caselaw, 23 to united-states-florida-other-courts-caselaw, 19 to united-states-district-of-columbia-other-courts-caselaw, 18 to united-states-district-of-columbia-caselaw, 6 to united-states-ca3-district-caselaw, 4 to united-states-virgin-islands-other-courts-caselaw, 2 to united-states-delaware-other-courts-caselaw, 1 to united-states-utah-caselaw, 1 to united-states-arkansas-caselaw, 1 to united-states-dakota-territory-caselaw. Now 143,963 decisions.
