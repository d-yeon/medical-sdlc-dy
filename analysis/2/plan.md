# Plan: Grounding Radiology Report Findings into Medical Image Segmentation (CF2Seg)

- Issue: #2
- Paper: `recommended/2026-08-21/cf2seg-report-guided-segmentation`
- DOI: https://doi.org/10.1038/s41746-026-03051-0
- Physician focus: no specific sub-question was given ("잘 봐주세요" / "please look at it well"),
  so the plan targets the paper's own core claim — using free-text report findings to guide
  spatial localization — against our cohort's report-text and multi-label structure.

## Proposed presentation

Dashboard entry with three parts, in this order:

1. **Text summary block** — paper title/DOI/link, one-paragraph relevance statement, and an
   explicit caveat that our cohort has no pixel-level expert annotation, so CF2Seg's reported
   segmentation accuracy (Dice/IoU-type metrics) cannot be reproduced or validated here. This
   goes first because it is the single fact that bounds every other claim on the page.

2. **Bar chart of `findings_label` frequency, single-label vs. multi-label (pipe-joined) split
   highlighted** — a bar/pie combination showing count per label plus the count of multi-finding
   reports (e.g. `Effusion|Infiltration`) vs. single-finding reports. Bar chart (not line) because
   this is categorical/nominal data with no natural order beyond frequency rank. This chart
   directly supports the paper's premise: CF2Seg was built because compound findings in narrative
   reports are hard to spatially disentangle, and our cohort has 50/272 (18.4%) multi-label
   studies — the exact scenario the method targets.

3. **Descriptive text panel on report length and structure** — a small table (not a chart, since
   there is only one distribution to state, not compare) reporting report_text length
   (min/mean/max characters) and institution/view-position spread, to frame whether our narrative
   style is short/templated enough that a findings-guided segmentation approach trained on richer
   multi-institutional reports would even have enough textual signal to work from.

No line/time-series chart is proposed: nothing in this cohort or question has a temporal axis.

## Open questions

- Does the physician want to scope the deep dive to the multi-label subgroup only (the cases most
  analogous to CF2Seg's motivating problem), or to the full 272-record cohort?
- Should the deep dive attempt any proxy for "spatial plausibility" (e.g., manual read of a sample
  of multi-label reports) given we have no pixel annotations, or should it stay purely textual
  (report length/vocabulary comparison to the paper's benchmark) and stop short of any
  segmentation attempt?
- Is a comparison against the paper's 53,386-exam benchmark composition (modalities/institutions)
  needed, or is a qualitative note on scale difference sufficient?
