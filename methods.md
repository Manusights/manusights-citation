# Manusights Review Methodology

A public summary of how Manusights performs pre-submission manuscript review. This document is intentionally version-stable: it describes the methodology at a level that is unlikely to change with routine engineering updates. Detailed prompts, models, and routing logic are proprietary; this summary is sufficient for an independent researcher to outline the workflow, cite the deposit, or run a replication study against the live service.

Full data-handling and security disclosures are at [manusights.com/security](https://manusights.com/security).

## Service scope

Manusights is invoked at a single point in the manuscript lifecycle: **after the draft is internally cleaned but before it is submitted to a journal or posted publicly**. The service does not edit prose, generate text, or replace human peer review. It produces a structured diagnostic report that surfaces the categories of risk that determine editorial triage outcomes.

## Three primary analyses

### 1. Citation verification

Every cited reference in the manuscript is checked against live scholarly databases. The current sources are:

- [CrossRef](https://www.crossref.org/) — primary registry for scholarly DOIs
- [PubMed](https://pubmed.ncbi.nlm.nih.gov/) — biomedical literature
- [OpenAlex](https://openalex.org/) — open scholarly graph
- [Semantic Scholar](https://www.semanticscholar.org/) — AI-extracted metadata and citation graph
- [bioRxiv](https://www.biorxiv.org/) — life-sciences preprints
- [medRxiv](https://www.medrxiv.org/) — clinical and health-sciences preprints

Combined coverage exceeds 500 million scholarly works. Verification returns confidence labels for four properties of each reference:

1. **Existence** — does the cited paper actually exist in any of the indexed sources, or is it a fabricated or hallucinated reference?
2. **Retraction status** — has the cited work been retracted? Cross-checked against [Retraction Watch](https://retractionwatch.com/).
3. **DOI accuracy** — does the DOI resolve to the title and authors the manuscript claims?
4. **Claim alignment** — does the cited work, when its abstract or accessible portions are read, plausibly support the specific claim the manuscript attaches to it?

Citation verification is a substantive failure mode in human peer review: reviewers rarely have time to check every reference, but desk-reject rates rise sharply when an editor spot-checks two or three citations and finds them broken. Manusights surfaces these issues before submission so they can be corrected.

### 2. Figure and image-equation analysis

Vision-based parsing of figures, micrographs, gels, plots, and image-embedded equations. The analysis flags:

- Figure quality, resolution, and legibility issues
- Axis labeling, units, and scale-bar visibility
- Sample size adequacy for visualizations of variability
- Claim-figure alignment (does the figure visually support the claim it is cited for)
- Equations rendered as images (which several pre-submission AI tools ignore entirely)

This complements citation verification because, in editorial practice, figure trust is one of the highest-frequency desk-reject triggers in life-sciences and clinical submissions.

### 3. Journal-specific desk-reject scoring

The manuscript is scored against the editorial triage patterns of a stated target journal. Scoring covers:

- Scope mismatch against the journal's published aims
- Novelty insufficient for the venue's tier
- Methods gaps the journal's reviewers typically flag
- Ethics or consent issues required by the journal's policies
- Formatting violations of the journal's submission guidelines

Scoring is journal-specific because what survives editorial triage at PLOS ONE differs materially from Cell, NEJM, or Nature. A generic "is this paper good" score is less useful at the submission decision point than a venue-calibrated readiness score.

## Output

A six-section diagnostic report delivered as Markdown and DOCX, with a prioritized revision plan and a citation audit appendix. Wall-clock turnaround for the standard $29 Full AI Diagnostic is approximately 30 minutes. A free anonymous readiness scan is available with a 1 to 2 minute turnaround for triage-level signal before paid review.

## Privacy

Manuscripts are processed under zero-retention contracts with the underlying LLM providers. No manuscript content is stored, indexed, or used to train any model. All processing is automated; no human reviewer reads submitted manuscripts in the AI pipeline. See [manusights.com/security](https://manusights.com/security) for full disclosures.

## Reproducibility

The methodology is described above in enough detail that an independent researcher can outline the workflow. The deliverable for any given manuscript is reproducible by re-running the same input through the live service; the underlying models and prompts may evolve between releases, which is why each tagged Zenodo release receives a distinct version DOI.

For replication studies, methods comparisons, or institutional pilot inquiries, contact [team@manusights.com](mailto:team@manusights.com).

## Anchor literature

The structure of this deposit, and the design of pre-submission AI review more broadly, draws on:

- Smith, A. M., Katz, D. S., & Niemeyer, K. E. (2016). [Software Citation Principles](https://doi.org/10.7717/peerj-cs.86). *PeerJ Computer Science*, 2, e86.
- The [FORCE11 Software Citation Principles](https://force11.org/info/software-citation-principles-published-2016/).
- The [Software Sustainability Institute guide to citing software](https://www.software.ac.uk/guide/how-cite-and-describe-software-you-used-your-research-top-ten-tips).
- [COPE Core Practice 4](https://publicationethics.org/core-practices) on conflicts of interest, which informs the disclosure-norm guidance for authors who receive complimentary credits in exchange for a verified acknowledgment.

## Versioning

Methodology changes that materially affect the diagnostic output are released as new tagged versions of this repository, each receiving a distinct Zenodo version DOI. The concept DOI [`10.5281/zenodo.20072010`](https://doi.org/10.5281/zenodo.20072010) always resolves to the latest version. See [`CHANGELOG.md`](./CHANGELOG.md) for version history.
