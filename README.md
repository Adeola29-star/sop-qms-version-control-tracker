# SOP and QMS Documentation Version-Control Tracker

## Problem

Clinical trial teams rely on Standard Operating Procedures (SOPs) to keep processes consistent, auditable, and compliant with Good Clinical Practice (GCP).

When SOPs are revised, changes need to be tracked accurately: what changed, why it changed, and whether the change improves data quality or introduces risk.

AI tools can speed up document review, but AI-generated summaries are not automatically trustworthy. This project examines the gap between automated document comparison and meaningful human review.

## Approach

Three clinical data SOPs were developed:

* **SOP-CD-001 — Query Resolution**
* **SOP-CD-002 — Data Entry**
* **SOP-CD-003 — Database Lock**

For each SOP, both versions were compared using an AI assistant, which produced a section-by-section summary of the differences. Each AI-generated summary was then manually checked against the original text to confirm accuracy, and reviewed a second time for something the AI summary could not do on its own: judging whether each change actually strengthens or weakens data integrity in a real clinical trial context.

A version-control log was built in Excel to track all six SOP versions *(SOP number, title, version, effective date, approver, change summary, last review date)*. A second tab was added as a status dashboard, showing the current version of each SOP, its next review due date, a formula-driven days-until-review count, a chart, and conditional formatting to flag SOPs approaching review.

## Skills Demonstrated

* SOP documentation and revision control
* QMS documentation practices
* Document version comparison and change tracking
* AI-assisted document review
* Human review and data-integrity assessment
* Excel-based version-control tracking
* Formula-driven monitoring and conditional formatting
* Clinical Data Management principles
* GCP and data-integrity awareness

## Result

All three SOPs were completed at both versions, with headers and footers identifying each document consistently across pages. The AI-generated diffs correctly identified every textual change but consistently missed the operational and clinical significance of those changes. The version-control log and dashboard are both functional, using live formulas rather than hardcoded values, so the dashboard updates automatically as dates change.

## Dashboard

The Excel version-control tracker includes a status dashboard showing current SOP versions, upcoming review dates, days remaining until review, and review status.

![SOP Version-Control Dashboard](Dashboard.png)

## Limitations

AI-assisted comparison was reliable for detecting textual changes but less reliable for determining why those changes matter from a clinical data and data-integrity perspective.

Manual review identified several important issues:

### 1. Shortened response and resolution deadlines

The Query Resolution SOP changed the response/resolution deadline from 3 business days to 1 business day, while the Database Lock SOP changed a deadline from 10 days to 7 days was flagged by the AI only as a numeric change. It did not raise the risk that a fixed deadline, applied to every query regardless of complexity, could pressure staff to close queries before they are properly resolved. This is a real concern when a query involves an evolving adverse event, where a subject's records may still be fluctuating before stabilizing.

### 2. Incomplete data-entry rules

The Data Entry SOP introduced a rule requiring free-text fields to be entered verbatim, but neither version included an equivalent rule for numeric fields. Rounding or approximating a lab value is arguably a more serious data-integrity risk than paraphrasing free text, since numeric values are often what triggers a safety or eligibility decision. The AI summary did not flag this omission because it was not a textual difference between the two versions, it was a gap present in both.

### 3. Source documentation and EDC timing

Neither version of the Data Entry SOP distinguished between when source documentation should be completed (at the time of the visit) and when EDC entry is due (up to several days later). Without that distinction, the SOP risks being read as permission to delay the source record itself, which would undermine the Contemporaneous principle that clinical data integrity depends on.

### 4. Database lock readiness

Version 1.0 of the Database Lock SOP had no formal pre-lock checklist step at all. It moved directly to lock approval with no documented confirmation that queries were closed or that source data verification was complete. Version 2.0 corrected this, and the AI summary captured that a new section had been added, but did not identify that its absence in Version 1.0 was a meaningful gap rather than a stylistic difference.

## Conclusion

AI-assisted document comparison is useful as a first-pass review tool because it can efficiently identify textual differences between document versions.

However, automated comparison does not replace human judgement.

A complete SOP review should consider not only **what changed**, but also **why the change matters, what risk it introduces, and whether the revised process supports data quality and integrity**.

AI-generated summaries should therefore be treated as a starting point for human review rather than as the review itself.
