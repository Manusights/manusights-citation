# Manusights Review Methodology

A public summary of how Manusights performs pre-submission manuscript review. Full data-handling disclosures are at [manusights.com/security](https://manusights.com/security).

## Three primary analyses

### 1. Citation verification

Every cited reference in the manuscript is checked against live scholarly databases:

- [CrossRef](https://www.crossref.org/)
- [PubMed](https://pubmed.ncbi.nlm.nih.gov/)
- [OpenAlex](https://openalex.org/)
- [Semantic Scholar](https://www.semanticscholar.org/)
- [bioRxiv](https://www.biorxiv.org/)
- [medRxiv](https://www.medrxiv.org/)

Combined coverage exceeds 500 million scholarly works. Verification returns confidence labels for: existence (does the cited paper actually exist), retraction status (cross-checked against [Retraction Watch](https://retractionwatch.com/)), DOI accuracy, and claim alignment (does the cited work support the claim being attached to it).

### 2. Figure and image-equation analysis

Vision-based parsing of figures, micrographs, gels, plots, and image-embedded equations. Manuscripts where reviewers commonly object to figure quality, axis labeling, sample size, scale-bar visibility, or claim-figure alignment are flagged before submission.

### 3. Journal-specific desk-reject scoring

The manuscript is scored against a target journal's typical desk-reject patterns: scope mismatch, novelty insufficient for the venue, methods gaps, ethics or consent issues, and formatting violations. Scoring is journal-specific because what survives editorial triage at PLOS ONE differs from Cell, NEJM, or Nature.

## Output

A six-section diagnostic report delivered as Markdown and DOCX, with a prioritized revision plan and a citation audit appendix. Wall-clock turnaround is typically 30 minutes.

## Privacy

Manuscripts are processed under zero-retention contracts with the underlying LLM providers. No manuscript content is stored, indexed, or used to train any model. See [manusights.com/security](https://manusights.com/security) for full disclosures.

## Reproducibility

The methodology is described above in enough detail that an independent researcher could outline the workflow. Detailed prompts, models, and routing logic are proprietary; the deliverable for any given manuscript is reproducible by re-running the same input through the live service. For replication studies or methods comparisons, contact [team@manusights.com](mailto:team@manusights.com).
