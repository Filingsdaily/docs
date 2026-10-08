# FilingsDaily

**Public government records, turned into clean daily data feeds.**
FilingsDaily is the data product of BILL-A-DOE SOFTWARE LLC, St. Petersburg, Florida. Website: https://filingsdaily.com

This repository is the public documentation for our datasets: what each feed contains, where it comes from, and how it
is built. It holds documentation only. The data itself is delivered from https://files.filingsdaily.com.

## Datasets

| Dataset | What it is | Docs | Free sample |
|---|---|---|---|
| Florida Business Filings | Every entity newly registered with the Florida Division of Corporations | [docs](datasets/business-filings.md#florida) | [weekly sample](https://files.filingsdaily.com/fl-sample-weekly.csv) |
| Florida Registry Change Feed | Dissolutions, reinstatements, amendments, conversions, name and agent changes, each resolved to its entity | [docs](datasets/business-filings.md#florida-registry-change-feed) | on request |
| Florida Fictitious Names | Newly registered Florida fictitious names (DBAs) | [docs](datasets/business-filings.md#florida-fictitious-names) | on request |
| New York Business Filings | Every newly registered New York business entity | [docs](datasets/business-filings.md#new-york) | [200 rows](https://files.filingsdaily.com/ny-sample.csv) |
| Texas Business Filings | New entities from the Texas franchise tax roll (about three weeks after charter) | [docs](datasets/business-filings.md#texas) | [200 rows](https://files.filingsdaily.com/tx-sample.csv) |
| Colorado Business Filings | Every newly formed Colorado business entity | [docs](datasets/business-filings.md#colorado) | on request |
| Florida water radars | All 2,363 Florida public water systems, scored for lead service lines, PFAS and resilience | [docs](datasets/florida-water.md) | [lead lines](https://files.filingsdaily.com/fl-lslr-radar-sample.csv) · [PFAS](https://files.filingsdaily.com/fl-pfas-radar-sample.csv) · [resilience](https://files.filingsdaily.com/fl-resilience-radar-sample.csv) |

Browse every Florida water system: https://files.filingsdaily.com/water/
Prices and subscriptions: https://filingsdaily.com/#datasets

## How the pipeline runs

1. **The agency publishes.** State agencies post bulk registry files on their own schedule.
2. **We ingest and archive.** Files are pulled from official endpoints, checksummed and stored immutably. A missed day
   self-heals on the next run instead of leaving a hole.
3. **We refine.** Parsers extract and normalise every field. Snapshots are diffed to derive change events. Malformed
   records go to quarantine, not into a delivered file.
4. **You download.** A documented CSV at a stable URL, refreshed each business morning.

## Sources and attribution

Every source agency and its terms: [SOURCES.md](SOURCES.md), and the live attribution file at
https://files.filingsdaily.com/ATTRIBUTION.txt. FilingsDaily is not affiliated with any government agency.

## Acceptable use

These datasets are derived from public government records and are sold for business research, market analysis,
business-to-business outreach, compliance, due diligence and record-keeping. They are **not consumer reports** and must
not be used for any purpose covered by the Fair Credit Reporting Act. Full terms: https://filingsdaily.com/#terms

## Contact

support@filingsdaily.com

---
Documentation © 2026 BILL-A-DOE SOFTWARE LLC.
