# Florida water radars

All **2,363 Florida public water systems**, one row each, joined across five federal and state sources on the PWSID
(the EPA public water system ID) and scored daily. Contains no personal data.

| Radar | What it watches |
|---|---|
| Lead service lines | Lead, galvanized-requiring-replacement and unknown-material line counts, scored against the Lead and Copper Rule Improvements baseline inventory deadline of **2027-11-01**, and joined to Florida DWSRF project funding and principal forgiveness |
| PFAS | UCMR 5 monitoring results for the systems in it, including detections above a federal maximum contaminant level |
| Resilience | America's Water Infrastructure Act risk and resilience assessment (RRA) and emergency response plan (ERP) certification status and due dates |

The paid feeds add a 0–100 **trigger score** per system (regulatory exposure, funding, deadline pressure, velocity),
the system's matched **State Revolving Fund projects**, and a **daily change feed** when anything moves.

## Public columns

These are the columns on every system's public page at https://files.filingsdaily.com/water/.

| Column | Meaning |
|---|---|
| `pwsid` | EPA public water system ID |
| `system_name` | system name, normalised for reading |
| `pws_type`, `activity_status` | from SDWIS |
| `population_served` | as reported to EPA |
| `lead_lines`, `galvanized_requiring_replacement_lines`, `unknown_material_lines`, `total_service_lines` | service line inventory counts, as reported |
| `lsl_inventory_baseline_due`, `lsl_full_replacement_due` | federal deadlines under the LCRI |
| `pfas_compounds_detected`, `pfas_above_federal_mcl` | UCMR 5 results (blank = not in UCMR 5) |
| `pfas_initial_monitoring_due`, `pfas_mcl_compliance_due` | federal PFAS deadlines |
| `awia_rra_certification`, `awia_erp_certification`, `awia_rra_due`, `awia_erp_due` | AWIA status and due dates |
| `page_url` | the system's public page |

## Sources

U.S. EPA: Safe Drinking Water Information System, the service line inventory, UCMR 5 occurrence data and AWIA
certifications; the Florida Department of Environmental Protection's State Revolving Fund lists. Federal government
works are not subject to copyright (17 U.S.C. §105). The compilation, cleaning and name normalisation are
FilingsDaily's. Not affiliated with the EPA or any utility. Verify against the agency before relying on any value.
