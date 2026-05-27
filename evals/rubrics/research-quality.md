# Research Quality Rubric

Use this rubric to evaluate AI Agent research reports produced in this workbench.

Score each dimension from 0 to 4.

- 0: Missing or unusable.
- 1: Weak; major gaps or unsupported claims.
- 2: Adequate; useful but incomplete.
- 3: Good; mostly complete and reliable.
- 4: Excellent; rigorous, well-sourced, and actionable.

Maximum score: 32.

## 1. Question Fit

Does the report answer the user's actual research question?

- 0: Does not address the question.
- 1: Addresses only a small part of the question.
- 2: Answers the main question but misses important scope.
- 3: Answers the question well with minor omissions.
- 4: Directly and completely answers the question, including relevant subquestions.

## 2. Source Quality

Are the sources credible and appropriate?

- 0: No sources.
- 1: Mostly weak or irrelevant sources.
- 2: Some credible sources, but important source types are missing.
- 3: Good mix of credible sources.
- 4: Strong primary sources, current references, and balanced perspectives.

Preferred sources:

- Official docs.
- Papers and preprints.
- Repository source, issues, releases, and READMEs.
- Benchmarks with methodology.
- Maintainer or author explanations.

## 3. Citation Coverage

Are important claims supported by citations?

- 0: Claims are uncited.
- 1: Few citations; many unsupported claims.
- 2: Major claims have some support.
- 3: Most important claims are cited.
- 4: Claims are consistently tied to specific sources, with dates or versions where relevant.

## 4. Factual Accuracy

Does the report avoid incorrect or misleading statements?

- 0: Contains serious factual errors.
- 1: Multiple questionable or misleading claims.
- 2: Mostly accurate but with some vague or unchecked claims.
- 3: Accurate with minor issues.
- 4: Highly accurate, carefully qualified, and internally consistent.

## 5. Synthesis Quality

Does the report synthesize rather than merely list sources?

- 0: No synthesis.
- 1: Mostly copied or listed notes.
- 2: Some grouping or comparison.
- 3: Clear themes, comparisons, and trade-offs.
- 4: Strong synthesis that reveals patterns, implications, and tensions across sources.

## 6. Uncertainty Handling

Does the report clearly separate fact, interpretation, and uncertainty?

- 0: No uncertainty handling.
- 1: Uncertainty is hidden or ignored.
- 2: Some caveats, but incomplete.
- 3: Clear limitations and confidence levels.
- 4: Excellent uncertainty tracking, including conflicting evidence and missing data.

## 7. Reproducibility

Could another agent or researcher reproduce or continue the work?

- 0: No reproducibility.
- 1: Sources or method are unclear.
- 2: Some sources and method are present.
- 3: Clear source table and enough method detail.
- 4: Search strategy, sources, dates, assumptions, and exclusions are clear.

## 8. Actionability

Does the report provide useful next steps?

- 0: No next actions.
- 1: Vague next actions.
- 2: Some useful follow-ups.
- 3: Clear and practical recommendations.
- 4: Prioritized next actions with rationale and suggested owners/tools.

## Score Bands

- 29-32: Excellent. Ready to rely on or publish internally.
- 24-28: Good. Minor improvements recommended.
- 18-23: Adequate. Useful, but should be revised before relying on it.
- 10-17: Weak. Major gaps; needs substantial follow-up.
- 0-9: Unusable. Redo the research.

## Required Review Output

When reviewing a report, use this format:

```markdown
# Research Quality Review

Report: [path or title]
Date: YYYY-MM-DD
Reviewer: [agent/name]

## Scores

| Dimension | Score | Notes |
|-----------|-------|-------|
| Question Fit | /4 | ... |
| Source Quality | /4 | ... |
| Citation Coverage | /4 | ... |
| Factual Accuracy | /4 | ... |
| Synthesis Quality | /4 | ... |
| Uncertainty Handling | /4 | ... |
| Reproducibility | /4 | ... |
| Actionability | /4 | ... |

Total: N/32
Band: Excellent | Good | Adequate | Weak | Unusable

## Strengths

- ...

## Required Fixes

- ...

## Suggested Improvements

- ...

## Verdict

Approved | Revise
```

## Minimum Acceptance Criteria

A report should normally be revised if any of these are true:

- Total score is below 24.
- Source Quality is below 3.
- Citation Coverage is below 3.
- Factual Accuracy is below 3.
- The report lacks explicit uncertainty/confidence notes.
- The report does not answer the original question.
