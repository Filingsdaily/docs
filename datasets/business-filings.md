# Business registry feeds

One CSV per state, refreshed each business morning, with the source fields kept intact. Each row is one newly
registered entity. The fields below are what each state actually publishes. Where a state does not publish something,
we say so rather than fill it in.

## Florida

Source: Florida Department of State, Division of Corporations (Sunbiz) bulk records.

- Entity name, type, status, filing date, state of incorporation
- Principal and mailing addresses, normalised
- Registered agent and officer records, with titles
- `first_seen`: the date FilingsDaily first saw the entity
- Volume: about 2,300 rows on a typical business day

Key fields: `doc_number` (the state's document number, e.g. `L26000422256`), `entity_name`, `entity_type`, `status`,
`filing_date`, `first_seen`.

## Florida Registry Change Feed

Derived by diffing daily snapshots; the state does not publish this.

- Dissolutions, reinstatements, amendments and conversions, each resolved to the entity's name through a
  full-registry directory of about 12.8 million Florida entities
- Name-change events, with the entity's prior name
- Registered-agent changes
- A rolling 7-day window, so a missed download loses nothing

## Florida Fictitious Names

- Newly registered fictitious names (DBAs): registered name, county, address, status, expiration
- One row per owner, with owner type
- Parsed from the state's fixed-width daily file

## New York

Source: New York State Department of State, Division of Corporations, via the Open NY portal (data.ny.gov). New York expressly permits commercial reuse.

- Formation date, DOS ID, entity type, county
- Service-of-process contact: name and full mailing address
- Registered agent where one is filed, roughly one record in three
- New York does not collect officers at formation, so this feed carries agent and process contact only
- Volume: about 700–900 new entities on a typical business day

## Texas

Source: Texas Comptroller of Public Accounts, franchise tax roll, via data.texas.gov.

- **Published about three weeks after charter.** An entity appears once it registers for franchise tax, so this is a
  coverage and diligence feed, not a same-week feed
- Charter date, SOS file number, entity type, taxpayer mailing address
- Franchise-tax standing and right-to-transact-business status
- No registered agent or officer records; Texas does not publish them in this source
- Volume: about 1,380 new entities on a typical business day

## Colorado

Source: Colorado Secretary of State, business filings open data (data.colorado.gov), published under a Public Domain licence.

- Formation date, entity ID, type, status, jurisdiction
- Principal and mailing addresses
- Registered agent details, person or organisation

## Notes that apply to every state feed

- `date` fields are as the state reports them. A day on which a state published no file has no rows: that is the
  state's release schedule, not a real drop to zero.
- Florida entity type codes are mapped to plain names in derived products (for example `FLAL` becomes "Florida LLC").
- Delivered files are written atomically, so an automated download never catches a half-written file.
